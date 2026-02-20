# 🚧 ESCOPO DO PROJETO (SOP-IA)

## 1. O que é
A fronteira blindada do projeto. O escopo detalha o que o sistema *fará* e, criticamente, o que ele *não fará*. Ele traduz a Definição de Objetivo em funcionalidades macro.

## 2. Por que existe
Projetos sem escopo fechado sofrem de "Gold Plating" (adicionar enfeites desnecessários) e Feature Creep (adicionar recursos durante o desenvolvimento). Para a IA, um escopo frouxo gera alucinações de código, onde o agente adiciona bibliotecas e camadas de abstração não solicitadas.

## 3. Quando usar
Na Fase 02 (Definição Estratégica). Requer aprovação explícita antes do desenho da arquitetura. NENHUMA linha de código pode ser escrita sem que o desenvolvedor/IA concorde que a funcionalidade está listada aqui.

## 4. Como usar passo a passo
1. Divida a solução em Módulos/Épicos grandes.
2. Liste as Funcionalidades de cada módulo.
3. Crie a lista Inegociável de "O Que Fica de Fora".
4. Adicione como Regra de Sistema para a IA: "Leia o `escopo-template.md`. Se pedirem algo fora desta lista, exija a abertura de um ticket de Controle de Mudanças."

## 5. Template Preenchível

```markdown
# Escopo Fechado: [Nome do Projeto]

## 1. Módulos Inclusos (In-Scope)

### Módulo A: [Nome do Módulo]
- Funcionalidade A.1: [Descrição. Ex: Fazer upload de arquivos .txt até 500MB.]
- Funcionalidade A.2: [Descrição. Ex: Ler conteúdo no browser via FileReader API.]

### Módulo B: [Nome do Módulo]
- Funcionalidade B.1: [Ex: Processar blocos C170, C191 e C195 do EFD Contribuições.]
- Funcionalidade B.2: [Ex: Recalcular bases de PIS/COFINS de acordo com CFO.]

## 2. O Que Está Fora do Escopo (Out-of-Scope) 🚫
*Seja extremamente específico e cruel com funcionalidades "legais mas não vitais".*
- Não haverá login/autenticação de usuários nesta versão.
- Não haverá persistência de dados em banco de dados na nuvem (tudo local).
- Não haverá design responsivo para mobile (Foco 100% em tela de PC/Contador).
- Não faremos integração via API com a Receita Federal.

## 3. Critérios de Exceção
Se uma funcionalidade "Fora de Escopo" se mostrar crítica para o MVP devido a uma descoberta técnica tardia, o processo de `controle-de-mudancas.md` deve ser engatilhado e o Sponsor notificado. Nenhuma IA tem permissão para adicionar features não mapeadas proativamente.
```

## 6. Exemplos Reais
No SPED-PIS-COFINS, tentar hospedar 80MB de planilhas num backend Node criaria problemas terríveis de latência de rede e estouraria tempos de lambda em Vercel/AWS. O Item 2 do Escopo ("Não haverá DB na nuvem") forçou a arquitetura a baixar todo o JS e rodar a pesada máquina de análise estrita do Validador de NCMs completamente dentro do Chrome do cliente. O projeto foi concluído 3x mais rápido por causa desse limite.

## 7. Métricas Associadas
- **Desvio de Escopo (%):** O quanto o In-Scope mudou entre a Data Zero e o Deploy. Ideal = 0%.
- **Índice de "Nãos":** Quantas vezes o Arquiteto/Dev/IA disse "Isso está fora do escopo" durante a Sprint.

## 8. Perguntas de Validação
- Se um Dev Sênior mal-intencionado tentasse usar React, Vue e Angular juntos, o documento de Escopo barraria ele? (Se não barraria, detalhe mais o Escopo Técnico).
- Há espaço para o cliente interpretar "Geração de PDF" como "Inclusa" se dissemos "Geração de Relatórios"? Especifique os formatos.

## 9. Checklist de Conformidade
- [ ] O documento In-Scope é factível no tempo mapeado pelo Roadmap?
- [ ] O Out-of-Scope barra explicitamente as 3 funcionalidades mais prováveis de serem pedidas de surpresa?
- [ ] O arquivo está commitado e a IA tem acesso ao lido na inicialização?

## 10. Erros Comuns
- Escrever In-Scope muito genérico ("Melhorar UX"). "Melhorar UX" não pode ser codado. "Diminuir botões de 5 para 1" pode.
- Deletar a seção Out-of-Scope por medo de ofender o cliente. O Out-of-Scope é o seu escudo judicial e métrico.
