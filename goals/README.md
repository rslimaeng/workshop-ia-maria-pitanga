# Goals · Workshop IA Maria Pitanga

Fonte única do estado do projeto. Antes de qualquer nova onda: ler esta tabela + o goal da onda anterior.

## Tabela de ondas

| # | Slug | Status | O que entrega |
|---|---|---|---|
| 01 | m2-infra-e-hub | 🟢 concluída | CLAUDE.md, goals/, _shared/, hub M2 (`m2/index.html`), 8 pastas em `exemplos/`, landing raiz |
| 02 | m2-casos-1-a-4 | 🟢 concluída | radar-reviews · playbook-nova-unidade · health-check-loja · comunicado-rede |
| 03 | m2-casos-5-a-8 | 🟢 concluída | treinamento-atendente · analise-vendas · ficha-anvisa · diagnostico-dor |
| 04 | m3-primeiros-agentes | 🟢 concluída | M3 single-page (7 seções) + caso-âncora `agente-relatorio-semanal` (4 arquivos: system prompt, contexto, comando, xlsx 4 semanas 2.946 linhas) |
| 05 | m4-automacao-cowork-n8n | 🟢 concluída | M4 single-page (8 seções): Cowork × n8n em paralelo, framework Gatilho→Execução→Entrega, matriz de escolha, 2 cards de case pra demo ao vivo do Rafael (Cowork organiza pasta + n8n triagem CV) |

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
