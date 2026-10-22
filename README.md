# Radar Simulation Lab

[English](README.en.md)

Projeto autoral de um laboratório local de simulação com dados inteiramente sintéticos e resultados auditáveis. A proposta ajuda uma pessoa a entender parâmetros, custos, limites e cada evento que compõe um resultado fictício.

**Estado em 22/10/2026: especificação preparada; produto não implementado; MVP não homologado.** Publicar documentos não aprova automaticamente a jornada ou sua implementação.

## Jornada mínima proposta

Selecionar cenário fictício → revisar parâmetros e limites → simular localmente → entender bloqueio de risco → consultar eventos e resultado reconciliado → exportar relatório.

Uso individual, um instrumento linear fictício, alavancagem um e execução offline. Modelo e estratégia próprios, com regras publicadas. Nenhuma conta, exchange ou operação financeira externa faz parte da proposta.

**Não há aplicação para instalar ou executar neste repositório.** O [exemplo sintético](examples/synthetic/README.md) é um exercício contábil calculado manualmente, não a saída de um motor existente.

## O que existe

| Material | Estado |
| --- | --- |
| Escopo, jornada e arquitetura | Propostos; D01–D03 pendentes |
| Backlog e critérios de aceite | Preparados para implementação e validação |
| Exemplo contábil | Fictício e manual, com fórmula explícita |
| Motor, interface, persistência e exportador | Não implementados |
| Testes funcionais, CI e validação humana | Sem evidência; pendentes |
| Aplicação hospedada | Inexistente; o repositório contém documentação |

## Documentação

| Documento | Finalidade |
| --- | --- |
| [Escopo](docs/PRODUCT_SCOPE.pt-BR.md) e [jornada](docs/USER_JOURNEY.pt-BR.md) | Proposta e decisões mínimas D01–D03 |
| [Arquitetura](docs/ARCHITECTURE.pt-BR.md) | Desenho próprio, ainda não implementado |
| [Estado do MVP](docs/MVP_STATUS.pt-BR.md) | Código, documentação, verificações locais, CI e validação humana |
| [Inventário de evidências](docs/EVIDENCE_INVENTORY.pt-BR.md) | Origem autoral, exemplo e limites das verificações |
| [Backlog](docs/BACKLOG.pt-BR.md) | Prioridades, dependências, esforço e critérios por lacuna |
| [Aceite](docs/MVP_ACCEPTANCE.pt-BR.md) | Evidências exigidas para homologação |
| [Segurança](SECURITY.md) e [direitos](RIGHTS.md) | Informações e procedência |
| [Exclusões](docs/EXCLUDED_MATERIALS.pt-BR.md) e [revisão](docs/PUBLICATION_REVIEW.pt-BR.md) | Limites do lote público |

## Próximas ações

1. Aprovar ou ajustar D01–D03: escopo local/sintético, jornada e primeira entrega mínima.
2. Implementar cenário, motor, contabilidade, risco e relatório; integrar a jornada local.
3. Demonstrar correção funcional, execução local e CI, e validar a jornada com o proprietário em uma versão identificada.

Quantidade de testes ou CI verde isolada não comprova prontidão. Não há modo de negociação real previsto. Dados externos, IA obrigatória, n8n, infraestrutura paga, multiusuário e deploy ficam fora deste MVP.

## Direitos e contribuição

O lote contém documentação própria e exemplo sintético. Não distribui código, ativos, registros ou relatórios de plataformas externas. Não envie informações privadas em issues.

Não foi escolhida uma licença geral para o conteúdo editorial próprio; consulte [RIGHTS.md](RIGHTS.md). A implementação depende das decisões de produto descritas no escopo.
