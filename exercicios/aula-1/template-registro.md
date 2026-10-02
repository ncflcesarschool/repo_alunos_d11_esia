# Registro individual — AV1.1

> **Como usar:** copie este modelo e substitua os espaços em branco pelas suas respostas. Consulte o [passo a passo da aula](README.md) e o [guia com exemplo de evidência](../README.md). Remova esta orientação da entrega; mantenha suas respostas e evidências em até uma página.

**Limite: uma página, incluindo evidências essenciais.** Estudante: Caroline Lima — Data: 01/10/2026
Origem: cartões C1–C3 fictícios do enunciado.

| Cartão | Como faria sem IA / entrada e resultado | Modalidade e justificativa ligada ao cartão | O que conferir para aprovar | Responsável humano |
|---|---|---|---|---|
| C1 | Para produzir os CAs sem usar IA, é necessário um estudo do contrato para entendimento da R2, listar os estados possíveis para cada chamado e determinar os critérios testáveis. Entrada: alterar um chamado para o estado fechado. Saída: confirmar que o chamado não aparece na listagem| Com assistência de IA. R2 tem critérios de aceite bem definidos e a revisão dos resultados é bastante simples. | Validar com casos de teste. Chamados com estado fechado não retornam. Chamados com estado aberto retornam na listagem. | Manutenção |
| C2 | É necessário determinar como é estabelicido o acesso por tipo de departamento. Estabelecer uma relação entre o tipo de departamento e o chamado. Criar casos de testes com múltiplos chamados, variando por estado e departamento de origem | Assim como em C1, a tarefa é bastante direta e regida por regras claras no contrato. | Validar que os casos de teste cobrem todos as combinações entre estado e departamento. Entrada: tabela de chamados. Saída: lista filtrada. | Gestão responsável / Equipe de QA|
| C3 | A tarefa solicitada não está bem especificada, até mesmo para execução humana. É necessário estabelecer melhor as regras para seguir com a execução da tarefa| Sem delegar a decisão. Não é possível seguir sem regras claras. | Exigir antes de seguir: documento da nova regra, lista de departamentos afetados e responsável claro pela aprovação | Gestão responsável |

**Exemplo que sustenta minha decisão (escolha C1, C2 ou C3; escreva entrada e saída esperada OU informação que falta, e explique a relação com sua decisão):** Um exemplo de entrada/saída para C1 seria uma tabela com 3 chamados, onde cada um tem um diferente estado: aberto, em_andamento, fechado. Após a execução de listar_ativos, apenas os chamados aberto e em_andamento são retornados


**Alternativa para o cartão C3:** Confirmar impacto da nova regra e definições de responsabilidade antes da implantação. Após atualização do contrato, é possível delegar a tarefa para IA com supervisão humana.
**Comparação com minha escolha (restrição e consequência):** O cartão 3 originalmente prevê que os critérios para a tarefa não estão bem definidos, o que restringe o uso da IA e até mesmo não garante uma implementação humana confiável.
**Limite da delegação e condição para rever a escolha:** Por ser um tema urgente e crítico, o limite da delegação é a implantação. Implementação do código e elaboração de testes podem ser delegados para IA, mas exigem uma revisão humana mais detalhada para que haja a implantação em produção. 

**Uso de IA na elaboração deste registro:** não utilizada / ferramenta e modelo visíveis: Ferramenta: Claude Sonnet; tarefa delegada e contexto: Pedi para o Claude me explicar o que era pedido na atividade utilizando termos simples; trecho aproveitado: nenhum trecho foi diretamente aproveitado neste documento; minha verificação/intervenção: verifiquei se a explicação estava condizente com o passo a passo disponibilizado pelo professor. Use “não informado” para metadados indisponíveis. O raciocínio e a decisão registrados são meus.

**Revisão:** [x] três decisões; [x] exemplo explicado; [x] alternativa e limite; [x] até uma página.
