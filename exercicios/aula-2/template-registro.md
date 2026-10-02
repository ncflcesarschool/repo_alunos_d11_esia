# Registro individual — AV1.2

> **Como usar:** copie este modelo e substitua os espaços em branco pelas suas respostas. Consulte o [passo a passo da aula](README.md) e o [guia com exemplo de evidência](../README.md). Remova esta orientação da entrega; mantenha suas respostas e evidências em até uma página.

**Limite: uma página.** Estudante: Caroline Lima — Data: 02/10/2026
**Critérios antes da análise:** como conferir a classificação por R1: impacto + urgencia = escore. A partir do escore é possível classificar o chamado entre alta (>=5), média (>3 <5) ou baixa (<5); o que seria necessário para sustentar uma afirmação sobre outras entradas ou repetições: é necessário verificar várias combinações dos pares possíveis e demonstrar que múltiplas execuções para cada par retornam um resultado semelhante.

| Entrada de A (impacto, urgência) | Cálculo e esperado por R1 | Trecho da resposta A | Conclusão por inspeção |
|---|---|---|---|
| (2, 3) | 2+3 = 5, alta | O enunciado A diz que basta considerar impacto, nesse caso impacto 2 = media| R1 prevê alta e a resposta A diz media, ou seja, não coincidem |
| (3, 1) | 3+1 = 4, media | O enunciado A diz que basta considerar impacto, nesse caso impacto 3 = alta | R1 prevê media e a resposta A diz alta, ou seja, não coincidem |

**B — trecho analisado:** As três saídas foram ‘alta’. Isso prova que o modelo é determinístico e sempre entrega a classificação correta, inclusive em outros chamados.
**O que posso concluir sobre o par citado em B:** o contrato diz 2+3 = 5, classificado como alta, logo, o par citado em B realmente corresponde a alta. No entanto, a execução individual prova que o modelo é determinístico apenas dentro do conjunto testado.
**Afirmação geral de B: o que falta para sustentá-la:** Pode-se afirmar que o modelo é determinístico a partir das múltiplas execuções gerando um mesmo resultado. Falta repetir com outros pares e até mesmo aumentar o número de execuções. 
**Contraexemplo ou condição não coberta:** Cenários diferentes que não foram testados, como por exemplo casos de fronteira, (1, 2) dá escore 3 que deveria ser média assim como (2, 2) que dá escore 4 e também é média.

**Decisão A + motivo:** Rejeitar. A resposta usa só o impacto e ignora a urgência, o que contradiz R1, que manda somar os dois. Os dois pares conferidos dão resultado diferente do esperado: (2,3) deveria ser alta e A disse media; (3,1) deveria ser media e A disse alta. A regra proposta está errada, então não dá para aproveitar nem parte dela.
**Decisão B + motivo:** Aceitar parcialmente. A classificação alta para (2,3) está correta, porque 2+3=5 e R1 diz que escore ≥ 5 é alta. Já a afirmação geral fica rejeitada: três repetições de um único par não provam que o modelo é determinístico e não dizem nada sobre outros chamados. Além disso, as saídas fazem parte da narrativa simulada e não foram observadas por mim.
**Alternativa de verificação e condição que mudaria uma decisão:** comparar as respostas com R1 nas 9 combinações possíveis de impacto e urgência, incluindo as fronteiras.

**Origem dos dados e como fiz a análise:** respostas didáticas simuladas; cálculos/inspeções próprios: soma manual de impacto+urgencia para comparação com as faixas estabelecidas em R1, além da leitura dos trechos de A e B; execução real: não realizada. Tokens/custo/latência/configuração: não informados.
**IA na produção do registro:** não utilizada / ferramenta-modelo visível: Claude Code (Sonnet 5.5); tarefa/contexto: como contexto foi utilizado o README.md da av1.2 junto com o prompt para que a ferramente resumisse e explicasse cada item a ser preenchido nesse template; trecho aproveitado e verificação própria: nenhum trecho foi produzido diretamente pela ferramenta.

**Revisão:** [x] critérios; [x] dois pares; [x] análise de B; [x] decisões/limites; [x] uma página.
