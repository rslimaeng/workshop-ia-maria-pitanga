# Goal 09 · M3 · Extra didático "Criando seu time de IA"

**Onda:** 09
**Status:** 🟢 concluída
**Escopo:** adicionar ao M3 um extra **só didático** sobre time de agentes — orquestrador + base de especialistas + ativação de persona — com 3 times de exemplo. Sem arquivo pra baixar, sem exercício. O objetivo é mostrar o **racional** pro aluno replicar depois.

## Escopo fechado com Rafael

- **Onde mora:** dentro do M3 (`m3/exemplos/time-de-agentes/`), não em repo separado
- **Por quê no M3:** os 3 times rodam em **Claude Projects** — a mesma superfície que o M3 ensina. Conecta direto no que o aluno acabou de montar
- **Ressalva assumida:** os exemplos NÃO são do universo Maria Pitanga (branding, decisão executiva, produto digital). Rafael decidiu manter — *"eles conseguem aprender o racional para tentar replicar"*. A página declara isso explicitamente na seção 6
- **Nome:** "Criando seu time de IA"
- **Formato:** só didático · nada pra baixar

## O que entrega

### `m3/exemplos/time-de-agentes/index.html` — conceito (8 seções)

1. Hero — "Criando seu time de IA" · liga ao que ele fez no M3
2. Chat solto × time orquestrado (exemplo de posicionamento de açaí no Nordeste)
3. As 3 peças (Orquestrador · Base de especialistas · Ativação de persona)
4. Anatomia do orquestrador — bloco de código real do `00-System_Instruction.md` + legenda em 4 blocos
5. O fluxo em 4 passos (Você → Orquestrador → Especialista → Você)
6. 3 times de exemplo (cards clicáveis)
7. Quando faz / NÃO faz sentido (2 callouts honestos)
8. Como montar o seu time — 5 passos

Layout 2 col com nav lateral scroll-spy, padrão M1/M3/M4/M5.

### 3 sub-páginas de time

| Arquivo | Time | Agentes |
|---|---|---|
| `conselho-consultivo.html` | Conselho Consultivo | 11 em 4 níveis |
| `time-marca.html` | Time de Marca | 15 em 5 níveis |
| `time-produto-digital.html` | Time de Produto Digital | 8 em 3 níveis |

Cada uma tem: hero + callout "quando usar" + legenda de níveis · card do orquestrador · grid de especialistas por nível (nome · credencial · atua em · consulte quando · quote) · tensões produtivas · roteiro de uso · insight final · nav bottom.

### Ligação com o M3

- `m3/index.html` seção 7 ganhou um `.case-card` "E quando um agente não basta?" → `exemplos/time-de-agentes/`
- Posicionado **depois** do callout do caso-âncora — a ordem pedagógica é: monte 1 agente primeiro, depois veja o time

## Decisões tomadas na execução

1. **Nomes dos agentes traduzidos.** Os 8 do Produto Digital eram criptográficos em inglês (Sigil, Latch, Anvil, Piper, Nexus, Vigil, Conduit, Orion) → **Guardião · Gatilho · Forja · Conector · Maestro · Radar · Alicerce · Bússola**. "Gatilho" casa com o framework Gatilho→Execução→Entrega do M4.
2. **Nomes de pessoas reais mantidos.** Ray Dalio, Al Ries, Byron Sharp etc. Só os agentes **funcionais fictícios** foram traduzidos (Brand Chief → Diretor de Marca, Naming Strategist → Estrategista de Nomes, Board Chair → Presidente do Conselho…).
3. **Quotes:** traduzidas nos agentes fictícios (personas inventadas não falam inglês). **Mantidas no original** nas pessoas reais — são citações atribuídas e reconhecíveis ("Invert, always invert").
4. **Vocabulário:** squad → **time** · tier → **nível** em toda superfície visível. Classes CSS `.tier-*` ficaram (invisíveis).
5. **Cards de especialista refeitos minimalistas** após feedback: saiu border-left 3px colorida + tag com fundo sólido + indentação de 38px. Entrou border 1px sutil + dot 7px da cor do nível + alinhamento à esquerda. Alinha com a regra do CLAUDE.md §6 (*"no lugar de border-left grossa"*).
6. **Página antiga apagada:** `brand-squad-apresentacao.html` (dark/dourado, fora do padrão) — ninguém linkava.

## Auditoria

- [x] Vocabulário canônico: 0 ocorrências de "Copiloto"; "Automação" aparece só como nome de camada (hooks/skills), nunca como modo
- [x] Sem "Advisory Board / Brand Squad / Claude Code Mastery" em superfície visível
- [x] Sem "squad" / "tier" em superfície visível (só comentários HTML e classes CSS)
- [x] Header MP + breadcrumb Home › Módulo 3 › … nas 4 páginas
- [x] Nav bottom encadeada: M3 → conceito → Conselho → Marca → Produto Digital → conceito
- [x] Paleta MP (creme #F0EEE6 + roxo #6B2E7A + Inter + JetBrains Mono)
- [x] Card no M3 apontando pro caso, depois do callout do caso-âncora
- [x] Verificado no browser: index, conselho, produto digital e card do M3

## Fontes

Extraído de `maria-pitanga-issac/agentes-ia/`:
- `00-System_Instruction.md` — o prompt orquestrador (base da seção 4)
- `01-advisory-board.md` (137KB) · `02-brand-squad.md` (103KB) · `04-claude-code-mastery.md` (187KB)

Leitura integral feita por 3 agents em paralelo, cada um devolvendo estrutura compacta.

## Backlog

- `06-copy-squad.md` (7KB) existe e não virou página — 4º time se Rafael quiser
- Adaptar 1 dos times pro universo MP de verdade (ex: "Time de Operação de Loja") — hoje o racional é transferível mas o exemplo é de fora
