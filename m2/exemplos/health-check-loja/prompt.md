# Prompt · Health check de loja (Iguatemi Fortaleza)

> Copia daqui até o fim e cola no Claude, Kimi ou DeepSeek. Os dados da loja já vêm inline no final do prompt — funciona sem upload da planilha. Se preferir, faça upload do `insumo-health-check-iguatemi.xlsx` (3 abas: métricas × benchmark, contexto qualitativo, série diária dos 31 dias).

---

# PAPEL
Você é uma consultora sênior de operações em redes de franquia de food service,
com 12 anos de experiência apoiando franqueados a "destravar" lojas que
performam abaixo do esperado. Trabalhou no Grupo Zona Sul (Rio) e na Cacau
Show. Sabe que 90% dos problemas de loja não são de vendas — são de
operação, gente ou mix — e que gerente pedindo socorro não precisa de mais
KPI, precisa de decisão executiva.

# CONTEXTO
Sou supervisor regional CE-Norte da Maria Pitanga (rede de +200 franquias
de açaí e gelatos). Uma das minhas lojas — Iguatemi Fortaleza, shopping
RioMar — passou de "boa loja" pra "loja com sinal vermelho" nos últimos 60
dias. Faturamento tá acima do benchmark (a loja tem tráfego alto), mas
quase tudo o mais tá caindo: ticket médio, NPS interno, absenteísmo,
quebra de estoque, reclamações formais.

A gerente Roberta me disse na última call: "estou apagando incêndio, não
consigo pensar em plano nenhum". Preciso ir à loja essa sexta com um
parecer de consultoria pronto — não com uma lista de KPIs, com decisões
executivas em 30 dias.

Vou anexar 3 blocos de dados no fim deste prompt:
1. **Métricas mensais x benchmark da rede** (10 indicadores)
2. **Contexto qualitativo dos últimos 30 dias** (eventos, saídas, obra no shopping)
3. **Série diária dos 31 dias** (faturamento, ticket, clientes, vendas por produto, absenteísmo, reclamações — dia a dia)

# TAREFA
Gere um **Artifact HTML self-contained** (uma página, imprimível A4) chamado
**"Health Check · Loja Iguatemi Fortaleza"** com estas 6 seções:

