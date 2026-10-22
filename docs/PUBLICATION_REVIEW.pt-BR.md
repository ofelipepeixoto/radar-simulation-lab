# Revisão do lote autoral

**Escopo autorizado:** documentação própria e exemplos sintéticos do `radar-simulation-lab`, um laboratório de simulação offline. A autorização editorial já foi concedida pelo proprietário. Este registro não cria uma nova etapa de consentimento.

**Estado da revisão:** inspeção local concluída sobre os 17 arquivos listados abaixo. Todos foram lidos; conteúdo, nomes relativos, links e exemplo foram conferidos. Nenhum bloqueador concreto foi encontrado para a publicação autoral já autorizada. Esta revisão não declara executada a atualização do repositório remoto ou de seu histórico.

## Decisões de conteúdo

| Categoria | Decisão |
| --- | --- |
| Apresentação, escopo, arquitetura, jornada e backlog próprios | Incluir versões autorais revisadas |
| Estado do MVP e critérios de aceite | Incluir, distinguindo proposta de implementação e testes executados |
| Políticas de direitos, segurança e publicação | Incluir |
| Exemplo manual de conciliação | Incluir somente dados fictícios com origem sintética explícita |
| Pesquisas externas, relatórios, inventários, metadados e estatísticas derivados de materiais externos | Excluir integralmente do lote público |
| Código ou ativos de terceiros, registros privados, capturas, pacotes e automações locais | Excluir |

Não se importam arquivos automaticamente de pastas de trabalho ou sessões. O lote público deve conter somente arquivos lidos, revisados e admitidos individualmente.

## Critérios da conferência final

- Ler todos os arquivos da árvore que será publicada e registrar a lista exata.
- Confirmar o escopo autoral, offline e sintético em todos os documentos.
- Confirmar a ausência de nomes, URLs, nomes de arquivo, hashes e referências aos materiais externos excluídos.
- Confirmar ausência de código externo, capturas, HAR, ZIP, logs brutos, arquivos executáveis e symlinks.
- Buscar credenciais, valores de autenticação, endereços de e-mail, caminhos pessoais, dados financeiros reais e identificadores de conta ou sessão; ler cada ocorrência em contexto.
- Validar a estrutura dos exemplos e os links locais, mantendo os dados sintéticos identificados.
- Distinguir o exemplo manual de uma saída de motor e manter o estado de implementação e homologação correto.
- Confirmar a reserva de direitos somente sobre contribuições próprias, sem licença geral externa ou cessão de terceiros presumida.
- Conferir o conteúdo, a lista de arquivos e a identidade pública de autoria antes de concluir o registro remoto.

Palavras como senha, cookie ou token em uma política de exclusões não constituem valores secretos. A inspeção precisa considerar o contexto; a ausência de padrões conhecidos não prova a inexistência de todo dado sensível possível.

## Resultado da inspeção local

| Verificação | Resultado observado |
| --- | --- |
| Inventário completo | 17 arquivos regulares: 15 Markdown, um JSON e o arquivo de exclusões do Git |
| Nomes e conteúdo | Sem referências identificadoras dos materiais externos excluídos; nenhum endereço externo ou identificador hexadecimal longo |
| Arquivos distribuídos | Nenhum código executável, recurso de terceiros, captura, pacote, HAR, log bruto ou symlink; nenhum arquivo com permissão de execução |
| Informação privada | Zero ocorrências dos padrões verificados de caminhos pessoais, e-mails, credenciais atribuídas, valores Bearer, tokens, JWT, chaves privadas, identificadores de conta ou execução e endereços de carteira/transação |
| Exemplo JSON | Decodificado com sucesso; origem sintética explícita, unidade fictícia SIM e indicação de referência contábil manual |
| Aritmética do exemplo | Taxas, custos, resultado bruto, resultado líquido modelado e patrimônio final conferidos com aritmética decimal exata |
| Links locais | Todos resolvem dentro do lote; nenhum link quebrado ou que saia da árvore |
| Inventário de evidências | P01–P08 descrevem somente documentos, exemplo, verificações editoriais e pendências do produto próprio |
| Estado do produto | Apresentações em português e inglês e documentos concordam: especificação preparada, motor e interface não implementados, MVP não homologado |
| CI e hospedagem | Nenhum workflow, execução de CI ou aplicação hospedada integra o lote; não são declarados como concluídos |
| Direitos | Reserva limitada às contribuições próprias; nenhuma licença geral ou cessão de terceiros presumida |

