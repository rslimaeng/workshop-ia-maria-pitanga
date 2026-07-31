# Goal 05 · M4 Automação na Prática (Cowork + n8n)

**Onda:** 05
**Status:** 🟢 concluída
**Escopo:** construir o M4 completo em single-page com 2 blocos paralelos (Claude Cowork + n8n), framework âncora, matriz de escolha e 2 cards descritivos dos cases que Rafael demonstra ao vivo.

## Escopo fechado com Rafael

- **Ferramentas mostradas:** Claude Cowork + n8n
- **Peso:** 50/50 (simétrico)
- **Rafael demonstra os 2 cases ao vivo** (não geramos executável — geramos descritivo de apoio na página)
- **Cases:** Cowork = organizar arquivos (+ variante responder e-mail) · n8n = triagem de currículos
- **Vocabulário:** mantém "Automação" no título (respeita ementa vendida) e reancorra no callout dos 3 modos ao final
- **Conceito Cowork:** adaptado do Mallory M5 (5 estações — usei especificamente a estação Cowork)
- **Conceito n8n:** adaptado do M0 do curso Rafael de n8n (framework Gatilho → Execução → Entrega, tópico-âncora)

## O que entrega

### `m4/index.html` — single-page do módulo (8 seções)

1. **Quando a IA age (não só responde)** — o salto conceitual do M1-M3 pro M4
2. **Cowork · o que muda vs Projects** — 3 diferenças concretas (escrita real · vários conectores · agenda/dispatch)
3. **Case Cowork · organizar arquivos + variante e-mail** — descritivo do que Rafael demonstra + prompt-modelo pra aluno adaptar
4. **n8n · o que muda** — roda 24/7, escala paralelo, determinístico
5. **Framework Gatilho → Execução → Entrega** — 3 caixas com "quando/faz/para" + teste rápido de mapeamento
6. **Case n8n · triagem de currículos** — descritivo + timeline visual do fluxo (5 nodes) + 3 cards Gatilho/Execução/Entrega + callout onde julgamento humano fica
7. **Matriz Cowork × n8n** — 5 perguntas de decisão em tabela 3 colunas
8. **Encaixe nos 3 modos** — Autopiloto (n8n triando CV · Cowork agendado) · Colaboração (Cowork interativo) · o que NUNCA vira automação (Manual)

Padrão idêntico ao M1 e M3: layout 2 col (nav lateral sticky com scroll-spy + conteúdo), design system MP, sem gradiente, sem dark mode.

### Sem insumo executável
Os cases são demo ao vivo do Rafael — a página serve como **mapa mental de apoio** pro aluno acompanhar. Cards de case usam badge "Rafael executa ao vivo" pra deixar claro.

## Ajustes globais

- `index.html` (landing raiz): card M4 mudou de `soon` → `ready`
- `goals/README.md`: onda 05 marcada como 🟢 concluída

## Decisões tomadas na execução

1. **Título mantido "Automação na Prática"** — respeita ementa vendida. Reancoragem no vocabulário canônico é feita na seção 8 (não no título).
2. **Simetria 50/50 preservada:** cada bloco tem 3 seções (Cowork = 2/3 · n8n = 4/5/6). Matriz e vocabulário fecham comparando.
3. **Framework de Rafael no bloco n8n:** adotei o "Gatilho → Execução → Entrega" verbatim do Tópico 2 M0 do curso de n8n dele. Isso alinha o material MP com o material completo do curso (aluno pode aprofundar depois no curso próprio).
4. **Case Cowork com 2 variações:** "organizar arquivos" (principal) + "responder e-mails" (variante em callout). Rafael citou as duas — mantive as duas mas com escala didática diferente pra não inflar.
5. **Case n8n com timeline visual:** 5 nodes em fluxo horizontal (Form → Extract PDF → AI Classifier → Switch → Sheets+Email). Renderizado em CSS puro (sem SVG externo, sem lib).
6. **Callout "onde julgamento humano fica" no case n8n:** essencial pra evitar leitura de "IA vai contratar sozinha". Reforça o vocabulário canônico dentro do próprio case.
7. **Matriz de escolha em 5 perguntas:** máquina ligada · arquivos locais · volume · julgamento humano · saída determinística. Cobre 90% dos casos reais MP.
8. **Nav bottom:** aponta pro M3 (anterior) e pro hub (M5 ainda não existe).

## Auditoria

- [x] Landing atualizada: card M4 = `ready`
- [x] Single-page M4 abre sem erro no browser (auditado via hook PostToolUse)
- [x] Nav lateral com scroll-spy funcional
- [x] Vocabulário: Autopiloto/Colaboração/Manual explicitados na seção 8 + callouts intermediários
- [x] "Automação" só aparece como categoria de mercado (título) e sempre acompanhada da reancoragem no canônico

## Próxima onda (backlog)

- M5 · Mini-Diagnóstico e Plano de Ação (fecha o workshop)
- `@media print` de algumas páginas
- Material pré-treinamento
- Refresh do Google Forms
