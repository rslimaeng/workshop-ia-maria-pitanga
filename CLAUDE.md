# CLAUDE.md — Workshop IA Maria Pitanga

## 1. Contexto

Material para 1 workshop presencial in-company da **Rede Maria Pitanga Açaí & Gelatos** (~200 franquias BR + Portugal + Espanha), conduzido pelo Rafael Lima.

- **Formato:** 1 encontro, **4h**, sábado
- **Turma:** 24 pessoas, 8 áreas (Fábrica, Logística, Lojas/Supervisão, TI, CRM, Marketing, RH, Financeiro, Compras)
- **Perfil:** heterogêneo — assistentes a gerentes. **Não** é só C-level. Vocabulário operacional-tático (reunião semanal, gerência, coordenação), evitar jargão executivo.
- **Ferramenta em sala:** Kimi (moonshot.cn) e/ou DeepSeek para alunos + Claude Pro na tela do Rafael

**Repo público:** https://github.com/rslimaeng/workshop-ia-maria-pitanga
**Site publicado:** https://rslimaeng.github.io/workshop-ia-maria-pitanga/

## 2. Ementa vendida (5 módulos, 4h)

| M | Título original |
|---|---|
| M1 | IA Sem Mistério: o que é, o que faz e por que agora |
| M2 | Mão na Massa com IA Generativa |
| M3 | Criando seu Primeiro Agente de IA |
| M4 | Automação na Prática: IA que Trabalha Sozinha |
| M5 | Mini-Diagnóstico e Plano de Ação |

## 3. Regras duras (git)

- **Autor de todos os commits:** `Rafael Lima <rslima.eng@gmail.com>`
- **Nunca** `--amend` em commit já pushado
- **Nunca** `push --force`
- **Nunca** `--no-verify`
- `.nojekyll` obrigatório na raiz (impede Jekyll renderizar .md)
- Nunca commitar arquivos com dados sensíveis reais (usar mocks fictícios)
- Autor real do trabalho: Rafael Lima. Commits **não** mencionam Claude Code.

## 4. Vocabulário oficial (não negociar sem OK do Rafael)

### 4.1 Os 3 modos de uso

- **Autopiloto** — IA executa, você revisa. Baixo risco, alto retorno em tarefa repetitiva.
- **Colaboração** — IA e você pensam juntos. Contexto pessoal + iteração. Risco médio.
- **Manual** — IA inspira, você decide. Alta responsabilidade autoral. Não delegar.

**Regra de ouro:** quanto maior o impacto/risco da decisão, mais manual o modo.

**Proibido** (usar só se descrever categoria de mercado): "Copiloto", "Automação" como modo, "Agente" como modo separado.

**De/Para com ementa vendida** (declarado no M1): Autopiloto ↔ Copiloto · Colaboração ↔ Automação · Manual ↔ Agente. Isso é intencional; a ementa vendida usa vocabulário genérico de mercado, o material didático usa o vocabulário canônico do Rafael.

### 4.2 Framework didático

- **IA generativa é auto-completar** treinado em quase tudo que a humanidade escreveu. Prevê próxima palavra por probabilidade. Não pensa.
- **Zonas de saber (WYSIATI · Kahneman):** sei que sei → IA padroniza · sei que não sei → IA acelera · não sei que não sei → IA expande.
- **Delegação Inteligente** (transferir execução) vs **Estruturação do Pensamento** (sócio analítico).
- **PCTFL+ · 6 camadas:** Papel · Contexto · Tarefa · Formato · Limitações · Critério de Sucesso.
- **Referência canônica de dado global:** Anthropic Economic Index (26,7% inconfiabilidade). Nunca inventar métrica.

## 5. Voz e tom

- Português-BR direto, sem jargão de IA
- Analogias do dia a dia MP: loja, franquia, comunicado à rede, supervisor, atendente, receita nova, sorbet, fila, review no Google Maps
- Tom parceiro, não professor
- Sem emoji em card decorativo (parece infantil). Emoji só em callout curto pontual

## 6. Base visual

