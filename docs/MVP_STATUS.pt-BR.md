# Estado concreto do MVP

Data do recorte: 22/10/2026. **Especificação preparada; produto não implementado; MVP não homologado.** O projeto é um laboratório autoral de simulação sintética.

## Evidência por dimensão

| Dimensão | O que existe | Conclusão e pendência |
| --- | --- | --- |
| Código funcional | Nenhum motor, serviço, interface, persistência ou exportador localizado nos artefatos autorais recuperados | Implementação pendente; documentação não é software executável |
| Especificação | Escopo, arquitetura, jornada, backlog e critérios de aceite | Preparados para revisão; D01–D03 pendentes |
| Mock/protótipo | Descrição textual de telas, estados e interações | Não há protótipo interativo validado |
| Exemplo | Referência contábil manual inteiramente fictícia | Ilustra cálculo; não executa estratégia nem testa motor |
| Hipóteses | Arquitetura local, contratos de dados e estratégia demonstrativa por definir | Propostas nossas; não decisões anteriores aprovadas |
| Verificação local do lote | Leitura editorial, JSON, referências internas, fórmula decimal do exemplo e revisão de informações/direitos | Consistência documental; não é teste funcional de produto |
| Teste local do produto | Nenhuma execução de jornada localizada | Pendente após implementação |
| CI do produto | Nenhum pipeline ou execução vinculada a uma implementação | Pendente; verificações locais não são CI |
| CI da documentação | Não configurado | Nenhuma passagem de CI declarada |
| Hospedagem | Documentação no GitHub | Nenhuma aplicação hospedada; deploy fora desta etapa |
| Validação humana | Nenhuma sessão de uso e aceite de versão localizada | Pendente; leitura de proposta não homologa jornada |

Essa avaliação descreve os artefatos autorais recuperados para este projeto; não afirma inexistência de software em outros ambientes. Ferramentas auxiliares e materiais externos não compõem a implementação nem o lote público.

## Jornada ainda a construir

Selecionar cenário fictício, revisar parâmetros e limites, simular localmente, entender um bloqueio, consultar eventos e exportar relatório reconciliado. Hoje uma pessoa consegue ler os documentos e conferir o exemplo manual, mas **não consegue completar essa jornada em software**.

Antes de implementar, D01–D03 precisam ser aprovadas: limite sintético/local/individual, jornada e primeira entrega mínima. Depois faltam cenário e validador, estratégia e motor determinístico, contabilidade, risco, executor limitado, revisão por versão, interface e exportação. Por último, são necessárias evidências funcionais, locais, de CI e de uso por uma pessoa. Consulte [backlog](BACKLOG.pt-BR.md) e [aceite](MVP_ACCEPTANCE.pt-BR.md).

Cada lacuna do backlog contém prioridade, categoria, dependências, esforço aproximado, critério verificável e decisão do proprietário. Esforços são faixas de pessoa-dias, não prazo contratado. Quantidade de testes ou pipeline verde isolado não comprova prontidão.

## Três próximas ações e decisões mínimas

1. **Aprovar ou ajustar D01–D03:** escopo offline/sintético/individual, jornada e primeira entrega mínima. Esta é a decisão necessária antes da implementação.
2. **Implementar a primeira entrega em mudanças revisáveis:** cenário → motor → eventos/contabilidade → risco → relatório; depois interface local e exportação. Escolhas técnicas rotineiras cabem à engenharia no escopo aprovado.
3. **Verificar e homologar a versão:** evidência funcional, local e CI; correções; tarefa real com o proprietário e aceite explícito. A decisão final depende de observar a jornada funcionando.

Licença editorial e identidade comercial podem ser decididas posteriormente; não há licença geral concedida. Não é necessário escolher exchange, credenciais, fornecedor de nuvem, framework ou plano pago para aprovar a proposta.
