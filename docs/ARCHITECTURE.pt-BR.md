# Arquitetura autoral proposta

Estado: **desenho não implementado; aprovação mínima pendente**. Nenhuma tecnologia citada está instalada ou integrada por constar neste documento.

## Estrutura recomendada

Separar motor financeiro, controle da execução, persistência e interface. O motor recebe somente dados sintéticos e configuração validada. A interface pode iniciar uma simulação local, mas não calcula permissões nem decide limites no navegador.

| Camada | Responsabilidade | Fronteira |
| --- | --- | --- |
| Interface local | Selecionar cenário, editar rascunho, revisar, acompanhar e ler relatório | Nenhum campo para credencial de exchange; sem acesso direto aos arquivos do sistema |
| Serviço local | Validar pedidos, vincular revisão à versão, controlar idempotência e consultar execuções | Sessão local, origem e Host verificados; escuta somente em loopback; sem serviço público |
| Executor | Impor limites de processo, tempo, memória, leitura e escrita; iniciar motor | Sem rede; insumos somente leitura e saída própria; isolamento precisa ser demonstrado no ambiente escolhido |
| Motor determinístico | Percorrer eventos em ordem, gerar intenções simuladas e aplicar regras de risco | Apenas estratégias próprias e permitidas; sem `eval`, extensões arbitrárias ou adaptadores de negociação |
| Livro e métricas | Persistir eventos, reconstruir estado e reconciliar patrimônio/custos | Escrita atômica; IDs únicos; fórmulas versionadas; falha não vira resultado conclusivo |

A interface local e seu transporte em loopback são separados do executor sem rede. Estar em loopback, isoladamente, não comprova autenticação nem proteção contra pedidos de outra origem.

Uma primeira implementação pode expor o motor também por CLI para diagnóstico e reprodução. Isso não substitui a jornada local que o usuário aprovar. Linguagem preferencial proposta para motor: Python, com aritmética decimal. Runtime, bibliotecas e armazenamento serão fixados após inspeção do ambiente; não há requisito de upgrade, framework web específico, serviço externo ou mensalidade.

## Fluxo de execução

O pedido contém o ID de uma versão revisada. O serviço valida acesso, hashes, limite de concorrência e chave idempotente. O executor recebe o cenário e a configuração congelados. Cada evento passa por validação temporal e de unidade, regra de estratégia, checagem prévia de risco e contabilização. O relatório deriva do livro, incluindo o motivo de parada e o alcance do modelo.

Mesmo cenário, configuração, semente e motor devem produzir os mesmos eventos e resultados. Horários de processamento podem variar e não entram no hash do resultado financeiro determinístico.

## Contratos de dados

| Entidade | Conteúdo mínimo | Invariante |
| --- | --- | --- |
| Cenário | ID, versão, `synthetic=true`, semente, gerador, instrumento fictício, unidade, timezone, intervalo, hash | Dados finitos, ordenados, dentro do tamanho aceito e sem ambiguidade de unidade |
| Configuração | Estratégia/versão, parâmetros, custos, regra de preenchimento, limites e cenário | Revisão congela versão; edição posterior cria outra |
| Execução | ID, hashes de dados/configuração/motor, estado, checkpoint e motivo de encerramento | Pedido repetido não duplica efeito; corpo diferente com mesma chave é conflito |
| Evento simulado | Sequência, instante do cenário, intenção, quantidade, preço, estado e causa | Ordem causal explícita; duplicata não repete custo ou preenchimento |
| Lançamento | Tipo, valor decimal, unidade e evento de origem | Livro append-only, saldo reproduzível e sem dupla contagem |
| Resultado | Período, timezone, métricas, unidade, cobertura, hipóteses e eventos de risco | Nulo não vira zero; parcial não vira completo; posição aberta permanece identificada |

Não aceitar caminhos arbitrários ou URLs fornecidos pelo navegador para obter cenários. Usar catálogo local de arquivos permitidos. Exportações não devem carregar scripts de terceiros, credenciais ou dados pessoais.

## Estados e interrupções

Configuração: `rascunho → validada → revisada/imutável`. Execução: `na_fila → executando → concluída`, com saídas explícitas `bloqueada`, `cancelada` ou `falhou`.

- **Bloquear novas entradas:** impede aumentar exposição simulada; o comportamento das posições existentes continua definido pelo modelo.
- **Interromper avaliação:** suspende o processamento; o sistema informa que preços e proteções não estão sendo avaliados.
- **Encerrar simulação:** finaliza o processamento e preserva o estado; posição aberta é marcada no relatório.

Esses comandos não são sinônimos de fechar uma posição. O MVP não promete retomada de checkpoint antes de validar sua reprodutibilidade. Nova tentativa gera execução rastreável e não sobrescreve a anterior.

## Regras financeiras próprias

O modelo mínimo é linear e fictício, com multiplicador igual a um, sem hedge e sem cálculo de liquidação de corretora. Sinal calculado em `t` só pode executar em `t+1`; antecipação de dados é proibida pelo contrato do motor.

PnL bruto por lote fechado = direção × quantidade × diferença entre preço de saída e entrada. Direção positiva para long e negativa para short. Taxas incidem no valor de cada preenchimento. Slippage altera o preço simulado e não pode ser descontado novamente como custo adicional do mesmo efeito.

Patrimônio = capital inicial fictício + resultado realizado bruto + resultado aberto − custos acumulados. O MVP não aceita aportes ou retiradas durante a execução. Caso uma futura expansão aceite fluxos, será necessário separá-los do resultado e definir uma convenção de retorno antes de exibir percentuais.

Funding, margem de manutenção e liquidação permanecem explicitamente fora do primeiro modelo. Relatórios não podem omitir essa limitação. Drawdown exige série de patrimônio e denominador válido; métricas não calculáveis têm motivo.

Limites são aplicados antes de cada nova entrada ou camada: exposição resultante, número de camadas, perda e validade dos dados. Stop e alvo seguem uma política publicada para gaps e ambiguidades temporais. Não escolher silenciosamente o preenchimento mais favorável.

## Limites e segurança

Definir no código e no executor um limite de arquivos, bytes, pontos de dados, eventos, processos, tempo, memória e saída. Valores iniciais serão ajustados por medição em cenários fictícios e registrados com o resultado; não se promete capacidade não testada.

Sem acesso a rede no motor; sem API key; sem cliente de exchange; sem dependência capaz de operar conta; sem endpoint de ordens reais. O serviço rejeita campos desconhecidos ou modos operacionais externos. UI oculta não é controle suficiente.

Logs usam lista de campos permitidos: execução, versão, contagens, duração, estado e código de falha. Dados de contas financeiras e materiais privados não pertencem ao produto. Uma expansão multiusuário exigiria projeto de identidade, autorização por objeto, armazenamento e testes de acesso cruzado; não faz parte deste MVP.

## Dependências e evolução

Indispensáveis: ambiente local identificado, bibliotecas e licenças verificadas, isolamento demonstrado, dados sintéticos e contratos aprovados. Propostas: motor Python, serviço local simples e armazenamento transacional local quando necessário. Não confirmadas: qualquer runtime de produto, API, interface ou pipeline de CI.

Não adicionar IA, n8n, banco externo, VPS, exchange, cache ou fila distribuída por preferência de stack. A evolução começa por evidência de limitação concreta. Qualquer integração externa é outra decisão de escopo.

Base da arquitetura: contratos próprios de simulação determinística, contabilidade, integridade dos dados e controles de risco. O desenho permanece sujeito à aprovação do escopo e à verificação no ambiente escolhido.