## 1. CAPA COM SEMÁFORO GERAL
- Título grande, meta (loja, período, gerente, supervisor)
- Um "veredicto de status" grande no topo — verde/amarelo/vermelho — com
  1 frase justificando (ex: "AMARELO · loja com tráfego saudável mas
  operação em colapso silencioso")
- Sumário executivo em 3-4 linhas com o achado principal e a decisão que
  o supervisor precisa tomar essa semana

## 2. RAIO-X DIMENSIONAL
5 dimensões pontuadas de 0 a 10, com barra visual, cor semântica, e 1 linha
justificando a nota:
- **Receita** (faturamento vs benchmark)
- **Rentabilidade** (ticket médio, mix, margem)
- **Gente** (NPS interno, absenteísmo, rotatividade)
- **Experiência do cliente** (nota Google, reclamações)
- **Operação** (quebra, gestão de estoque)

Layout tipo "dashboard de saúde" — não tabela chata.

## 3. GRÁFICO DE TENDÊNCIA (usando a série diária)
Usando os dados da aba 3, gere pelo menos 2 mini-gráficos visuais (SVG
inline no HTML) mostrando:
- **Ticket médio ao longo do mês** (linha caindo — mostra a degradação)
- **Fluxo de clientes vs reclamações no mês** (2 séries — mostra que quando
  fluxo cai por causa da reforma, reclamações caem junto; quando o novato
  Bruno entra dia 25, reclamações voltam mesmo com fluxo médio)

Marcar visualmente os eventos-chave no gráfico (03/jul lançamento cupuaçu,
08/jul saída Ana, 12-19/jul reforma, 22/jul saída Rodrigo, 25/jul entrada Bruno).

## 4. TOP-3 ALAVANCAS PRIORITÁRIAS
3 cards grandes, um pra cada alavanca. Cada card com:
- Nome da alavanca (verbo no infinitivo — "Estabilizar equipe", "Recuperar
  ticket médio", "Ajustar mix e compra")
- Impacto esperado em métrica específica (ex: "ticket médio de R$16,20 pra
  R$19+ em 45 dias")
- 3-4 ações concretas com responsável e prazo
- Investimento estimado (baixo/médio/alto)

Priorize pelo efeito cascata (o que resolve outros problemas de tabela).

## 5. PLANO DE 30 DIAS
Cronograma semana a semana (S1, S2, S3, S4) com 2-3 ações concretas por
semana, cada uma amarrada a uma das 3 alavancas. Formato de gantt visual
horizontal ou tabela com barras.

## 6. PARECER EXECUTIVO ASSINADO
Bloco warm com:
- Diagnóstico em 1 parágrafo direto (nada de "vale destacar")
- Principal risco se nada for feito nos próximos 30 dias
- Decisão executiva pedida ao supervisor (não à gerente Roberta — ao supervisor)
- Assinado "Márcio Vasconcelos · Supervisor Regional CE-Norte · Maria Pitanga"

# ESTILO DE SAÍDA
- Página HTML self-contained (tudo inline)
- Formato A4 imprimível: margens generosas, respiro editorial
- Fundo **off-white creme #F0EEE6**, texto **#141413**
- Accent **roxo Maria Pitanga #6B2E7A**
- Cores semânticas: verde `#2E7D32`, amarelo `#B8860B`, vermelho `#B85C5C`
- Tipografia sans-serif limpa (Inter/system-ui)
- Cards com sombra suave, sem borda grossa colorida
- Big numbers grandes, sem card com border-left
- Gráficos em SVG inline (não usar Chart.js ou lib externa)
- Section titles com numeração 01, 02, 03… ao lado do título (estilo editorial)
- **NÃO dark mode**, **NÃO gradientes**, **NÃO emoji em card decorativo**
- `@media print` embutido — tudo expandido pra imprimir A4

# LINGUAGEM
Português-BR executivo, direto. Sem "vale destacar", "é importante notar".
Se pra falar, fala. Você tá escrevendo pra um supervisor experiente que
precisa decidir sexta.

# ANTES DE GERAR
Confirme em 3 bullets:
(a) Seu diagnóstico macro em 1 frase (o que está acontecendo com essa loja)
(b) Qual das 5 dimensões está mais crítica e por quê
(c) Quais são as 3 alavancas que você vai propor (só o nome — desenvolvo depois)

Espere meu OK. **Só depois** gera o Artifact HTML completo.

---

## DADOS · Loja Iguatemi Fortaleza · Julho 2026

**Loja:** Iguatemi Fortaleza · Shopping RioMar
**Período:** 01/07/2026 a 31/07/2026 (30 dias)
**Gerente:** Roberta Cavalcanti
**Supervisor:** Márcio Vasconcelos (regional CE-Norte)

### Aba 1 · Indicadores mensais × benchmark da rede

| Indicador | Valor (loja) | Benchmark (rede) | Delta | Tendência 3m | Status | Observação |
|---|---|---|---|---|---|---|
| Faturamento mensal (R$) | R$ 128.400 | R$ 118.000 | +8,8% | → estável | 🟢 Verde | Está acima do benchmark em receita bruta. |
| Ticket médio (R$) | R$ 16,20 | R$ 22,40 | -27,7% | ↓ caindo | 🔴 Vermelho | Perdeu R$ 1,80 em 60 dias. Cliente está comprando o item mais barato. |
| Fluxo de clientes/dia | 264 | 184 | +43,5% | ↑ subindo | 🟢 Verde | Movimento excelente. Loja lotada é o problema? Provável. |
| Nota Google Maps (30d) | 4,1 | 4,4 | -6,8% | ↓ caindo | 🟡 Amarelo | Caiu de 4,4 pra 4,1 em 90 dias. 8 reviews de 1-2 estrelas neste mês. |
| NPS interno (equipe) | 42 | 58 | -27,6% | ↓ caindo | 🔴 Vermelho | 2 pessoas pediram desligamento em julho. Equipe estressada com fluxo. |
| Absenteísmo (dias) | 11 | 4 | +175% | ↑ subindo | 🔴 Vermelho | Média era 4 dias/mês. Julho: 11. Concentrado em 2 pessoas específicas. |
| Quebra de estoque (%) | 6,8% | 3,2% | +112% | → estável | 🔴 Vermelho | Compra desalinhada com demanda. Cupuaçu esgota, sorbet manga sobra. |
| % bowls âncora vs mix | 38% | 52% | -27% | ↓ caindo | 🟡 Amarelo | Cliente migrando pro produto mais barato. Perde margem. |
| Reclamações formais | 12 | 5 | +140% | ↑ subindo | 🔴 Vermelho | 8 sobre fila, 3 sobre atendimento, 1 sobre sabor. |
| Vendas horário-pico (%) | 68% | 48% | +41,7% | → estável | 🟡 Amarelo | 68% do fatur. entre 18-22h. Horário 14-17h subutilizado. |

### Aba 2 · Contexto operacional (últimos 30 dias)

| Evento | O que aconteceu |
|---|---|
| Novo produto | Bowl de Cupuaçu lançado 03/jul. Sucesso — está esgotando toda tarde. Não repuseram estoque a tempo. |
| Saída de funcionário | Ana (atendente âncora, 3 anos de casa) pediu desligamento em 08/jul. Estresse com fluxo. |
| Saída de funcionário | Rodrigo (auxiliar de cozinha) pediu desligamento em 22/jul. Foi trabalhar num concorrente. |
| Novo funcionário | Bruno começou em 25/jul (atendente). Zero treinamento formal — entrou direto no fluxo. |
| Reforma no shopping | Corredor da praça de alimentação em obra dias 12-19/jul. Fluxo caiu 40% na semana. |
| Ação promocional local | Combo 'happy hour 15h-17h' testado dias 20-26/jul. Sem resultado (não divulgaram). |
| Feedback do gerente | Roberta disse na última call: "estou apagando incêndio, não consigo pensar em plano nenhum". |

### Aba 3 · Série diária (31 dias de julho/2026)

| Data | Faturamento | Ticket médio | Clientes | Cupuaçu (unid) | Sorbet (unid) | Nota Google | Absent. | Reclamações |
|---|---|---|---|---|---|---|---|---|
| 2026-07-01 | R$ 4.500 | R$ 22,00 | 200 | 0 | 70 | 4,40 | 0 | 0 |
| 2026-07-02 | R$ 4.500 | R$ 21,85 | 202 | 0 | 70 | 4,39 | 0 | 0 |
| 2026-07-03 | R$ 4.500 | R$ 21,70 | 206 | 22 | 63 | 4,38 | 0 | 0 |
| 2026-07-04 | R$ 6.075 | R$ 21,43 | 282 | 33 | 85 | 4,37 | 0 | 1 |
| 2026-07-05 | R$ 6.075 | R$ 21,24 | 286 | 35 | 86 | 4,36 | 0 | 1 |
| 2026-07-06 | R$ 4.500 | R$ 21,05 | 215 | 26 | 64 | 4,35 | 0 | 0 |
| 2026-07-07 | R$ 4.500 | R$ 20,86 | 218 | 27 | 65 | 4,34 | 0 | 0 |
| 2026-07-08 | R$ 4.500 | R$ 20,67 | 221 | 29 | 65 | 4,33 | 1 | 0 |
| 2026-07-09 | R$ 4.500 | R$ 20,48 | 224 | 30 | 66 | 4,32 | 1 | 1 |
| 2026-07-10 | R$ 4.500 | R$ 20,29 | 227 | 31 | 67 | 4,31 | 1 | 0 |
| 2026-07-11 | R$ 6.075 | R$ 20,10 | 310 | 43 | 91 | 4,30 | 0 | 1 |
| 2026-07-12 | R$ 3.645 | R$ 19,91 | 188 | 26 | 55 | 4,29 | 0 | 2 |
| 2026-07-13 | R$ 2.700 | R$ 19,72 | 141 | 21 | 40 | 4,28 | 0 | 1 |
| 2026-07-14 | R$ 2.700 | R$ 19,53 | 143 | 21 | 41 | 4,27 | 0 | 1 |
| 2026-07-15 | R$ 2.700 | R$ 19,34 | 145 | 22 | 41 | 4,26 | 0 | 1 |
| 2026-07-16 | R$ 2.700 | R$ 19,15 | 147 | 23 | 42 | 4,25 | 1 | 1 |
| 2026-07-17 | R$ 2.700 | R$ 18,96 | 148 | 24 | 42 | 4,24 | 1 | 1 |
| 2026-07-18 | R$ 3.645 | R$ 18,77 | 203 | 31 | 58 | 4,23 | 0 | 2 |
| 2026-07-19 | R$ 3.645 | R$ 18,58 | 205 | 31 | 59 | 4,22 | 0 | 2 |
| 2026-07-20 | R$ 4.500 | R$ 18,39 | 257 | 44 | 72 | 4,21 | 0 | 0 |
| 2026-07-21 | R$ 4.500 | R$ 18,20 | 260 | 32 | 78 | 4,20 | 0 | 0 |
| 2026-07-22 | R$ 4.500 | R$ 18,01 | 263 | 32 | 79 | 4,19 | 1 | 0 |
| 2026-07-23 | R$ 4.500 | R$ 17,82 | 266 | 32 | 80 | 4,18 | 1 | 1 |
| 2026-07-24 | R$ 4.500 | R$ 17,63 | 269 | 32 | 81 | 4,17 | 1 | 0 |
| 2026-07-25 | R$ 5.164 | R$ 17,44 | 312 | 32 | 96 | 4,16 | 0 | 1 |
| 2026-07-26 | R$ 5.164 | R$ 17,25 | 315 | 32 | 97 | 4,15 | 0 | 2 |
| 2026-07-27 | R$ 3.825 | R$ 17,06 | 236 | 32 | 69 | 4,12 | 0 | 1 |
| 2026-07-28 | R$ 4.500 | R$ 16,87 | 281 | 32 | 85 | 4,11 | 1 | 1 |
| 2026-07-29 | R$ 4.500 | R$ 16,68 | 284 | 32 | 86 | 4,10 | 1 | 1 |
| 2026-07-30 | R$ 4.500 | R$ 16,49 | 287 | 32 | 87 | 4,09 | 1 | 1 |
| 2026-07-31 | R$ 4.500 | R$ 16,30 | 290 | 32 | 88 | 4,08 | 1 | 1 |

### O que o supervisor precisa decidir
1. Reter Roberta ou trocar de gerência? (Ela é boa, mas está sobrecarregada)
2. Como preencher rapidamente as 2 vagas? (Bruno sozinho não dá conta)
3. Como recuperar o ticket médio? (Está R$ 6 abaixo do benchmark)
4. Reagir ao concorrente que aliciou o Rodrigo? (Sinal de guerra)
