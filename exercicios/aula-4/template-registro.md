# Registro individual — AV1.4

**Limite: uma página.** Estudante: Caroline Lima — Data: 10/10/2026
**Critério de aceite por R2:** a saída inclui os chamados `aberto` e `em_andamento`, exclui os `fechado` e mantém a ordem em que os chamados chegaram. 

| Entrada | IDs esperados por R2 | IDs do candidato | Status: inferido/observado | Mecanismo/trecho essencial |
|---|---|---|---|---|
| TR-41, TR-42, TR-43, TR-44 | [TR-41, TR-42, TR-44] (TR-43 excluído por ter estado fechado) | [TR-42, TR-44, TR-41] | Inferido por leitura | `sorted(ativos, key=impacto + urgencia, reverse=True)`: o filtro por estado está certo, mas o `sorted` reordena por prioridade (6, 4, 2). |

**Teste entregue — o que verifica e o que não consegue distinguir:** Verifica que o fechado (TR-43) fica de fora e que o resultado é [TR-42, TR-44, TR-41]. Não distingue quem preserva a ordem de quem ordena por prioridade, porque a entrada do teste já está em ordem decrescente de prioridade.
**Trecho do teste (entrada e comparação de IDs) que sustenta minha análise:** Entrada: TR-42, TR-44, TR-41, TR-43. Comparação com ["TR-42", "TR-44", "TR-41"]. Por R2, o esperado seria esse mesmo, e o candidato também devolve isso. Os dois passam, então o teste não mostra o erro.
**Decisão (aceitar, aceitar com condições ou rejeitar) e motivo:** Rejeitar. Com a entrada de revisão o candidato devolve TR-42 antes de TR-41, e R2 manda manter a ordem de entrada. O teste não pega isso.
**Comparação entre manter e ajustar / responsável pelo aceite:** Manter deixaria uma ordenação que R2 não pede, e o teste continuaria passando sem avisar. Ajustar é uma mudança pequena. O aceite é da manutenção.
**Ajuste proposto (texto ou código):** Tirar o `sorted` e devolver só o filtro: `return [c for c in chamados if c["estado"] in ("aberto", "em_andamento")]`. Também trocar o teste por uma entrada em que a ordem de prioridade seja diferente da de chegada.

| Caso para conferir o ajuste: entrada e ordem | IDs esperados | Resultado previsto ou observado / status |
|---|---|---|
| TR-41, TR-42, TR-43, TR-44 | [TR-41, TR-42, TR-44] | Previsto por leitura: o filtro tira TR-43 e a ordem fica igual à de entrada, [TR-41, TR-42, TR-44]. Coincide com o esperado. |

**Limite remanescente e condição para rever o parecer:** Só conferi uma entrada, sem lista vazia nem chamados com a mesma prioridade. Eu reveria o parecer se um teste com ordem diferente da de prioridade desse resultado diferente do esperado.
**Origem dos dados e da análise:** candidato/teste/entrada simulados; método próprio: inspeção; comando e trecho de saída, se executado: não realizado.
**Uso de IA neste registro:** ferramenta-modelo: Claude Code, modelo Claude Sonnet 5.5; tarefa/contexto: ler o guia da aula 6 e o enunciado da AV1.4 e refinar as respostas escritas nesse modelo; trecho aproveitado e minha verificação: refinamento da escrita e formatação do texto, conferi que o raciocínio original foi mantido.

**Revisão:** [x] comparação com R2; [x] alcance do teste; [x] ajuste/revalidação; [x] status; [x] uma página.
