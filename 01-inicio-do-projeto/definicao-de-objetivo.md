# 🎯 DEFINIÇÃO DE OBJETIVO (SOP-IA)

## 1. O que é
É a declaração singular de existência do projeto. Se o projeto fosse uma pessoa, esta seria sua missão de vida descrita em no máximo duas frases.

## 2. Por que existe
Para servir como "Filtro de Ouro". Qualquer nova ideia técnica, biblioteca, ou funcionalidade (Feature Creep) proposta pelo cliente ou sugerida pela IA deve ser testada contra este objetivo. Se não contribui diretamente para ele, é descartada ou posta em um backlog futuro.

## 3. Quando usar
Durante a Fase 01 (Início do Projeto). Deve ser o primeiro documento aprovado pelo C-Level/Stakeholder antes de se discutir arquitetura ou escopo técnico.

## 4. Como usar passo a passo
1. Entreviste o cliente: "Qual dor estamos resolvendo?".
2. Esboce 3 versões do objetivo.
3. Refine para a versão mais curta e pragmática possível.
4. Preencha o template abaixo.
5. Fixe este documento. Ele guiará conflitos de prioridade futuros.

## 5. Template Preenchível

```markdown
# Objetivo do Projeto: [Nome]

**A Dor (Problema):**
[Descreva o problema de negócio de forma quantificável. Ex: A equipe perde 40h mensais analisando planilhas fragmentadas.]

**O Remédio (A Solução):**
[Descreva o que será entregue. Ex: Uma automação que consolida os arquivos e gera um PDF gerencial diário.]

**O Impacto (Resultado Esperado):**
[Como saberemos que vencemos? Ex: Reduzir tempo de análise para zero e aumentar precisão para 100%.]

**A Bússola O que este projeto NÃO É:**
[Liste 1 ou 2 coisas óbvias que poderiam causar confusão. Ex: Não é um ERP financeiro completo.]
```

## 6. Exemplos Reais
**SPED-PIS-COFINS:**
- **Problema:** Contadores precisavam abrir TXTs de 50.000 linhas para alterar alíquotas cegamente antes de o validador expirar.
- **Solução:** Aplicativo web local e rápido que faz parse, agrupa e recalcula o SPED offline via browser.
- **Resultado:** Redução de dias de auditoria para 2 cliques.
- **O que NÃO é:** Não é integrador para SEFAZ. Não salva no servidor (100% Privacy Client-Side).

## 7. Métricas Associadas
- **Alinhamento do Time:** Todos devem ser capazes de recitar o Objetivo de cor.
- **Sobrevivência do Objetivo:** Se o objetivo muda durante o projeto, o projeto fracassou no planejamento.

## 8. Perguntas de Validação
- Se não fizermos NADA ALÉM de atingir este objetivo, o cliente ficará satisfeito e pagará?
- O objetivo menciona a tecnologia (ex: "Fazer em Python") em vez da solução de negócio? Se sim, reescreva. Tecnologia é meio, não fim.

## 9. Checklist de Conformidade
- [ ] O Objetivo cabe em um parágrafo longo ou dois curtos?
- [ ] Está escrito em linguagem de negócio (Dólares, Horas, Retenção, Risco) e não em linguagem técnica?
- [ ] Foi formalmente aceito pelos Stakeholders?

## 10. Erros Comuns
- **Objetivos Frankenstein:** Tentar resolver todos os problemas da empresa no "V1.0" do projeto.
- **Confundir Tecnologia com Objetivo:** "O objetivo é migrar para Kubernetes". Errado. O objetivo é "Atingir 99.99% de Uptime para suportar o pico da Black Friday". Kubernetes é a ferramenta.
