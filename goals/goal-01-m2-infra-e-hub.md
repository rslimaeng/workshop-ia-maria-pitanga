# Goal 01 · M2 — Infra + hub

**Status:** 🟢 concluída
**Onda anterior:** — (primeira onda estruturada)
**Onda seguinte:** `goal-02-m2-casos-1-a-4`

## Objetivo

Preparar a infraestrutura do projeto (contrato, goals, tokens) e o hub do M2, deixando pronto o esqueleto onde os 8 casos vão morar.

## Escopo desta onda

- [x] `CLAUDE.md` do repo com vocabulário, git rules, padrão visual, padrão de casos
- [x] `goals/README.md` — tabela de ondas
- [x] `goals/goal-01-m2-infra-e-hub.md` (este arquivo)
- [x] `_shared/design-tokens.md` — referência humana dos tokens do M1
- [x] `m2/index.html` — hub do M2 com:
  - Header + hero explicando o M2 ("Mão na Massa")
  - Intro curta sobre "8 casos pra praticar" no tom Rafael
  - Grid de 8 cards clicáveis (1 por caso), cada card com: número · título · áreas cobertas · tipo de artefato-alvo · link "abrir caso →"
  - Callout "Como usar" (baixar insumo, colar prompt no Kimi/DeepSeek/Claude, refinar 1-2 vezes)
  - Footer com assinatura Rafael
- [x] 8 pastas criadas em `m2/exemplos/` com `.gitkeep` — placeholder pras próximas ondas
- [x] Atualizar `index.html` da raiz: virar landing curta com M1 + M2 listados (antes era só redirect pra /m1/)
- [x] Commit + push
- [x] `curl -I` no hub retornou 200

## Casos que vão ser construídos nas próximas ondas

| # | Slug | Áreas | Artefato-alvo |
|---|---|---|---|
| 1 | `radar-reviews` | Lojas · Supervisão · CRM | Dashboard HTML com temas + heatmap loja×tema |
| 2 | `playbook-nova-unidade` | Franquia · Marketing · Operações | Documento executivo A4 · plano 90 dias |
| 3 | `health-check-loja` | Supervisão · Financeiro | Parecer consultoria com semáforo + top-3 alavancas |
| 4 | `comunicado-rede` | Marketing · RH · Compras | Comunicado A4 + versão WhatsApp + card visual |
| 5 | `treinamento-atendente` | RH · Fábrica · Lojas | Deck HTML 5 slides + apostila |
| 6 | `analise-vendas` | Financeiro · Compras · Supervisão | Parecer executivo padrão Mallory M3 + top-5 insights |
| 7 | `ficha-anvisa` | Fábrica · Marketing · Logística | Ficha ANVISA + copy social |
| 8 | `diagnostico-dor` | TI · qualquer | Plano de ação HTML tipo consultoria |

## Decisões que eu tomei sozinho

1. **Landing raiz virou landing pequena**, não redirect. Motivo: com 2 módulos no ar, não faz sentido puxar automaticamente pro M1. Landing lista os dois com cards clicáveis, mesma linguagem visual.
2. **Design tokens ficam replicados inline em cada HTML.** Motivo: single-file é mais portável (Rafael abre o `.html` sem servidor) e evita link relativo quebrado. `_shared/design-tokens.md` é referência humana, não CSS carregado.
3. **8 pastas com `.gitkeep`** pra o hub ter links funcionais desde o dia 1 (404 nas pastas ainda não construídas é aceitável — a nav do hub sinaliza "em breve" nos que ainda não têm `index.html`).

## Auditoria antes de fechar

- URL do hub: https://rslimaeng.github.io/workshop-ia-maria-pitanga/m2/
- URL da landing: https://rslimaeng.github.io/workshop-ia-maria-pitanga/
- Vocabulário oficial (Autopiloto/Colaboração/Manual) preservado no hub
- Nenhum "Copiloto/Automação/Agente" no hub
