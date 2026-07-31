# Goal 03 · M2 casos 5 a 8

**Onda:** 03
**Status:** 🟢 concluída
**Escopo:** completar os 4 casos restantes do M2 (5, 6, 7, 8) mantendo o padrão dos casos 1-4.

## O que entrega

### Caso 5 · treinamento-atendente (RH + Fábrica + Lojas)
- `insumo-manual-padrao-atendimento.docx` — manual v3.2 com os 6 momentos do atendimento MP + regras de higiene + cardápio âncora
- `prompt.md` — PCTFL+ com papel de head de treinamento sênior, tarefa em 3 blocos (deck 5 slides + apostila A4 + roteiro do supervisor)
- `index.html` — 5 steps, preview com deck 16:9 + apostila A4 + roteiro
- Personagem novo: Marina Torres (supervisora RH)

### Caso 6 · analise-vendas (Financeiro + Compras + Supervisão) ⚠️ VOLUME GRANDE
- `insumo-vendas-20-lojas-30-dias.xlsx` — **600 linhas** (20 lojas × 30 dias) em 3 abas (vendas diárias + dicionário de lojas + contexto qualitativo)
- Narrativa embutida nos números: 3 lojas subindo forte (MP002, MP007, MP014), 2 despencando (MP005, MP011), MP009 e MP019 sem cupuaçu (falha logística interior), MP020 com reforma 12-19/jul
- `prompt.md` — 778 linhas com toda a base inline, PCTFL+ pedindo parecer executivo estilo revista de negócios (HSM/HBR) em 6 blocos
- `index.html` — 5 steps, preview com capa de revista + big numbers + insights + ranking com barras

### Caso 7 · ficha-anvisa (Fábrica + Marketing + Logística)
- `insumo-briefing-novo-sorbet.docx` — brainstorm de P&D pro Sorbet Umbu-Cajá do Sertão (Cooperativa Sertão Vivo/Petrolina/PE)
- `prompt.md` — PCTFL+ com papel de nutricionista + regulatory affairs, tarefa em 3 blocos (ficha ANVISA RDC 429/2020 + post feed 1:1 + 3 stories 9:16)
- `index.html` — 5 steps, preview com ficha preto/branco oficial + post roxo/umbu + 3 stories verticais
- Regra de confidencialidade explícita: custos NÃO vão pras peças finais
- Personagens novos: Dra. Cristiane Aguiar (nutricionista), Cooperativa Sertão Vivo

### Caso 8 · diagnostico-dor (TI + qualquer área)
- `insumo-transcricao-conversa-time.docx` — transcrição Otter.ai realista de 42 min · 5 pessoas · 10 dores mapeadas (do backup crítico à autonomia técnica)
- `prompt.md` — PCTFL+ com papel de consultora de gestão de times técnicos, tarefa em 5 blocos (capa + dores catalogadas + matriz 2×2 + gantt 30d + 3 decisões executivas)
- `index.html` — 5 steps, preview com matriz 2×2 real (4 quadrantes com dores) + gantt de 4 semanas colorido por categoria
- Personagens novos: Ricardo Mendes (CTO), Fernanda Torres (líder dev), Bruno Kaique, Amanda Ribeiro, Diego Sá

## Ajustes globais

- Hub M2 (`m2/index.html`): 4 cards restantes de `data-status="in-progress"` → `data-status="ready"` (M2 100% completo)
- `goals/README.md`: onda 03 marcada como 🟢 concluída

## Decisões tomadas na execução

1. **Coerência de universo mantida**: nenhuma persona nova conflita com as anteriores. Bowl Cupuaçu Sertanejo do caso 4 aparece transversalmente (menções nos casos 5, 6, 7). Roberta (caso 3), Aline (caso 4), Jorge (caso 2) não foram forçados nos novos.
2. **Volume xlsx do caso 6**: 600 linhas com narrativa temporal real (perfis crescendo, despencando, cluster interior sem cupuaçu). Semente Python fixa (seed 42) pra determinismo — script pode ser re-executado.
3. **Ficha ANVISA (caso 7)**: mantida em preto/branco no mockup preview (é documento regulatório oficial — cor decorativa quebra credibilidade). Mockups sociais usam paleta MP + amarelo-umbu novo `#E5A932` só nesse caso.
4. **Matriz + gantt (caso 8)**: renderizados em CSS grid puro, sem SVG externo, sem Chart.js. Legenda visual embutida no gantt.
5. **Nav-bottom do caso 8**: aponta pra "Hub do Módulo 2" (não caso 9 — não existe). Fecha a jornada.

## Auditoria

- [x] 4 index.html sem quebra visível no browser
- [x] Insumos gerados: 1 xlsx (600 linhas) + 3 docx
- [x] Todos os prompt.md têm dados inline (funciona sem upload em Kimi/DeepSeek)
- [x] `data-status="ready"` em todos os 8 cards do hub
- [x] Vocabulário: Autopiloto/Colaboração/Manual mencionado nos steps 01 dos 4 casos novos
- [x] Fictício declarado em callout warn de todos os step 3
- [x] `.gitkeep` das 4 pastas será substituído pelos arquivos reais no commit

## Próxima onda (backlog)

- M3, M4, M5 (não planejados)
- `@media print` do M1 (dívida da onda anterior)
- Refresh do Google Forms (perguntas revisadas prontas em conversa anterior)
