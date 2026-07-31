# Goal 06 · M5 Mini-Diagnóstico + Canvas MP

**Onda:** 06
**Status:** 🟢 concluída
**Escopo:** construir o M5 completo — módulo de fechamento do workshop, com 6 gatilhos de uso (adaptados do Mallory M3) + Canvas MP interativo (adaptado do Mallory M6) que exporta linha TSV pra colar no Sheets do backlog da rede.

## Escopo fechado com Rafael

- **Base conceitual:** Mallory M3 (6 gatilhos) + Mallory M6 (canvas 8 blocos)
- **Nomes dos gatilhos:** manter os originais Mallory (Robô Humano · Tela em Branco · Detetive Cansado · Parceiro de Sparring · Tradutor Técnico · Olho Biônico), com exemplos e sinais adaptados pro universo MP
- **Canvas:** versão enxuta com 5 blocos essenciais (Problema · Fluxo hoje · Onde IA entra + ferramenta · Sucesso 30d + Gatilho + Modo)
- **Backlog:** só gera TSV — Rafael abre Sheets em sala e alunos colam. Sem depender de URL pré-criada

## O que entrega

### `m5/index.html` — single-page do módulo (6 seções)

1. **Contrato do módulo** — o que você entra, o que acontece, o que sai (callout tríplice)
2. **6 gatilhos MP** — grid 3×2 com card por gatilho (número · nome · modo canônico · sinal na semana · 3 exemplos MP · teste rápido) + pergunta de diagnóstico em callout accent
3. **Como preencher o Canvas** — 5 steps horizontais mini (escolhe tarefa · identifica gatilho · preenche · copia · cola)
4. **Canvas MP interativo** — form com 8 campos (nome · área · gatilho dropdown · modo dropdown · 4 textareas), rascunho salvo em localStorage, 3 botões (copiar linha · preview · limpar), schema visual das colunas TSV
5. **Backlog da rede** — instrução visual de como colar no Sheets + callout "e se meu gatilho é Manual"
6. **Compromisso pra semana** — 3 compromissos ("colou linha · marcou revisão 30d · escolheu 1 par") + callout "o material continua no ar"

Padrão idêntico M1/M3/M4: layout 2 col (nav lateral scroll-spy), design system MP.

### Interatividade do Canvas
- **8 campos** (nome, área, gatilho, modo, problema, fluxo, ferramenta, sucesso)
- **localStorage** — rascunho salva a cada input/change
- **Botão "Copiar linha pra planilha"** — sanitiza (tab e quebra viram espaço/·), monta linha TSV com 9 colunas (as 8 + data de hoje), copia pra clipboard
- **Botão "Ver preview"** — mostra o TSV formatado antes de copiar
- **Botão "Limpar rascunho"** — com confirmação
- **Validação mínima** — não copia se nome ou problema estão vazios
- **Toast feedback** — "Linha copiada · cole no Sheets ✓"

### Sanitização TSV
Substitui `\t` por espaço e `\n` por ` · ` pra não quebrar a linha da planilha quando aluno digitar com Enter no textarea.

## Ajustes globais

- `index.html` (landing raiz): card M5 mudou de `soon` → `ready`
- `goals/README.md`: onda 06 marcada como 🟢 concluída
- **Landing agora está 100% ready** — todos os 5 módulos publicados

## Decisões tomadas na execução

1. **Manteve nomes originais dos 6 gatilhos** — memoráveis, universais, testados no Mallory. Apliquei todos os 6 exemplos por gatilho no universo MP (20 lojas, franqueado, cupuaçu, pesquisa NPS, RFI de embalagem, contrato de aluguel).
2. **Modo canônico ao lado de cada gatilho:** 4 são Colaboração (Tela em Branco, Detetive, Sparring — porque exigem julgamento), 2 são Autopiloto (Robô Humano, Tradutor Técnico, Olho Biônico — porque saída é objetiva). Coerente com M1.
3. **Canvas fundiu blocos do Mallory M6:** Persona virou coluna "área" no topo (mais fácil), Dados virou parte do bloco "Fluxo hoje", Checkpoint humano virou callout separado ("e se meu gatilho é Manual").
4. **Data de hoje incluída na linha TSV** — pra virar campo de "quando entrou no backlog" na planilha da rede.
5. **Formato TSV escolhido em vez de CSV:** Sheets divide automaticamente em colunas ao colar TSV. CSV precisaria "Colar Especial → dividir texto em colunas". TSV é 1 clique.
6. **Compromisso final em 3 itens concretos** (colar linha · marcar 30d · escolher par) — mais forte que "próximos passos" abstrato. Padrão do M6 Mallory ("piloto sem dono morre em 2 semanas").
7. **Nav bottom aponta pra hub** — não pra próximo módulo (workshop acabou).

## Auditoria

- [x] Landing atualizada: card M5 = `ready`
- [x] Single-page M5 abre sem erro (auditado via hook PostToolUse)
- [x] Nav lateral com scroll-spy funcional
- [x] Canvas com localStorage funcionando (rascunho persiste entre refreshes)
- [x] Botão de cópia usa navigator.clipboard com fallback pra execCommand
- [x] Vocabulário canônico: 6 modos marcados nos gatilhos + reencaixe explícito no canvas (dropdown de modo)
- [x] Callout "se gatilho é Manual" preserva vocabulário canônico

## Próxima onda (backlog · pós-workshop)

- `@media print` de algumas páginas (M1, M2, cases M2)
- Material pré-treinamento (padrão Mallory: autodiagnóstico + tarefa 5min + ferramentas)
- Refresh do Google Forms (perguntas revisadas em conversa antiga)
- Página "backlog vivo" opcional — se Rafael quiser publicar um snapshot depois do workshop
- Banco de prompts consolidado (todos os prompts dos 8 casos M2 + agente M3 num único índice)
