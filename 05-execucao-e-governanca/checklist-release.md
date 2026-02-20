# 🚀 CHECKLIST RELEASE (SOP-IA)

## 1. O que é
A barreira final antes do código "atingir" os usuários reais. Enquanto o Pré-Merge testa o código isolado na branch, o Checklist de Release valida o pacote unificado em um ambiente similar a produção (Staging) garantindo que peças integradas não explodiram.

## 2. Por que existe
Deploys não devem ser "eventos de suor frio". Deploys sem Checklist costumam esquecer variáveis de ambiente, quebrar migrações de banco e não notificar o time de suporte sobre a nova funcionalidade. A IA é instruída a só engatilhar os scripts de Deploy/Build finais após o C-Level ou Tech Lead aprovarem isso.

## 3. Quando usar
A cada fim de Milestone/Sprint quando uma versão final (ex: V1.0) for ser comitada para os servidores públicos (AWS/Vercel) ou pacotes fechados (ZIP).

## 4. Como usar passo a passo
1. Trave o repositório (Code Freeze).
2. Execute a bateria completa de Testes Unitários e E2E.
3. Se verde, suba para Staging.
4. Execute o `plano-de-validacao.md`.
5. Preencha este checklist. Se tudo passar, assine e aperte o botão final (Production/Build).

## 5. Template Preenchível e Executável

```markdown
# Checklist de Release para V.[NÚMERO]

## 🏗️ Ambiente & Infra
- [ ] **Variáveis (ENVs):** As chaves de API do Gateway/Banco foram mudadas de "Sandbox/Mocks" para as de "Produção" reais?
- [ ] **Banco de Dados:** As `migrations` (Prisma/SQL) rodam liso no ambiente produtivo sem apagar tabelas clientes passadas?
- [ ] **Rollback:** Se a V1.x matar a interface, sabemos apertar o "Revert" para voltar para a V1.x-1 em menos de 10 minutos?

## 🛂 Funcionalidade & Qualidade
- [ ] Todos os Critérios de Aceite Mapeados estão como "Sucesso"? (Testes 100% Verdes / O Agente de QA não emite Warnings de Console).
- [ ] A Validação Fim-a-Fim foi executada pelo C-Level / Sponsor.

## 📢 Negócio e Suporte
- [ ] O manual de uso foi escrito na `docs/` e está alinhado com a feature nova entregue?
- [ ] A Notificação da Release (Release Notes/Changelog) foi enviado aos Stakeholders/Clientes?
```

## 6. Exemplos Reais
O Release Final do SPED exigiu a documentação completa no `README.md` orientando "Como instanciar com Vite e npm run dev" ANTES do commit `v1.0 (Clean)` aprovado pelo Stakeholder. O Checklist previu que deploys de IA poderiam apagar repositórios acidentalmente se os branches não estivessem isolados.

## 7. Métricas Associadas
- **Deploy Success Rate:** Número de Deploys limpos vs Número de Rollbacks urgentes por pânico (Downtimes).
- **Tempo Até Recuperação (MTTR):** Se falhar, e você marcou [X] na caixa de Rollback, é provado matematicamente que demora pouco.

## 8. Perguntas de Validação
- Seu Deploy depende de um Engenheiro "lembrar de apertar um botão no Cloudflare" que não está escrito aqui? (Se for manual, registre quem aperta e onde).

## 9. Checklist de Conformidade
- [ ] O Build Process Automático só termina se esses critérios checarem sucesso via Scripts?

## 10. Erros Comuns
- Testar no "Staging", mas esquecer de migrar a URL do Banco de Dados. O cliente entra na nova feature de Produção e o App continua chamando a API de Sandbox. Esse Checklist resolve isso primariamente.
