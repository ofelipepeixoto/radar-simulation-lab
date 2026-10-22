# Escopo do produto autoral

Estado: **proposta; aprovação mínima pendente antes de implementar**.

O Radar Simulation Lab é uma proposta de laboratório independente de simulação sintética offline. A presença destes documentos não significa que existe produto funcional, que uma jornada foi aprovada ou que uma integração está homologada.

## Identidade e finalidade

O projeto organiza cenários fictícios, configurações próprias, eventos simulados e fórmulas explícitas para apoiar aprendizado e verificação. Seu código e sua interface serão autorais, com procedência e licenças registradas para eventuais bibliotecas reutilizadas. O laboratório não opera contas financeiras.

## Problema e público

O usuário precisa entender como parâmetros e limites alteram uma simulação e explicar cada resultado por eventos e fórmulas. O primeiro usuário é o proprietário do laboratório, em uso local e individual.

O resultado esperado é um relatório reproduzível, com origem sintética, período, unidade, custos, posições simuladas, bloqueios de risco e reconciliação. Não se promete desempenho financeiro ou fidelidade a uma exchange.

## MVP proposto

A jornada mínima é:

1. Selecionar cenário sintético validado.
2. Revisar parâmetros, custos, limites e hipóteses.
3. Executar simulação determinística da versão revisada.
4. Aplicar bloqueios de risco antes de cada entrada simulada.
5. Registrar eventos e lançamentos contábeis rastreáveis.
6. Consultar e exportar relatório reconciliado, com lacunas explícitas.

O primeiro modelo usa um instrumento linear fictício e uma posição líquida por execução, com alavancagem fixada em um. Não modela liquidação de uma corretora. O motor informa os custos que modela e os que exclui. Preços sintéticos não são dados históricos de mercado.

Dados ausentes, valor zero informado, cobertura parcial e dados desatualizados são estados diferentes. Métrica indisponível permanece nula com motivo. Uma execução pode terminar com posição aberta; o relatório não inventa fechamento para melhorar o resultado.

## Indispensável para considerar o MVP

- Escopo e jornada aprovados explicitamente.
- Cenários sintéticos, configuração e motor versionados e identificados por hash.
- Estratégia própria, pequena e determinística, com regras publicadas.
- Livro de eventos e contabilidade reconciliáveis.
- Limites de exposição, camadas, perda, validade dos dados e recursos do executor.
- Distinção entre bloquear novas entradas, interromper avaliação e encerrar uma simulação.
- Fluxo local utilizável e exportação sanitizada.
- Evidências funcionais, locais, de CI e de validação com o usuário.

CI significa integração contínua: verificações automáticas sobre um commit identificável. CI verde e quantidade de testes não substituem correção funcional, observação local ou aprovação do usuário.

## Fora deste MVP

Exchange ou carteira conectada; chave API; ordens reais; depósitos, saques e transferências; dados de conta; assinatura ou taxa de desempenho; crédito interno; afiliados; multinível; múltiplos clientes; VPS; banco externo; n8n no fluxo; IA obrigatória; publicação de serviço.

Uma possível integração apenas de leitura é uma decisão futura de produto, permissão e dados. Não fica autorizada pela aprovação deste MVP. Não há modo live oculto ou ativável por configuração.

## Decisões mínimas pendentes

| ID | Decisão do proprietário | Proposta para aprovação | Efeito |
| --- | --- | --- | --- |
| D01 | Aceitar o limite de produto | Laboratório sintético, local, individual e offline; sem operações financeiras externas | Fixa o que pode ser construído |
| D02 | Aceitar a jornada mínima | Cenário → revisão → simulação → bloqueios → livro de eventos → relatório | Evita construir módulos antes do primeiro resultado útil |
| D03 | Aceitar a primeira entrega mínima | Cenário demonstrativo e estratégia determinística próprios, interface local simples e relatório reconciliado | Permite iniciar o backlog indispensável |

**D01, D02 e D03 estão pendentes.** Estes documentos apresentam uma proposta de jornada; não há registro de sua aprovação. A preparação da documentação não constitui aprovação da implementação.

Escolhas rotineiras de bibliotecas e organização do código podem ser resolvidas tecnicamente após essas decisões, verificando versões, licenças e ambiente. Novas integrações, serviço público, contratação, acesso a dados reais ou expansão financeira exigem decisões próprias.

## Como revisar

Ler [jornada](USER_JOURNEY.pt-BR.md), [arquitetura](ARCHITECTURE.pt-BR.md), [aceite](MVP_ACCEPTANCE.pt-BR.md) e [backlog](BACKLOG.pt-BR.md). Aprovar uma versão específica desses documentos e registrar eventuais alterações de escopo antes de implementar.

Base da proposta: contratos próprios de simulação, integridade de dados, contabilidade e controle de risco. Decisões de implementação e resultados futuros devem permanecer identificáveis e verificáveis.
