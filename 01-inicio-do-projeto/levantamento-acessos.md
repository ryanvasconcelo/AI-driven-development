# 🔑 LEVANTAMENTO DE ACESSOS E CREDENCIAIS (SOP-IA)

## 1. O que é
A matriz centralizada que consolida tudo o que o desenvolvedor/IA precisa para começar a construir a solução tecnicamente, sem ficar travado ("blocker").

## 2. Por que existe
Oma das maiores causas de *Time-to-Market* lento (Sprints falhas) é o time de engenharia ficar parado esperando um token de API, um acesso VPN ou permissão em banco de dados que demora 3 semanas para ser aprovado pelas áreas de TI/Segurança. 

Ao mapeá-los no dia zero do projeto, toda a parte burocrática corre em paralelo.

## 3. Quando usar
Logo após a Definição de Objetivo (Fase 1). 

## 4. Como usar passo a passo
1. Liste cada ator sistêmico.
2. Determine que tipo de chave/credencial é exigida.
3. Peça e registre as datas ("esperando aprovação desde...").
4. Para a IA: Forneça um mock/stub dos dados até que a credencial real chegue. Nunca deixe a engenharia parar por falta do token real.

## 5. Template Preenchível

```markdown
| Sistema/API | Tipo de Acesso (Token, Senha, VPN) | Ambiente | Responsável por Prover | Status do Acesso | Data de Recebimento Estimada | E-mail Aprovador |
| :--- | :---: | :---: | :--- | :---: | :---: | :--- |
| Ex: Gateway de PGTO | OAuth2 Secret Key | Sandbox | Maria (Financeiro) | Pendente | 25/Nov | maria@empresa.com |
| Ex: Banco de Dados | String Conexão Leitura | Prod | João (DBA) | APROVADO | 20/Nov | joao.dba@empresa |
| Ex: Conta GitHub | Convite Orgs | - | Admin GitHub | APROVADO | 19/Nov | admin@empresa |
```

## 6. Exemplos Reais
O SPED-PIS-COFINS teve **NENHUM** requisito de acesso externo para DBs, justamente porque o SOP revelou nas *Perguntas Obrigatórias* que os dados não subiriam pra nuvem. 
Mas em projetos de Automação de RH da mesma empresa, foi mapeado que seria necessário a API da Gupy. Identificou-se que demoraria 7 dias para a Gupy liberar, logo a IA começou programando com mocks offline para não perder a sprint.

## 7. Métricas Associadas
- **Lead Time de Infra:** Quantidade de dias média gastos apenas esperando acessos para codar.
- **Sprint Success Rate:** Impactado pelo atraso burocrático.

## 8. Perguntas de Validação
- Há alguma feature planejada que exige comunicação com o mundo externo (APIs) que não está na tabela?
- Há senhas de produção escritas neste documento? *(ERRO GRAVE. Nunca guarde credenciais literais no Git. Use um .env remoto ou cofre de senhas (Bitwarden/1Password) e apenas liste o STATUS aqui)*.

## 9. Checklist de Conformidade
- [ ] O status de toda a matriz está "Aprovado" antes da primeira Sprint de Engenharia?
- [ ] As credenciais "hard" estão salvas em cofres seguros e não comitadas?

## 10. Erros Comuns
- Confiar que "o cliente vai mandar a senha por zap, tá tranquilo". Isso desalinha a comunicação com a equipe distribuída ou a IA do projeto que precisa saber *exatamente* de onde extrair a Connection String.
