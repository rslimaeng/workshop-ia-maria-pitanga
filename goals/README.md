# Goals · Workshop IA Maria Pitanga

Fonte única do estado do projeto. Antes de qualquer nova onda: ler esta tabela + o goal da onda anterior.

## Tabela de ondas

| # | Slug | Status | O que entrega |
|---|---|---|---|
| 01 | m2-infra-e-hub | 🟢 concluída | CLAUDE.md, goals/, _shared/, hub M2 (`m2/index.html`), 8 pastas em `exemplos/`, landing raiz |
| 02 | m2-casos-1-a-4 | ⏳ próxima | radar-reviews · playbook-nova-unidade · health-check-loja · comunicado-rede |
| 03 | m2-casos-5-a-8 | ⏳ | treinamento-atendente · analise-vendas · ficha-anvisa · diagnostico-dor |

## Convenções

- **1 onda = 1 número.** Sem sufixos `a/b/v2/final`
- Nome do arquivo: `goal-{NN}-{slug}.md` (NN com 2 dígitos)
- Se a onda precisa ser refeita **antes de rodar:** editar o arquivo, não criar nova versão
- Se precisa complementar **depois de rodar:** nova onda com número seguinte

## Auditoria antes de fechar onda

- [ ] `curl -I` da URL final retornou 200
- [ ] `grep` confirma vocabulário oficial (Autopiloto/Colaboração/Manual) nos arquivos alterados
- [ ] `grep` confirma que "Copiloto/Automação/Agente" só aparece no callout De/Para do M1 (não vazou pra outros módulos)
- [ ] Nenhum arquivo alterado fora do escopo do goal
- [ ] Commits em nome de Rafael Lima
- [ ] `.nojekyll` presente na raiz do repo
- [ ] Se criou insumo mock: é fictício (não vazou dado real)
