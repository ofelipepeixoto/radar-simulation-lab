# Jornada mínima proposta

Estado: **proposta; aprovação do usuário pendente**. Não há registro de aprovação desta jornada. A preparação da documentação não constitui essa aprovação.

Usuário inicial: proprietário em uso local e individual. Tarefa: testar uma configuração com dados fictícios e entender o resultado, os custos, os bloqueios e as limitações.

## Caminho principal

| Etapa | O usuário vê e faz | O sistema precisa garantir | Saída |
| --- | --- | --- | --- |
| 1. Cenário | Escolhe um exemplo sintético e lê período, unidade e qualidade | Catálogo permitido, hash, origem fictícia e validação temporal | Cenário válido selecionado |
| 2. Parâmetros | Edita rascunho com estratégia própria, capital fictício, custos e limites | Campos tipados, unidades explícitas e preservação dos valores válidos | Rascunho validado |
| 3. Revisão | Confere hipótese de preenchimento, custos excluídos e efeito dos limites | Revisão vinculada à versão exata; edição invalida revisão anterior | Configuração imutável aprovada para aquela simulação |
| 4. Simulação | Aciona “Simular cenário” e acompanha estado real | Idempotência, limite de recursos, motor sem rede e sem execução externa | ID e processamento determinístico |
| 5. Bloqueios | Entende quando uma entrada candidata foi negada ou o processamento parou | Checagem prévia de exposição/perda/camadas/dados e motivo verificável | Evento de risco e estado preservado |
| 6. Eventos | Consulta intenções, preenchimentos e lançamentos simulados | Ordenação, referências, deduplicação e reconciliação | Livro reproduzível |
| 7. Relatório | Lê resultado, posição aberta, custos, cobertura e hipóteses; exporta | Fórmulas versionadas; separação entre zero, ausência, parcial e desatualizado | Resultado reconciliado ou limitação explícita |

Nenhuma etapa solicita conta, carteira, API key, depósito, assinatura ou permissão de negociação. A revisão da etapa 3 é consentimento para uma execução sintética identificada, não uma autorização permanente ou aprovação para operar uma conta.

## Telas mínimas

Podem ser áreas de uma aplicação local simples. Não é obrigatório criar uma tela independente por etapa.

| Área | Ação principal | Estados e recuperação |
| --- | --- | --- |
| Cenário e configuração | Revisar configuração | Inicial, sem cenário, rascunho, inválido, salvo; erro indica campo e mantém dados válidos |
| Revisão | Simular cenário | Pronta, configuração alterada, limite incompatível; voltar ao rascunho sem perder dados |
| Execução e eventos | Ver resultado quando disponível | Na fila, executando, bloqueada, cancelada, falhou; preservar último checkpoint íntegro |
| Relatório | Exportar relatório | Completo, parcial, indisponível, exportação falhou; não substituir ausência por zero |

## Interrupção com significado claro

“Bloquear novas entradas” impede aumentar a posição simulada. “Interromper avaliação” congela o processamento e deixa explícito que o motor não está avaliando proteções. “Encerrar simulação” preserva o estado final, inclusive posição aberta. O texto do controle informa seu efeito antes da ação.

Não usar “pausar” como promessa genérica de segurança. Não apresentar cancelamento ou retomada como disponíveis enquanto esses comportamentos não estiverem implementados e verificados.

## Linguagem e acessibilidade

Mensagem constante: “Simulação offline com dados fictícios. Nenhuma ordem é enviada.”

O usuário deve reconhecer os próximos passos sem precisar inventar parâmetros técnicos. Oferecer um exemplo pequeno e valores editáveis com unidade. Detalhes extensos podem ser revelados progressivamente, mantendo custos e limites visíveis na revisão.

Navegação por teclado, foco visível, rótulos, erros textuais e leitura em uma coluna no mobile são critérios de aceite. Ganho, perda, bloqueio e cobertura não dependem somente de cor. Gráficos têm tabela equivalente e identificam período/unidade. Movimento reduzido é respeitado.

## Validação com o usuário

Após evidência funcional e execução local, o proprietário percorre o cenário incluído: selecionar, revisar, simular, explicar um bloqueio e localizar o resultado líquido modelado e suas limitações. Registrar conclusão da tarefa, dificuldades observadas, correções e decisão explícita sobre a versão.

Sem essa sessão, o estado permanece “validação com usuário pendente”. Não simular participantes nem converter opinião do agente em validação de usabilidade.

Decisões necessárias antes de implementar: aceitar o escopo sintético, esta jornada e a primeira entrega mínima descrita no [escopo](PRODUCT_SCOPE.pt-BR.md). Comparação de execuções, múltiplos instrumentos e interface mais elaborada são melhorias posteriores.

Base da jornada: tarefas e estados próprios do laboratório, com controle por versão, integridade de dados e interpretação explícita dos resultados.
