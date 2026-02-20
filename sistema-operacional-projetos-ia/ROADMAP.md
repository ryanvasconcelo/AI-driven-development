# ROADMAP — SOP-IA

Este documento registra o que está planejado para as próximas versões do framework, o que está em avaliação, e o que foi descartado com justificativa. O ROADMAP é revisado ao fim de cada projeto que usa o SOP-IA.

**Última revisão:** 2026-02-20
**Responsável:** Ryan Vasconcelo

---

## Versão Atual: v2.0.0

Lançada em 2026-02-20. Foco em maturidade enterprise: modelo de maturidade em 5 níveis, RACI formal, limites da IA, matriz de rastreabilidade, guia de deploy anti-falha, protocolo de escalação, modos de operação Startup e Enterprise.

Histórico detalhado em [`CHANGELOG.md`](./CHANGELOG.md).

---

## v2.1.0 — Biblioteca de Case Studies (Planejado)

**Objetivo:** Transformar a pasta `case-studies/` em uma biblioteca real com pelo menos 3 projetos documentados de tipos diferentes, cobrindo diferentes stacks, tamanhos de time e graus de complexidade.

**Motivação:** O único caso documentado atualmente é o SPED-PIS-COFINS — um projeto Client-Side, solo, de alta velocidade. Isso deixa sem referência times que trabalham em projetos com backend, banco de dados, múltiplos devs ou ciclos mais longos.

**Artefatos Planejados:**
- `case-studies/automacao-rpa.md` — Projeto de automação de processo interno com RPA, ilustrando uso do framework em contexto sem interface visual
- `case-studies/api-backend.md` — Projeto com API REST, banco de dados e deploy em nuvem, ilustrando o guia de deploy e a matriz de rastreabilidade em contexto real
- `case-studies/produto-digital-squad.md` — Projeto desenvolvido por squad de 3+ devs, ilustrando RACI, protocolo de escalação e modo Enterprise em operação

**Critério de Aceite:**
Cada case study deve conter os artefatos reais preenchidos (não templates vazios), incluindo as métricas de impacto realizadas e as lições aprendidas registradas em `quality/benchmarks.md`.

**Status:** Aguardando conclusão de projetos em andamento para extração dos artefatos reais.

---

## v2.2.0 — Automação de Scaffold (Planejado)

**Objetivo:** Criar um script de inicialização que gera automaticamente a estrutura de pastas e arquivos do SOP-IA na raiz de um novo repositório, com prompts interativos para preencher as variáveis básicas (nome do projeto, Sponsor, stack presumida).

**Motivação:** Atualmente, adotar o framework exige copiar manualmente a pasta `sistema-operacional-projetos-ia/` ou extrair o ZIP. Isso cria fricção de adoção, especialmente em times que iniciam projetos rapidamente.

**Abordagem Avaliada:**
```bash
npx sop-ia init
# ou
bash scaffold.sh "Nome do Projeto" "Nome do Sponsor"
```

O script geraria apenas os artefatos obrigatórios do Modo Startup por padrão, com flag `--enterprise` para gerar o conjunto completo.

**Critério de Aceite:**
Um dev sem conhecimento prévio do framework consegue inicializar um projeto com os 3 artefatos mínimos preenchidos em menos de 10 minutos usando apenas o script.

**Status:** Em avaliação de viabilidade. Dependente da v2.1.0 estar estável.

---

## v3.0.0 — Interface Web (Visão de Produto)

**Objetivo:** Transformar o SOP-IA de um repositório de Markdown em uma aplicação web que guia o time pelo framework de forma interativa, com formulários estruturados, geração automática de artefatos e dashboard de saúde do projeto.

**O que seria diferente de um Jira ou Notion:**
O SOP-IA web não seria uma ferramenta genérica de gestão de tarefas. Seria uma interface opinionada que força o processo correto — impossível pular a fase de escopo sem preencher o objetivo, impossível criar tarefa sem critério de aceite, impossível declarar pronto sem os itens do DoD marcados.

**Funcionalidades Prioritárias (ICE Score):**

| Feature | Impacto | Confiança | Facilidade | Score |
|---|:---:|:---:|:---:|:---:|
| Formulário de Kickoff com geração de artefato | 10 | 8 | 6 | 4.8 |
| Dashboard de saúde do projeto (artefatos preenchidos %) | 9 | 7 | 7 | 4.4 |
| Geração do prompt mestre para IA a partir do kickoff | 9 | 9 | 5 | 4.0 |
| Histórico de benchmarks entre projetos | 8 | 8 | 6 | 3.8 |
| Controle de Change Requests com aprovação | 7 | 7 | 5 | 2.5 |

**Stack Avaliada:** Next.js + banco local (SQLite via Prisma) para MVP — sem dependência de nuvem, alinhado com o princípio de dado local do próprio framework.

**Critério para Iniciar v3.0.0:**
- v2.1.0 lançada e estável
- Pelo menos 5 projetos internos completados usando v2.x (base de aprendizado real)
- Validação com ao menos 2 usuários não-desenvolvedores (o Sponsor deve conseguir ler o dashboard sem explicação)

**Status:** Visão de produto aprovada. Implementação condicionada aos critérios acima.

---

## Em Avaliação (Sem Versão Definida)

### Integração com GitHub Actions
Automatizar a coleta de métricas de KPI (bugs, lead time, Change Requests) diretamente do repositório via GitHub Actions, eliminando a necessidade de preenchimento manual do `quality/benchmarks.md`.

**Bloqueador:** Requer padronização dos labels e milestones do GitHub em todos os projetos que usam o SOP-IA. Ainda não há massa crítica de projetos suficiente para validar o padrão.

### Templates por Domínio
Versões especializadas dos artefatos para domínios específicos: fiscal/contábil, RPA, produto B2B, automação interna. Os templates atuais são genéricos por design, mas há evidência de que times perdem tempo adaptando exemplos de SPED para contextos muito diferentes.

**Decisão pendente:** Avaliar se a especialização gera valor real ou apenas aumenta o custo de manutenção do framework sem benefício proporcional.

---

## Descartado (Com Justificativa)

### Integração com Notion ou Confluence
**Motivo do descarte:** Cria dependência de ferramenta externa proprietária e contradiz o princípio de portabilidade do framework. Markdown em Git é acessível, versionável e funciona offline. Notion não.

### Suporte a múltiplos idiomas
**Motivo do descarte:** O custo de manutenção de versões paralelas em inglês e espanhol superaria o benefício para o contexto atual de uso do framework (times brasileiros). Revisável se o SOP-IA for adotado por times internacionais.

### Templates em formato DOCX ou PDF estático
**Motivo do descarte:** Arquivos binários não são versionáveis com Git de forma legível. A rastreabilidade de mudanças nos artefatos é um princípio do framework — não pode ser comprometida por conveniência de formato.

---

## Como Sugerir Itens para o ROADMAP

Abra uma Issue no repositório com o template abaixo:

```markdown
## Proposta de Roadmap

**Funcionalidade:** [Nome curto]
**Problema que resolve:** [Descreva a dor real, com exemplo de projeto]
**Alternativas consideradas:** [O que você tentou antes de propor isso]
**Impacto esperado (ICE):** Impact [1-10] / Confidence [1-10] / Ease [1-10]
**Você validou isso em um projeto real?** Sim / Não — [se sim, qual projeto]
```

Propostas sem evidência de uso real são registradas mas não recebem compromisso de prazo.
