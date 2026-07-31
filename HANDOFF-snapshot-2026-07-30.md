# Handoff · Workshop IA Maria Pitanga

> Estado do projeto em 2026-07-30 — snapshot pra sobreviver ao `/compact`.
> Rafael + Claude (chat) estão executando um M2 grande em 3 ondas. Aqui está tudo que a próxima sessão precisa saber pra continuar sem alucinar.

---

## 1. Contexto do treinamento

- **Cliente:** Rede Maria Pitanga Açaí & Gelatos (+200 franquias BR + Portugal + Espanha)
- **Instrutor:** Rafael Lima ([@iacomrafael](https://www.instagram.com/iacomrafael/))
- **Formato:** 1 workshop presencial · **4h** · sábado
- **Turma:** 24 pessoas, 8 áreas (Fábrica, Logística, Lojas/Supervisão, TI, CRM, Marketing, RH, Financeiro, Compras)
- **Ferramenta em sala:** Kimi (moonshot.cn) + DeepSeek grátis pros alunos, Claude Pro do Rafael pra mostrar o degrau
- **Ementa vendida:** 5 módulos, fio condutor triagem de currículos (M1: IA Sem Mistério · M2: Mão na Massa · M3: Primeiro Agente · M4: Automação · M5: Diagnóstico + Plano)

## 2. Estrutura de arquivos

```
maria-pitanga-issac/
├── HANDOFF.md                              ← este arquivo (fonte da verdade)
├── briefing-maria-pitanga.md               ← briefing institucional
├── Ementa - Workshop IA - ....docx         ← ementa vendida
├── pagina-de-exemplos/                     ← dumps do Claude use cases (design ref)
├── prints-forms/                           ← 4 prints do Google Forms atual
└── workshop-ia-mp/                         ← REPO GIT (published)
    ├── CLAUDE.md                           ← contrato do repo
    ├── README.md  .nojekyll  .gitignore
    ├── index.html                          ← landing com M1 e M2
    ├── _shared/design-tokens.md            ← referência dos tokens do M1
    ├── goals/                              ← 1 arquivo .md por onda
    │   ├── README.md                       ← tabela de ondas (rodando · próxima · concluídas)
    │   ├── goal-01-m2-infra-e-hub.md       ← 🟢 concluída
    │   ├── goal-02-m2-casos-1-a-4.md       ← 🟢 concluída
    │   └── (goal-03-m2-casos-5-a-8.md)     ← ⏳ a criar na próxima sessão
    ├── m1/index.html                       ← M1 completo (1117+ linhas, 10 seções)
    └── m2/
        ├── index.html                      ← hub com grid dos 8 casos
        └── exemplos/
            ├── radar-reviews/              ← 🟢 caso 1
            ├── playbook-nova-unidade/      ← 🟢 caso 2
            ├── health-check-loja/          ← 🟢 caso 3
            ├── comunicado-rede/            ← 🟢 caso 4
            ├── treinamento-atendente/      ← ⏳ caso 5 (.gitkeep)
            ├── analise-vendas/             ← ⏳ caso 6 (.gitkeep)
            ├── ficha-anvisa/               ← ⏳ caso 7 (.gitkeep)
            └── diagnostico-dor/            ← ⏳ caso 8 (.gitkeep)
```

**Repo público:** https://github.com/rslimaeng/workshop-ia-maria-pitanga
**Landing:** https://rslimaeng.github.io/workshop-ia-maria-pitanga/
**Hub M2:** https://rslimaeng.github.io/workshop-ia-maria-pitanga/m2/

## 3. Estado exato agora (2026-07-30)

- **Onda 01** — Infra + hub M2 · 🟢 concluída · commit `7d69aec`
- **Onda 02** — Casos 1 a 4 · 🟢 concluída · commit `1688a38`
- **Volume upgrade da Onda 02** — 🟢 concluída · commit `f8055ff` (subiu volume dos xlsx: caso 1 de 30 pra 150 reviews · caso 3 ganhou aba 3 série diária 31×9)
- **Onda 03** — Casos 5 a 8 · ⏳ **PRÓXIMA A EXECUTAR**

Último commit no ar: **`f8055ff`** em `main`.

## 4. Decisões travadas (não mexer sem OK do Rafael)

### 4.1 Vocabulário oficial
- **Autopiloto · Colaboração · Manual** (não "Copiloto · Automação · Agente" da ementa vendida)
- No M1, tem callout De/Para explícito mostrando a equivalência
- Nos outros módulos, só o canônico

### 4.2 Base visual
- **Paleta:** creme `#F0EEE6` fundo, roxo Açaí `#6B2E7A` accent, sombras suaves
- **Tipografia:** Inter (corpo) + JetBrains Mono (kicker/meta) via Google Fonts CDN
- **Regra dura:** sem dark mode, sem gradients, sem border-left grossa colorida em card/callout (usar fundo tingido + dot 6px via `::before` no título)
- Tokens replicados inline em cada HTML (single-file portable)

### 4.3 Padrão de casos práticos M2 (Mallory M5 adaptado)
- **Hub** (`m2/index.html`) com grid de 8 cards
- **Cada caso** em `m2/exemplos/<slug>/`:
  - `index.html` — formato Claude use case (5 passos: task · context · insumo · prompt · resultado)
  - `insumo.xlsx` OU `insumo.docx` (Rafael pediu: **nada de txt/csv**)
  - `prompt.md` — pronto pra copiar (autocontido, dados inline)

### 4.4 Ferramenta em sala (afeta prompts)
- Kimi/DeepSeek gratuitos + Claude Pro do Rafael
- Por isso: `prompt.md` sempre autocontido (dados inline no final), pra funcionar em qualquer chat sem upload
- Aluno também pode fazer upload do xlsx/docx direto — os 2 caminhos funcionam

### 4.5 Volume nos xlsx (decisão nova, 30/jul)
Rafael pediu "mais linhas pra efeito uau real":
- **Caso 1 radar-reviews:** 150 reviews (30/loja × 5 lojas)
- **Caso 3 health-check:** aba 3 "Série diária" 31 linhas × 9 colunas (com narrativa embutida)
- **Caso 6 analise-vendas** (Onda 3): já nascer com **20 lojas × 30 dias = 600 linhas**
- Docx dos casos 2, 4, 5, 7, 8 fica como está (documento sequencial não agrega volume)

## 5. Os 8 casos do M2 (universo Maria Pitanga coerente)

| # | Slug | Áreas | Insumo | Artefato-alvo | Status |
|---|---|---|---|---|---|
| 1 | `radar-reviews` | Lojas · Supervisão · CRM | xlsx 150 reviews Google Maps 5 lojas | Dashboard HTML com temas + heatmap loja×tema | 🟢 |
| 2 | `playbook-nova-unidade` | Franquia · Marketing · Operações | docx briefing 1 pág Petrolina/PE | Playbook A4 executivo · plano 90 dias | 🟢 |
| 3 | `health-check-loja` | Supervisão · Financeiro | xlsx 3 abas (métricas + contexto + série diária 31d) | Parecer consultoria com semáforo + top-3 alavancas + gráfico tendência | 🟢 |
| 4 | `comunicado-rede` | Marketing · RH · Compras | docx briefing lançamento Bowl Cupuaçu | Kit 3 peças (e-mail A4 + WhatsApp + card visual) | 🟢 |
| 5 | `treinamento-atendente` | RH · Fábrica · Lojas | docx manual de padrão (a criar) | Deck HTML 5 slides + apostila do aluno | ⏳ |
| 6 | `analise-vendas` | Financeiro · Compras · Supervisão | xlsx 20 lojas × 30 dias (600 linhas) | Parecer executivo estilo revista de negócios + top-5 insights | ⏳ |
| 7 | `ficha-anvisa` | Fábrica · Marketing · Logística | docx descrição livre novo sorbet (a criar) | Ficha ANVISA + tabela nutricional + copy Instagram | ⏳ |
| 8 | `diagnostico-dor` | TI · qualquer | docx transcrição conversa time (a criar) | Plano ação HTML com matriz impacto×esforço + timeline | ⏳ |

### Coerência entre casos (universo MP consistente)
O **Bowl Cupuaçu Sertanejo** do caso 4 é o mesmo que:
- Aparece nos reviews positivos do caso 1 ("bowl novo salvou minha experiência")
- Aparece no health check do caso 3 ("Cupuaçu esgota toda tarde, sorbet manga sobra")
- **Casos 5-8 devem manter esse universo** (Roberta gerente Iguatemi, atendente Bruno de Sobral, cooperativa Tomé-Açu/PA, gerente Jorge de Petrolina, marketing Aline Ximenes)

## 6. Padrão técnico dos casos (importante pra Onda 3 não divergir)

### 6.1 Cada `index.html` de caso segue este esqueleto
- Header sticky com brand MP + chip "Caso N de 8"
- Breadcrumb (Home › M2 › Caso XX)
- Hero: kicker mono + h1 grande + subtítulo + hero-meta (áreas + artefato)
- 5 sections `<section class="step">` com número mono gigante + eyebrow + título
  - **Step 01** — Descreva a tarefa (contexto do problema)
  - **Step 02** — Dê o contexto que a IA precisa (info-grid 4 cards)
  - **Step 03** — Baixe o insumo (download-card + download-preview + callout warn "fictícios")
  - **Step 04** — Cole o prompt no chat (prompt-box com botão copiar + baixar .md + prompt-content inline abreviado)
  - **Step 05** — O que esperar (result-block com preview visual + result-desc + callout info "depois de gerar")
- Nav-bottom com "← anterior · próximo →" (linka casos adjacentes)
- Footer + toast + script IIFE do copy

### 6.2 CSS mestre (copiado idêntico entre casos, só muda preview do step 5)
Cores, tipografia, classes `.step`, `.info-grid`, `.download-card`, `.prompt-box`, `.callout` são idênticas nos 4 casos existentes. Copiar do caso 4 pra ganhar tempo.

### 6.3 Prompt sempre em PCTFL+
Estrutura obrigatória:
- `# PAPEL` — personagem sênior específico (não "assistente de IA")
- `# CONTEXTO` — situação MP + público + restrição de tempo
- `# TAREFA` — N seções numeradas do que o Artifact deve ter
- `# ESTILO DE SAÍDA` — dita paleta MP, fundo creme, sem dark mode, sem gradients
- `# LINGUAGEM` — PT-BR direto, sem "vale destacar"
- `# ANTES DE GERAR` — pede 3 confirmações em bullets antes do HTML
- `---` + dados inline no final

### 6.4 JS do copy-to-clipboard
Padrão IIFE com fallback `execCommand('copy')` — copiar do caso 4 sem alterar.

### 6.5 Data attributes no hub
Card no hub M2 tem `data-status="in-progress"` (chip "Em breve") ou `"ready"` (chip escondido, hover ativo). Ao terminar cada caso, editar hub pra marcar ready.

## 7. Comandos-chave

```bash
# gerar xlsx/docx via Python (scratchpad tem os scripts que geraram os atuais)
python3 /private/tmp/claude-501/-Users-rafaellima-developer-4-cursos-treinamentos-treinamentos-in-company/34820797-5245-41f3-a1c6-6489bf971626/scratchpad/gen_reviews_v2.py       # 150 reviews caso 1
python3 /private/tmp/claude-501/.../scratchpad/gen_prompt_reviews.py   # prompt.md caso 1
python3 /private/tmp/claude-501/.../scratchpad/gen_health_check_v2.py  # xlsx 3 abas caso 3
python3 /private/tmp/claude-501/.../scratchpad/gen_prompt_health.py    # prompt.md caso 3
python3 /private/tmp/claude-501/.../scratchpad/gen_briefing_petrolina.py     # docx caso 2
python3 /private/tmp/claude-501/.../scratchpad/gen_briefing_cupuacu.py       # docx caso 4

# git no repo — SEMPRE cd primeiro (o repo é uma subpasta)
cd /Users/rafaellima/developer/4-cursos-treinamentos/treinamentos-in-company/maria-pitanga-issac/workshop-ia-mp
git add -A && git commit -m "..." && git push

# checagem HTTP pós-deploy (Pages leva ~1 min)
curl -I https://rslimaeng.github.io/workshop-ia-maria-pitanga/m2/
```

## 8. Padrão Rafael de git (do CLAUDE.md do repo)

- Autor: `Rafael Lima <rslima.eng@gmail.com>` (config global já correta)
- **NUNCA** `--amend` em commit já pushado
- **NUNCA** `push --force`
- **NUNCA** `--no-verify`
- `.nojekyll` obrigatório na raiz
- Commits **não** mencionam Claude Code (autor real: Rafael)

## 9. O que Rafael pediu explicitamente até agora nesta sessão

Ordem cronológica:
1. "Vamos para o M2 — 8 casos como Mallory M5 mas com estética Claude use cases"
2. "Aprovado o 1a + 1b + 1c" (radar de reviews · playbook nova unidade · health check loja — trocou o Google Maps original)
3. "CV deixa depois" (triagem de currículos NÃO entra nos 8 iniciais)
4. "Cria a infra do projeto pra evitar erros depois" (CLAUDE.md, goals/, _shared/)
5. "Faça a divisão de ondas como achar melhor" (escolhi 3 ondas)
6. "Insumos em docx e xlsx, nada de txt/csv"
7. "Prompt.md pode criar, é o que eu mostro em aula"
8. Depois de ver o caso 1: "**quando for excel, ter mais linhas** — algo mais de volume pra efeito uau"
9. Agora: "salve tudo pra dar um compact"

## 10. Próxima onda (Onda 03) — quando voltar

**Objetivo:** construir os 4 casos restantes (5-8) no mesmo padrão dos 4 primeiros.

### Passo a passo pra próxima sessão

1. **Ler este HANDOFF.md do início ao fim**, depois `workshop-ia-mp/CLAUDE.md`, depois `workshop-ia-mp/goals/README.md`
2. **Abrir 2-3 dos 4 casos existentes** (radar-reviews, health-check-loja, comunicado-rede) pra internalizar o padrão HTML/CSS
3. **Criar `goals/goal-03-m2-casos-5-a-8.md`** listando escopo
4. **Marcar Onda 3 como in_progress** (TaskUpdate na task pendente, se ainda existir)
5. Executar caso a caso:

#### Caso 5 · treinamento-atendente
- **Insumo:** `docx` "manual-padrao-atendimento.docx" — 1-2 pág com padrão de recepção MP (saudação, escuta ativa, sugestão de topping, cross-sell, resolução de reclamação, encerramento)
- **Prompt:** pede deck HTML de 5 slides + apostila do aluno + roteiro do supervisor
- **Artefato-alvo (preview no step 5):** thumbnail de deck 5 slides + capa apostila com sumário
- **Nomes fictícios:** treinamento chamado "Padrão Maria Pitanga · Atendimento 30 min", supervisora RH Marina Torres

#### Caso 6 · analise-vendas ⚠️ VOLUME GRANDE
- **Insumo:** `xlsx` "vendas-20-lojas-30-dias.xlsx" — **600 linhas** (20 lojas × 30 dias)
- **Colunas:** data, código loja, cidade, faturamento dia, ticket médio, qtd bowls, qtd sorbet, cupuaçu unid
- **Narrativa dentro dos números:** 3 lojas subindo forte, 2 despencando, 15 estáveis; cupuaçu vendendo em 18 das 20; padrão de sazonalidade fim-semana; lojas do interior com ticket menor
- **Prompt:** pede parecer executivo estilo revista de negócios (padrão Mallory M3 já referenciado) com top-5 insights + ranking por growth + recomendação onde investir
- **Artefato-alvo:** capa editorial grande + 4-5 sections numeradas + ranking com barras

#### Caso 7 · ficha-anvisa
- **Insumo:** `docx` "briefing-novo-sorbet.docx" — descrição livre estilo "brainstorm da fábrica" de um novo sorbet (sabor: Umbu-Cajá do Sertão). Ingredientes, textura, público-alvo, gap na linha atual, custo estimado, sugestão de preço
- **Prompt:** pede ficha técnica no padrão ANVISA (informação nutricional obrigatória, ingredientes ordem decrescente, alergênicos, validade, RDC 429) + copy pra Instagram (feed + stories)
- **Artefato-alvo:** ficha oficial estilo rotulagem + card pra rede social
- **Nomes fictícios:** produto novo "Sorbet Umbu-Cajá do Sertão", nutricionista responsável Dra. Cristiane Aguiar

#### Caso 8 · diagnostico-dor
- **Insumo:** `docx` "transcricao-conversa-time.docx" — transcrição de reunião do time de TI (5 pessoas conversando 40 min sobre as dores atuais). Formato realista: fala do CTO, dor do dev júnior, reclamação do sistemas, etc
- **Prompt:** pede plano de ação estilo consultoria com matriz impacto × esforço 2×2 (quick wins, projetos, ganhos incrementais, apostas) + timeline visual das próximas 4 semanas + próximos passos
- **Artefato-alvo:** matriz + gantt visual + parecer
- **Nomes fictícios:** CTO Ricardo Mendes, líder dev Fernanda Torres, contexto: sistema de gestão de franquias legado precisando de refresh

### Ao terminar a Onda 3

1. Atualizar hub M2: 4 cards restantes de `in-progress` pra `ready` (`m2/index.html`)
2. Atualizar `goals/README.md` marcando Onda 3 como 🟢
3. Escrever `goals/goal-03-m2-casos-5-a-8.md` com decisões tomadas
4. Commit + push
5. `curl -I` nas 4 URLs pra confirmar 200
6. Atualizar este HANDOFF.md marcando M2 100% completo

## 11. Dívidas conhecidas (backlog pós-M2)

- Sem `@media print` em algumas páginas de casos
- Sem material pré-treinamento (padrão MC/GPS: .md com autodiagnóstico + tarefa 5min + ferramentas instalar)
- Google Forms não foi refeito (8 perguntas revisadas prontas em conversa anterior, esperando Rafael colocar no form real)
- M3, M4, M5 ainda não construídos (sem planejamento de tempo em cima da restrição de 3h restantes após M1+M2)
- 3 dúvidas em aberto do Rafael (do HANDOFF anterior):
  - Franqueados donos de loja participam do workshop? (afeta pergunta 1 do form + vocabulário)
  - Caso-âncora universal MP (equivalente à "planilha herdada" do Mallory)?
  - Alguma ferramenta corporativa de IA já em uso na rede? (afeta M3+M4)

## 12. O que Rafael valoriza (calibração)

- Verdade > conforto. Aponta problema se ver.
- Comunicação enxuta. Bullets > parágrafos longos.
- **Chat decide, terminal executa.** Nunca perguntar decisão de produto ao terminal — perguntar aqui.
- Efeito uau real (por isso o volume nos xlsx).
- Universo MP coerente (Roberta, Bruno, Cupuaçu, Petrolina, Aline atravessam os casos).
- Padrão Mallory como referência de método (goals/, .md canônico, HTML enriquece).

## 13. URLs pra Rafael validar

- **Landing:** https://rslimaeng.github.io/workshop-ia-maria-pitanga/
- **Hub M2:** https://rslimaeng.github.io/workshop-ia-maria-pitanga/m2/
- **Caso 1:** https://rslimaeng.github.io/workshop-ia-maria-pitanga/m2/exemplos/radar-reviews/
- **Caso 2:** https://rslimaeng.github.io/workshop-ia-maria-pitanga/m2/exemplos/playbook-nova-unidade/
- **Caso 3:** https://rslimaeng.github.io/workshop-ia-maria-pitanga/m2/exemplos/health-check-loja/
- **Caso 4:** https://rslimaeng.github.io/workshop-ia-maria-pitanga/m2/exemplos/comunicado-rede/

---

**Última atualização:** 2026-07-30 · commit `f8055ff`
**Próximo movimento:** Onda 03 (casos 5-8), começando por criar `goals/goal-03-m2-casos-5-a-8.md`
