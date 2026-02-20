# 🕵️ AUDITORIA DE PROJETO (SOP-IA)

## 1. O que é
O Check-up executivo pós-projeto ou pós-milestone. Uma inspeção crua e sem emoção para ver se o time (Humanos + IA) realmente seguiu as cartilhas do SOP-IA ou se cortaram caminho e esconderam dívida técnica debaixo do tapete.

## 2. Por que existe
Sem auditoria, o "Sistema Operacional" vira apenas "um monte de arquivos mortos na pasta docs" que ninguém lê. A auditoria garante que a Governança é real e que o Tech Lead/C-Level possa assinar a entrega tranquilamente.

## 3. Quando usar
Toda vez que uma Fase Grande for Concluída, antes de faturar o Projeto ao Cliente.

## 4. Como usar passo a passo
1. O Auditor (não pode ser a pessoa/IA que codou a funcionalidade atual) clona o repositório.
2. Abre este documento e verifica os logaritmos.
3. Reprova o projeto se houver Red Flags.

## 5. Template Preenchível

```markdown
# Auditoria de Projeto: [Nome]

**Data da Auditoria:** [DD/MM/AAAA]
**Auditor Responsável:** [Nome]
**Fase Auditada:** [Fase Final V1.0]

## 📋 Inspeção do Repositório (Governança SOP-IA)
- [ ] O `prompt-inicial-para-ia.md` está na raiz protegendo o uso do Agente? (Sim/Não)
- [ ] Existe algum arquivo grande modificado sem nenhum `ADR` cadastrado na docs/? (Issue: IA autônoma agindo sem documentar o racional).
- [ ] As `metricas-de-sucesso-template.md` mapeadas na Fase 2 foram batidas em Tela (Console, Vendas, Economia de Horas do Cliente)?
- [ ] O repositório central possui arquivos `lixo` sensíveis não incluídos no `gitignore` (ex: txts do cliente, `.env.local`)? (Red Flag!).
- [ ] Todos os Pull Requests foram abertos contendo Evidência Visual aprovada pela Definição de Pronto (`DoD`) do *06/definicao-de-pronto.md*?

## 🚨 Status da Auditoria
- [ ] **APROVADO:** O código e a governaça técnica estão em 100% de aderência ao Sistema SOP. O produto final é robusto.
- [ ] **Ressalvas (Fix Required):** Código aprovado mas artefatos documentais de `Arquitetura` estão desatualizados. Bloquear novo escopo até pagar essa Dívida Técnica.
- [ ] **REJEITADO CATASTROFICAMENTE:** IAs codaram escopo nulo. Features foram acopladas no App sem `Change Requests` e a arquitetura não suporta os "Critérios de Aceite". Mandar Retrabalhar.
```

## 6. Exemplos Reais
O Projeto Base SPED foi rejeitado em uma Auditoria rápida no meio de seu Sprint porque o Dev/IA incluiu um `.TXT de Receita Federal real` diretamente na árvore do GitHub. Isso furou completamente as Leis Anti-Chaos (Fase 8). Exigiu-se a remoção rigorosa (e do cache Git via Ignore) restabelecendo a Auditoria como ferramenta vital de Proteção de Dados.

## 7. Métricas Associadas
- **Score SOP-IA:** Grau Percentual do aderência do Projeto às metas de Planejamento (Quantas Pastas de `00 a 08` do Sistema Mestre não estão vazias?).
