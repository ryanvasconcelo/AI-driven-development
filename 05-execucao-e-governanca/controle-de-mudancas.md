# 🔄 CONTROLE DE MUDANÇAS (CHANGE REQUEST) (SOP-IA)

## 1. O que é
A barreira de contenção contra o "Já que você está mexendo nisso, faz só um negocinho a mais". 

## 2. Por que existe
O "Feature Creep" (Aumento sorrateiro do escopo inicial) é o assassino nº 1 de projetos em escopo fechado. IAs, por padrão, sofrem da "Doença do Sim" (Sycophancy). Se um cliente disser à IA "Gere uma página de login pra mim" e ela não for orientada a usar este arquivo, em 3 min a interface ganha uma distração visual colossal incompatível com a linha cronológica e orçamentária que a arquitetura presumiu.

## 3. Quando usar
Sempre que uma tarefa solicitada durante a Sprint pertencer ativamente à lista de "Out-of-Scope" mapeada na Fase 2.

## 4. Como usar passo a passo
1. O Sponsor/Cliente faz um pedido.
2. O Tech Lead / IA verifica o manifesto In-Scope / Out-of-Scope.
3. Se o pedido for "Out-of-Scope" ou inflar agressivamente a Complexidade ("Ease >" ICE Score): Pare. Exija a criação desta Requisição de Mudança (CR).
4. O Pedido passa pelo *ICE Score* novamente para ver o orçamento de esmagamento contra as priorities de hoje.

## 5. Template Preenchível e Executável

```markdown
# Mudança de Escopo: CR-[Num]

## 1. O Pedido
**Solicitante:** [Dono da ideia]
**O Quê (A Funcionalidade Nova):** [Botão que gera Dashboard Pix]
**Por Que (A Dor Oculta):** [A ferramenta melhorou, agora querem ver números gráficos do faturamento além do SPED bruto]

## 2. A Avaliação do Orçamento/Esforço Mestre (Tech-Lead/IA)
- **Custo Cognitivo/Técnico:** [Adicionar libs como Recharts para Dashboarding aumentará em X Minutos o loading local e destruirá a Sprint 3 inteira focada em Cálculos do PIS].
- **Novo Score ICE:** Impact (8) x Confidence (6) x Ease (2) = 0.96.

## 3. O Trade-Off (A Troca Inegociável)
Para alocar este novo "O Quê" na Fase Atual de Entrega (Sprint 3) sem atrasar a data fatal para o cliente, **O QUE VAMOS DESCARTAR do Milestone Original?**
- Item Descartado (Trocado): [O "Export de PDF", previsto pro final da Sprint, será cortado].
Se o cliente/sponsor NÃO aceitar descartar (Trade-off = Null), a Data Fatal DEVE ser adicionada no Cronograma Macro.

## 4. Veridito do C-Level
- [ ] Aprovado (Re-planeja Roadmap)
- [ ] Rejeitado (Vai para Backlog "Mesa de Ideias")
```

## 6. Exemplos Reais
Ao decorrer do "SPED-PIS-COFINS", surgiu uma vontade latente de que a IA também avaliasse não só os NCMs, mas CFOPs dos Contadores. A mudança de escopo (Change Request) foi registrada e barrada da versão "V1.0", sendo realocada para o roadmap do V2, pois atrasaria o foco cruel no sucesso puro da agregação de mercadorias. A IA negou-se a introduzir lógicas de CFOP por estarem despriorizadas.

## 7. Métricas Associadas
- **Volume de CRs (Change Requests):** Indica quão mal foi feito o "Kickoff" na Fase 1. Se choveem solicitações de mudança de escopo brutais na Fase 3, as "Perguntas Obrigatórias" não descobriram o núcleo do negócio. Punição retroativa de planejamento.

## 8. Perguntas de Validação
- Existe clareza matemática que a Mudança de Escopo sempre custa algo (seja em Qualidade, Tempo ou Cancelamento de outras Modificações Finais)? 

## 9. Checklist de Conformidade
- [ ] O Promp Master Inicial exigiu que a IA abra "Disputa de CR" sempre que o escopo tentar ser transmutado? (Sycophancy Mitigated)

## 10. Erros Comuns
- Dizer "É rápido, deixo eu fazer antes de almoçar". Esse é o "rápido" que consome as horas de testes automatizados depois por alterar layouts vitais. Nenhum código oculto passa sob o pano; todos assinam antes.
