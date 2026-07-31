
> Estado do projeto em 2026-07-31 (workshop 100% construído · pós-auditoria dos 5 módulos · fix M4 aplicado) — snapshot pra sobreviver ao `/compact`.
> **Todos os 5 módulos publicados e auditados. Backlog de polimento menor documentado na §11.**

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
    ├── HANDOFF-snapshot-2026-07-30.md      ← cópia deste handoff (survival)
    ├── README.md  .nojekyll  .gitignore
    ├── index.html                          ← landing com M1 e M2
    ├── _shared/design-tokens.md            ← referência dos tokens do M1
    ├── goals/                              ← 1 arquivo .md por onda
    │   ├── README.md                       ← tabela de ondas
    │   ├── goal-01-m2-infra-e-hub.md       ← 🟢 concluída
    │   ├── goal-02-m2-casos-1-a-4.md       ← 🟢 concluída
    │   └── goal-03-m2-casos-5-a-8.md       ← 🟢 concluída (+ fixes pós-auditoria)
    ├── m1/index.html                       ← M1 completo (1117+ linhas)
    └── m2/
        ├── index.html                      ← hub 8 cards ready
        └── exemplos/
            ├── radar-reviews/              ← 🟢 caso 1
            ├── playbook-nova-unidade/      ← 🟢 caso 2
            ├── health-check-loja/          ← 🟢 caso 3
            ├── comunicado-rede/            ← 🟢 caso 4
            ├── treinamento-atendente/      ← 🟢 caso 5 (fix aplicado)
            ├── analise-vendas/             ← 🟢 caso 6 (xlsx regerado com obra MP020)
            ├── ficha-anvisa/               ← 🟢 caso 7 (lupa 15g corrigida)
            └── diagnostico-dor/            ← 🟢 caso 8
```

**Repo público:** https://github.com/rslimaeng/workshop-ia-maria-pitanga
**Landing:** https://rslimaeng.github.io/workshop-ia-maria-pitanga/
**Hub M2:** https://rslimaeng.github.io/workshop-ia-maria-pitanga/m2/

## 3. Estado exato agora (2026-07-30 pós-auditoria)

- **Onda 01** — Infra + hub M2 · 🟢 · commit `7d69aec`
- **Onda 02** — Casos 1 a 4 · 🟢 · commit `1688a38`
- **Volume upgrade Onda 02** · 🟢 · commit `f8055ff`
- **Onda 03** — Casos 5 a 8 · 🟢 · commit `d4bfb0b`
- **Fixes pós-auditoria** · 🟢 · commit **`72f74ec`** (último)
- **M2 100% pronto pra teste em sala.**

## 4. Auditoria realizada (pra próxima sessão saber o histórico)

Rafael pediu auditoria antes de testar. Executei:

### 4.1 Web audit (4 URLs)
- 8 downloads OK (insumos xlsx/docx + prompts.md): todos HTTP 200
- DOM validado: 5 steps, botão copiar, nav prev/next, previews visuais nos 4 casos

### 4.2 Simulação de execução via subagents
Cada caso rodou como se fosse aluno colando prompt no Claude. Notas:

| Caso | Nota inicial | Achado | Nota pós-fix |
|---|---|---|---|
| 5 treinamento | 8,5 | Ambiguidade placeholder + conflito setas/scroll | 9,0 |
| 6 vendas | 7,0 | Xlsx não modelava obra MP020 declarada no contexto | 9,0 |
| 7 ANVISA | 8,5 | ⚠️ **REGRA DA LUPA ESTAVA ERRADA (25g → 15g/100g)** | 9,0 |
| 8 TI | 9,0 | Nenhum crítico | 9,0 (mantido) |

### 4.3 Fixes aplicados no commit `72f74ec`
- **Caso 7 (crítico):** limite da lupa "ALTO EM AÇÚCARES ADICIONADOS" corrigido de 25g pra **15g/100g em sólido** (RDC 429/2020 Anexo XXVII). Adicionado pedido explícito do cálculo de %VD dos açúcares (50g/dia referência).
- **Caso 6 (médio):** `gen_vendas_20lojas.py` ganhou lógica de aplicar -40% no faturamento da MP020 dias 12-19/jul (dia_do_mes 11-18). Xlsx e prompt.md regerados. Validação: MP020 obra R$ 3.446 vs resto R$ 5.524 = -37,6%.
- **Caso 5 (menor):** placeholder virou "bloco chapado 100×100 roxo com label Bowl MP" (não SVG). Setas do teclado só ativam quando container do deck está visível na viewport (IntersectionObserver).

### 4.4 Decisões deixadas propositais
- **MP005 Salvador em queda sem causa declarada** — Rafael decidiu manter proposital (é realista: supervisor vai à loja pra descobrir). Se em sala 2 alunos derem respostas diferentes, isso vira insight didático, não bug.

## 5. Decisões travadas (não mexer sem OK do Rafael)

### 5.1 Vocabulário oficial
- **Autopiloto · Colaboração · Manual** (não "Copiloto · Automação · Agente")
- No M1, callout De/Para explícito. Nos outros módulos, só o canônico

### 5.2 Base visual
- **Paleta:** creme `#F0EEE6` + roxo Açaí `#6B2E7A` + sombras suaves
- **Tipografia:** Inter + JetBrains Mono via Google Fonts CDN
- **Regra dura:** sem dark mode, sem gradients, sem border-left grossa (usar fundo tingido + dot 6px via `::before`)
- Tokens replicados inline em cada HTML (single-file portable)
- Exceção específica caso 7: amarelo-umbu `#E5A932` no mockup Instagram (só naquele caso)

