# quality

**Fase de Qualidade e Metricas**

A camada de prova. Define o que significa "pronto de verdade", mede o impacto real
do projeto e garante que o historico de projetos seja aprendizado, nao amnesia.

## Para que serve
Fecha o ciclo do projeto com evidencia. Sem esta pasta, o time sempre sabe o que fez
mas nunca sabe se funcionou. Com ela, cada projeto alimenta o proximo com dados reais.

## Quando executar
- `definition-of-done.md` — Fixar no inicio e usar em todo PR
- `kpis.md` — Atualizar ao fim de cada Sprint
- `audit.md` — Executar antes de cada Release maior
- `benchmarks.md` — Preencher ao fim de cada projeto

## Beneficios
- A Definition of Done elimina o "tá pronto" sem evidencia
- Os KPIs transformam velocidade de codigo em impacto de negocio mensuravel
- A auditoria revela divida tecnica antes que ela exploda em producao
- Os benchmarks constroem a memoria quantitativa da empresa: quanto tempo leva, quantos
  bugs saem, qual e o lead time medio — dados reais para estimar projetos futuros

## Criterio de Maturidade
Times no Nivel 3+ do Modelo de Maturidade possuem pelo menos 3 projetos registrados
em `benchmarks.md` com dados reais preenchidos.
