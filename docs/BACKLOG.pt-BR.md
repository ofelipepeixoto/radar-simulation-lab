# Backlog autoral e lacunas

Estado: **planejamento; aprovação mínima pendente antes de implementar**. Nenhum item é apresentado como implementado apenas por estar documentado.

Prioridade expressa ordem recomendada. Classificação indica se o item é indispensável ao MVP, melhoria posterior ou fora do escopo. Esforço é uma faixa aproximada em pessoa-dias de trabalho técnico, não prazo de calendário, orçamento ou compromisso. As faixas dependem do ambiente, revisão e solução escolhida; itens compartilham atividades e não devem ser somados como estimativa contratual.

## Indispensáveis ao MVP

| ID | Prioridade / lacuna | Classe | Dependências | Esforço aproximado | Critério verificável | Decisão do usuário |
| --- | --- | --- | --- | --- | --- | --- |
| B00 | P0 — aprovar escopo, jornada e primeira entrega mínima | Indispensável | Revisão dos documentos | 0,25–0,5 | D01–D03 registradas explicitamente para uma versão; sem aprovação, implementação não começa | **Sim: pendente** |
| B01 | P0 — contrato técnico e ambiente local | Indispensável | B00 | 0,5–1,5 | Runtime/licenças reais registrados; contratos e modo sintético fixados; nenhum recurso externo contratado | Não para escolhas rotineiras; sim se houver custo ou mudança de escopo |
| B02 | P0 — cenário e validador sintéticos | Indispensável | B01 | 1–2 | Seed/hash reproduzíveis; rejeita dado não finito, fora de ordem, duplicado, unidade errada e volume excessivo | Não, dentro do escopo aprovado |
| B03 | P0 — estratégia própria e motor determinístico | Indispensável | B02 | 2–4 | Regra publicada; execução em `t+1`; cenários long/short simples reproduzem mesmos eventos | Não para regra demonstrativa; sim para alterar objetivo do produto |
| B04 | P0 — livro de eventos e contabilidade | Indispensável | B03 | 2–3 | IDs/ordenação, lotes e custos reconciliam; duplicata não altera saldo duas vezes; escrita é atômica | Não |
| B05 | P0 — limites de risco e interrupções | Indispensável | B03, B04 | 1,5–3 | Exposição candidata/camadas/perda/dados são checados antes da entrada; comandos têm efeitos distintos e testados | Não para implementação; sim para flexibilizar limites fora do contrato |
| B06 | P0 — fórmulas e relatório reconciliado | Indispensável | B04, B05 | 1,5–3 | Realizado/aberto/custos separados; ausência/zero/parcial distintos; relatório leva período, unidade, fuso, hashes e limitações | Não |
| B07 | P0 — executor e recursos limitados | Indispensável | B01, B03 | 1,5–3 | Sem rede; insumos somente leitura/saída própria; limites efetivos demonstrados no ambiente local | Não; se exigir novo ambiente ou contratação, apresentar decisão específica |
| B08 | P0 — revisão por versão e idempotência | Indispensável | B02–B04 | 1–2 | Edição invalida revisão; pedido duplicado reutiliza execução; mesma chave/corpo diferente gera conflito | Não |
| B09 | P0 — jornada local mínima | Indispensável | B06–B08 | 2–4 | Caminho completo com cenário, revisão, estado, bloqueio, eventos e relatório; teclado/mobile/erros verificados | Não para rotinas; mudança da jornada aprovada requer nova decisão |
| B10 | P0 — exportação e observabilidade sanitizadas | Indispensável | B04, B06, B09 | 0,5–1,5 | Exportações reproduzíveis com hashes; logs por lista permitida; marcadores sensíveis fictícios não vazam | Não |
| B11 | P0 — evidência funcional, local e CI | Indispensável | B02–B10 | 2–4 | Matriz A01–A18 tem evidência verificável nos critérios indispensáveis; pendências bloqueiam homologação; commit, execução local e CI identificados; sem usar contagem de testes como prontidão | Não para verificar/corrigir dentro do escopo |
| B12 | P0 — validação da jornada com proprietário | Indispensável | B11 e correções necessárias | 0,5–1,5 | Usuário conclui tarefas e interpreta bloqueio/custos/lacunas; decisão de homologação registrada para a versão | **Sim: homologação do usuário** |

Não implementar B01–B12 antes de B00. Preparação documental e leitura autorizada do repositório não são evidência de que B00 passou.

## Melhorias após o primeiro resultado útil