### 5.3 Padrão de casos práticos M2 (Mallory M5 adaptado)
- Hub M2 (`m2/index.html`) com grid 8 cards
- Cada caso em `m2/exemplos/<slug>/`:
  - `index.html` — formato Claude use case (5 passos)
  - `insumo.xlsx` OU `insumo.docx` (**nada de txt/csv**)
  - `prompt.md` — autocontido, dados inline no final

### 5.4 Ferramenta em sala (afeta prompts)
- Kimi/DeepSeek gratuitos + Claude Pro do Rafael
- `prompt.md` sempre autocontido — funciona sem upload
- Aluno pode fazer upload do xlsx/docx também — ambos caminhos funcionam
- **Contexto pra Rafael dar em aula:** Kimi/DeepSeek podem gerar insights genéricos no caso 6 (600 linhas). Claude entrega leitura fina. Serve como demo do degrau de qualidade.

### 5.5 Volume nos xlsx
- Caso 1: 150 reviews
- Caso 3: aba 3 série diária 31×9
- **Caso 6: 600 linhas (20 lojas × 30 dias) com narrativa temporal real** — semente Python fixa (seed 42), script re-executável

## 6. Os 8 casos do M2 (universo coerente)

| # | Slug | Áreas | Insumo | Artefato-alvo | Nota |
|---|---|---|---|---|---|
| 1 | radar-reviews | Lojas · CRM | xlsx 150 reviews | Dashboard temas + heatmap | ✓ |
| 2 | playbook-nova-unidade | Franquia · Ops | docx briefing Petrolina | Plano executivo A4 90 dias | ✓ |
| 3 | health-check-loja | Supervisão · Fin | xlsx 3 abas (métricas + contexto + série diária 31d) | Parecer consultoria semáforo | ✓ |
| 4 | comunicado-rede | Mkt · RH · Compras | docx briefing Bowl Cupuaçu | Kit 3 peças (email + WA + card) | ✓ |
| 5 | treinamento-atendente | RH · Fábrica · Lojas | docx manual v3.2 | Deck 5 slides + apostila + roteiro | 9,0 |
| 6 | analise-vendas | Fin · Compras · Sup | xlsx 600 linhas 20×30 | Parecer executivo revista | 9,0 |
| 7 | ficha-anvisa | Fábrica · Mkt · Log | docx briefing sorbet Umbu-Cajá | Ficha ANVISA + kit Instagram | 9,0 |
| 8 | diagnostico-dor | TI · qualquer | docx transcrição TI 42min | Plano ação matriz + gantt | 9,0 |

### Universo consistente
Bowl Cupuaçu Sertanejo aparece em casos 1 (review positivo), 3 (esgotando), 4 (lançamento), 6 (indicador de crescimento). Roberta (gerente Iguatemi), Marina (RH), Cristiane (nutricionista), Ricardo/Fernanda/Bruno/Amanda/Diego (time TI), Márcio (supervisor regional), Aline (marketing), Jorge (franqueado Petrolina) — nomes NÃO conflitam.

## 7. Comandos-chave

