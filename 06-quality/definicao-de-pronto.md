# 🥇 DEFINIÇÃO DE PRONTO (DEFINITION OF DONE - DoD) (SOP-IA)

## 1. O que é
O contrato final que diz: "Somente quando TODAS estas caixas estiverem marcadas, um Engenheiro (ou IA) tem permissão de dizer a palavra PRONTO na reunião diária".

## 2. Por que existe
Para estancar o problema do "Tá pronto, só falta testar" ou "Tá pronto, só falta subir". No SOP-IA, 99% pronto é igual a 0% pronto. Uma feature pela metade tem zero valor de negócio, mas consome 100% da ansiedade do Sponsor.

## 3. Quando usar
Toda vez que uma Task do `task.md` for movida de `[/]` (Em Andamento) para `[x]` (Concluída).

## 4. Como usar passo a passo
Fixe este documento no README do repositório ou no Master Prompt da IA. Nenhuma Pull Request pode ser mesclada sem cumprir o DoD.

## 5. Template Preenchível e Executável

```markdown
# Definition of Done (DoD) Universal

Uma funcionalidade SÓ ESTÁ PRONTA se:

- [ ] **1. O Código Funciona:** Passa no *Happy Path* do Critério de Aceite.
- [ ] **2. Está Testado:** Testes unitários foram escritos e passam no Pipeline CI. Nenhuma linha nova reduziu o *Code Coverage*.
- [ ] **3. Está Limpo:** Sem `console.log` esquecidos, sem `TODOs` inúteis largados no código, sem variáveis com nomes genéricos (`x`, `data2`). O ESLint/Prettier rodou e não acusou erros formais.
- [ ] **4. A Documentação Está Viva:** O `README` e as instruções de uso foram atualizados para refletir a nova funcionalidade. A IA gerou um ADR caso uma lib gigantesca tenha sido incluída.
- [ ] **5. A Métrica Confere:** O ganho ou conserto não comprometeu o Score Geral da Métrica de Impacto ou Risco Mapeada.
- [ ] **6. Está em Staging/Produção:** O cliente real consegue enxergar a feature se acessar o link agora. (Se está só no localhost do Dev, NÃO ESTÁ PRONTO).
```

## 6. Exemplos Reais
No SPED-PIS-COFINS, enquanto a equipe montava o parse dos números NCM, as funções estavam escritas, calculando certo no Console. Porém, como a *Documentação de Instrução ao Contador* não estava atualizada junto ao Design da Modal Front-End, o Epic não foi marcado como "Pronto". 

## 7. Métricas Associadas
- **Falsos Prontos:** Quantas vezes o board marcou itens como terminados, mas não podiam ser testados em Staging (ambiente restrito)?
- **Lead Time sem Retrabalho:** Código pronto, testado na ponta cega, sem chamados de bug reabrindo tickets. 

## 8. Perguntas de Validação
- Se uma IA escreve um motor backend incrível mas não conecta a Rota de API do Front-End... Você aceitaria ela te dizer que a task Backend está "Pronta"? (Se sim, você tem silos mortos em seu projeto).

## 9. Checklist de Conformidade
- [ ] A IA Copilot "entende" este conceito de Pronto quando acionada para codar Autonomamente? (Prompte ela).

## 10. Erros Comuns
- Confundir "Critério de Aceite" com "Definição de Pronto".
  - *Critério de Aceite* é específico da funcionalidade: "O botão deve ficar verde".
  - *Definição de Pronto* é universal pro time: "O botão ficou verde, ele foi testado automaticamente, não tem lixo no console, e está na nuvem".
