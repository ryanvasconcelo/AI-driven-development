# RACI — MATRIZ DE RESPONSABILIDADES (SOP-IA v2.0)

## O que e
RACI e um modelo que define quatro tipos de envolvimento em cada atividade do projeto:
Responsavel (R), Aprovador (A), Consultado (C) e Informado (I). Elimina a ambiguidade
de quem faz o que, evitando tanto o vacio de ownership quanto o conflito por dupla
responsabilidade.

## Por que existe
Em times que alternam entre trabalho solo, duplas e squads, e comum que tarefas criticas
nao tenham dono claro. O resultado e ou retrabalho (duas pessoas fazem a mesma coisa)
ou negligencia (ninguem faz porque todos acharam que o outro faria).

## Nivel de Maturidade Minimo: 2
## Modo de Operacao: Dupla ou Squad (dispensavel em projetos solos)

## Aplicacao por Configuracao de Time

### Solo (1 dev)
Quando ha apenas um dev, o RACI e implicito: o dev e sempre R+A. A IA e C.
O Sponsor continua sendo A para decisoes de escopo e deploy em producao.

### Dupla (2 devs)
O RACI resolve: quem lidera o codigo (R) e quem lidera a documentacao e o deploy (A).
A rotacao entre tarefas deve ser explicitada ao inicio de cada Sprint.

### Squad (3+ devs)
O RACI formal deve ser preenchido para cada fase do projeto.

---

## Template RACI por Fase

```
R = Responsavel (executa)
A = Aprovador (tem a palavra final)
C = Consultado (opina, mas nao decide)
I = Informado (recebe o resultado)
```

| Atividade | Dev 1 | Dev 2 | Dev 3 | Sponsor | Agente IA |
|---|:---:|:---:|:---:|:---:|:---:|
| Definir objetivo do projeto | R | C | I | A | C |
| Escrever escopo e out-of-scope | R | C | I | A | C |
| Escrever criterios de aceite | R | R | I | C | C |
| Definir arquitetura | R | C | I | I | C |
| Codificacao de features | R | R | R | I | R |
| Revisao de Pull Request | C | R | C | I | C |
| Aprovacao de merge | A | R | C | I | — |
| Execucao de testes | R | R | R | I | R |
| Execucao de deploy | R | A | I | I | C |
| Aprovacao de release final | C | C | I | A | — |
| Abertura de Change Request | R | C | I | A | — |

## Legenda de Papeis (Projeto Solo com IA)

| Papel | Humano | Agente IA |
|---|---|---|
| Responsavel por execucao | Dev | Pode executar dentro dos limites definidos |
| Aprovador final | Dev ou Sponsor | Nunca pode ser o aprovador |
| Consultado tecnico | Dev, Tech Lead | Pode ser consultado |
| Informado | Sponsor | — |

## Erros Comuns
- Colocar a IA como Aprovador de qualquer atividade. A IA e sempre R ou C, nunca A.
- Deixar o papel de A vazio. Se nao ha aprovador definido, a tarefa nao tem dono final.
- Usar RACI para projetos solo onde ele e overhead desnecessario.