O exemplo manual não demonstra estratégia executada, bloqueio de risco, isolamento ou jornada funcional. As verificações realizadas nesta revisão são documentais e aritméticas; não são testes de um motor existente. Não foi necessário remover informação privada dos 17 arquivos finais inspecionados.

## Arquivos conferidos e admitidos

| Arquivo | Categoria e decisão |
| --- | --- |
| `.gitignore` | Exclusões próprias; incluído, sem ser tratado como prova de segurança |
| `AGENTS.md` | Orientações próprias para mudanças; incluído |
| `README.md` | Apresentação autoral em português; incluído |
| `README.en.md` | Apresentação autoral em inglês, coerente com a principal; incluído |
| `RIGHTS.md` | Direitos e autoria das contribuições próprias; incluído |
| `SECURITY.md` | Política própria de segurança e privacidade; incluído |
| `docs/ARCHITECTURE.pt-BR.md` | Arquitetura própria proposta; incluído |
| `docs/BACKLOG.pt-BR.md` | Planejamento próprio com dependências e pendências; incluído |
| `docs/EVIDENCE_INVENTORY.pt-BR.md` | Inventário exclusivamente autoral e sintético; incluído |
| `docs/EXCLUDED_MATERIALS.pt-BR.md` | Categorias genéricas de exclusão; incluído, sem identificar fontes excluídas |
| `docs/MVP_ACCEPTANCE.pt-BR.md` | Critérios futuros de aceite; incluído, sem alegar execução |
| `docs/MVP_STATUS.pt-BR.md` | Estado efetivo da documentação e implementação pendente; incluído |
| `docs/PRODUCT_SCOPE.pt-BR.md` | Proposta de escopo offline e sintético; incluído |
| `docs/PUBLICATION_REVIEW.pt-BR.md` | Registro desta revisão local; incluído |
| `docs/USER_JOURNEY.pt-BR.md` | Jornada própria proposta; incluído |
| `examples/synthetic/README.md` | Explicação de referência manual fictícia; incluído |
| `examples/synthetic/reconciliation.example.json` | Exemplo inteiramente sintético; incluído, sem ser schema aprovado do produto |

## Direitos e limites

O aviso de direitos reservados abrange as contribuições próprias na medida dos direitos de seu titular. Não é uma licença geral para reutilização, nem uma declaração de cessão de terceiros. [RIGHTS.md](../RIGHTS.md), [SECURITY.md](../SECURITY.md) e [EXCLUDED_MATERIALS.pt-BR.md](EXCLUDED_MATERIALS.pt-BR.md) delimitam as decisões aplicáveis.

Esta é uma revisão editorial, de procedência e privacidade. Não certifica cumprimento jurídico universal, segurança integral ou prontidão do MVP. Nenhuma implementação, passagem de CI, aplicação hospedada ou validação financeira é inferida da publicação de documentos.

**Decisão:** o lote local listado está adequado à publicação editorial autorizada. D01–D03 continuam pendentes para implementar o produto; não bloqueiam a publicação destes documentos próprios.

## Fronteira desta revisão

Metadados planejados: nome `radar-simulation-lab`, descrição de laboratório independente offline e sintético, conteúdo limitado aos 17 arquivos admitidos e nenhuma licença geral escolhida. O publicador preparará uma raiz própria sem commits pais e usará sua identidade pública com endereço GitHub noreply.

Essas operações remotas não foram executadas por esta revisão. A conferência do repositório, do ponteiro da branch, da árvore, do histórico e da identidade do commit pertencerá a um recibo separado após o envio. Este registro anterior ao envio não incorpora links ou identificadores de publicações anteriores.

Qualquer mudança posterior no conteúdo ou na lista de arquivos exige a conferência correspondente.