| ID | Prioridade / lacuna | Classe | Dependências | Esforço aproximado | Critério verificável | Decisão do usuário |
| --- | --- | --- | --- | --- | --- | --- |
| B13 | P1 — comparar execuções | Melhoria | B12 | 1–2,5 | Destaca diferenças de versão/dados/custos; bloqueia equivalência indevida | Sim para incluir no próximo ciclo |
| B14 | P1 — biblioteca ampliada de cenários adversos | Melhoria | B12 | 1–3 | Cenários novos têm origem sintética, expectativa independente e cobertura registrada | Não, se prevista no ciclo aprovado |
| B15 | P1 — experiência e visualização mais elaboradas | Melhoria | B09, B12 | 1–3 | Mudança reduz dificuldade observada e mantém acessibilidade, estados e conteúdo exato | Sim se alterar jornada ou identidade aprovada |
| B16 | P2 — múltiplos instrumentos, margem e funding | Melhoria fora do primeiro modelo | B12, novo contrato financeiro | 3–8 | Modelos/unidades/horários explícitos, reconciliação e cenários adversos independentes antes de habilitar | **Sim: expansão de modelo** |

## Fora deste MVP

| ID | Prioridade / lacuna futura | Classe | Dependências | Esforço aproximado | Critério para reconsiderar | Decisão do usuário |
| --- | --- | --- | --- | --- | --- | --- |
| X01 | P2 — dados externos somente leitura | Fora | Novo escopo, origem/licença de dados e permissão verificadas | 2–6 após descoberta | Dados e acesso legítimos; nenhum privilégio de negociação; nova homologação de cobertura/falhas | **Sim, específica** |
| X02 | P2 — IA explicativa opcional | Fora | Necessidade demonstrada, dados permitidos, orçamento e limites | 1–4 após descoberta | Melhora medida sobre explicação determinística; não decide risco, cálculo ou permissão | **Sim se incluir custo ou envio externo** |
| X03 | P2 — n8n, VPS, banco externo ou serviço público | Fora | Requisito operacional concreto, arquitetura, licença, custos e destino | 2–8 após descoberta | Não adicionar por preferência de stack; isolamento e operação próprios comprovados | **Sim, específica** |
| X04 | P2 — multiusuário e autenticação remota | Fora | Novo produto/ameaças, identidade, autorização e isolamento | 4–10 após descoberta | Acesso por objeto e testes cruzados; não basta coluna de usuário ou botão oculto | **Sim, específica** |
| X05 | P2 — execução financeira, chaves, depósitos, cobrança ou afiliados | Fora | Novo estudo e mandato explícito, arquitetura e homologação próprios | Não estimado: escopo insuficiente | Não existe caminho operacional no MVP; qualquer estudo futuro é separado desta aprovação | **Sim; não autorizado neste escopo** |

P2 em itens fora do escopo significa baixa precedência documental, não compromisso de construir. Faixas exploratórias de X01–X04 não autorizam implementação nem contratação. X05 permanece sem estimativa para evitar falsa precisão.

## Ordem de entrega revisável

Primeira fatia: B01–B07, cenário ao relatório por interface técnica reproduzível. Segunda fatia: B08–B10, jornada local aprovada e exportação. Terceira fatia: B11–B12, evidências integradas, correções e homologação. Cada fatia deve ter objetivo coerente, validação própria e dependências explícitas; documentação, código e testes da mesma mudança permanecem juntos.

A primeira entrega mínima de D03 compreende as duas primeiras fatias técnicas; a terceira produz a evidência necessária para homologar essa entrega.

## Cobertura do backlog

A jornada completa é indispensável: a primeira fatia técnica sozinha não é um MVP utilizável. Esta priorização é uma proposta sujeita a D01–D03, ainda pendentes.

| Requisito próprio | Itens responsáveis |
| --- | --- |
| Escopo e decisões | B00–B01 |
| Cenário e esquema sintéticos | B02 |
| Livro e motor determinístico | B03–B04 |
| Risco antes da entrada | B05 |
| Relatório e fórmulas | B06 |
| Executor isolado | B07 |
| Rascunho, revisão e idempotência | B08 |
| Jornada local acessível | B09 |
| Exportação e observabilidade | B10 |
| Evidência funcional, local e de CI | B11 |
| Homologação pelo usuário | B12 |
| Comparação e refinamento | B13–B15, melhorias posteriores |
| Margem, funding e múltiplos instrumentos | B16, expansão posterior |
| Integrações e operação externa | X01–X05, fora deste MVP |

A presença de um requisito nesta tabela não significa que ele foi executado, testado ou homologado. Verificação e aprovação devem ser registradas para versões específicas.

CI e revisão do agente não representam aprovação humana. Uma modificação após homologação precisa das verificações afetadas; mudança material de escopo ou jornada retorna à decisão correspondente.

Base do planejamento: escopo, arquitetura, jornada e critérios de aceite próprios deste projeto. Os esforços são estimativas aproximadas, sem medição de implementação concluída.
