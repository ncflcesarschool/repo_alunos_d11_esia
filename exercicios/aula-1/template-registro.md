# Registro individual — AV1.1

**Limite: uma página, incluindo evidências essenciais.** Estudante: Caroline Lima — Data: 10/10/2026
Origem: cartões C1–C3 fictícios do enunciado.

| Cartão | Como faria sem IA / entrada e resultado | Modalidade e justificativa ligada ao cartão | O que conferir para aprovar | Responsável humano |
|---|---|---|---|---|
| C1 | A manutenção lê R2 e escreve um critério para cada parte da regra. Resultado: rascunho de critérios de aceite. | **Com assistência.** A IA escreve o rascunho. O contrato já está aprovado e o pedido é só um rascunho, então é fácil revisar. | Os critérios cobrem as quatro partes de R2 (incluir `aberto` e `em_andamento`, excluir `fechado`, manter a ordem) e não inventam regra nova. | Manutenção |
| C2 | QA lê R3 e monta chamados variando departamento e estado, com o resultado esperado de cada um. Resultado: proposta de teste com entrada, saída esperada e justificativa. | **Com assistência.** A IA sugere as combinações, mas QA define o esperado, porque é fácil confundir R3 com R2 e achar que chamado `fechado` não pode ser visto. | Há caso de mesmo departamento e de departamento diferente, e um chamado `fechado` do próprio departamento continua visível. | Equipe de QA |
| C3 | A gestão busca o que falta (regra nova, dados afetados, verificações e aprovador) antes de decidir. Resultado hoje: não autorizar. | **Sem delegar a decisão.** É uma autorização em produção e só existe o resumo "facilitar acesso entre áreas", que pode contrariar R3. A IA só ajudaria a listar as perguntas pendentes. | Regra nova escrita e comparada com R3, dados afetados identificados, verificações definidas e aprovador confirmado. | Gestão responsável |

**Exemplo que sustenta minha decisão (escolha C1, C2 ou C3; escreva entrada e saída esperada OU informação que falta, e explique a relação com sua decisão):** C2. Entrada fictícia: chamado `T1`, da Oficina, estado `fechado`. Se quem pede é da Oficina, o esperado é permitir, porque R3 só olha o departamento. Se é do Laboratório, o esperado é não permitir. Esse caso mostra se a proposta de teste misturou R2 com R3.

**Alternativa para o cartão C3:** com assistência — pedir à IA uma recomendação de autorizar ou não.
**Comparação com minha escolha (restrição e consequência):** A IA só teria o resumo e precisaria supor a regra nova. Daria menos trabalho, mas a recomendação pareceria fundamentada sem ser, e a mudança em produção ficaria sem responsável.
**Limite da delegação e condição para rever a escolha:** A IA vai até a lista de pendências; autorizar é decisão da gestão. Eu reveria a escolha se a regra nova entrasse no contrato, com dados afetados, verificações e aprovador definidos. Aí a IA poderia rascunhar os testes, mantendo a autorização humana.

**Uso de IA na elaboração deste registro:** ferramenta e modelo visíveis: Claude Code, modelo Claude Sonnet 5.5; tarefa delegada e contexto: ler o guia da aula 4 e avaliar minhas respostas neste template; trecho aproveitado: correção da tabela e dos campos finais; minha verificação/intervenção: conferi cada campo e verifiquei que as respostas originais foram apenas formatadas e não tiradas de contexto. O raciocínio e a decisão registrados são meus.

**Revisão:** [x] três decisões; [x] exemplo explicado; [x] alternativa e limite; [x] até uma página.
