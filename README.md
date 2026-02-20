# 🧠 Sistema Operacional de Projetos Orientados por IA (SOP-IA)

> Um framework mestre para garantir **qualidade, resultado e velocidade** em qualquer projeto de software desenvolvido com o apoio de Inteligência Artificial.

---

## 🎯 O que é este repositório

Este repositório contém o **SOP-IA** — um framework completo de governança para projetos de software guiados por IA. Foi construído a partir de aprendizados reais do projeto [`sped-pis-cofins`](https://github.com/ryanvasconcelo/sped-pis-cofins) e é aplicável a qualquer tipo de projeto: automação, dados, web, backend, RPA, produto digital.

---

## 📦 Como usar

**Opção 1 — Usar a pasta diretamente:**
Clone este repositório e copie a pasta `sistema-operacional-projetos-ia/` para a raiz do seu novo projeto.

**Opção 2 — Usar o ZIP:**
Baixe o arquivo `sistema-operacional-projetos-ia.zip` e extraia na raiz do seu repositório.

---

## 🗂 Estrutura do SOP-IA

```text
sistema-operacional-projetos-ia/
├── 00-guia-principal/          ← Comece aqui. Visão geral e roadmap de uso.
├── 01-inicio-do-projeto/       ← Kickoff, perguntas obrigatórias, acessos, prompt da IA.
├── 02-definicao-estrategica/   ← Escopo, critérios de aceite, métricas, riscos.
├── 03-planejamento-operacional/← Roadmap, sprints, testes e validação.
├── 04-arquitetura-e-organizacao/← Arquitetura, padrões de código, ADRs, estrutura de pastas.
├── 05-execucao-e-governanca/   ← Checklists diário, pré-merge, release e controle de mudanças.
├── 06-qualidade-e-metricas/    ← Definition of Done, KPIs e auditoria de projeto.
├── 07-exemplos-aplicados/      ← Case study real: projeto SPED-PIS-COFINS.
└── 08-anti-caos/               ← As 6 Leis Anti-Desvio e o Contrato de Compromisso.
```

---

## ⚡ As 3 Leis do SOP-IA para IAs

1. **Nunca gere código sem Critério de Aceite explícito.**
2. **Registre toda decisão arquitetural no ADR (docs vivos).**
3. **Impeça o Desvio de Escopo** — qualquer pedido fora do `escopo-template.md` exige um Change Request formal.

---

## 📚 Projeto de Referência

Este sistema foi extraído e generalizado do projeto:
**[ryanvasconcelo/sped-pis-cofins](https://github.com/ryanvasconcelo/sped-pis-cofins)**

Um app React/Vite local que automatiza a auditoria e correção de alíquotas PIS/COFINS em arquivos SPED EFD-Contribuições, processando 80.000+ registros sem banco de dados externo.
