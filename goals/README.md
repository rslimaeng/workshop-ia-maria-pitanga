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
| 06 | m5-diagnostico-canvas | 🟢 concluída | M5 single-page (6 seções): 6 gatilhos MP (Robô Humano · Tela em Branco · Detetive · Sparring · Tradutor · Olho Biônico) + Canvas MP interativo 5 blocos com localStorage + export TSV pra colar no Sheets do backlog da rede + compromisso 3 pontos |
| 07 | fix-m4-timeline-nav-mobile | 🟢 concluída | Fix pós-auditoria: timeline n8n do M4 (`flex-wrap:nowrap` + coluna no mobile) e nav lateral virando barra horizontal rolável abaixo de 900px |
| 08 | nav-modulos-e-copiar-prompt | 🟢 concluída | Nav voltar/próximo em M1 e M2 + fix dos links de M3/M4/M5 apontando pro módulo errado + botão "Copiar prompt" dos 8 casos M2 passa a copiar só o texto visível |
| 09 | m3-time-de-agentes | 🟢 concluída | Extra didático do M3: `exemplos/time-de-agentes/` com conceito em 8 seções + 3 times de exemplo (Conselho Consultivo 11 · Time de Marca 15 · Time de Produto Digital 8). Nada pra baixar — só o racional |

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
