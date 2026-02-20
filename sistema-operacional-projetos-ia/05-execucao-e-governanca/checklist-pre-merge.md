# 🛑 CHECKLIST PRÉ-MERGE (SOP-IA)

## 1. O que é
É o pedágio obrigatório antes do código ir para a "Branch Principal" (Main/Master). Se o código não passa aqui, ele não existe.

## 2. Por que existe
Para proteger a base de código (e a empresa) de lixo gerado apressadamente. Inteligências Artificiais são ótimas em vomitar 5.000 linhas de código em 10 segundos, mas péssimas em garantir que as variáveis de ambiente de produção não foram "mockadas" por acidente.

## 3. Quando usar
A cada Pull Request (Ou a cada tentativa da IA de editar o branch core).

## 4. Como usar passo a passo
1. O criador do PR (Dev ou IA) revisa a própria obra usando o checklist.
2. O Tech Lead revisa a obra usando o M-E-S-M-O checklist.
3. Reprovações geram aprendizado instantâneo.

## 5. Template Preenchível (Modelo de PR)

```markdown
# Checklist Pré-Merge (Pull Request)

**Referência (Task/Critério):** [Ex: Ticket #12 ou Funcionalidade "Modal De-Para"]

## 🛡️ Defesa de Qualidade
- [ ] **Isolamento:** O código novo não quebrou features antigas? (Você testou ou "acha" que testou?)
- [ ] **Cobertura OBRIGATÓRIA:** Se você criou uma função matemática complexa, há pelo menos UM teste atrelado a ela na pasta `tests/`?
- [ ] **Logs Inúteis:** Todos os `console.log("chegou aqui")` de depuração estúpida foram removidos?
- [ ] **Escopo Oculto:** Há alguma lib nova (`npm i momentjs`) injetada aqui que não estava na Arquitetura inicial? Se sim, cadê o ADR de justificativa?
- [ ] **Artefatos:** Se você mudou lógica de negócios, a IA/Você lembrou de *atualizar a documentação viva* na pasta `/docs`?

**Assinatura Automática (IA):** Ao marcar essas caixas, atesto que cumpri as Três Leis do SOP-IA.
```

## 6. Exemplos Reais
O Pull Request final do Projeto "Automação SPED" foi rejeitado internamente na primeira passagem porque a Inteligência Artifical tinha adicionado chamadas a pacotes não-utilizados de backend no React. O Checklist apontou "Escopo Oculto (lib inútil)". O PR foi limpo antes do merge, salvando o peso do payload final.

## 7. Métricas Associadas
- **Densidade de Defeitos:** Número de reprovações neste checklist por Sprint (Alta Rejeição = IA/Dev não entende o Escopo Base).

## 8. Perguntas de Validação
- Seu CI/CD (`GitHub Actions`) exige que este checklist exista no *Body* da Pull Request para permitir o clique do botão verde de Merge? Se não, automatize isso no repositório.

## 9. Checklist de Conformidade
- [ ] Há evidência (print/vídeo) atrelada ao PR mostrando a feature rodando?

## 10. Erros Comuns
- Agentes de Bot (Dependabot) criando PRs sem critérios. Mesmo PRs automáticos de IA precisam ser avaliados por este crivo. Nunca confie cegamente em commits de pacotes não-supervisionados.