- **Paleta:** creme `#F0EEE6` (fundo) + roxo Açaí `#6B2E7A` (accent) + tipografia Inter + JetBrains Mono. Design system Claude adaptado.
- **Design tokens:** documentados em `_shared/design-tokens.md`. Cada página HTML replica os tokens no `<style>` inline (mantém single-file portable).
- **Estética:** minimalista, sem gradients, sem glassmorphism, cards com bordas sutis, fundos levemente tingidos derivados da cor semântica no lugar de border-left grossa.

## 7. Padrão de módulo

Cada módulo é uma **página HTML single-file** em `m<N>/index.html`, self-contained (fontes via Google Fonts CDN é OK), com:

1. Header sticky com brand + chip de contexto
2. Nav lateral sticky com scroll-spy (colapsa em `900px` pra topo)
3. Hero (kicker + H1 + subtítulo)
4. N seções (`<section id="s-N">`) — tabelas, cards, callouts, artefatos interativos
5. Footer com assinatura Rafael

Componentes reaproveitáveis criados no M1 (documentados em `_shared/design-tokens.md`):
- `.card` · `.card-accent` · `.card-highlight`
- `.callout` (info/warn) com dot colorido via `::before` no título
- `.table-wrap` + tabela dark-neutral com `td.cell-verde` / `td.cell-vermelho`
- `.matriz` 2×2 responsiva
- `.compare` (vago × situado com fundo tingido, sem border grossa)
- `.prompt-box` (código monoespaçado)
- `.gen` (gerador de prompt com localStorage)

## 8. Padrão de casos práticos (M2 em diante)

Módulos com casos práticos seguem o padrão **Mallory M5 adaptado**:

- **Hub** (`m<N>/index.html`) — página de entrada com intro curta + grid de cards navegáveis pra cada caso
- **Cada caso** vive em `m<N>/exemplos/<slug>/` com:
  - `index.html` — página do caso no formato Claude use case: **1. Descreva a tarefa · 2. Dê contexto · 3. Copie o prompt · 4. Baixe o insumo · 5. Veja o artefato esperado**
  - `insumo.xlsx` ou `insumo.docx` — arquivo mock que o aluno baixa (formato realista, `.txt`/`.csv` evitados)
  - `prompt.md` — prompt pronto pra copiar (Rafael exibe em aula e alunos baixam)

**Regra de ouro:** todo arquivo mock é fictício. Nomes de pessoa, CNPJ, valores — tudo inventado. Nenhum dado real da rede sai do briefing pra dentro dos arquivos.

## 9. Estrutura de arquivos

```
workshop-ia-mp/
├── CLAUDE.md                     ← este arquivo
├── README.md
├── .nojekyll  .gitignore
├── index.html                    ← landing com módulos
├── _shared/
│   └── design-tokens.md          ← referência humana dos tokens
├── goals/
│   ├── README.md                 ← índice de ondas
│   └── goal-XX-<slug>.md         ← 1 arquivo por onda
├── m1/index.html                 ← M1 pronto (fusão M1+M2 T2 Mallory)
├── m2/
│   ├── index.html                ← hub
│   └── exemplos/
│       └── <slug>/
│           ├── index.html
│           ├── insumo.xlsx|docx
│           └── prompt.md
└── m3..m5/                       ← futuro
```

## 10. Disciplina de execução

- 1 onda = 1 goal em `goals/goal-XX-<slug>.md`
- `goals/README.md` mantém a tabela de ondas (rodando · próxima · concluídas)
- Antes de fechar onda: `curl -I` da URL retornou 200 · vocabulário oficial confere · commit em nome do Rafael · `.nojekyll` presente
- Não avançar M(n+1) enquanto M(n) tiver pendência de validação

## 11. Modelo mental do Rafael

Rafael é PM não-técnico. **Ele decide, terminal executa.** Ele valida via browser + audit meu do chat.

- **Verdade > conforto.** Se o goal está estranho, dizer.
- **Comunicação enxuta.** Bullets > parágrafos.
- **Chat decide, terminal executa.** Nunca perguntar decisão de produto ao terminal — perguntar ao Rafael.