```bash
# regenerar xlsx caso 6 (com fix da obra MP020)
python3 /private/tmp/claude-501/.../scratchpad/gen_vendas_20lojas.py
python3 /private/tmp/claude-501/.../scratchpad/gen_prompt_vendas.py

# outros geradores (scratchpad tem os scripts que geraram os atuais)
python3 /private/tmp/claude-501/.../scratchpad/gen_reviews_v2.py
python3 /private/tmp/claude-501/.../scratchpad/gen_health_check_v2.py
python3 /private/tmp/claude-501/.../scratchpad/gen_prompt_reviews.py
python3 /private/tmp/claude-501/.../scratchpad/gen_prompt_health.py
python3 /private/tmp/claude-501/.../scratchpad/gen_briefing_petrolina.py
python3 /private/tmp/claude-501/.../scratchpad/gen_briefing_cupuacu.py
python3 /private/tmp/claude-501/.../scratchpad/gen_manual_atendimento.py
python3 /private/tmp/claude-501/.../scratchpad/gen_briefing_sorbet.py
python3 /private/tmp/claude-501/.../scratchpad/gen_transcricao_ti.py

# git no repo — SEMPRE cd primeiro (o repo é subpasta)
cd /Users/rafaellima/developer/4-cursos-treinamentos/treinamentos-in-company/maria-pitanga-issac/workshop-ia-mp
git add -A && git commit -m "..." && git push

# checagem HTTP pós-deploy
curl -I https://rslimaeng.github.io/workshop-ia-maria-pitanga/m2/
```

## 8. Git rules (do CLAUDE.md do repo)

- Autor: `Rafael Lima <rslima.eng@gmail.com>` (config global já correta)
- **NUNCA** `--amend` em commit pushado
- **NUNCA** `push --force`
- **NUNCA** `--no-verify`
- `.nojekyll` obrigatório na raiz
- Commits NÃO mencionam Claude Code

## 9. O que Rafael pediu explicitamente nesta sessão (cronológico)

1. "Vamos pro M2 — 8 casos como Mallory M5 com estética Claude use cases"
2. "Aprovado 1a+1b+1c" (radar + playbook + health check, trocou Google Maps)
3. "CV deixa depois"
4. "Cria infra do projeto"
5. "Divide ondas como achar melhor" (fiz 3 ondas)
6. "Insumos docx e xlsx, nada de txt/csv"
7. "Prompt.md pode criar, é o que eu mostro"
8. Pós-caso 1: "quando for excel, ter mais linhas"
9. "Salve tudo pra dar um compact" → fiz snapshot #1
10. Pós-compact: "pode seguir para os proximos" → executei Onda 3
11. **"Faça auditoria antes de eu testar"** → fiz web audit + subagents
12. **"Pode ajustar tudo. Vc gerar os arquivos, executar, ver o resultado, validar os dados"** → apliquei 3 fixes e re-validei (todos foram pra 9/10)
13. **"deixa MP005 proposital, salva o que precisa e vamos para o m3"** → este handoff atualizado; próxima sessão começa M3

## 10. Estado atual · workshop 100% construído

**Status:** 🟢 5 módulos publicados e auditados. Fix crítico do M4 aplicado. Pronto pra validação final.

### Ondas concluídas (histórico)
- **Onda 01-03:** M2 (hub + 8 casos)
- **Onda 04:** M3 (single-page + caso-âncora agente-relatorio-semanal com 4 arquivos)
- **Onda 05:** M4 (Cowork + n8n, framework Gatilho→Execução→Entrega, 2 cards demo)
- **Onda 06:** M5 (6 gatilhos + Canvas MP interativo + export TSV)
- **Onda 07:** fixes pós-auditoria (M5 preview horizontal removido · M4 timeline + nav mobile)

### Auditoria browser dos 5 módulos (2026-07-31)
| Módulo | Status | Nota |
|---|---|---|
| M1 | 🟢 aprovado | 2 obs baixa (backlog) |
| M2 (hub + 3 casos amostrados) | 🟢 aprovado | 1 obs baixa (backlog) |
| M3 | 🟢 aprovado | 2 obs média (reforço vocabulário — backlog) |
| M4 | 🟢 aprovado pós-fix | 2 críticos corrigidos na Onda 07 |
| M5 | 🟢 aprovado pós-fix | 1 obs média (backlog · overflow 4px) |

### Fixes aplicados na Onda 07 (commit da sessão)
1. **M4 · Timeline n8n** — `flex-wrap:wrap` → `nowrap` (evita setas órfãs no desktop) + em mobile `flex-direction:column` com seta rotacionada 90° via CSS
2. **M4 · Nav lateral mobile** — vira barra horizontal rolável (chip-like, scroll-x) em vez de bloco vertical de 800px. Item ativo destacado por border-bottom em vez de border-left

