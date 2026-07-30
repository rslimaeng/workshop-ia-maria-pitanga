# Prompt · Health check de loja (Iguatemi Fortaleza)

> Copia daqui até o fim e cola no Claude, Kimi ou DeepSeek. Os dados da loja já vêm inline no final do prompt — funciona sem upload da planilha.

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

Vou anexar os dados de 30 dias no fim deste prompt, com métricas x
benchmark e contexto qualitativo (eventos recentes: saídas, novo produto,
reforma no shopping, etc).

# TAREFA
Gere um **Artifact HTML self-contained** (uma página, imprimível A4) chamado
**"Health Check · Loja Iguatemi Fortaleza"** com estas 5 seções:

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

## 3. TOP-3 ALAVANCAS PRIORITÁRIAS
3 cards grandes, um pra cada alavanca. Cada card com:
- Nome da alavanca (verbo no infinitivo — "Estabilizar equipe", "Recuperar
  ticket médio", "Ajustar mix e compra")
- Impacto esperado em métrica específica (ex: "ticket médio de R$16,20 pra
  R$19+ em 45 dias")
- 3-4 ações concretas com responsável e prazo
- Investimento estimado (baixo/médio/alto)

Priorize pelo efeito cascata (o que resolve outros problemas de tabela).

## 4. PLANO DE 30 DIAS
Cronograma semana a semana (S1, S2, S3, S4) com 2-3 ações concretas por
semana, cada uma amarrada a uma das 3 alavancas. Formato de gantt visual
horizontal ou tabela com barras.

## 5. PARECER EXECUTIVO ASSINADO
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

### Indicadores × benchmark da rede

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

### Contexto operacional (últimos 30 dias)

| Evento | O que aconteceu |
|---|---|
| Novo produto | Bowl de Cupuaçu lançado 03/jul. Sucesso — está esgotando toda tarde. Não repuseram estoque a tempo. |
| Saída de funcionário | Ana (atendente âncora, 3 anos de casa) pediu desligamento em 08/jul. Estresse com fluxo. |
| Saída de funcionário | Rodrigo (auxiliar de cozinha) pediu desligamento em 22/jul. Foi trabalhar num concorrente. |
| Novo funcionário | Bruno começou em 25/jul (atendente). Zero treinamento formal — entrou direto no fluxo. |
| Reforma no shopping | Corredor da praça de alimentação em obra dias 12-19/jul. Fluxo caiu 40% na semana. |
| Ação promocional local | Combo 'happy hour 15h-17h' testado dias 20-26/jul. Sem resultado (não divulgaram). |
| Feedback do gerente | Roberta disse na última call: "estou apagando incêndio, não consigo pensar em plano nenhum". |

### O que o supervisor precisa decidir
1. Reter Roberta ou trocar de gerência? (Ela é boa, mas está sobrecarregada)
2. Como preencher rapidamente as 2 vagas? (Bruno sozinho não dá conta)
3. Como recuperar o ticket médio? (Está R$ 6 abaixo do benchmark)
4. Reagir ao concorrente que aliciou o Rodrigo? (Sinal de guerra)
