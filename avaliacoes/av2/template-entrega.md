# Entrega individual — AV2

Estudante: Caroline Lima · Data: 11/10/2026 · Via: inspeção
**Limites:** análise até duas páginas; anexo técnico até duas páginas. [Enunciado](README.md).

## Análise

**1. Recorte e requisito.** Função/tarefa, quem usa o resultado e limites de entrada: A função `pode_visualizar_proposta` decide se uma pessoa pode ver um chamado, com base no estado do chamado e no departamento do solicitante. Quem usa o resultado é a manutenção, que aprova a regra e a documentação. As entradas são válidas: departamentos Oficina e Laboratório, estados `aberto`, `em_andamento` e `fechado`, impacto e urgência de 1 a 3.
R3/R4 em minhas palavras e critério de aceite definido antes da verificação: R3 diz que a pessoa só vê chamados do próprio departamento, em qualquer estado. R4 diz que a documentação precisa descrever essa mesma regra. Aprovo o código se o retorno depender só do departamento, e a documentação se não acrescentar nenhuma condição que R3 não tem.

**2. Estratégia.** Eixos da matriz, motivo dos quatro casos e o que mantenho constante: Os eixos são departamento (igual ou diferente do solicitante) e estado (aberto ou fechado). Os quatro casos cobrem todas as combinações. O solicitante é sempre Oficina. 
Caso decisivo e caso de controle, com justificativa: O decisivo é T2 (Oficina, fechado). Excluir chamados fechados é uma regra de R2, que trata da listagem de ativos. R3, que trata de visibilidade, não tem essa condição. O código copiou o filtro de estado de R2 para R3, e T2 é o caso em que isso muda o resultado. O controle é T1 (Oficina, aberto): aqui R2 e R3 pedem a mesma coisa, permitir, então o código acerta. Isso mostra que a comparação de departamento funciona e que o erro só aparece quando o estado entra.

**3. Evidência e interpretação.** Principais achados com referência a linhas T1–T4 e trechos E1–E3 do anexo: T1, T3 e T4 coincidem com R3. T2 diverge: R3 manda permitir e o código nega (E2), porque aplica a exclusão de chamados fechados que pertence a R2. A documentação (E3) também diz que chamados fechados ficam indisponíveis, o que repete essa mistura.
Relação entre contrato, comportamento do código e documentação: O código e a documentação concordam entre si, os dois bloqueiam chamados fechados. Mas os dois divergem de R3, que não olha o estado. A condição é de R2 e não passa automaticamente para R3.

**4. Decisão comparada.** Encaminhamento do código e da documentação, com fundamento: Rejeitar o código e rejeitar a documentação. O código nega o acesso em T2 por usar uma condição de R2, e a documentação repete esse erro.
Alternativa considerada / comparação sob o mesmo critério: Manter o código e mudar R3 para que chamados fechados fiquem ocultos também na visibilidade. Seria pouca mudança, mas é mudança de requisito, que precisa de aprovação, e não uma correção. Corrigir o código é mais simples e segue R3 sem depender de ninguém. A exclusão de fechados continua valendo na listagem, por R2.
Ajuste proposto, se aplicável, e revalidação (linhas do anexo): Trocar o retorno por `chamado["departamento"] == departamento` e reescrever a documentação sem falar de estado. Revalidei T1–T4 por leitura no anexo, e todas coincidem com R3.
Responsável pelo aceite e condição para rever a decisão: A manutenção aprova o ajuste. Eu reveria se a gestão responsável aprovasse uma mudança de R3 que escondesse chamados fechados.

**5. Procedência e limites.** Artefatos didáticos simulados utilizados: o código candidato, a documentação candidata e os registros V-01 a V-04 de insumos.md.
O que observei em execução / inferi por inspeção / apenas propus: Não observei nada em execução. Inferi os retornos por leitura do código. O ajuste e a nova documentação são só propostas, revalidadas por leitura.
Limite concreto da cobertura e consequência para minha decisão: Usei só quatro casos, com um solicitante e um par de valores de impacto e urgência por departamento. `em_andamento` não foi testado. Pelo código ele seria permitido, mas isso não foi conferido. A rejeição não depende disso, porque T2 já mostra a divergência.
IA: ferramenta-modelo visível: Claude Code, modelo Claude Sonnet 5.5; data: 11/10/2026; tarefa/contexto: ler o guia da aula 4 e os insumos da AV2 e refinar a escrita das respostas deste modelo assim como preencher a tabela; trecho aproveitado: redação dos campos e da matriz; verificação/intervenção próprias: conferi que o raciocínio original se manteve após as modificações e que o preenchimento da matriz estava condinzente com as regras descritas na documentação.

## Anexo técnico — trechos essenciais

**Dados e condições comuns:** registros V-01 a V-04 de insumos.md. Solicitante constante: Oficina. Impacto e urgência: 1 e 1 em V-01 e V-02, 3 e 3 em V-03 e V-04. O departamento do chamado e o do solicitante são comparados.

| Caso | Entrada/referência + solicitante | Relação de departamento / estado | Esperado por R3 | Retorno do candidato | Status observado/inferido | Interpretação |
|---|---|---|---|---|---|---|
| T1 | V-01, solicitante Oficina | Igual / aberto | True (mesmo departamento) | True | Inferido | Coincide. `==` é verdadeiro e `!= "fechado"` também. |
| T2 | V-02, solicitante Oficina | Igual / fechado | True (mesmo departamento, estado não importa) | False | Inferido | **Diverge.** `==` é verdadeiro, mas `!= "fechado"` é falso, então o `and` dá False. |
| T3 | V-03, solicitante Oficina | Diferente / aberto | False (outro departamento) | False | Inferido | Coincide. `==` é falso e o `and` já dá False. |
| T4 | V-04, solicitante Oficina | Diferente / fechado | False (outro departamento) | False | Inferido | Coincide, mas por acaso: o departamento diferente já basta para negar. |

**E1 — trecho do contrato e localização:** R3, em insumos.md (seção "Contrato de referência") e em caso/regras.md: "permite acesso somente à pessoa do mesmo departamento do chamado, independentemente de estado ou prioridade".
**E2 — trecho do código + percurso lógico de um caso decisivo e um controle:** `chamado["departamento"] == departamento and chamado["estado"] != "fechado"`.
Decisivo, T2: Oficina == Oficina é True; "fechado" != "fechado" é False; True and False dá False. R3 esperava True.
Controle, T1: Oficina == Oficina é True; "aberto" != "fechado" é True; True and True dá True. Coincide com R3, então a falha vem só da segunda condição.
**E3 — trecho da documentação e confronto com R3/código:** "chamados fechados ficam indisponíveis". Isso contraria R3, que diz "independentemente de estado". Concorda com o código, mas o código também está errado. A frase "Impacto e urgência não alteram essa decisão" está de acordo com R3.
**Execução, se escolhida — ambiente, comando e trecho de saída:** não realizada.
**Alternativa/ajuste e revalidação:** comportamento proposto: devolver só `chamado["departamento"] == departamento`, e a documentação passa a dizer que a pessoa vê chamados do próprio departamento em qualquer estado, e que impacto e urgência não alteram isso; T1–T4 após ajuste (esperado/retorno/status): T1 True/True, T2 True/True, T3 False/False, T4 False/False, todos inferidos por leitura e coincidindo com R3; limite: só quatro casos, e `em_andamento` não foi coberto.

**Checklist:** [x] 4 combinações; [x] critérios prévios; [x] código e texto; [x] status; [x] alternativa; [x] limites/IA; [x] 2+2 páginas.
