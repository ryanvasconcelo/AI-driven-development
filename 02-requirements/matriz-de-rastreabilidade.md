# MATRIZ DE RASTREABILIDADE (SOP-IA v2.0)

## O que e
Um documento que conecta cada objetivo de negocio a cada feature, cada feature a
cada criterio de aceite, e cada criterio a sua evidencia de validacao. E a cadeia de
prova de que o software entregue resolve o problema para o qual foi contratado.

## Por que existe
Em projetos sem rastreabilidade, e impossivel responder: "Como saber se este codigo
serve ao objetivo original do projeto?" A matriz transforma essa pergunta subjetiva em
uma verificacao objetiva e auditavel.

## Nivel de Maturidade Minimo: 3
## Modo de Operacao: Recomendado para todos; obrigatorio em projetos criticos

---

## Template da Matriz

| ID | Objetivo de Negocio | Feature (Escopo) | Criterio de Aceite | Teste Associado | Evidencia de Validacao | Status |
|---|---|---|---|---|---|:---:|
| TR-01 | [Objetivo 1] | [Feature A] | [Criterio A.1] | [test_a1.spec.js] | [Link para screenshot/log] | Pendente |
| TR-02 | [Objetivo 1] | [Feature B] | [Criterio B.1] | [test_b1.spec.js] | — | Pendente |
| TR-03 | [Objetivo 2] | [Feature C] | [Criterio C.1] | Manual | — | Pendente |

---

## Regras de Preenchimento

1. Todo item do "In-Scope" deve ter pelo menos uma linha nesta matriz
2. Nenhuma Feature pode ter Status "Validado" sem evidencia (screenshot, log, link de teste)
3. A coluna "Objetivo de Negocio" deve ser copiada diretamente do `definicao-de-objetivo.md`
4. A coluna "Criterio de Aceite" deve ser copiada do `criterios-de-aceite-template.md`
5. A matriz deve ser atualizada a cada fechamento de Sprint

---

## Exemplo Aplicado (SPED-PIS-COFINS)

| ID | Objetivo de Negocio | Feature | Criterio de Aceite | Teste | Evidencia | Status |
|---|---|---|---|---|---|:---:|
| TR-01 | Reduzir auditoria de 3 dias para 3 cliques | Parser C170/C191 | Arquivo de 50MB processado em menos de 3s | automatico | console.time log | Validado |
| TR-02 | Zero dados fiscais em nuvem | Arquitetura Client-Side | Nenhuma chamada de rede durante processamento | inspecao Network tab | screenshot devtools | Validado |
| TR-03 | Automacao de CST via regras De-Para | Modal De-Para | CST alterado em 100% dos registros do NCM alvo | manual | video rayo_final_depara_check | Validado |

---

## Como a IA Usa Esta Matriz

Instrua o agente: "Antes de declarar qualquer feature concluida, verifique se ela tem
entrada na `matriz-de-rastreabilidade.md` com status Validado e evidencia preenchida.
Se nao tiver, nao pode ser marcada como Pronta no `task.md`."
