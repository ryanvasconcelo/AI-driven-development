# 🚦 RISCOS E DEPENDÊNCIAS (SOP-IA)

## 1. O que é
Um mapa preventivo de tudo que pode explodir o projeto, atrasar o cronograma ou estourar o orçamento, classificando a probabilidade e o plano de mitigação ("Plano B") antes que o desastre ocorra.

## 2. Por que existe
Projetos de software não falham por surpresas; falham por riscos ignorados. A IA, por padrão, é otimista ("Eu consigo codar isso!"). Este artefato força o Engenheiro e a IA a adotarem uma postura pessimista e pragmática durante o design.

## 3. Quando usar
Na Fase 02 (Definição Estratégica), após definir o Escopo. Deve ser revisado mensalmente no `checklist-diario.md`.

## 4. Como usar passo a passo
1. Faça um brainstorming das piores coisas que podem acontecer.
2. Defina o Impacto (Baixo, Médio, Alto).
3. Defina a Probabilidade (Baixa, Média, Alta).
4. Escreva o Gatilho (Como saberemos que o risco virou problema?).
5. Escreva a Mitigação (O que faremos agora para evitar?) e a Contingência (O que faremos se explodir de vez?).

## 5. Template Preenchível

```markdown
# Matriz de Riscos: [Nome do Projeto]

### Risco 1: Limitação de Memória do Navegador
- **Descrição:** O cliente faz upload de arquivos SPED maiores que 2GB, causando o crash silencioso (SIGHUP OOM) na aba do Chrome.
- **Impacto:** ALTO (Inviabiliza o uso da ferramenta para grandes empresas).
- **Probabilidade:** MÉDIA (Comum no segmento de Varejo/Hipermercados).
- **Gatilho:** Arquivo TXT > 1.5GB detectado via FileReader no `App.jsx`.
- **Mitigação Preventiva:** Implementar leitura particionada por "Chunks" (`readAsBlob` chunking) ao invés do clássico `readAsText` integral no `sped-parser.js`.
- **Contingência (Se falhar):** Emitir um aviso Toast de erro dizendo "Arquivo acima de XX MB não suportado nesta versão Local", bloqueando a execução antes do crash e resetando a UI.

### Dependência 1: Aprovação do C-Level
- **Descrição:** A definição do "De-Para" de NCMs precisa ser aprovada pelo Controller fiscal, que está de férias até dia 15.
- **Impacto na Sprint:** MÉDIO (Trava a Fase 3 da interface gráfica).
- **Ação:** Iniciar pelo backend de cálculos e deixar a UI do "De-Para" com botões *mock* no Redux até a aprovação funcional da contabilidade.
```

## 6. Exemplos Reais
No SPED-PIS-COFINS, um risco documentado era a "lentidão na renderização de 40.000 div's na DOM causando o travamento do PC do contador". A Mitigação foi migrar precocemente para o framework `react-virtuoso` logo no Início da Sprint 2. Por ter sido mapeado na Fase 02, evitou-se refatorar toda a estrutura do `NcmGroupCard.jsx` quando a arquitetura já estivesse pronta.

## 7. Métricas Associadas
- **Materialização de Risco:** Quantidade de Riscos Altos mapeados que realmente ocorreram no projeto.
- **Taxa de Mitigação Excedida:** Quantas vezes o Plano de Contingência foi testado e também falhou.

## 8. Perguntas de Validação
- Se formos hackeados amanhã, temos contingência para perda dos dados?
- O que acontece se o Desenvolvedor Chefe/Sponsor ficar doente numa reta final? (Truck Factor mapeado).

## 9. Checklist de Conformidade
- [ ] O Risco 1 está ativamente endereçado com uma issue no Board/Commit inicial da arquitetura?
- [ ] A equipe de negócios aprovou os "cortes de escopo" sugeridos pelo plano de contingência?

## 10. Erros Comuns
- Confundir Riscos com Problemas Atuais. Risco é o que "pode" acontecer; Problema é o bug que "já" aconteceu.
- Escrever mitigação ingênua: "Pedir para o usuário não fazer upload grandes". Mitigação deve ser Sistêmica (bloqueado em código).
