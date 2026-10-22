# Critérios de aceite do MVP

Estado atual: **especificação preparada; implementação e aprovações pendentes**. Este documento define evidências futuras. Não afirma que os testes abaixo foram executados.

## Portas de decisão

| Etapa | Evidência exigida | O que permite concluir |
| --- | --- | --- |
| Aprovação mínima | Registro explícito de escopo, jornada e primeira entrega mínima, vinculados à versão dos documentos | Pode começar a implementação daquele escopo |
| Funcional | Cenários e resultados esperados; eventos, bloqueios, cálculos e reconciliação verificáveis | A fatia satisfaz os contratos examinados |
| Local | Execução real no ambiente alvo identificado, versões/comandos e evidência da jornada e do isolamento | Funciona naquele ambiente e recorte |
| CI | Pipeline sobre commit exato, com verificações pertinentes e falhas resolvidas | Regressões verificadas automaticamente naquele commit |
| Usuário | Proprietário conclui a jornada, entende os resultados e aprova ou registra correções | Homologação da versão para o uso local delimitado |

Uma etapa não substitui a outra. Build, CI verde, número de testes, revisão de código e demonstração fictícia não provam produção nem integração financeira. Contagem de testes não é indicador isolado de prontidão.

## Aceite funcional indispensável

| ID | Requisito | Verificação e evidência |
| --- | --- | --- |
| A01 | Apenas cenários sintéticos | Catálogo mostra origem fictícia; entradas de URL, caminho arbitrário, credencial ou modo live são rejeitadas pelo serviço |
| A02 | Dados íntegros | Casos fora de ordem, duplicados, não finitos, unidade incompatível e tamanho excedente falham com motivo; dados inválidos não viram zero |
| A03 | Revisão por versão | Mudança de parâmetro ou cenário invalida revisão anterior; execução referencia hashes exatos aprovados |
| A04 | Determinismo | Repetir dados/configuração/semente/motor produz eventos e resultados iguais; metadados de tempo real ficam separados |
| A05 | Sem antecipação | Alterar ou remover dados futuros não muda decisões anteriores; sinal em `t` não é preenchido antes de `t+1` |
| A06 | Contabilidade correta | Casos simples de long, short, fechamento parcial e posição aberta reconciliam lotes, taxas, saldo e patrimônio com referência independente |
| A07 | Custos sem duplicidade | Slippage aparece no preço, taxas por preenchimento; o mesmo custo não é subtraído duas vezes; custos fora do modelo são declarados |
| A08 | Risco antes da entrada | Candidato que excede exposição, camadas ou perda é bloqueado antes de gerar preenchimento; evento mostra regra, valor e limite |
| A09 | Estados de interrupção | Bloquear entradas, interromper avaliação e encerrar têm efeitos distintos; posição aberta não é silenciosamente fechada ou esquecida |
| A10 | Livro íntegro e idempotência | Repetição de evento/pedido não duplica ordem, custo ou resultado; mesma chave com corpo diferente gera conflito |
| A11 | Falhas preservadas | Timeout ou falha de escrita gera estado explícito e preserva checkpoint íntegro; resultado parcial não é apresentado como completo |
| A12 | Métricas honestas | Realizado e aberto separados; cobertura, período, fuso e unidade visíveis; ausência/zero/parcial/desatualizado distinguíveis; denominador inválido gera nulo justificado |
| A13 | Ordem de preenchimento declarada | Gap e conflito entre stop/alvo seguem regra documentada; não selecionar o desfecho mais favorável sem evidência temporal |
| A14 | Executor limitado | Evidência local demonstra ausência de rede e acesso apenas aos insumos/saída permitidos; limites de tempo, memória, volume e concorrência são efetivos |
| A15 | Produto sem operação externa | Inspeção e casos negativos mostram ausência de cliente de exchange, chave API e endpoint de ordens/transferências; controle não depende somente da UI |
| A16 | Exportação sanitizada | JSON/CSV/HTML incluem versão, hashes, fórmulas e limitações; marcadores sensíveis sintéticos não vazam; sem scripts externos ou dados privados |
| A17 | Jornada utilizável | Cenário → revisão → simulação → bloqueios → livro → relatório funciona na interface local aprovada, inclusive erros e estados vazios |
| A18 | Acessibilidade básica | Fluxo completo por teclado, foco visível, rótulos/erros textuais, mobile e alternativa tabular aos gráficos; estado não depende de cor |

## Evidência local

Registrar sistema operacional, versões reais, commit, insumos e hashes, comando ou ação de início, duração, resultado e limitações. Demonstrar a aplicação local e o processo de simulação separados, com o isolamento do executor comprovado. Logs e relatórios são sanitizados antes de compartilhar.

Se o isolamento não puder ser demonstrado, A14 continua pendente. Não chamar um parser, processo filho ou limite de memória de sandbox. Uma configuração apenas escrita não prova o controle em execução.

## Evidência de CI

O pipeline deve examinar schema, determinismo, contabilidade, risco, estados, idempotência, exportação e construção da interface quando existente. Usar cenários sintéticos fixados; não usar conta, segredos ou dados financeiros reais.

Guardar link da execução e commit. Diferenciar cobertura de unidade, comportamento integrado e controles que só foram testados localmente. Falha ignorada, suíte parcial ou job não executado permanecem visíveis. Nenhum pipeline foi criado por esta documentação.

## Evidência de validação com usuário

O proprietário deve executar o exemplo e demonstrar que consegue identificar:

- Que os dados são fictícios e que não há operação externa.
- Qual versão foi simulada e quais limites foram aplicados.
- Por que uma entrada foi bloqueada.
- O que compõe o resultado e quais custos estão excluídos.
- A diferença entre zero, ausência de dados e relatório parcial.

Registrar tarefa, versão, resultado observado, dificuldades e decisão: aprovado para uso local delimitado, aprovado com limitações documentadas ou requer correções. Não assumir aprovação por silêncio.

## Estados de entrega

`Documentado` → `aprovado para implementar` → `implementado` → `verificado funcionalmente` → `verificado localmente e em CI` → `validado pelo usuário`.

Hoje o projeto está no primeiro estado. Uso externo, multiusuário, infraestrutura pública, dados reais e operações financeiras não fazem parte da homologação deste MVP e não são autorizados por concluí-la.

Base dos critérios: contratos próprios de simulação, controles de risco e decisões de escopo documentadas neste projeto.