### Respostas de escopo históricas (Rafael · pré-M3/M4/M5)

**"Agente" no vocabulário canônico:** assistente de ferramenta (Claude Projects, Gemini Gems, Custom GPTs) com system prompt + contexto redondos. Complementa Autopiloto/Colaboração/Manual — cabe em Colaboração com repetibilidade.

**Ferramenta demo M3:** didático + Claude Projects. Argumento "por que a paga vale".

**Caso-âncora M3:** apresentação de resultado semanal (todo mundo faz). Loja MP047 · Juazeiro do Norte/CE · 4 semanas · 2.946 vendas.

**Casos demo M4:** Cowork = organizar arquivos (+ variante e-mail) · n8n = triagem de currículos.

**Canvas M5:** 5 blocos essenciais + gatilho + modo + nome + área = 8 campos. Export TSV (não CSV — Sheets divide colunas automaticamente). Nomes dos gatilhos: originais Mallory. Sheets do backlog: só gera TSV, Rafael abre em sala.

### Respostas de escopo (Rafael · 2026-07-30 pós-compact)

**1. Definição de "Agente" no vocabulário canônico:**
Agente = **assistente de ferramenta** com system prompt + contexto "redondos", pra sempre executar aquela tarefa de forma padronizada. Exemplos concretos: Claude Projects, Gemini Gems, Custom GPTs. Complementa (não substitui) Autopiloto/Colaboração/Manual — cabe dentro de "Colaboração" mas com repetibilidade.

**2. Ferramenta demo em sala:**
**Didático + Claude Projects.** Foco no potencial e no argumento "por que vale a pena ter uma paga". Reconhecer que na gratuita dá pra ter o mesmo efeito começando o prompt com system + contexto ("forçar a barra"). Não usar Custom GPT, não usar n8n neste módulo.

**3. Caso-âncora universal MP:**
**Apresentação de resultados semanais.** Todo mundo (gerente, supervisor, coordenador) tem que fazer um relatório/apresentação de fechamento. Insumos do agente:
- **Excel de exemplo** — fechamento semanal (vendas, ticket, top produto, ocorrências)
- **System prompt** — papel do agente
- **Contexto** — modelo do relatório (estrutura fixa MP)
- **Comando de uso simples** — "segue o excel dos resultados, cria o relatório"
Resultado: HTML pronto pra apresentar (não PPT — mesma lógica dos casos M2).

**4. Tempo em sala:**
Rafael se vira. **Foco 100% no conteúdo** — não travar decisão de time slot.

