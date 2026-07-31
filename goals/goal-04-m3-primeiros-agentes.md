# Goal 04 · M3 Primeiros Agentes

**Onda:** 04
**Status:** 🟢 concluída
**Escopo:** construir o M3 completo — página principal do módulo + caso-âncora prático (Agente Relatório Semanal MP).

## Escopo fechado com Rafael pós-compact

- **"Agente" no vocabulário canônico** = assistente de ferramenta (Claude Projects, Gemini Gems, Custom GPTs) com system prompt + contexto redondos, executando tarefa padronizada. Complementa (não substitui) Autopiloto/Colaboração/Manual — encaixa como Autopiloto quando a tarefa é repetitiva.
- **Ferramenta em foco:** didático + Claude Projects. Foco no argumento "vale a pena a paga". Reconhecer que na gratuita dá pra "forçar a barra" colando system prompt + contexto a cada nova conversa.
- **Caso-âncora:** apresentação de resultado semanal (todo mundo na rede faz).
- **Persona do agente:** Head de Operações da Rede.
- **Insumo:** 1 loja nova (MP047 · Juazeiro do Norte/CE · Shopping Cariri Garden) · 4 semanas · ~50 vendas/dia · 2.946 linhas.

## O que entrega

### `m3/index.html` — single-page do módulo (7 seções)

1. **O que é um agente** — 6 cards (3 "é" + 3 "não é") + callout do modo Autopiloto
2. **Chat solto × agente pronto** — comparativo lado a lado (mesmo pedido, resultados diferentes)
3. **As 3 partes de todo agente** — Papel (Instructions) · Contexto (Knowledge) · Comando (chat)
4. **Onde monta na prática · Claude Projects** — mockup visual com 2 campos + chat de uso
5. **Caso-âncora MP** — case-card destacado com link pro caso completo
6. **Paga × gratuita** — dois planos comparados + argumento de ROI ("18h/mês")
7. **Seu primeiro agente** — 3 perguntas pra o aluno responder mentalmente + próximo passo

Padrão idêntico ao M1: layout 2 col (nav lateral sticky com scroll-spy + conteúdo), design system MP (creme `#F0EEE6` + roxo `#6B2E7A`), sem gradiente, sem dark mode.

### `m3/exemplos/agente-relatorio-semanal/` — caso-âncora prático

- `system-prompt.md` — Head de Operações MP, régua de qualidade, formato de saída em HTML, "antes de gerar confirme em 3 bullets"
- `contexto-modelo-relatorio.md` — modelo oficial do relatório em 6 blocos (capa · manchete · 3 big numbers · narrativa 3 parágrafos · 3 recomendações · rodapé) + estilo visual obrigatório
- `comando-de-uso.md` — 1 frase padrão + 4 variações + o que NÃO precisa dizer no comando
- `insumo-fechamento-semanal-mp047.xlsx` — 2.946 linhas item a item · 3 abas (`vendas`, `resumo-semanal`, `produtos`) · narrativa embutida:
  - S1 (06-12/jul): baseline · sem Cupuaçu
  - S2 (13-19/jul): Cupuaçu chegou 15/jul · vendas sobem 10%
  - S3 (20-26/jul): Cupuaçu vira top 2 · sáb 25/jul recorde Padre Cícero (+35% fluxo)
  - S4 (27/jul-02/ago): quarta 30/jul congelador fora 18h-20h (–28% no dia)
  - Faturamento total 4 semanas: **R$ 44.849**
- `index.html` — página do caso no padrão M2 (5 steps + preview do relatório final + comparativo chat vs agente)

## Ajustes globais

- `index.html` (landing raiz): card M3 mudou de `soon` → `ready` com nova copy
- `goals/README.md`: onda 04 marcada como 🟢 concluída
- `HANDOFF.md`: §10 atualizado com respostas de escopo + reescrita da estrutura final

## Decisões tomadas na execução

1. **Ferramenta demo:** apenas Claude Projects (não Gemini Gems nem Custom GPTs), com menção lateral. Mantém foco.
2. **Persona escolhida:** Head de Operações da Rede (não Analista de BI nem Braço direito do gerente). Alinha com o parecer executivo do caso 6 e cria continuidade M2→M3.
3. **Loja nova (MP047):** fora do universo do caso 6 (que já usa MP001-MP020). Cidade Juazeiro do Norte/CE existe; Shopping Cariri Garden é fictício. Coerência universo mantida (Cupuaçu Sertanejo do caso 4 aparece transversalmente).
4. **Volume xlsx:** 2.946 linhas item a item (não 50 linhas de vendas/dia agregadas). Rafael pediu granularidade real de operação de loja. Semente Python fixa `seed(42)` pra determinismo.
5. **Modo do M3 = Autopiloto** (não Colaboração como no M2). Coerente com "tarefa repetitiva, formato padronizado, risco baixo".
6. **Argumento ROI incluído** (~18h/mês economia com 1 supervisor + 5 gerentes) pra munir o aluno de conversa com liderança sobre o custo do plano pago.
7. **Nav bottom:** aponta pra M2 (módulo anterior) e pro caso-âncora (próximo passo prático) — não pra M4 que ainda não existe.

## Auditoria

- [x] Landing atualizada: card M3 = `ready`
- [x] Single-page M3 abre sem erro no browser (auditado via hook PostToolUse)
- [x] Página do caso abre sem erro no browser (auditado via hook PostToolUse)
- [x] 4 arquivos do caso baixáveis pelos links do step 3
- [x] Vocabulário: Autopiloto mencionado explicitamente na seção 1 (callout) e no caso (step 1)
- [x] Fictício declarado em callout warn (step 3 do caso)
- [x] Nav lateral com scroll-spy funcional (script portado do M1)

## Próxima onda (backlog)

- M4 · Automação na Prática (n8n)
- M5 · Mini-Diagnóstico e Plano
- `@media print` de algumas páginas
- Material pré-treinamento
- Refresh do Google Forms
