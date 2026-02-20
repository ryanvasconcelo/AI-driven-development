# 📈 MÉTRICAS DE SUCESSO OBRIGATÓRIAS (SOP-IA)

## 1. O que é
Um painel de instrumentos com exatamente 5 dimensões numéricas que definem se o projeto foi um sucesso ou um fracasso retumbante. 

## 2. Por que existe
Projetos sem métricas são declarados "sucesso" simplesmente porque foram entregues, mesmo que não gerem dinheiro, quebrem em produção ou destruam a moral do time. Se você não mede, você não gerencia.

## 3. Quando usar
Na Fase 02 (Definição Estratégica). As métricas devem ser preenchidas junto ao Escopo e aprovadas pelo Sponsor.

## 4. Como usar passo a passo
1. Reúna a equipe de negócio e técnica.
2. Defina 1 (uma) métrica principal para cada uma das 5 categorias obrigatórias.
3. Estabeleça o "Status Atual" (Baseline) e a "Meta" (Alvo).
4. Defina como a métrica será extraída (Instrumentação).

## 5. Template Preenchível

```markdown
# Painel de Controle: [Nome do Projeto]

### 1. Métrica de Impacto (O Negócio)
*Como isso afeta os ponteiros da empresa? (Receita, Custo, Tempo).*
- **Indicador:** [Ex: Horas gastas por mês fechando SPEDs]
- **Baseline (Atual):** 120 horas
- **Meta:** Menos de 5 horas.
- **Instrumentação:** Entrevista mensal com o analista sênior.

### 2. Métrica de Qualidade (O Produto)
*Como garantimos que o que entregamos é excelente?*
- **Indicador:** [Ex: Quantidade de Bugs Críticos vazados para Produção no 1º mês]
- **Baseline (Atual):** N/A
- **Meta:** 0 (Zero).
- **Instrumentação:** GitHub Issues / Jira.

### 3. Métrica de Prazo (A Execução)
*Estamos entregando como prometido?*
- **Indicador:** [Ex: Variância de Prazo da Release 1.0]
- **Baseline (Atual):** Data Alvo: 15/Dez
- **Meta:** +/- 10% de variação (Entre 13/Dez e 17/Dez).
- **Instrumentação:** Gráfico de Burndown / Trello.

### 4. Métrica de Risco (A Segurança/Infra)
*Como evitamos catástrofes irremediáveis?*
- **Indicador:** [Ex: Arquivos de clientes salvos em servidores externos]
- **Baseline (Atual):** N/A
- **Meta:** 0 (Plataforma deve ser 100% Client-Side).
- **Instrumentação:** Revisão de Arquitetura.

### 5. Métrica de Aprendizado (O Time/Processo)
*O que o time ou a IA aprendeu para o próximo projeto?*
- **Indicador:** [Ex: Componentes React reaproveitáveis criados]
- **Baseline (Atual):** 0
- **Meta:** 3 componentes adicionados ao Storybook/Design System da empresa.
- **Instrumentação:** Pull Requests merging para a branch de UI.
```

## 6. Exemplos Reais
Ao aplicar estas métricas no SPED-PIS-COFINS:
- **Impacto:** Transformar uma auditoria de 3 dias em 3 cliques.
- **Risco:** O contador *mataria* o projeto se as notas fiscais milionárias dos clientes fossem enviadas para um backend na AWS Cloud. A métrica de risco "0 uploads para nuvem" blindou a decisão arquitetônica de usar a FileReader API no navegador local.

## 7. Métricas Associadas
- **Clareza de Negócio:** % de Devs/IAs do time que sabem recitar a Métrica de Impacto de cor.

## 8. Perguntas de Validação
- Se batermos as metas de Prazo e Qualidade, mas zerarmos a Métrica de Impacto, o projeto valeu a pena? (Se a resposta for não, sua Métrica de Impacto está perfeita).

## 9. Checklist de Conformidade
- [ ] As 5 dimensões possuem um número-alvo (Meta)?
- [ ] O Sponsor concordou que a Métrica de Impacto reflete o ROIs (Return on Investment) esperado?

## 10. Erros Comuns
- "Nossa Métrica de Aprendizado é fazer código limpo". (Subjetivo). Transforme em "100% dos PRs devem ter zero avisos no ESLint".
- Medir "Story Points entregues" como Métrica de Impacto. Story points medem esforço (Custo), não Impacto (Receita/Economia).