### Formato do M3 (decidido)
Single-page HTML no padrão M1/M2 (creme #F0EEE6, roxo #6B2E7A, sem dark mode). Estrutura:

1. **Hero** — chips "Módulo 3 · Primeiros Agentes" + H1 (ementa: "Criando seu Primeiro Agente de IA")
2. **Abre-caminho** — 1 parágrafo definindo agente na linguagem MP (sem jargão)
3. **Bloco conceitual** — 3 cards: (a) o que é agente, (b) diferença de chat solto, (c) 3 partes de um agente (system prompt + contexto + comando de uso)
4. **Ancora comparativa** — didático puro (sem ferramenta): mesmo pedido "faz o relatório da semana" resolvido de 2 jeitos (chat solto vs. agente pronto)
5. **Caso-âncora: Agente Relatório Semanal MP** — mostrar os 4 componentes reais (excel insumo + system prompt + contexto/modelo + comando). Card com preview do relatório HTML gerado.
6. **Bloco ferramenta · Claude Projects** — screenshot/mockup de como montar. Argumento "por que a paga vale". Bônus "como forçar a barra na gratuita".
7. **CTA final** — "no seu trabalho da semana, qual seria seu primeiro agente?"

### Estrutura de arquivos
```
m3/
├── index.html                                    ← single-page principal
└── exemplos/
    └── agente-relatorio-semanal/
        ├── index.html                            ← caso completo (padrão M2)
        ├── insumo-fechamento-semanal.xlsx        ← dados de 1 loja MP · semana real
        ├── system-prompt.md                      ← papel + regras do agente
        ├── contexto-modelo-relatorio.md          ← template do relatório MP
        └── comando-de-uso.md                     ← 1 linha + como colar
```

Hub M2 já tá em `data-status="ready"`. Landing atualiza pra apontar M3 quando fechar.

## 11. Dívidas conhecidas (backlog pós-workshop · não-bloqueantes)

### Achados menores da auditoria (obs baixa/média · não travam sala)
- **M5 (média)** overflow horizontal fantasma de 4px no mobile (barra de scroll aparece)
- **M4 (média)** pill do header quebra em 3 linhas no mobile — encurtar pra "M4" em <640px
- **M3 (média)** vocabulário "Colaboração" mencionado só 1x no single-page — desbalanceado (Autopiloto 4x, Manual 3x). Reforço no s3 ou s5
- **M3 (média)** caso-âncora `agente-relatorio-semanal` não amarra o modo canônico explicitamente. Vale trecho "este agente é modo Colaboração (você aciona + revisa)"
- **M1 (baixa)** exemplo do gerador de prompt tem "Campanha de Verão 2027 pra as +200 unidades" — corrigir pra "pras" ou "para as"
- **M1 (baixa)** palavra "Agente" solta em texto descritivo. Se for higiene 100%, trocar por "assistente"
- **M2 (baixa · dívida técnica)** span `<class="case-status">Em breve</span>` oculto no HTML de cards `data-status="ready"` — remover pra evitar acidente futuro

### Backlog original
- `@media print` de algumas páginas de caso do M2
- Material pré-treinamento (padrão Mallory: .md com autodiagnóstico + tarefa 5min + ferramentas)
- Google Forms não foi refeito (8 perguntas revisadas prontas em conversa antiga)
- Banco de prompts consolidado (todos os prompts M2 + agente M3 num único índice)
- Página "backlog vivo" opcional — publicar snapshot pós-workshop com o Sheets preenchido pelos alunos

### 3 dúvidas antigas (nunca resolvidas · não-bloqueantes)
- Franqueados donos de loja participam? (afeta vocabulário)
- Alguma ferramenta corporativa de IA já em uso na rede?

## 12. O que Rafael valoriza (calibração)

- Verdade > conforto. Aponta problema se ver.
- Comunicação enxuta. Bullets > parágrafos.
- **Chat decide, terminal executa.** Nunca pedir decisão de produto ao terminal.
- Efeito uau real (por isso o volume no xlsx do caso 6, por isso auditoria antes de testar).
- Universo MP coerente atravessando os casos.
- Padrão Mallory como referência de método.
- **Auditoria pré-teste é padrão pra Rafael quando o volume de material é grande** (validar antes de mostrar em sala).

## 13. URLs pra Rafael validar

- **Landing:** https://rslimaeng.github.io/workshop-ia-maria-pitanga/
- **M1:** https://rslimaeng.github.io/workshop-ia-maria-pitanga/m1/
- **M2 hub:** https://rslimaeng.github.io/workshop-ia-maria-pitanga/m2/
- **M3:** https://rslimaeng.github.io/workshop-ia-maria-pitanga/m3/
- **M4:** https://rslimaeng.github.io/workshop-ia-maria-pitanga/m4/
- **M5:** https://rslimaeng.github.io/workshop-ia-maria-pitanga/m5/
- **Casos M2 1-8:** https://rslimaeng.github.io/workshop-ia-maria-pitanga/m2/exemplos/<slug>/
- **Caso M3:** https://rslimaeng.github.io/workshop-ia-maria-pitanga/m3/exemplos/agente-relatorio-semanal/

## 14. Roteiro em sala (pra Rafael conferir)

- **Abertura + M1** (~50 min) — IA sem mistério, 3 modos, PCTFL+
- **M2** (~80 min) — 3-4 casos escolhidos ao vivo pelos alunos, executados no Kimi/DeepSeek. Rafael mostra fluxo, alunos replicam
- **M3** (~35 min) — o que é agente, montar Agente Relatório Semanal no Claude Projects (demo Rafael)
- **M4** (~40 min) — Cowork demo (organizar arquivos) + n8n demo (triagem CV) + matriz de escolha
- **M5** (~25 min) — 6 gatilhos + Canvas MP preenchido individualmente + colar no Sheets do backlog + compromisso de 30d
- **Fechamento** (~10 min)

Total: ~240 min = 4h.

---

**Última atualização:** 2026-07-31 · pós-fix Onda 07 · workshop 100% pronto pra validação
**Próximo movimento:** Rafael valida os 5 módulos ao vivo · se OK, workshop sábado. Backlog de polimento fica na §11.
