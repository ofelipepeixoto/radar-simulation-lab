# Exemplo contábil sintético — referência manual

**Inteiramente fictício. Não é saída de um motor implementado.** Trata-se de uma referência pequena para discutir as fórmulas propostas, antes da implementação. Não é schema aprovado, cenário de mercado ou recomendação financeira.

Unidade fictícia: `SIM`. Instrumento fictício linear: `SYNTH-UNIT`. Multiplicador um; alavancagem um; sem funding, liquidação, impostos, aportes ou retiradas. Todas as quantias no JSON são strings decimais para evitar arredondamento binário. Slippage é zero neste exemplo; um futuro modelo precisa declarar sua regra.

| Evento ilustrativo | Quantidade | Preço SIM | Taxa de 0,1% sobre o valor |
| --- | ---: | ---: | ---: |
| Entrada long | 1 | 100 | 0,100 |
| Saída completa | 1 | 102 | 0,102 |

Cálculo manual: resultado bruto = `1 × (102 − 100) = 2`; custos = `0,100 + 0,102 = 0,202`; resultado líquido modelado = `2 − 0,202 = 1,798`. Patrimônio final = `1.000 + 1,798 = 1.001,798 SIM`. Não sobra posição aberta. Não há referência temporal suficiente para calcular drawdown; ele permanece nulo com motivo.

O arquivo [reconciliation.example.json](reconciliation.example.json) preserva os dados e esse resultado ilustrativo. Ele não demonstra estratégia, bloqueio de risco, ordenação temporal do motor, interface, isolamento, determinismo ou aceite do MVP. Esses comportamentos precisam ser implementados e verificados separadamente.

English: this is wholly synthetic, manually calculated accounting data. It is neither an implemented simulator's output nor evidence of a validated product.
