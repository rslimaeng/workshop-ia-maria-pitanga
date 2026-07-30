# Goal 02 · M2 — Casos 1 a 4

**Status:** 🟢 concluída
**Onda anterior:** `goal-01-m2-infra-e-hub`
**Onda seguinte:** `goal-03-m2-casos-5-a-8`

## Objetivo

Construir os 4 primeiros casos práticos do M2, cada um seguindo o formato
Claude use case (5 passos didáticos: task · context · insumo · prompt · resultado)
com insumo docx/xlsx realista e prompt PCTFL+ autocontido.

## Entregas

| # | Slug | Insumo | Prompt | Página |
|---|---|---|---|---|
| 1 | `radar-reviews` | `insumo-reviews-5-lojas.xlsx` (30 reviews, 5 lojas, 6 colunas) | 68 linhas PCTFL+ com dados inline | index.html com preview de dashboard + heatmap |
| 2 | `playbook-nova-unidade` | `insumo-briefing-nova-unidade.docx` (5 blocos: praça, franqueado, público, expectativas, pedido) | 132 linhas com briefing colado | index.html com preview de doc executivo A4 |
| 3 | `health-check-loja` | `insumo-health-check-iguatemi.xlsx` (2 abas: 10 métricas + benchmark, 7 eventos qualitativos) | 148 linhas com dados inline | index.html com preview de parecer com semáforo + dimensões |
| 4 | `comunicado-rede` | `insumo-briefing-nova-receita.docx` (5 blocos: produto, por que agora, o que muda, cronograma, pedido) | 138 linhas com briefing inline | index.html com preview das 3 peças (e-mail + WhatsApp + card) |

## Decisões que eu tomei sozinho

1. **Prompts contêm os dados inline no final** — Kimi/DeepSeek gratuitos nem sempre aceitam upload de xlsx/docx. Solução: prompt.md é 100% autocontido, funciona colando em qualquer chat. O xlsx/docx serve como "olha, é o formato do sistema real" — dá pra abrir em paralelo pra ver estruturado.
2. **Preview visual do resultado em cada `step 5`** — Ao invés de descrever o artefato-alvo em texto, cada página tem um mini-mockup HTML/CSS do que a IA vai gerar. Facilita o aluno visualizar antes de rodar.
3. **Callout "Nomes são fictícios" em cada caso** — Legal reforçar em cada página pra ninguém confundir com dados reais da rede (Roberta, Jorge, Aline, @larissasertanejo — inventados).
4. **Dados coerentes entre casos** — o Bowl Cupuaçu Sertanejo do caso 4 é o mesmo que aparece nos reviews do caso 1 (elogios) e no health-check do caso 3 (esgotando estoque). Cria universo Maria Pitanga consistente que reforça a sensação de rede real.
5. **Chip "Em breve" dos 4 cards no hub removido** — atributo `data-status="in-progress"` trocado por `"ready"`. CSS já esconde o chip quando `ready`.

## Auditoria

- Todas as 4 pastas: `insumo.{xlsx,docx}` + `prompt.md` + `index.html` presentes
- Vocabulário oficial (Autopiloto/Colaboração/Manual) usado nos step 1 de cada caso
- "Copiloto/Automação/Agente" não vazou pra nenhum caso
- Nomes de pessoas físicas e valores em todos os insumos são fictícios
- URLs finais devem retornar 200 após deploy:
  - `/m2/exemplos/radar-reviews/`
  - `/m2/exemplos/playbook-nova-unidade/`
  - `/m2/exemplos/health-check-loja/`
  - `/m2/exemplos/comunicado-rede/`

## O que a Onda 3 vai entregar

Casos 5-8: treinamento-atendente · analise-vendas · ficha-anvisa · diagnostico-dor.
Mesmo padrão: pasta com insumo + prompt.md + index.html no template de 5 passos.
