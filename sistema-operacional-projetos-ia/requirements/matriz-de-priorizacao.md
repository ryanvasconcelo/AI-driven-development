# ⚖️ MATRIZ DE PRIORIZAÇÃO (SOP-IA)

## 1. O que é
Um sistema matemático para matar "A Síndrome do Tudo é Urgente". É o artefato que decide a ordem exata em que o backlog do Escopo será executado, baseando-se em Valor vs Esforço.

## 2. Por que existe
Stakeholders inevitavelmente pedem todas as features para a "Sprint 1". A equipe de engenharia pode tentar começar pela feature tecnicamente mais divertida. A IA pode escolher codar a feature mais óbvia em vez da mais crítica. A Matriz força o time a entregar 80% do valor do negócio nos primeiros 20% do cronograma.

## 3. Quando usar
No final da Fase 02 (Definição Estratégica), após ter o Escopo fechado. Revisada sempre que uma mudança de escopo for aprovada.

## 4. Como usar passo a passo
Usaremos a Matriz **ICE** (Impact, Confidence, Ease). Dê notas de 1 a 10 para cada funcionalidade do escopo:
1. **Impact: Qual o impacto se construirmos? (10 = Revolucionário, 1 = Invisível)**
2. **Confidence: Quão confiantes estamos de que vai funcionar como esperado? (10 = Certeza absoluta, 1 = Risco gigante de P&D)**
3. **Ease: Quão fácil/rápido é de construir com as integrações atuais e as limitações de IA/Devs? (10 = Feito em um dia, 1 = Leva três Sprints)**
4. **Cálculo ICE Score:** (Impact x Confidence x Ease) / 100. Classifique as features do maior score pro menor. O topo do backlog nasce aqui.

## 5. Template Preenchível

```markdown
# Backlog Priorizado: [Nome do Projeto]

| Funcionalidade (Módulo do Escopo) | Impacto (1-10) | Confiança (1-10) | Facilidade (1-10) | ICE Score | Decisão (Sprint/Backlog) |
| --- | :---: | :---: | :---: | :---: | --- |
| Parser C170/C190 EFD Core | 10 | 8 | 5 | 4.0 | Sprint 1 (Base/Must-Have) |
| Grouping por NCM no UI | 9 | 10 | 7 | 6.3 | Sprint 1 (Core Focus) |
| Módulo "De-Para" de CFO/CST | 8 | 6 | 4 | 1.9 | Sprint 2 (Value Add) |
| Export TXT para NCMs únicos | 5 | 10 | 9 | 4.5 | Sprint 2 (Quick Win) |
| Tema Claro/Escuro Avançado | 2 | 10 | 8 | 1.6 | Sprint 3 (Nice to Have) |
```

## 6. Exemplos Reais
No SPED-PIS-COFINS, se os devs tivessem começado implementando a "Exportação TXT para NCMs" inteiramente antes do "Parser Central C170/C191", o projeto poderia travar antes mesmo das fundações de cálculo do PIS estarem feitas.
Focar na Funcionalidade `Grouping por NCM no UI` logo de início foi crítico, pois provou rápido ao cliente que as milhares de linhas desordenadas seriam condensadas magicamente antes do limite temporal da contabilidade expirar. O ICE Score blindou o time de devaneios artísticos pregressos como o `Tema Claro`.

## 7. Métricas Associadas
- **Aderência ao ICE:** Quantidade de *Pull Requests (PR)* ou incrementos que contemplam itens fora da ordem natural estabelecida no backlog. Ideal = zero desvios sem aval de Change Request.

## 8. Perguntas de Validação
- Se o orçamento do projeto acabasse hoje e tivéssemos que publicar os itens do topo do modelo ICE listado agora na produção: O sistema ficaria de pé e resolveria minimamente a dor apontada no `definicao-de-objetivo.md`?

## 9. Checklist de Conformidade
- [ ] Pontuações dadas pelo Time Técnico vs C-Level possuem discordâncias resolvidas documentadas?
- [ ] Features identificadas como "Nice to Have" foram enviadas para o final do projeto e comitadas no `plano-de-sprints.md`?

## 10. Erros Comuns
- Tentar começar o projeto focando nas tarefas "Ease 10" ("Vou colocar uns botões aqui só pra ter o front feito logo"), gerando um mockup lindo mas que não resolve o motor bruto do software de cara.
- Pontuar tudo com Impacto 10. Se tudo é Prioridade Máxima, então a Matriz inteira é inútil.
