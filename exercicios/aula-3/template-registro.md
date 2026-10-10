# Registro individual — AV1.3

**Limite: uma página.** Estudante: Caroline Lima — Data: 10/10/2026
**O que a listagem e a documentação precisam cumprir, conforme R2/R4:** incluir os chamados `aberto` e `em_andamento`, excluir os `fechado` e manter a ordem de entrada. A documentação precisa descrever esse mesmo comportamento, sem acrescentar regra.

| Caso / estado a verificar | Entrada (IDs e ordem) | IDs esperados na ordem | Obrigação de R2 e como verificar |
|---|---|---|---|
| 1 / aberto | [TR-33] | [TR-33] | Incluir `aberto`. Comparo a saída com a lista esperada e vejo se TR-33 está nela. |
| 2 / em_andamento | [TR-31] | [TR-31] | Incluir `em_andamento`. Comparo a saída com a lista esperada e vejo se TR-31 está nela. |
| 3 / fechado | [TR-32] | [] | Excluir `fechado`. A saída deve ser uma lista vazia. |

**Entrada combinada TR-31, TR-32, TR-33 → IDs esperados:** [TR-31, TR-33]
**Como conferiria a ordem (compare a posição dos IDs na entrada e na saída esperada):** Na entrada, TR-31 vem antes de TR-33. Na saída, TR-31 também deve vir antes de TR-33. TR-33 passa da 3ª para a 2ª posição porque TR-32 é excluído devido ao seu estado, o que não quebra a ordem. 
**Documentação proposta (até três frases):** A listagem inclui os chamados com estado `aberto` e `em_andamento`. Os chamados fechados são excluídos da listagem. Os chamados que permanecem aparecem na mesma ordem em que foram recebidos.

**Etapa em que admitiria IA / tarefa que ela faria / pessoa responsável por conferir:** Na redação dos casos de teste. A IA faria o primeiro rascunho dos casos, e a manutenção conferiria.
**O que essa pessoa deve verificar antes de aprovar:** Se cada caso tem entrada, saída esperada e regra conferida, e se a saída esperada vem de R2 e não de algum código. Também deve ver se a ordem foi tratada.
**Alternativa sem IA e comparação:** Eu mesma escreveria os casos a partir de R2. Levaria mais tempo, mas teria menos texto para revisar. Com IA, o rascunho sai mais rápido, mas ainda é preciso conferir cada caso. 
**O que os casos não verificam e o que me faria rever a aprovação:** Eles não testam lista vazia, só chamados fechados nem chamados repetidos, e usam poucos registros. Eu reveria a aprovação se um caso novo, como uma lista só com chamados fechados, desse resultado diferente do esperado.

**Origem dos dados e como fiz a análise:** entrada fictícia do enunciado; esperado por contrato: saídas esperadas calculadas por R2; inspeção própria: filtrei os registros à mão e comparei as posições; execução opcional (comando/resultado, se houver): não realizada.
**Uso de IA neste registro:** ferramenta: Claude Code, modelo Claude Sonnet 5.5; contexto/tarefa: ler o guia da aula 4 e o enunciado da AV1.3 e refinar as respostas desse modelo de acordo com o material de apoio; trecho aproveitado e minha verificação: conferi que as modificações feitas pelo modelo mudaram apenas a formatação das respostas e não o seu contexto original.

**Revisão:** [x] três estados; [x] ordem; [x] texto; [x] aceite/limite; [x] uma página.
