# Registro individual — AV1.2

**Limite: uma página.** Estudante: Caroline Lima — Data: 10/10/2026
**Critérios antes da análise:** como conferir a classificação por R1: somar impacto e urgência e comparar o resultado com as faixas (>= 5 alta, 3 a 4 media, < 3 baixa); o que seria necessário para sustentar uma afirmação sobre outras entradas ou repetições: várias execuções reais, registradas, com entradas diferentes e o esperado calculado por R1 em cada uma.

| Entrada de A (impacto, urgência) | Cálculo e esperado por R1 | Trecho da resposta A | Conclusão por inspeção |
|---|---|---|---|
| (2, 3) | 2 + 3 = 5; R1 dá `alta`. | "(impacto=2, urgencia=3) é media" | Não coincide. R1 pede `alta` e A disse `media`. |
| (3, 1) | 3 + 1 = 4; R1 dá `media`. | "(impacto=3, urgencia=1) é alta" | Não coincide. R1 pede `media` e A disse `alta`. |

**B — trecho analisado:** "As três saídas foram 'alta'. Isso prova que o modelo é determinístico e sempre entrega a classificação correta, inclusive em outros chamados."

**O que posso concluir sobre o par citado em B:** Para (2, 3), 2 + 3 = 5 e R1 dá `alta`, então a saída citada está certa para esse par.

**Afirmação geral de B: o que falta para sustentá-la:** B generaliza a partir de uma única entrada repetida três vezes. Faltam outras entradas, incluindo as faixas `media` e `baixa`, e saídas realmente observadas. Repetir o mesmo resultado também não prova que ele é correto em todos os casos.

**Contraexemplo ou condição não coberta:** (1, 1) deveria dar `baixa` e (2, 1) deveria dar `media`. B não testou nenhum dos dois. Isso é só uma proposta de teste, não foi executado.

**Decisão A + motivo:** Rejeitar. Os dois pares estão errados em relação a R1, porque A usa só o impacto e ignora a urgência.

**Decisão B + motivo:** Aceitar parcialmente. O par (2, 3) está certo, mas "prova" e "sempre" não têm base em uma entrada só.

**Alternativa de verificação e condição que mudaria uma decisão:** Rodar entradas de todas as faixas, como (1, 1), (2, 1), (2, 2) e (3, 3), com o esperado calculado antes por R1 e depois comparado. Eu reveria a decisão sobre B se houvesse execuções registradas que cobrissem as três faixas e batessem com R1.

**Origem dos dados e como fiz a análise:** respostas didáticas simuladas; cálculos/inspeções próprios: soma manual e comparação com R1; execução real: não realizada. Tokens/custo/latência/configuração: não informados.
**IA na produção do registro:** ferramenta-modelo visível: Claude Code, modelo Claude Sonnet 5.5; tarefa/contexto: ler o guia da aula 4 e refinar as respostas presentes neste template de acordo com o material de apoio; trecho aproveitado e verificação própria: verifiquei que os valores calculados e as respostas originais foram apenas refinados mas não tirados de contexto.

**Revisão:** [x] critérios; [x] dois pares; [x] análise de B; [x] decisões/limites; [x] uma página.
