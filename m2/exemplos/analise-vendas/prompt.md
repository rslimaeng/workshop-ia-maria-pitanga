# Prompt · Analise executiva de vendas · 20 lojas × 30 dias

> Copia daqui até o fim e cola no Claude, Kimi ou DeepSeek. A base completa
> (600 linhas) já vem inline no final — funciona sem upload. Se preferir,
> faça upload de `insumo-vendas-20-lojas-30-dias.xlsx` (3 abas: vendas diarias,
> dicionario de lojas, contexto de julho).

---

# PAPEL
Você é um consultor senior de business intelligence com 12 anos apoiando
redes de food service no Brasil. Trabalhou no Grupo Mateus, Cacau Show e
Sodexo. Sua especialidade é abrir planilha de 600 linhas e sair com 5
achados que valem R$ 500 mil em decisao pro dono da rede — não com relatorio
de 40 paginas cheio de KPI. Você odeia grafico de pizza inutil e frase
generica tipo "vendas apresentam variacao".

# CONTEXTO
Sou supervisor regional da Maria Pitanga, rede de +200 franquias de acai e
gelatos no Nordeste. Recebi essa manha a base consolidada de vendas de 20
lojas ao longo de julho/2026 (30 dias × 20 lojas = 600 registros diarios).
Preciso apresentar amanha ao comite executivo um parecer de negocio com o
que aconteceu no mes, onde estao os 5 insights que mudam decisao, e onde a
franqueadora deve investir na proxima quinzena.

O comite tem 8 pessoas — CEO, diretor comercial, marketing, financeiro,
operacoes, expansao, CFO e conselho consultivo. Todos ocupados. Se o
parecer nao entrega valor nas primeiras 2 paginas, ninguem le o resto.

Alguns pontos de contexto embutidos nos dados (aba 3 do xlsx):
- Julho e ferias escolares — trafego +18% no fim de semana nas capitais
- Bowl Cupuacu Sertanejo lancado em 03/jul, vende em 18 das 20 lojas
- MP009 Petrolina e MP019 Cariri nao venderam cupuacu (falha logistica interior)
- MP020 Iguatemi Fortaleza teve praca em obra dias 12-19/jul
- Um concorrente local abriu em Sobral (MP011) em 15/jul
- Benchmark da rede: R$ 22,40 ticket medio, R$ 3.940 faturamento/dia/loja

# TAREFA
Gere um **Artifact HTML self-contained** no formato de **parecer executivo
estilo revista de negocios** (referencia visual: HSM Management, Harvard
Business Review). Uma pagina web, respiro editorial, tipografia elegante,
imprimivel A4. Titulo: **"Radar Comercial · Julho/2026 · 20 lojas"**.

Estrutura obrigatoria em 6 blocos numerados (com numeracao mono editorial
tipo "01" grande ao lado do titulo):

## 01 · CAPA
- Kicker: "Parecer Executivo · Maria Pitanga · comite comercial"
- Titulo grande: um enunciado que resume o mes em 1 frase de impacto
  (ex: "Rede cresceu 4% mas 3 lojas concentram 80% da alavanca")
- Sub: periodo, quem assina, "leitura em 4 minutos"
- Big numbers em linha: faturamento total do mes, ticket medio, top loja, loja em queda

## 02 · SUMARIO EM 3 LINHAS
3 paragrafos curtos, cada um comecando por: "**O que aconteceu:** ...",
"**O que isso significa:** ...", "**O que fazer agora:** ...".
Nada de "vale destacar". Frase direta.

## 03 · OS 5 INSIGHTS QUE MUDAM DECISAO
Cards grandes, um por insight, cada um com:
- Numero mono grande (01, 02, 03, 04, 05)
- Titulo curto e concreto (verbo + substantivo)
- Big number destacado (o dado que sustenta)
- 2-3 linhas de leitura de negocio
- 1 acao concreta recomendada com prazo

Priorize por impacto financeiro. Nao coloque insight tipo "sabado vende
mais que segunda" (obvio). Priorize:
- Loja que quebrou o padrao (subindo ou caindo)
- Cluster que revela oportunidade (tipo × cidade × dia da semana)
- Produto que responde melhor em contexto X vs Y
- Alavanca escondida (mix, sazonalidade, cluster)

## 04 · RANKING DAS 20 LOJAS
Tabela com barras horizontais visuais (usar SVG inline ou div com width%).
Colunas: posicao, loja, cidade, faturamento total do mes, delta vs
benchmark (%), status semantico (verde/amarelo/vermelho com dot 6px). Ordem:
maior faturamento pro menor. Barras da barra proporcional coloridas em roxo
para as top 5, cinza para as demais.

## 05 · MAPA DE CALOR · CUPUACU POR LOJA
Grid de 20 quadrados (5×4), um por loja, cor variando por total de unidades
vendidas de cupuacu no mes (roxo mais escuro = mais vendas, cinza claro = 0).
Cada quadrado tem o codigo da loja e o numero total. Destacar visualmente
MP009 e MP019 (as duas que ficaram em 0) — mostrar como "gap de execucao".

## 06 · RECOMENDACAO EXECUTIVA (fecha o parecer)
Um card grande, warm, com:
- **Onde investir na proxima quinzena** (1-2 linhas concretas)
- **O que parar de fazer** (1 linha)
- **A pergunta que o comite precisa responder** (1 linha)
- Assinatura: "Marcio Vasconcelos · Supervisor Regional CE-Norte · Maria Pitanga"

# ESTILO DE SAIDA
- Pagina HTML self-contained (tudo inline)
- Formato A4 imprimivel, respiro editorial generoso (padding 40-60px)
- Fundo **off-white creme #F0EEE6**, texto **#141413**
- Accent **roxo Maria Pitanga #6B2E7A**
- Cores semanticas: verde `#2E7D32`, amarelo `#B8860B`, vermelho `#B85C5C`
- Tipografia: serif elegante pro titulo (opcional: usar font-family georgia
  ou similar via system-font stack), Inter no corpo, JetBrains Mono nos
  numeros e kickers
- Big numbers grandes (60-80px), texto ao lado com kicker mono
- Cards com sombra suave, sem borda grossa colorida
- Numeracao dos blocos: "01", "02"... em mono 40px, roxo, ao lado do titulo
- **NAO dark mode**, **NAO gradientes**, **NAO emoji decorativo**
- **NAO** usar Chart.js, ApexCharts ou lib externa — tudo em SVG inline ou CSS
- `@media print` embutido — tudo expandido pra imprimir A4

# LINGUAGEM
Portugues-BR executivo. Direto. Zero "vale destacar", "e importante notar",
"nota-se que". Se pra falar, fala. Voce esta escrevendo pra um CEO ocupado
que decide em 5 min se o parecer merece 20 min de leitura.

# ANTES DE GERAR
Confirme em 3 bullets:
(a) Sua leitura macro do mes em 1 frase (o que aconteceu)
(b) Quais 2-3 lojas voce ja identificou como "quebradoras de padrao"
    (subindo ou caindo forte) e por que
(c) O insight nao-obvio que voce ja detectou (nao pode ser "shopping vende
    mais que interior" — precisa ser algo que so uma leitura cuidadosa revela)

Espere meu OK. **So depois** gera o Artifact HTML completo.

---

## DADOS · Vendas diarias · 20 lojas × 30 dias (600 registros)

**Periodo:** 01/07/2026 a 30/07/2026 (julho, 30 dias)
**Total de lojas:** 20 (8 shoppings, 6 rua, 6 interior)
**Distribuicao geografica:** Nordeste — CE (4), PE (2), BA (2), RN (2),
PB (1), MA (1), PI (1), SE (1), AL (1), PA (1), AM (1)
**Colunas:** Data · Codigo · Cidade · UF · Tipo · Faturamento (R$) ·
Ticket medio (R$) · Clientes · Bowls · Sorbet · Cupuacu (unid)

### Dicionario das lojas (perfil comercial interno)

| Codigo | Cidade | UF | Tipo | Perfil |
|---|---|---|---|---|
| MP001 | Fortaleza | CE | shopping | Alto desempenho consolidado |
| MP002 | Fortaleza | CE | rua | ★ Crescimento acelerado (30d) |
| MP003 | Recife | PE | shopping | Regular, dentro do benchmark |
| MP004 | Recife | PE | rua | Regular, dentro do benchmark |
| MP005 | Salvador | BA | shopping | ★ Queda acentuada (30d) - sinal vermelho |
| MP006 | Salvador | BA | rua | Abaixo do benchmark, estavel |
| MP007 | Natal | RN | shopping | ★ Crescimento acelerado (30d) |
| MP008 | Joao Pessoa | PB | rua | Regular, dentro do benchmark |
| MP009 | Petrolina | PE | interior | Abaixo do benchmark, estavel |
| MP010 | Juazeiro | BA | interior | Abaixo do benchmark, estavel |
| MP011 | Sobral | CE | interior | ★ Queda acentuada (30d) - sinal vermelho |
| MP012 | Mossoro | RN | interior | Regular, dentro do benchmark |
| MP013 | Sao Luis | MA | shopping | Regular, dentro do benchmark |
| MP014 | Teresina | PI | shopping | ★ Crescimento acelerado (30d) |
| MP015 | Aracaju | SE | shopping | Regular, dentro do benchmark |
| MP016 | Maceio | AL | rua | Regular, dentro do benchmark |
| MP017 | Belem | PA | shopping | Alto desempenho consolidado |
| MP018 | Manaus | AM | shopping | Regular, dentro do benchmark |
| MP019 | Cariri | CE | interior | Abaixo do benchmark, estavel |
| MP020 | Iguatemi FTL | CE | shopping | Regular, dentro do benchmark |

### Base completa (600 linhas · uma linha por loja/dia)

| Data | Codigo | Cidade | UF | Tipo | Faturamento | Ticket | Clientes | Bowls | Sorbet | Cupuacu |
|---|---|---|---|---|---|---|---|---|---|---|
| 01/07/2026 | MP001 | Fortaleza | CE | shopping | R$ 6180.11 | R$ 22.64 | 272 | 204 | 123 | 61 |
| 02/07/2026 | MP001 | Fortaleza | CE | shopping | R$ 6233.60 | R$ 26.04 | 239 | 181 | 98 | 43 |
| 03/07/2026 | MP001 | Fortaleza | CE | shopping | R$ 6412.62 | R$ 24.52 | 261 | 187 | 114 | 54 |
| 04/07/2026 | MP001 | Fortaleza | CE | shopping | R$ 7857.85 | R$ 23.40 | 335 | 295 | 129 | 70 |
| 05/07/2026 | MP001 | Fortaleza | CE | shopping | R$ 8344.59 | R$ 25.28 | 330 | 248 | 153 | 78 |
| 06/07/2026 | MP001 | Fortaleza | CE | shopping | R$ 4883.66 | R$ 22.90 | 213 | 174 | 75 | 50 |
| 07/07/2026 | MP001 | Fortaleza | CE | shopping | R$ 6420.79 | R$ 25.40 | 252 | 226 | 90 | 60 |
| 08/07/2026 | MP001 | Fortaleza | CE | shopping | R$ 6054.69 | R$ 25.79 | 234 | 209 | 89 | 59 |
| 09/07/2026 | MP001 | Fortaleza | CE | shopping | R$ 6273.60 | R$ 22.72 | 276 | 208 | 121 | 50 |
| 10/07/2026 | MP001 | Fortaleza | CE | shopping | R$ 6435.98 | R$ 22.94 | 280 | 227 | 110 | 60 |
| 11/07/2026 | MP001 | Fortaleza | CE | shopping | R$ 7531.79 | R$ 23.36 | 322 | 275 | 112 | 80 |
| 12/07/2026 | MP001 | Fortaleza | CE | shopping | R$ 7977.61 | R$ 23.21 | 343 | 275 | 169 | 74 |
| 13/07/2026 | MP001 | Fortaleza | CE | shopping | R$ 5680.18 | R$ 25.05 | 226 | 194 | 91 | 59 |
| 14/07/2026 | MP001 | Fortaleza | CE | shopping | R$ 6376.12 | R$ 23.44 | 272 | 200 | 114 | 52 |
| 15/07/2026 | MP001 | Fortaleza | CE | shopping | R$ 5565.20 | R$ 26.24 | 212 | 178 | 102 | 52 |
| 16/07/2026 | MP001 | Fortaleza | CE | shopping | R$ 5830.21 | R$ 26.13 | 223 | 174 | 102 | 45 |
| 17/07/2026 | MP001 | Fortaleza | CE | shopping | R$ 6978.29 | R$ 23.57 | 296 | 265 | 110 | 71 |
| 18/07/2026 | MP001 | Fortaleza | CE | shopping | R$ 7250.32 | R$ 26.45 | 274 | 209 | 134 | 50 |
| 19/07/2026 | MP001 | Fortaleza | CE | shopping | R$ 7045.70 | R$ 25.00 | 281 | 238 | 129 | 57 |
| 20/07/2026 | MP001 | Fortaleza | CE | shopping | R$ 4938.58 | R$ 26.44 | 186 | 166 | 67 | 51 |
| 21/07/2026 | MP001 | Fortaleza | CE | shopping | R$ 5278.88 | R$ 25.37 | 208 | 177 | 90 | 46 |
| 22/07/2026 | MP001 | Fortaleza | CE | shopping | R$ 6182.31 | R$ 22.98 | 269 | 217 | 115 | 69 |
| 23/07/2026 | MP001 | Fortaleza | CE | shopping | R$ 6519.42 | R$ 23.57 | 276 | 214 | 131 | 67 |
| 24/07/2026 | MP001 | Fortaleza | CE | shopping | R$ 7488.53 | R$ 23.71 | 315 | 270 | 132 | 67 |
| 25/07/2026 | MP001 | Fortaleza | CE | shopping | R$ 8263.78 | R$ 24.65 | 335 | 290 | 147 | 69 |
| 26/07/2026 | MP001 | Fortaleza | CE | shopping | R$ 7445.92 | R$ 22.62 | 329 | 309 | 130 | 95 |
| 27/07/2026 | MP001 | Fortaleza | CE | shopping | R$ 4848.18 | R$ 22.77 | 212 | 200 | 81 | 49 |
| 28/07/2026 | MP001 | Fortaleza | CE | shopping | R$ 5959.89 | R$ 22.81 | 261 | 234 | 105 | 58 |
| 29/07/2026 | MP001 | Fortaleza | CE | shopping | R$ 5944.53 | R$ 24.70 | 240 | 202 | 86 | 55 |
| 30/07/2026 | MP001 | Fortaleza | CE | shopping | R$ 5566.37 | R$ 24.65 | 225 | 181 | 110 | 47 |
| 01/07/2026 | MP002 | Fortaleza | CE | rua | R$ 3994.24 | R$ 20.48 | 195 | 159 | 82 | 39 |
| 02/07/2026 | MP002 | Fortaleza | CE | rua | R$ 3373.02 | R$ 19.48 | 173 | 137 | 82 | 35 |
| 03/07/2026 | MP002 | Fortaleza | CE | rua | R$ 3768.72 | R$ 20.42 | 184 | 155 | 65 | 48 |
| 04/07/2026 | MP002 | Fortaleza | CE | rua | R$ 4308.71 | R$ 19.16 | 224 | 179 | 108 | 44 |
| 05/07/2026 | MP002 | Fortaleza | CE | rua | R$ 5365.31 | R$ 20.23 | 265 | 228 | 101 | 69 |
| 06/07/2026 | MP002 | Fortaleza | CE | rua | R$ 2972.89 | R$ 18.71 | 158 | 126 | 69 | 34 |
| 07/07/2026 | MP002 | Fortaleza | CE | rua | R$ 4029.91 | R$ 20.55 | 196 | 160 | 103 | 43 |
| 08/07/2026 | MP002 | Fortaleza | CE | rua | R$ 3712.62 | R$ 21.16 | 175 | 130 | 79 | 35 |
| 09/07/2026 | MP002 | Fortaleza | CE | rua | R$ 3830.02 | R$ 19.29 | 198 | 168 | 69 | 46 |
| 10/07/2026 | MP002 | Fortaleza | CE | rua | R$ 4930.01 | R$ 20.16 | 244 | 203 | 80 | 62 |
| 11/07/2026 | MP002 | Fortaleza | CE | rua | R$ 5765.78 | R$ 21.36 | 269 | 220 | 135 | 61 |
| 12/07/2026 | MP002 | Fortaleza | CE | rua | R$ 4876.84 | R$ 19.68 | 247 | 184 | 102 | 59 |
| 13/07/2026 | MP002 | Fortaleza | CE | rua | R$ 3264.39 | R$ 20.91 | 156 | 125 | 68 | 39 |
| 14/07/2026 | MP002 | Fortaleza | CE | rua | R$ 4600.31 | R$ 20.18 | 227 | 181 | 112 | 47 |
| 15/07/2026 | MP002 | Fortaleza | CE | rua | R$ 4620.28 | R$ 20.25 | 228 | 197 | 89 | 47 |
| 16/07/2026 | MP002 | Fortaleza | CE | rua | R$ 4279.49 | R$ 20.01 | 213 | 173 | 108 | 55 |
| 17/07/2026 | MP002 | Fortaleza | CE | rua | R$ 4380.91 | R$ 18.99 | 230 | 198 | 93 | 51 |
| 18/07/2026 | MP002 | Fortaleza | CE | rua | R$ 5054.11 | R$ 21.25 | 237 | 190 | 94 | 55 |
| 19/07/2026 | MP002 | Fortaleza | CE | rua | R$ 5506.75 | R$ 20.27 | 271 | 241 | 98 | 61 |
| 20/07/2026 | MP002 | Fortaleza | CE | rua | R$ 3899.50 | R$ 19.16 | 203 | 169 | 80 | 44 |
| 21/07/2026 | MP002 | Fortaleza | CE | rua | R$ 4208.75 | R$ 20.81 | 202 | 153 | 82 | 49 |
| 22/07/2026 | MP002 | Fortaleza | CE | rua | R$ 4973.84 | R$ 18.63 | 266 | 200 | 117 | 63 |
| 23/07/2026 | MP002 | Fortaleza | CE | rua | R$ 4896.38 | R$ 21.21 | 230 | 173 | 108 | 53 |
| 24/07/2026 | MP002 | Fortaleza | CE | rua | R$ 5461.51 | R$ 20.36 | 268 | 244 | 117 | 58 |
| 25/07/2026 | MP002 | Fortaleza | CE | rua | R$ 6392.58 | R$ 19.36 | 330 | 301 | 122 | 75 |
| 26/07/2026 | MP002 | Fortaleza | CE | rua | R$ 5441.34 | R$ 18.74 | 290 | 230 | 135 | 66 |
| 27/07/2026 | MP002 | Fortaleza | CE | rua | R$ 4161.52 | R$ 19.05 | 218 | 175 | 103 | 48 |
| 28/07/2026 | MP002 | Fortaleza | CE | rua | R$ 5151.24 | R$ 21.11 | 244 | 185 | 100 | 48 |
| 29/07/2026 | MP002 | Fortaleza | CE | rua | R$ 4171.89 | R$ 20.87 | 199 | 160 | 94 | 48 |
| 30/07/2026 | MP002 | Fortaleza | CE | rua | R$ 4837.11 | R$ 19.77 | 244 | 171 | 110 | 53 |
| 01/07/2026 | MP003 | Recife | PE | shopping | R$ 5704.10 | R$ 24.68 | 231 | 203 | 101 | 36 |
| 02/07/2026 | MP003 | Recife | PE | shopping | R$ 4735.05 | R$ 23.75 | 199 | 183 | 81 | 40 |
| 03/07/2026 | MP003 | Recife | PE | shopping | R$ 6552.54 | R$ 23.36 | 280 | 205 | 130 | 44 |
| 04/07/2026 | MP003 | Recife | PE | shopping | R$ 7383.22 | R$ 24.13 | 305 | 239 | 149 | 53 |
| 05/07/2026 | MP003 | Recife | PE | shopping | R$ 7351.54 | R$ 26.37 | 278 | 256 | 108 | 43 |
| 06/07/2026 | MP003 | Recife | PE | shopping | R$ 4670.95 | R$ 23.84 | 195 | 181 | 79 | 40 |
| 07/07/2026 | MP003 | Recife | PE | shopping | R$ 5587.82 | R$ 23.59 | 236 | 188 | 120 | 41 |
| 08/07/2026 | MP003 | Recife | PE | shopping | R$ 5647.52 | R$ 23.41 | 241 | 207 | 109 | 38 |
| 09/07/2026 | MP003 | Recife | PE | shopping | R$ 5568.59 | R$ 23.43 | 237 | 170 | 103 | 32 |
| 10/07/2026 | MP003 | Recife | PE | shopping | R$ 6502.92 | R$ 26.33 | 246 | 200 | 96 | 38 |
| 11/07/2026 | MP003 | Recife | PE | shopping | R$ 7540.62 | R$ 24.64 | 306 | 251 | 158 | 57 |
| 12/07/2026 | MP003 | Recife | PE | shopping | R$ 6238.51 | R$ 26.31 | 237 | 174 | 111 | 34 |
| 13/07/2026 | MP003 | Recife | PE | shopping | R$ 4662.44 | R$ 23.77 | 196 | 164 | 85 | 31 |
| 14/07/2026 | MP003 | Recife | PE | shopping | R$ 5295.58 | R$ 23.54 | 224 | 173 | 116 | 39 |
| 15/07/2026 | MP003 | Recife | PE | shopping | R$ 5247.99 | R$ 25.36 | 206 | 181 | 86 | 34 |
| 16/07/2026 | MP003 | Recife | PE | shopping | R$ 4663.33 | R$ 25.14 | 185 | 142 | 82 | 31 |
| 17/07/2026 | MP003 | Recife | PE | shopping | R$ 6295.39 | R$ 23.72 | 265 | 208 | 113 | 40 |
| 18/07/2026 | MP003 | Recife | PE | shopping | R$ 6428.47 | R$ 23.04 | 279 | 245 | 99 | 51 |
| 19/07/2026 | MP003 | Recife | PE | shopping | R$ 7413.51 | R$ 24.95 | 297 | 239 | 120 | 40 |
| 20/07/2026 | MP003 | Recife | PE | shopping | R$ 4193.96 | R$ 24.23 | 173 | 148 | 71 | 29 |
| 21/07/2026 | MP003 | Recife | PE | shopping | R$ 5127.82 | R$ 23.38 | 219 | 192 | 80 | 41 |
| 22/07/2026 | MP003 | Recife | PE | shopping | R$ 4787.77 | R$ 22.87 | 209 | 176 | 85 | 33 |
| 23/07/2026 | MP003 | Recife | PE | shopping | R$ 5597.39 | R$ 25.48 | 219 | 176 | 105 | 32 |
| 24/07/2026 | MP003 | Recife | PE | shopping | R$ 5297.46 | R$ 23.50 | 225 | 196 | 84 | 34 |
| 25/07/2026 | MP003 | Recife | PE | shopping | R$ 6621.19 | R$ 25.01 | 264 | 213 | 100 | 42 |
| 26/07/2026 | MP003 | Recife | PE | shopping | R$ 6344.64 | R$ 25.11 | 252 | 200 | 90 | 43 |
| 27/07/2026 | MP003 | Recife | PE | shopping | R$ 4002.67 | R$ 24.21 | 165 | 139 | 56 | 27 |
| 28/07/2026 | MP003 | Recife | PE | shopping | R$ 4638.67 | R$ 23.52 | 197 | 169 | 90 | 36 |
| 29/07/2026 | MP003 | Recife | PE | shopping | R$ 5409.14 | R$ 26.41 | 204 | 184 | 74 | 41 |
| 30/07/2026 | MP003 | Recife | PE | shopping | R$ 5340.59 | R$ 25.36 | 210 | 183 | 79 | 37 |
| 01/07/2026 | MP004 | Recife | PE | rua | R$ 3724.12 | R$ 20.78 | 179 | 140 | 82 | 25 |
| 02/07/2026 | MP004 | Recife | PE | rua | R$ 3512.33 | R$ 20.85 | 168 | 141 | 69 | 26 |
| 03/07/2026 | MP004 | Recife | PE | rua | R$ 3513.51 | R$ 19.31 | 181 | 138 | 79 | 27 |
| 04/07/2026 | MP004 | Recife | PE | rua | R$ 4036.39 | R$ 19.14 | 210 | 184 | 86 | 31 |
| 05/07/2026 | MP004 | Recife | PE | rua | R$ 4321.98 | R$ 20.14 | 214 | 164 | 99 | 32 |
| 06/07/2026 | MP004 | Recife | PE | rua | R$ 3170.80 | R$ 20.27 | 156 | 141 | 60 | 30 |
| 07/07/2026 | MP004 | Recife | PE | rua | R$ 3302.39 | R$ 18.42 | 179 | 150 | 68 | 33 |
| 08/07/2026 | MP004 | Recife | PE | rua | R$ 3770.00 | R$ 19.74 | 190 | 163 | 83 | 33 |
| 09/07/2026 | MP004 | Recife | PE | rua | R$ 3171.96 | R$ 19.10 | 166 | 123 | 82 | 23 |
| 10/07/2026 | MP004 | Recife | PE | rua | R$ 4078.11 | R$ 19.69 | 207 | 160 | 84 | 28 |
| 11/07/2026 | MP004 | Recife | PE | rua | R$ 4549.69 | R$ 18.49 | 246 | 201 | 101 | 34 |
| 12/07/2026 | MP004 | Recife | PE | rua | R$ 4571.43 | R$ 18.83 | 242 | 181 | 119 | 34 |
| 13/07/2026 | MP004 | Recife | PE | rua | R$ 2690.01 | R$ 19.45 | 138 | 115 | 64 | 24 |
| 14/07/2026 | MP004 | Recife | PE | rua | R$ 3670.85 | R$ 19.21 | 191 | 133 | 89 | 26 |
| 15/07/2026 | MP004 | Recife | PE | rua | R$ 3807.92 | R$ 19.52 | 195 | 172 | 77 | 35 |
| 16/07/2026 | MP004 | Recife | PE | rua | R$ 3607.45 | R$ 21.44 | 168 | 119 | 80 | 21 |
| 17/07/2026 | MP004 | Recife | PE | rua | R$ 3559.25 | R$ 20.54 | 173 | 136 | 82 | 28 |
| 18/07/2026 | MP004 | Recife | PE | rua | R$ 4703.13 | R$ 18.94 | 248 | 217 | 98 | 38 |
| 19/07/2026 | MP004 | Recife | PE | rua | R$ 4758.71 | R$ 21.49 | 221 | 155 | 103 | 29 |
| 20/07/2026 | MP004 | Recife | PE | rua | R$ 3013.01 | R$ 21.47 | 140 | 117 | 55 | 20 |
| 21/07/2026 | MP004 | Recife | PE | rua | R$ 3555.54 | R$ 20.41 | 174 | 140 | 63 | 30 |
| 22/07/2026 | MP004 | Recife | PE | rua | R$ 3481.94 | R$ 18.79 | 185 | 172 | 77 | 32 |
| 23/07/2026 | MP004 | Recife | PE | rua | R$ 3341.56 | R$ 19.59 | 170 | 135 | 77 | 29 |
| 24/07/2026 | MP004 | Recife | PE | rua | R$ 4212.48 | R$ 18.74 | 224 | 202 | 98 | 44 |
| 25/07/2026 | MP004 | Recife | PE | rua | R$ 4639.91 | R$ 19.79 | 234 | 216 | 87 | 40 |
| 26/07/2026 | MP004 | Recife | PE | rua | R$ 4746.94 | R$ 20.12 | 235 | 190 | 102 | 40 |
| 27/07/2026 | MP004 | Recife | PE | rua | R$ 2729.36 | R$ 21.13 | 129 | 103 | 66 | 22 |
| 28/07/2026 | MP004 | Recife | PE | rua | R$ 3190.99 | R$ 19.89 | 160 | 131 | 72 | 22 |
| 29/07/2026 | MP004 | Recife | PE | rua | R$ 3686.38 | R$ 18.98 | 194 | 160 | 71 | 30 |
| 30/07/2026 | MP004 | Recife | PE | rua | R$ 3710.34 | R$ 20.64 | 179 | 129 | 86 | 29 |
| 01/07/2026 | MP005 | Salvador | BA | shopping | R$ 5151.13 | R$ 25.36 | 203 | 174 | 79 | 36 |
| 02/07/2026 | MP005 | Salvador | BA | shopping | R$ 5841.36 | R$ 24.46 | 238 | 190 | 121 | 34 |
| 03/07/2026 | MP005 | Salvador | BA | shopping | R$ 6697.29 | R$ 23.74 | 282 | 234 | 123 | 47 |
| 04/07/2026 | MP005 | Salvador | BA | shopping | R$ 7010.93 | R$ 25.46 | 275 | 228 | 106 | 42 |
| 05/07/2026 | MP005 | Salvador | BA | shopping | R$ 6619.42 | R$ 23.01 | 287 | 209 | 132 | 42 |
| 06/07/2026 | MP005 | Salvador | BA | shopping | R$ 4823.41 | R$ 23.27 | 207 | 162 | 85 | 34 |
| 07/07/2026 | MP005 | Salvador | BA | shopping | R$ 5864.34 | R$ 24.60 | 238 | 175 | 112 | 31 |
| 08/07/2026 | MP005 | Salvador | BA | shopping | R$ 4846.94 | R$ 23.24 | 208 | 158 | 81 | 29 |
| 09/07/2026 | MP005 | Salvador | BA | shopping | R$ 5691.53 | R$ 24.71 | 230 | 182 | 114 | 40 |
| 10/07/2026 | MP005 | Salvador | BA | shopping | R$ 5775.97 | R$ 25.96 | 222 | 183 | 97 | 35 |
| 11/07/2026 | MP005 | Salvador | BA | shopping | R$ 5956.34 | R$ 22.74 | 261 | 229 | 120 | 50 |
| 12/07/2026 | MP005 | Salvador | BA | shopping | R$ 6194.17 | R$ 22.83 | 271 | 209 | 136 | 37 |
| 13/07/2026 | MP005 | Salvador | BA | shopping | R$ 4145.67 | R$ 23.73 | 174 | 143 | 91 | 30 |
| 14/07/2026 | MP005 | Salvador | BA | shopping | R$ 4849.19 | R$ 25.64 | 189 | 149 | 76 | 29 |
| 15/07/2026 | MP005 | Salvador | BA | shopping | R$ 4588.31 | R$ 25.91 | 177 | 151 | 87 | 31 |
| 16/07/2026 | MP005 | Salvador | BA | shopping | R$ 4696.40 | R$ 25.44 | 184 | 153 | 93 | 27 |
| 17/07/2026 | MP005 | Salvador | BA | shopping | R$ 5373.93 | R$ 23.16 | 232 | 166 | 108 | 28 |
| 18/07/2026 | MP005 | Salvador | BA | shopping | R$ 5682.20 | R$ 24.87 | 228 | 172 | 103 | 36 |
| 19/07/2026 | MP005 | Salvador | BA | shopping | R$ 5926.68 | R$ 24.32 | 243 | 221 | 91 | 48 |
| 20/07/2026 | MP005 | Salvador | BA | shopping | R$ 3739.25 | R$ 25.13 | 148 | 128 | 69 | 25 |
| 21/07/2026 | MP005 | Salvador | BA | shopping | R$ 4343.29 | R$ 26.10 | 166 | 132 | 86 | 23 |
| 22/07/2026 | MP005 | Salvador | BA | shopping | R$ 3928.24 | R$ 25.48 | 154 | 123 | 71 | 21 |
| 23/07/2026 | MP005 | Salvador | BA | shopping | R$ 4225.17 | R$ 25.28 | 167 | 147 | 76 | 29 |
| 24/07/2026 | MP005 | Salvador | BA | shopping | R$ 4101.51 | R$ 22.70 | 180 | 141 | 81 | 26 |
| 25/07/2026 | MP005 | Salvador | BA | shopping | R$ 4560.53 | R$ 26.31 | 173 | 151 | 76 | 34 |
| 26/07/2026 | MP005 | Salvador | BA | shopping | R$ 5551.70 | R$ 25.18 | 220 | 159 | 105 | 34 |
| 27/07/2026 | MP005 | Salvador | BA | shopping | R$ 3154.02 | R$ 25.09 | 125 | 103 | 63 | 21 |
| 28/07/2026 | MP005 | Salvador | BA | shopping | R$ 3779.22 | R$ 24.47 | 154 | 114 | 65 | 21 |
| 29/07/2026 | MP005 | Salvador | BA | shopping | R$ 3730.90 | R$ 25.90 | 144 | 119 | 56 | 22 |
| 30/07/2026 | MP005 | Salvador | BA | shopping | R$ 3883.11 | R$ 25.73 | 150 | 123 | 66 | 23 |
| 01/07/2026 | MP006 | Salvador | BA | rua | R$ 2767.42 | R$ 21.50 | 128 | 103 | 54 | 23 |
| 02/07/2026 | MP006 | Salvador | BA | rua | R$ 2999.35 | R$ 20.14 | 148 | 113 | 69 | 21 |
| 03/07/2026 | MP006 | Salvador | BA | rua | R$ 3528.05 | R$ 20.40 | 172 | 139 | 84 | 28 |
| 04/07/2026 | MP006 | Salvador | BA | rua | R$ 4142.62 | R$ 19.80 | 209 | 165 | 104 | 37 |
| 05/07/2026 | MP006 | Salvador | BA | rua | R$ 3855.17 | R$ 19.17 | 201 | 157 | 80 | 31 |
| 06/07/2026 | MP006 | Salvador | BA | rua | R$ 2216.67 | R$ 21.58 | 102 | 88 | 47 | 15 |
| 07/07/2026 | MP006 | Salvador | BA | rua | R$ 3120.37 | R$ 19.99 | 156 | 132 | 69 | 24 |
| 08/07/2026 | MP006 | Salvador | BA | rua | R$ 3122.16 | R$ 21.54 | 144 | 114 | 58 | 22 |
| 09/07/2026 | MP006 | Salvador | BA | rua | R$ 3182.61 | R$ 20.03 | 158 | 147 | 62 | 27 |
| 10/07/2026 | MP006 | Salvador | BA | rua | R$ 3554.82 | R$ 19.73 | 180 | 158 | 82 | 34 |
| 11/07/2026 | MP006 | Salvador | BA | rua | R$ 3561.19 | R$ 19.36 | 183 | 166 | 65 | 33 |
| 12/07/2026 | MP006 | Salvador | BA | rua | R$ 3440.15 | R$ 20.12 | 170 | 137 | 70 | 27 |
| 13/07/2026 | MP006 | Salvador | BA | rua | R$ 2430.17 | R$ 19.43 | 125 | 101 | 47 | 20 |
| 14/07/2026 | MP006 | Salvador | BA | rua | R$ 2705.20 | R$ 20.88 | 129 | 102 | 47 | 21 |
| 15/07/2026 | MP006 | Salvador | BA | rua | R$ 3105.99 | R$ 19.64 | 158 | 141 | 61 | 32 |
| 16/07/2026 | MP006 | Salvador | BA | rua | R$ 2886.76 | R$ 18.52 | 155 | 129 | 64 | 28 |
| 17/07/2026 | MP006 | Salvador | BA | rua | R$ 3621.97 | R$ 19.81 | 182 | 149 | 79 | 31 |
| 18/07/2026 | MP006 | Salvador | BA | rua | R$ 3675.83 | R$ 20.50 | 179 | 138 | 73 | 31 |
| 19/07/2026 | MP006 | Salvador | BA | rua | R$ 3611.43 | R$ 20.62 | 175 | 156 | 67 | 34 |
| 20/07/2026 | MP006 | Salvador | BA | rua | R$ 2668.35 | R$ 19.62 | 136 | 113 | 52 | 24 |
| 21/07/2026 | MP006 | Salvador | BA | rua | R$ 3148.28 | R$ 18.51 | 170 | 133 | 64 | 29 |
| 22/07/2026 | MP006 | Salvador | BA | rua | R$ 3235.01 | R$ 20.79 | 155 | 116 | 75 | 24 |
| 23/07/2026 | MP006 | Salvador | BA | rua | R$ 3148.42 | R$ 19.82 | 158 | 143 | 60 | 24 |
| 24/07/2026 | MP006 | Salvador | BA | rua | R$ 3559.72 | R$ 19.34 | 184 | 138 | 87 | 27 |
| 25/07/2026 | MP006 | Salvador | BA | rua | R$ 3816.45 | R$ 20.94 | 182 | 131 | 84 | 29 |
| 26/07/2026 | MP006 | Salvador | BA | rua | R$ 3864.94 | R$ 19.17 | 201 | 164 | 103 | 32 |
| 27/07/2026 | MP006 | Salvador | BA | rua | R$ 2311.45 | R$ 19.22 | 120 | 96 | 42 | 21 |
| 28/07/2026 | MP006 | Salvador | BA | rua | R$ 3013.19 | R$ 18.91 | 159 | 125 | 71 | 25 |
| 29/07/2026 | MP006 | Salvador | BA | rua | R$ 2986.37 | R$ 19.76 | 151 | 126 | 55 | 22 |
| 30/07/2026 | MP006 | Salvador | BA | rua | R$ 2810.02 | R$ 19.95 | 140 | 111 | 56 | 22 |
| 01/07/2026 | MP007 | Natal | RN | shopping | R$ 6105.62 | R$ 23.70 | 257 | 234 | 111 | 61 |
| 02/07/2026 | MP007 | Natal | RN | shopping | R$ 5611.10 | R$ 25.23 | 222 | 174 | 114 | 50 |
| 03/07/2026 | MP007 | Natal | RN | shopping | R$ 6420.46 | R$ 26.08 | 246 | 205 | 91 | 59 |
| 04/07/2026 | MP007 | Natal | RN | shopping | R$ 7086.05 | R$ 25.04 | 283 | 245 | 115 | 73 |
| 05/07/2026 | MP007 | Natal | RN | shopping | R$ 7713.06 | R$ 25.83 | 298 | 269 | 111 | 78 |
| 06/07/2026 | MP007 | Natal | RN | shopping | R$ 4686.49 | R$ 24.27 | 193 | 167 | 77 | 41 |
| 07/07/2026 | MP007 | Natal | RN | shopping | R$ 5554.92 | R$ 25.47 | 218 | 158 | 100 | 44 |
| 08/07/2026 | MP007 | Natal | RN | shopping | R$ 6574.20 | R$ 24.62 | 267 | 248 | 107 | 64 |
| 09/07/2026 | MP007 | Natal | RN | shopping | R$ 6434.78 | R$ 24.43 | 263 | 237 | 107 | 63 |
| 10/07/2026 | MP007 | Natal | RN | shopping | R$ 6297.48 | R$ 26.31 | 239 | 201 | 80 | 62 |
| 11/07/2026 | MP007 | Natal | RN | shopping | R$ 8352.62 | R$ 26.38 | 316 | 295 | 129 | 79 |
| 12/07/2026 | MP007 | Natal | RN | shopping | R$ 8567.64 | R$ 22.59 | 379 | 311 | 165 | 91 |
| 13/07/2026 | MP007 | Natal | RN | shopping | R$ 5509.57 | R$ 24.83 | 221 | 206 | 84 | 50 |
| 14/07/2026 | MP007 | Natal | RN | shopping | R$ 5886.40 | R$ 22.64 | 260 | 229 | 115 | 72 |
| 15/07/2026 | MP007 | Natal | RN | shopping | R$ 5927.04 | R$ 22.79 | 260 | 241 | 100 | 63 |
| 16/07/2026 | MP007 | Natal | RN | shopping | R$ 6274.30 | R$ 23.09 | 271 | 230 | 132 | 64 |
| 17/07/2026 | MP007 | Natal | RN | shopping | R$ 6730.75 | R$ 26.02 | 258 | 198 | 105 | 58 |
| 18/07/2026 | MP007 | Natal | RN | shopping | R$ 9002.11 | R$ 26.25 | 342 | 290 | 131 | 72 |
| 19/07/2026 | MP007 | Natal | RN | shopping | R$ 8413.13 | R$ 22.93 | 366 | 295 | 161 | 93 |
| 20/07/2026 | MP007 | Natal | RN | shopping | R$ 5033.90 | R$ 23.99 | 209 | 184 | 74 | 57 |
| 21/07/2026 | MP007 | Natal | RN | shopping | R$ 6086.49 | R$ 25.23 | 241 | 217 | 86 | 58 |
| 22/07/2026 | MP007 | Natal | RN | shopping | R$ 6631.52 | R$ 23.28 | 284 | 233 | 100 | 64 |
| 23/07/2026 | MP007 | Natal | RN | shopping | R$ 7129.44 | R$ 25.06 | 284 | 216 | 144 | 65 |
| 24/07/2026 | MP007 | Natal | RN | shopping | R$ 7473.74 | R$ 23.03 | 324 | 248 | 161 | 74 |
| 25/07/2026 | MP007 | Natal | RN | shopping | R$ 8446.90 | R$ 23.39 | 361 | 305 | 172 | 76 |
| 26/07/2026 | MP007 | Natal | RN | shopping | R$ 10049.57 | R$ 22.55 | 445 | 363 | 225 | 90 |
| 27/07/2026 | MP007 | Natal | RN | shopping | R$ 5686.79 | R$ 23.22 | 244 | 188 | 124 | 44 |
| 28/07/2026 | MP007 | Natal | RN | shopping | R$ 7679.59 | R$ 23.47 | 327 | 246 | 151 | 59 |
| 29/07/2026 | MP007 | Natal | RN | shopping | R$ 7663.82 | R$ 24.60 | 311 | 265 | 139 | 80 |
| 30/07/2026 | MP007 | Natal | RN | shopping | R$ 7330.52 | R$ 22.97 | 319 | 283 | 115 | 68 |
| 01/07/2026 | MP008 | Joao Pessoa | PB | rua | R$ 3631.11 | R$ 21.17 | 171 | 140 | 74 | 31 |
| 02/07/2026 | MP008 | Joao Pessoa | PB | rua | R$ 3041.63 | R$ 19.93 | 152 | 127 | 60 | 25 |
| 03/07/2026 | MP008 | Joao Pessoa | PB | rua | R$ 4294.46 | R$ 18.64 | 230 | 180 | 88 | 31 |
| 04/07/2026 | MP008 | Joao Pessoa | PB | rua | R$ 4181.34 | R$ 20.43 | 204 | 163 | 93 | 37 |
| 05/07/2026 | MP008 | Joao Pessoa | PB | rua | R$ 4452.41 | R$ 19.85 | 224 | 173 | 111 | 36 |
| 06/07/2026 | MP008 | Joao Pessoa | PB | rua | R$ 3134.70 | R$ 20.48 | 153 | 136 | 63 | 24 |
| 07/07/2026 | MP008 | Joao Pessoa | PB | rua | R$ 3360.47 | R$ 19.13 | 175 | 139 | 74 | 27 |
| 08/07/2026 | MP008 | Joao Pessoa | PB | rua | R$ 3069.59 | R$ 19.77 | 155 | 127 | 71 | 22 |
| 09/07/2026 | MP008 | Joao Pessoa | PB | rua | R$ 3745.16 | R$ 18.61 | 201 | 161 | 103 | 28 |
| 10/07/2026 | MP008 | Joao Pessoa | PB | rua | R$ 4134.09 | R$ 21.00 | 196 | 165 | 82 | 33 |
| 11/07/2026 | MP008 | Joao Pessoa | PB | rua | R$ 4239.29 | R$ 18.79 | 225 | 186 | 88 | 39 |
| 12/07/2026 | MP008 | Joao Pessoa | PB | rua | R$ 4810.47 | R$ 20.71 | 232 | 209 | 102 | 39 |
| 13/07/2026 | MP008 | Joao Pessoa | PB | rua | R$ 2944.04 | R$ 19.08 | 154 | 123 | 74 | 21 |
| 14/07/2026 | MP008 | Joao Pessoa | PB | rua | R$ 3681.82 | R$ 19.58 | 188 | 163 | 81 | 35 |
| 15/07/2026 | MP008 | Joao Pessoa | PB | rua | R$ 3681.65 | R$ 21.52 | 171 | 150 | 74 | 31 |
| 16/07/2026 | MP008 | Joao Pessoa | PB | rua | R$ 3013.42 | R$ 21.37 | 140 | 116 | 68 | 20 |
| 17/07/2026 | MP008 | Joao Pessoa | PB | rua | R$ 4100.21 | R$ 19.39 | 211 | 153 | 103 | 33 |
| 18/07/2026 | MP008 | Joao Pessoa | PB | rua | R$ 4490.35 | R$ 19.68 | 228 | 181 | 87 | 31 |
| 19/07/2026 | MP008 | Joao Pessoa | PB | rua | R$ 4681.08 | R$ 19.09 | 245 | 193 | 109 | 37 |
| 20/07/2026 | MP008 | Joao Pessoa | PB | rua | R$ 3043.70 | R$ 20.89 | 145 | 111 | 72 | 19 |
| 21/07/2026 | MP008 | Joao Pessoa | PB | rua | R$ 3120.45 | R$ 20.38 | 153 | 123 | 73 | 25 |
| 22/07/2026 | MP008 | Joao Pessoa | PB | rua | R$ 3388.30 | R$ 19.81 | 171 | 141 | 64 | 24 |
| 23/07/2026 | MP008 | Joao Pessoa | PB | rua | R$ 3342.81 | R$ 19.31 | 173 | 146 | 76 | 30 |
| 24/07/2026 | MP008 | Joao Pessoa | PB | rua | R$ 3483.42 | R$ 19.66 | 177 | 134 | 90 | 25 |
| 25/07/2026 | MP008 | Joao Pessoa | PB | rua | R$ 4113.68 | R$ 18.84 | 218 | 166 | 95 | 28 |
| 26/07/2026 | MP008 | Joao Pessoa | PB | rua | R$ 4682.03 | R$ 18.96 | 246 | 206 | 95 | 41 |
| 27/07/2026 | MP008 | Joao Pessoa | PB | rua | R$ 3121.21 | R$ 20.98 | 148 | 120 | 52 | 20 |
| 28/07/2026 | MP008 | Joao Pessoa | PB | rua | R$ 3007.29 | R$ 21.35 | 140 | 123 | 62 | 25 |
| 29/07/2026 | MP008 | Joao Pessoa | PB | rua | R$ 3570.95 | R$ 19.74 | 180 | 127 | 84 | 24 |
| 30/07/2026 | MP008 | Joao Pessoa | PB | rua | R$ 3645.88 | R$ 20.38 | 178 | 166 | 68 | 29 |
| 01/07/2026 | MP009 | Petrolina | PE | interior | R$ 1932.58 | R$ 15.15 | 127 | 106 | 55 | 0 |
| 02/07/2026 | MP009 | Petrolina | PE | interior | R$ 1740.35 | R$ 15.32 | 113 | 87 | 50 | 0 |
| 03/07/2026 | MP009 | Petrolina | PE | interior | R$ 1889.25 | R$ 15.83 | 119 | 91 | 48 | 0 |
| 04/07/2026 | MP009 | Petrolina | PE | interior | R$ 2546.57 | R$ 15.42 | 165 | 148 | 65 | 0 |
| 05/07/2026 | MP009 | Petrolina | PE | interior | R$ 2495.95 | R$ 15.13 | 164 | 120 | 73 | 0 |
| 06/07/2026 | MP009 | Petrolina | PE | interior | R$ 1554.54 | R$ 16.46 | 94 | 74 | 46 | 0 |
| 07/07/2026 | MP009 | Petrolina | PE | interior | R$ 1901.89 | R$ 15.79 | 120 | 107 | 49 | 0 |
| 08/07/2026 | MP009 | Petrolina | PE | interior | R$ 1763.11 | R$ 16.87 | 104 | 88 | 43 | 0 |
| 09/07/2026 | MP009 | Petrolina | PE | interior | R$ 1838.35 | R$ 16.72 | 109 | 85 | 54 | 0 |
| 10/07/2026 | MP009 | Petrolina | PE | interior | R$ 1840.06 | R$ 15.65 | 117 | 89 | 52 | 0 |
| 11/07/2026 | MP009 | Petrolina | PE | interior | R$ 2073.32 | R$ 15.82 | 131 | 103 | 55 | 0 |
| 12/07/2026 | MP009 | Petrolina | PE | interior | R$ 2073.72 | R$ 16.64 | 124 | 101 | 43 | 0 |
| 13/07/2026 | MP009 | Petrolina | PE | interior | R$ 1646.63 | R$ 16.09 | 102 | 83 | 44 | 0 |
| 14/07/2026 | MP009 | Petrolina | PE | interior | R$ 1808.27 | R$ 16.54 | 109 | 94 | 50 | 0 |
| 15/07/2026 | MP009 | Petrolina | PE | interior | R$ 1917.73 | R$ 16.18 | 118 | 93 | 50 | 0 |
| 16/07/2026 | MP009 | Petrolina | PE | interior | R$ 1635.43 | R$ 14.69 | 111 | 91 | 38 | 0 |
| 17/07/2026 | MP009 | Petrolina | PE | interior | R$ 1975.62 | R$ 16.34 | 120 | 93 | 57 | 0 |
| 18/07/2026 | MP009 | Petrolina | PE | interior | R$ 2180.01 | R$ 15.64 | 139 | 113 | 59 | 0 |
| 19/07/2026 | MP009 | Petrolina | PE | interior | R$ 2130.45 | R$ 15.48 | 137 | 107 | 58 | 0 |
| 20/07/2026 | MP009 | Petrolina | PE | interior | R$ 1458.39 | R$ 16.05 | 90 | 79 | 38 | 0 |
| 21/07/2026 | MP009 | Petrolina | PE | interior | R$ 1599.04 | R$ 14.77 | 108 | 87 | 51 | 0 |
| 22/07/2026 | MP009 | Petrolina | PE | interior | R$ 1880.85 | R$ 16.20 | 116 | 108 | 46 | 0 |
| 23/07/2026 | MP009 | Petrolina | PE | interior | R$ 1713.61 | R$ 16.01 | 107 | 80 | 46 | 0 |
| 24/07/2026 | MP009 | Petrolina | PE | interior | R$ 2283.17 | R$ 16.30 | 140 | 114 | 57 | 0 |
| 25/07/2026 | MP009 | Petrolina | PE | interior | R$ 2564.43 | R$ 15.32 | 167 | 141 | 63 | 0 |
| 26/07/2026 | MP009 | Petrolina | PE | interior | R$ 2494.92 | R$ 16.23 | 153 | 138 | 63 | 0 |
| 27/07/2026 | MP009 | Petrolina | PE | interior | R$ 1584.77 | R$ 15.87 | 99 | 82 | 44 | 0 |
| 28/07/2026 | MP009 | Petrolina | PE | interior | R$ 1725.81 | R$ 15.45 | 111 | 81 | 50 | 0 |
| 29/07/2026 | MP009 | Petrolina | PE | interior | R$ 1976.78 | R$ 15.77 | 125 | 91 | 58 | 0 |
| 30/07/2026 | MP009 | Petrolina | PE | interior | R$ 1603.86 | R$ 16.67 | 96 | 77 | 35 | 0 |
| 01/07/2026 | MP010 | Juazeiro | BA | interior | R$ 1928.57 | R$ 16.77 | 115 | 85 | 48 | 18 |
| 02/07/2026 | MP010 | Juazeiro | BA | interior | R$ 1626.94 | R$ 15.49 | 105 | 86 | 38 | 18 |
| 03/07/2026 | MP010 | Juazeiro | BA | interior | R$ 2205.00 | R$ 14.95 | 147 | 117 | 64 | 24 |
| 04/07/2026 | MP010 | Juazeiro | BA | interior | R$ 2174.33 | R$ 15.66 | 138 | 114 | 52 | 22 |
| 05/07/2026 | MP010 | Juazeiro | BA | interior | R$ 2339.44 | R$ 15.32 | 152 | 130 | 69 | 28 |
| 06/07/2026 | MP010 | Juazeiro | BA | interior | R$ 1469.13 | R$ 16.93 | 86 | 75 | 40 | 14 |
| 07/07/2026 | MP010 | Juazeiro | BA | interior | R$ 1734.39 | R$ 15.87 | 109 | 101 | 45 | 22 |
| 08/07/2026 | MP010 | Juazeiro | BA | interior | R$ 1630.09 | R$ 15.17 | 107 | 95 | 41 | 19 |
| 09/07/2026 | MP010 | Juazeiro | BA | interior | R$ 1614.75 | R$ 16.67 | 96 | 79 | 47 | 17 |
| 10/07/2026 | MP010 | Juazeiro | BA | interior | R$ 1940.81 | R$ 16.82 | 115 | 88 | 47 | 19 |
| 11/07/2026 | MP010 | Juazeiro | BA | interior | R$ 2165.70 | R$ 15.68 | 138 | 101 | 67 | 17 |
| 12/07/2026 | MP010 | Juazeiro | BA | interior | R$ 2321.62 | R$ 15.13 | 153 | 132 | 74 | 22 |
| 13/07/2026 | MP010 | Juazeiro | BA | interior | R$ 1674.13 | R$ 16.66 | 100 | 88 | 39 | 15 |
| 14/07/2026 | MP010 | Juazeiro | BA | interior | R$ 1693.70 | R$ 16.63 | 101 | 80 | 50 | 16 |
| 15/07/2026 | MP010 | Juazeiro | BA | interior | R$ 1762.98 | R$ 14.55 | 121 | 88 | 53 | 19 |
| 16/07/2026 | MP010 | Juazeiro | BA | interior | R$ 1805.91 | R$ 16.37 | 110 | 84 | 54 | 15 |
| 17/07/2026 | MP010 | Juazeiro | BA | interior | R$ 1954.79 | R$ 14.66 | 133 | 114 | 50 | 22 |
| 18/07/2026 | MP010 | Juazeiro | BA | interior | R$ 2103.78 | R$ 16.82 | 125 | 95 | 63 | 19 |
| 19/07/2026 | MP010 | Juazeiro | BA | interior | R$ 2176.78 | R$ 14.90 | 146 | 121 | 59 | 22 |
| 20/07/2026 | MP010 | Juazeiro | BA | interior | R$ 1486.87 | R$ 16.22 | 91 | 75 | 31 | 13 |
| 21/07/2026 | MP010 | Juazeiro | BA | interior | R$ 1796.16 | R$ 15.82 | 113 | 101 | 51 | 19 |
| 22/07/2026 | MP010 | Juazeiro | BA | interior | R$ 1772.21 | R$ 16.14 | 109 | 92 | 54 | 15 |
| 23/07/2026 | MP010 | Juazeiro | BA | interior | R$ 1908.60 | R$ 15.41 | 123 | 107 | 52 | 23 |
| 24/07/2026 | MP010 | Juazeiro | BA | interior | R$ 2168.62 | R$ 15.38 | 141 | 108 | 55 | 23 |
| 25/07/2026 | MP010 | Juazeiro | BA | interior | R$ 2139.55 | R$ 16.51 | 129 | 109 | 51 | 22 |
| 26/07/2026 | MP010 | Juazeiro | BA | interior | R$ 2493.98 | R$ 14.70 | 169 | 144 | 76 | 27 |
| 27/07/2026 | MP010 | Juazeiro | BA | interior | R$ 1351.13 | R$ 15.04 | 89 | 73 | 30 | 14 |
| 28/07/2026 | MP010 | Juazeiro | BA | interior | R$ 1994.54 | R$ 15.91 | 125 | 103 | 47 | 18 |
| 29/07/2026 | MP010 | Juazeiro | BA | interior | R$ 1723.73 | R$ 16.51 | 104 | 87 | 50 | 15 |
| 30/07/2026 | MP010 | Juazeiro | BA | interior | R$ 1728.46 | R$ 16.78 | 102 | 93 | 39 | 17 |
| 01/07/2026 | MP011 | Sobral | CE | interior | R$ 2572.63 | R$ 15.79 | 162 | 143 | 59 | 28 |
| 02/07/2026 | MP011 | Sobral | CE | interior | R$ 2443.93 | R$ 16.37 | 149 | 116 | 57 | 25 |
| 03/07/2026 | MP011 | Sobral | CE | interior | R$ 2613.88 | R$ 15.35 | 170 | 134 | 64 | 25 |
| 04/07/2026 | MP011 | Sobral | CE | interior | R$ 2953.88 | R$ 15.61 | 189 | 156 | 87 | 26 |
| 05/07/2026 | MP011 | Sobral | CE | interior | R$ 3095.31 | R$ 15.43 | 200 | 170 | 99 | 38 |
| 06/07/2026 | MP011 | Sobral | CE | interior | R$ 2029.60 | R$ 14.73 | 137 | 112 | 63 | 24 |
| 07/07/2026 | MP011 | Sobral | CE | interior | R$ 2216.71 | R$ 16.94 | 130 | 102 | 51 | 22 |
| 08/07/2026 | MP011 | Sobral | CE | interior | R$ 1860.56 | R$ 14.71 | 126 | 105 | 59 | 20 |
| 09/07/2026 | MP011 | Sobral | CE | interior | R$ 2096.90 | R$ 16.07 | 130 | 119 | 48 | 22 |
| 10/07/2026 | MP011 | Sobral | CE | interior | R$ 2485.32 | R$ 15.99 | 155 | 125 | 69 | 26 |
| 11/07/2026 | MP011 | Sobral | CE | interior | R$ 2446.20 | R$ 14.82 | 165 | 141 | 73 | 27 |
| 12/07/2026 | MP011 | Sobral | CE | interior | R$ 2600.49 | R$ 15.20 | 171 | 133 | 72 | 30 |
| 13/07/2026 | MP011 | Sobral | CE | interior | R$ 1564.46 | R$ 16.85 | 92 | 70 | 44 | 15 |
| 14/07/2026 | MP011 | Sobral | CE | interior | R$ 1887.62 | R$ 16.81 | 112 | 84 | 54 | 17 |
| 15/07/2026 | MP011 | Sobral | CE | interior | R$ 2034.60 | R$ 15.34 | 132 | 97 | 63 | 19 |
| 16/07/2026 | MP011 | Sobral | CE | interior | R$ 2021.56 | R$ 16.69 | 121 | 110 | 46 | 22 |
| 17/07/2026 | MP011 | Sobral | CE | interior | R$ 2237.08 | R$ 15.82 | 141 | 102 | 63 | 18 |
| 18/07/2026 | MP011 | Sobral | CE | interior | R$ 2484.16 | R$ 14.60 | 170 | 137 | 77 | 29 |
| 19/07/2026 | MP011 | Sobral | CE | interior | R$ 2310.57 | R$ 16.08 | 143 | 105 | 61 | 24 |
| 20/07/2026 | MP011 | Sobral | CE | interior | R$ 1543.09 | R$ 15.86 | 97 | 88 | 38 | 15 |
| 21/07/2026 | MP011 | Sobral | CE | interior | R$ 1886.05 | R$ 16.16 | 116 | 97 | 46 | 18 |
| 22/07/2026 | MP011 | Sobral | CE | interior | R$ 1814.07 | R$ 16.51 | 109 | 86 | 53 | 19 |
| 23/07/2026 | MP011 | Sobral | CE | interior | R$ 1606.00 | R$ 16.84 | 95 | 67 | 43 | 12 |
| 24/07/2026 | MP011 | Sobral | CE | interior | R$ 1693.60 | R$ 15.35 | 110 | 91 | 51 | 20 |
| 25/07/2026 | MP011 | Sobral | CE | interior | R$ 2235.59 | R$ 16.67 | 134 | 108 | 52 | 21 |
| 26/07/2026 | MP011 | Sobral | CE | interior | R$ 1821.90 | R$ 15.30 | 119 | 98 | 51 | 17 |
| 27/07/2026 | MP011 | Sobral | CE | interior | R$ 1418.78 | R$ 14.93 | 95 | 83 | 38 | 17 |
| 28/07/2026 | MP011 | Sobral | CE | interior | R$ 1599.94 | R$ 15.96 | 100 | 79 | 52 | 13 |
| 29/07/2026 | MP011 | Sobral | CE | interior | R$ 1496.74 | R$ 15.99 | 93 | 82 | 37 | 15 |
| 30/07/2026 | MP011 | Sobral | CE | interior | R$ 1464.06 | R$ 15.80 | 92 | 74 | 43 | 16 |
| 01/07/2026 | MP012 | Mossoro | RN | interior | R$ 2091.40 | R$ 16.57 | 126 | 102 | 60 | 17 |
| 02/07/2026 | MP012 | Mossoro | RN | interior | R$ 1878.20 | R$ 15.65 | 120 | 93 | 56 | 19 |
| 03/07/2026 | MP012 | Mossoro | RN | interior | R$ 2306.37 | R$ 16.35 | 141 | 127 | 55 | 29 |
| 04/07/2026 | MP012 | Mossoro | RN | interior | R$ 2488.08 | R$ 15.47 | 160 | 128 | 73 | 25 |
| 05/07/2026 | MP012 | Mossoro | RN | interior | R$ 2577.65 | R$ 15.16 | 169 | 125 | 72 | 24 |
| 06/07/2026 | MP012 | Mossoro | RN | interior | R$ 1834.43 | R$ 15.16 | 120 | 97 | 61 | 18 |
| 07/07/2026 | MP012 | Mossoro | RN | interior | R$ 2139.15 | R$ 15.33 | 139 | 119 | 62 | 23 |
| 08/07/2026 | MP012 | Mossoro | RN | interior | R$ 2099.37 | R$ 15.32 | 137 | 112 | 46 | 22 |
| 09/07/2026 | MP012 | Mossoro | RN | interior | R$ 2335.21 | R$ 15.08 | 154 | 113 | 74 | 22 |
| 10/07/2026 | MP012 | Mossoro | RN | interior | R$ 2636.60 | R$ 16.19 | 162 | 133 | 68 | 29 |
| 11/07/2026 | MP012 | Mossoro | RN | interior | R$ 2684.74 | R$ 16.77 | 160 | 143 | 64 | 27 |
| 12/07/2026 | MP012 | Mossoro | RN | interior | R$ 2664.86 | R$ 15.98 | 166 | 131 | 66 | 22 |
| 13/07/2026 | MP012 | Mossoro | RN | interior | R$ 1786.82 | R$ 16.47 | 108 | 93 | 37 | 19 |
| 14/07/2026 | MP012 | Mossoro | RN | interior | R$ 1907.88 | R$ 17.00 | 112 | 95 | 42 | 18 |
| 15/07/2026 | MP012 | Mossoro | RN | interior | R$ 2321.23 | R$ 16.44 | 141 | 110 | 57 | 22 |
| 16/07/2026 | MP012 | Mossoro | RN | interior | R$ 1870.83 | R$ 14.88 | 125 | 99 | 53 | 19 |
| 17/07/2026 | MP012 | Mossoro | RN | interior | R$ 2476.59 | R$ 15.84 | 156 | 127 | 62 | 22 |
| 18/07/2026 | MP012 | Mossoro | RN | interior | R$ 3051.45 | R$ 16.40 | 186 | 144 | 81 | 31 |
| 19/07/2026 | MP012 | Mossoro | RN | interior | R$ 2751.19 | R$ 16.33 | 168 | 141 | 62 | 27 |
| 20/07/2026 | MP012 | Mossoro | RN | interior | R$ 1859.46 | R$ 17.01 | 109 | 95 | 43 | 20 |
| 21/07/2026 | MP012 | Mossoro | RN | interior | R$ 2194.77 | R$ 14.60 | 150 | 133 | 53 | 28 |
| 22/07/2026 | MP012 | Mossoro | RN | interior | R$ 2239.19 | R$ 16.00 | 139 | 119 | 60 | 21 |
| 23/07/2026 | MP012 | Mossoro | RN | interior | R$ 2165.03 | R$ 16.10 | 134 | 108 | 68 | 22 |
| 24/07/2026 | MP012 | Mossoro | RN | interior | R$ 2143.50 | R$ 16.93 | 126 | 88 | 59 | 16 |
| 25/07/2026 | MP012 | Mossoro | RN | interior | R$ 2501.62 | R$ 16.28 | 153 | 130 | 58 | 29 |
| 26/07/2026 | MP012 | Mossoro | RN | interior | R$ 2974.27 | R$ 16.40 | 181 | 129 | 81 | 23 |
| 27/07/2026 | MP012 | Mossoro | RN | interior | R$ 1710.05 | R$ 16.21 | 105 | 83 | 48 | 14 |
| 28/07/2026 | MP012 | Mossoro | RN | interior | R$ 2307.71 | R$ 15.40 | 149 | 125 | 56 | 26 |
| 29/07/2026 | MP012 | Mossoro | RN | interior | R$ 2172.23 | R$ 16.29 | 133 | 105 | 64 | 19 |
| 30/07/2026 | MP012 | Mossoro | RN | interior | R$ 2129.28 | R$ 15.10 | 140 | 119 | 69 | 22 |
| 01/07/2026 | MP013 | Sao Luis | MA | shopping | R$ 4834.68 | R$ 25.30 | 191 | 148 | 83 | 33 |
| 02/07/2026 | MP013 | Sao Luis | MA | shopping | R$ 5568.67 | R$ 23.61 | 235 | 187 | 88 | 36 |
| 03/07/2026 | MP013 | Sao Luis | MA | shopping | R$ 6669.13 | R$ 25.75 | 259 | 241 | 106 | 45 |
| 04/07/2026 | MP013 | Sao Luis | MA | shopping | R$ 6415.45 | R$ 25.34 | 253 | 201 | 107 | 37 |
| 05/07/2026 | MP013 | Sao Luis | MA | shopping | R$ 6726.06 | R$ 23.33 | 288 | 257 | 105 | 54 |
| 06/07/2026 | MP013 | Sao Luis | MA | shopping | R$ 4035.22 | R$ 24.95 | 161 | 128 | 76 | 26 |
| 07/07/2026 | MP013 | Sao Luis | MA | shopping | R$ 5238.74 | R$ 25.04 | 209 | 157 | 85 | 33 |
| 08/07/2026 | MP013 | Sao Luis | MA | shopping | R$ 4701.48 | R$ 25.56 | 183 | 139 | 71 | 31 |
| 09/07/2026 | MP013 | Sao Luis | MA | shopping | R$ 5083.82 | R$ 26.21 | 193 | 167 | 88 | 30 |
| 10/07/2026 | MP013 | Sao Luis | MA | shopping | R$ 6645.81 | R$ 23.80 | 279 | 252 | 104 | 44 |
| 11/07/2026 | MP013 | Sao Luis | MA | shopping | R$ 6880.27 | R$ 24.64 | 279 | 257 | 104 | 57 |
| 12/07/2026 | MP013 | Sao Luis | MA | shopping | R$ 6232.83 | R$ 26.00 | 239 | 201 | 82 | 46 |
| 13/07/2026 | MP013 | Sao Luis | MA | shopping | R$ 4310.73 | R$ 24.48 | 176 | 168 | 67 | 37 |
| 14/07/2026 | MP013 | Sao Luis | MA | shopping | R$ 5670.18 | R$ 22.58 | 251 | 194 | 123 | 44 |
| 15/07/2026 | MP013 | Sao Luis | MA | shopping | R$ 4931.13 | R$ 26.42 | 186 | 154 | 80 | 34 |
| 16/07/2026 | MP013 | Sao Luis | MA | shopping | R$ 5638.12 | R$ 24.37 | 231 | 168 | 106 | 30 |
| 17/07/2026 | MP013 | Sao Luis | MA | shopping | R$ 5921.03 | R$ 23.55 | 251 | 204 | 93 | 44 |
| 18/07/2026 | MP013 | Sao Luis | MA | shopping | R$ 6869.97 | R$ 25.51 | 269 | 223 | 95 | 49 |
| 19/07/2026 | MP013 | Sao Luis | MA | shopping | R$ 7290.51 | R$ 24.56 | 296 | 234 | 111 | 42 |
| 20/07/2026 | MP013 | Sao Luis | MA | shopping | R$ 4038.76 | R$ 23.81 | 169 | 127 | 75 | 23 |
| 21/07/2026 | MP013 | Sao Luis | MA | shopping | R$ 5516.69 | R$ 26.28 | 209 | 173 | 79 | 29 |
| 22/07/2026 | MP013 | Sao Luis | MA | shopping | R$ 5391.80 | R$ 25.26 | 213 | 151 | 96 | 28 |
| 23/07/2026 | MP013 | Sao Luis | MA | shopping | R$ 5081.96 | R$ 24.51 | 207 | 188 | 87 | 35 |
| 24/07/2026 | MP013 | Sao Luis | MA | shopping | R$ 5430.92 | R$ 26.13 | 207 | 168 | 82 | 30 |
| 25/07/2026 | MP013 | Sao Luis | MA | shopping | R$ 6165.50 | R$ 23.14 | 266 | 232 | 113 | 45 |
| 26/07/2026 | MP013 | Sao Luis | MA | shopping | R$ 6839.88 | R$ 24.39 | 280 | 239 | 113 | 43 |
| 27/07/2026 | MP013 | Sao Luis | MA | shopping | R$ 4152.11 | R$ 25.50 | 162 | 130 | 84 | 25 |
| 28/07/2026 | MP013 | Sao Luis | MA | shopping | R$ 5454.30 | R$ 22.85 | 238 | 182 | 118 | 36 |
| 29/07/2026 | MP013 | Sao Luis | MA | shopping | R$ 5206.85 | R$ 24.78 | 210 | 157 | 90 | 31 |
| 30/07/2026 | MP013 | Sao Luis | MA | shopping | R$ 4721.07 | R$ 23.35 | 202 | 155 | 100 | 31 |
| 01/07/2026 | MP014 | Teresina | PI | shopping | R$ 5864.51 | R$ 24.32 | 241 | 197 | 104 | 47 |
| 02/07/2026 | MP014 | Teresina | PI | shopping | R$ 5473.83 | R$ 25.70 | 212 | 177 | 97 | 54 |
| 03/07/2026 | MP014 | Teresina | PI | shopping | R$ 6804.57 | R$ 24.81 | 274 | 203 | 114 | 49 |
| 04/07/2026 | MP014 | Teresina | PI | shopping | R$ 8217.64 | R$ 26.20 | 313 | 259 | 105 | 62 |
| 05/07/2026 | MP014 | Teresina | PI | shopping | R$ 7266.75 | R$ 25.55 | 284 | 265 | 105 | 77 |
| 06/07/2026 | MP014 | Teresina | PI | shopping | R$ 4817.85 | R$ 26.43 | 182 | 157 | 66 | 49 |
| 07/07/2026 | MP014 | Teresina | PI | shopping | R$ 5667.84 | R$ 25.22 | 224 | 190 | 97 | 55 |
| 08/07/2026 | MP014 | Teresina | PI | shopping | R$ 5690.13 | R$ 23.24 | 244 | 203 | 103 | 60 |
| 09/07/2026 | MP014 | Teresina | PI | shopping | R$ 5572.30 | R$ 22.55 | 247 | 181 | 104 | 53 |
| 10/07/2026 | MP014 | Teresina | PI | shopping | R$ 7012.30 | R$ 24.63 | 284 | 234 | 139 | 62 |
| 11/07/2026 | MP014 | Teresina | PI | shopping | R$ 7499.33 | R$ 26.21 | 286 | 227 | 143 | 69 |
| 12/07/2026 | MP014 | Teresina | PI | shopping | R$ 7853.68 | R$ 25.54 | 307 | 244 | 163 | 62 |
| 13/07/2026 | MP014 | Teresina | PI | shopping | R$ 4783.97 | R$ 22.67 | 211 | 182 | 85 | 44 |
| 14/07/2026 | MP014 | Teresina | PI | shopping | R$ 6651.11 | R$ 24.12 | 275 | 205 | 124 | 63 |
| 15/07/2026 | MP014 | Teresina | PI | shopping | R$ 5675.63 | R$ 24.52 | 231 | 194 | 85 | 58 |
| 16/07/2026 | MP014 | Teresina | PI | shopping | R$ 6136.66 | R$ 24.88 | 246 | 201 | 114 | 52 |
| 17/07/2026 | MP014 | Teresina | PI | shopping | R$ 6813.14 | R$ 25.13 | 271 | 205 | 118 | 49 |
| 18/07/2026 | MP014 | Teresina | PI | shopping | R$ 9421.37 | R$ 25.99 | 362 | 325 | 157 | 89 |
| 19/07/2026 | MP014 | Teresina | PI | shopping | R$ 8579.55 | R$ 26.35 | 325 | 295 | 139 | 89 |
| 20/07/2026 | MP014 | Teresina | PI | shopping | R$ 5423.10 | R$ 24.17 | 224 | 170 | 94 | 51 |
| 21/07/2026 | MP014 | Teresina | PI | shopping | R$ 6691.20 | R$ 25.87 | 258 | 213 | 99 | 65 |
| 22/07/2026 | MP014 | Teresina | PI | shopping | R$ 7474.33 | R$ 24.74 | 302 | 270 | 135 | 67 |
| 23/07/2026 | MP014 | Teresina | PI | shopping | R$ 6437.96 | R$ 23.34 | 275 | 249 | 102 | 76 |
| 24/07/2026 | MP014 | Teresina | PI | shopping | R$ 7184.93 | R$ 25.38 | 283 | 212 | 124 | 62 |
| 25/07/2026 | MP014 | Teresina | PI | shopping | R$ 9309.86 | R$ 25.96 | 358 | 293 | 132 | 87 |
| 26/07/2026 | MP014 | Teresina | PI | shopping | R$ 9297.74 | R$ 24.42 | 380 | 321 | 182 | 102 |
| 27/07/2026 | MP014 | Teresina | PI | shopping | R$ 5345.18 | R$ 26.21 | 203 | 167 | 105 | 53 |
| 28/07/2026 | MP014 | Teresina | PI | shopping | R$ 7143.58 | R$ 23.49 | 304 | 241 | 145 | 75 |
| 29/07/2026 | MP014 | Teresina | PI | shopping | R$ 7334.14 | R$ 25.58 | 286 | 232 | 118 | 62 |
| 30/07/2026 | MP014 | Teresina | PI | shopping | R$ 6889.14 | R$ 24.55 | 280 | 213 | 136 | 68 |
| 01/07/2026 | MP015 | Aracaju | SE | shopping | R$ 5161.92 | R$ 25.83 | 199 | 170 | 95 | 33 |
| 02/07/2026 | MP015 | Aracaju | SE | shopping | R$ 5278.03 | R$ 23.41 | 225 | 167 | 98 | 37 |
| 03/07/2026 | MP015 | Aracaju | SE | shopping | R$ 6093.59 | R$ 24.18 | 252 | 189 | 108 | 36 |
| 04/07/2026 | MP015 | Aracaju | SE | shopping | R$ 7300.85 | R$ 24.50 | 298 | 259 | 122 | 48 |
| 05/07/2026 | MP015 | Aracaju | SE | shopping | R$ 7281.75 | R$ 26.33 | 276 | 231 | 121 | 41 |
| 06/07/2026 | MP015 | Aracaju | SE | shopping | R$ 4732.91 | R$ 23.20 | 203 | 172 | 90 | 38 |
| 07/07/2026 | MP015 | Aracaju | SE | shopping | R$ 5252.59 | R$ 25.06 | 209 | 146 | 96 | 32 |
| 08/07/2026 | MP015 | Aracaju | SE | shopping | R$ 5755.59 | R$ 25.16 | 228 | 192 | 105 | 42 |
| 09/07/2026 | MP015 | Aracaju | SE | shopping | R$ 4864.83 | R$ 25.31 | 192 | 146 | 75 | 28 |
| 10/07/2026 | MP015 | Aracaju | SE | shopping | R$ 6149.12 | R$ 25.15 | 244 | 203 | 107 | 40 |
| 11/07/2026 | MP015 | Aracaju | SE | shopping | R$ 5959.53 | R$ 24.70 | 241 | 183 | 94 | 34 |
| 12/07/2026 | MP015 | Aracaju | SE | shopping | R$ 7534.66 | R$ 22.61 | 333 | 297 | 140 | 64 |
| 13/07/2026 | MP015 | Aracaju | SE | shopping | R$ 4854.69 | R$ 22.96 | 211 | 151 | 95 | 27 |
| 14/07/2026 | MP015 | Aracaju | SE | shopping | R$ 5233.02 | R$ 25.74 | 203 | 158 | 86 | 30 |
| 15/07/2026 | MP015 | Aracaju | SE | shopping | R$ 5082.72 | R$ 24.75 | 205 | 173 | 103 | 36 |
| 16/07/2026 | MP015 | Aracaju | SE | shopping | R$ 5634.14 | R$ 25.10 | 224 | 204 | 92 | 35 |
| 17/07/2026 | MP015 | Aracaju | SE | shopping | R$ 5806.72 | R$ 24.71 | 235 | 163 | 109 | 29 |
| 18/07/2026 | MP015 | Aracaju | SE | shopping | R$ 6759.77 | R$ 24.24 | 278 | 242 | 121 | 53 |
| 19/07/2026 | MP015 | Aracaju | SE | shopping | R$ 6103.52 | R$ 24.61 | 248 | 179 | 108 | 39 |
| 20/07/2026 | MP015 | Aracaju | SE | shopping | R$ 4831.12 | R$ 24.40 | 197 | 138 | 90 | 31 |
| 21/07/2026 | MP015 | Aracaju | SE | shopping | R$ 5698.34 | R$ 24.75 | 230 | 189 | 77 | 35 |
| 22/07/2026 | MP015 | Aracaju | SE | shopping | R$ 5775.91 | R$ 24.84 | 232 | 206 | 95 | 39 |
| 23/07/2026 | MP015 | Aracaju | SE | shopping | R$ 4672.02 | R$ 23.18 | 201 | 168 | 72 | 32 |
| 24/07/2026 | MP015 | Aracaju | SE | shopping | R$ 6549.09 | R$ 23.84 | 274 | 219 | 137 | 50 |
| 25/07/2026 | MP015 | Aracaju | SE | shopping | R$ 7123.68 | R$ 24.50 | 290 | 236 | 154 | 46 |
| 26/07/2026 | MP015 | Aracaju | SE | shopping | R$ 7309.47 | R$ 23.88 | 306 | 284 | 114 | 55 |
| 27/07/2026 | MP015 | Aracaju | SE | shopping | R$ 4710.19 | R$ 22.66 | 207 | 179 | 70 | 35 |
| 28/07/2026 | MP015 | Aracaju | SE | shopping | R$ 5020.05 | R$ 26.23 | 191 | 160 | 76 | 33 |
| 29/07/2026 | MP015 | Aracaju | SE | shopping | R$ 4682.95 | R$ 24.96 | 187 | 167 | 77 | 29 |
| 30/07/2026 | MP015 | Aracaju | SE | shopping | R$ 4768.47 | R$ 25.33 | 188 | 165 | 75 | 31 |
| 01/07/2026 | MP016 | Maceio | AL | rua | R$ 3078.95 | R$ 18.42 | 167 | 129 | 73 | 24 |
| 02/07/2026 | MP016 | Maceio | AL | rua | R$ 3100.13 | R$ 19.00 | 163 | 134 | 68 | 26 |
| 03/07/2026 | MP016 | Maceio | AL | rua | R$ 3465.44 | R$ 19.53 | 177 | 138 | 68 | 26 |
| 04/07/2026 | MP016 | Maceio | AL | rua | R$ 4298.26 | R$ 19.33 | 222 | 165 | 107 | 36 |
| 05/07/2026 | MP016 | Maceio | AL | rua | R$ 4849.84 | R$ 21.53 | 225 | 176 | 108 | 33 |
| 06/07/2026 | MP016 | Maceio | AL | rua | R$ 2639.50 | R$ 19.36 | 136 | 102 | 67 | 20 |
| 07/07/2026 | MP016 | Maceio | AL | rua | R$ 3335.62 | R$ 19.95 | 167 | 122 | 72 | 22 |
| 08/07/2026 | MP016 | Maceio | AL | rua | R$ 3502.03 | R$ 20.30 | 172 | 125 | 79 | 23 |
| 09/07/2026 | MP016 | Maceio | AL | rua | R$ 3766.24 | R$ 19.46 | 193 | 170 | 75 | 32 |
| 10/07/2026 | MP016 | Maceio | AL | rua | R$ 3754.92 | R$ 21.01 | 178 | 168 | 67 | 29 |
| 11/07/2026 | MP016 | Maceio | AL | rua | R$ 4229.76 | R$ 21.43 | 197 | 149 | 85 | 33 |
| 12/07/2026 | MP016 | Maceio | AL | rua | R$ 4917.22 | R$ 19.33 | 254 | 215 | 112 | 43 |
| 13/07/2026 | MP016 | Maceio | AL | rua | R$ 2711.35 | R$ 19.60 | 138 | 117 | 64 | 20 |
| 14/07/2026 | MP016 | Maceio | AL | rua | R$ 3452.10 | R$ 20.30 | 170 | 145 | 69 | 29 |
| 15/07/2026 | MP016 | Maceio | AL | rua | R$ 3769.65 | R$ 19.88 | 189 | 159 | 85 | 29 |
| 16/07/2026 | MP016 | Maceio | AL | rua | R$ 3557.35 | R$ 21.02 | 169 | 143 | 78 | 28 |
| 17/07/2026 | MP016 | Maceio | AL | rua | R$ 4035.12 | R$ 19.17 | 210 | 184 | 85 | 39 |
| 18/07/2026 | MP016 | Maceio | AL | rua | R$ 3968.06 | R$ 21.57 | 183 | 147 | 80 | 29 |
| 19/07/2026 | MP016 | Maceio | AL | rua | R$ 4865.95 | R$ 20.61 | 236 | 206 | 91 | 39 |
| 20/07/2026 | MP016 | Maceio | AL | rua | R$ 3164.32 | R$ 20.12 | 157 | 122 | 78 | 26 |
| 21/07/2026 | MP016 | Maceio | AL | rua | R$ 3528.60 | R$ 19.54 | 180 | 139 | 91 | 31 |
| 22/07/2026 | MP016 | Maceio | AL | rua | R$ 3544.82 | R$ 19.68 | 180 | 167 | 67 | 32 |
| 23/07/2026 | MP016 | Maceio | AL | rua | R$ 3000.61 | R$ 19.23 | 156 | 129 | 66 | 26 |
| 24/07/2026 | MP016 | Maceio | AL | rua | R$ 3980.60 | R$ 19.83 | 200 | 169 | 76 | 34 |
| 25/07/2026 | MP016 | Maceio | AL | rua | R$ 4420.49 | R$ 19.50 | 226 | 159 | 102 | 30 |
| 26/07/2026 | MP016 | Maceio | AL | rua | R$ 4909.80 | R$ 18.77 | 261 | 215 | 134 | 40 |
| 27/07/2026 | MP016 | Maceio | AL | rua | R$ 2859.02 | R$ 19.06 | 149 | 121 | 64 | 23 |
| 28/07/2026 | MP016 | Maceio | AL | rua | R$ 3560.56 | R$ 19.42 | 183 | 154 | 67 | 27 |
| 29/07/2026 | MP016 | Maceio | AL | rua | R$ 3684.93 | R$ 20.47 | 179 | 142 | 88 | 32 |
| 30/07/2026 | MP016 | Maceio | AL | rua | R$ 3191.03 | R$ 18.96 | 168 | 132 | 66 | 30 |
| 01/07/2026 | MP017 | Belem | PA | shopping | R$ 5595.16 | R$ 24.13 | 231 | 185 | 89 | 50 |
| 02/07/2026 | MP017 | Belem | PA | shopping | R$ 5304.30 | R$ 24.95 | 212 | 169 | 83 | 45 |
| 03/07/2026 | MP017 | Belem | PA | shopping | R$ 7214.91 | R$ 23.35 | 309 | 279 | 122 | 67 |
| 04/07/2026 | MP017 | Belem | PA | shopping | R$ 7030.96 | R$ 25.96 | 270 | 204 | 116 | 56 |
| 05/07/2026 | MP017 | Belem | PA | shopping | R$ 7330.61 | R$ 25.92 | 282 | 239 | 115 | 68 |
| 06/07/2026 | MP017 | Belem | PA | shopping | R$ 5218.79 | R$ 24.84 | 210 | 179 | 77 | 51 |
| 07/07/2026 | MP017 | Belem | PA | shopping | R$ 6430.28 | R$ 25.31 | 254 | 206 | 101 | 50 |
| 08/07/2026 | MP017 | Belem | PA | shopping | R$ 5454.64 | R$ 23.00 | 237 | 178 | 109 | 52 |
| 09/07/2026 | MP017 | Belem | PA | shopping | R$ 5995.54 | R$ 24.18 | 247 | 187 | 103 | 47 |
| 10/07/2026 | MP017 | Belem | PA | shopping | R$ 7100.64 | R$ 25.26 | 281 | 258 | 101 | 73 |
| 11/07/2026 | MP017 | Belem | PA | shopping | R$ 7754.67 | R$ 23.09 | 335 | 265 | 141 | 64 |
| 12/07/2026 | MP017 | Belem | PA | shopping | R$ 7511.00 | R$ 22.58 | 332 | 272 | 118 | 86 |
| 13/07/2026 | MP017 | Belem | PA | shopping | R$ 5089.63 | R$ 24.48 | 207 | 172 | 94 | 53 |
| 14/07/2026 | MP017 | Belem | PA | shopping | R$ 5963.78 | R$ 22.86 | 260 | 207 | 93 | 54 |
| 15/07/2026 | MP017 | Belem | PA | shopping | R$ 5656.87 | R$ 24.65 | 229 | 177 | 94 | 53 |
| 16/07/2026 | MP017 | Belem | PA | shopping | R$ 6361.65 | R$ 24.69 | 257 | 184 | 117 | 55 |
| 17/07/2026 | MP017 | Belem | PA | shopping | R$ 7410.57 | R$ 23.98 | 309 | 245 | 161 | 73 |
| 18/07/2026 | MP017 | Belem | PA | shopping | R$ 7860.48 | R$ 26.42 | 297 | 242 | 105 | 72 |
| 19/07/2026 | MP017 | Belem | PA | shopping | R$ 7396.57 | R$ 26.46 | 279 | 221 | 124 | 67 |
| 20/07/2026 | MP017 | Belem | PA | shopping | R$ 5008.67 | R$ 26.44 | 189 | 154 | 92 | 47 |
| 21/07/2026 | MP017 | Belem | PA | shopping | R$ 6106.19 | R$ 23.91 | 255 | 222 | 107 | 55 |
| 22/07/2026 | MP017 | Belem | PA | shopping | R$ 5462.23 | R$ 23.35 | 233 | 168 | 109 | 44 |
| 23/07/2026 | MP017 | Belem | PA | shopping | R$ 5665.81 | R$ 24.65 | 229 | 190 | 88 | 49 |
| 24/07/2026 | MP017 | Belem | PA | shopping | R$ 6493.00 | R$ 25.90 | 250 | 228 | 108 | 56 |
| 25/07/2026 | MP017 | Belem | PA | shopping | R$ 8637.42 | R$ 25.62 | 337 | 322 | 127 | 100 |
| 26/07/2026 | MP017 | Belem | PA | shopping | R$ 7077.86 | R$ 25.94 | 272 | 223 | 103 | 68 |
| 27/07/2026 | MP017 | Belem | PA | shopping | R$ 5401.98 | R$ 25.19 | 214 | 178 | 89 | 46 |
| 28/07/2026 | MP017 | Belem | PA | shopping | R$ 5856.90 | R$ 24.31 | 240 | 215 | 91 | 52 |
| 29/07/2026 | MP017 | Belem | PA | shopping | R$ 6002.41 | R$ 23.63 | 254 | 218 | 121 | 69 |
| 30/07/2026 | MP017 | Belem | PA | shopping | R$ 5732.13 | R$ 22.55 | 254 | 227 | 104 | 67 |
| 01/07/2026 | MP018 | Manaus | AM | shopping | R$ 5148.14 | R$ 25.14 | 204 | 151 | 98 | 30 |
| 02/07/2026 | MP018 | Manaus | AM | shopping | R$ 4847.85 | R$ 24.22 | 200 | 150 | 88 | 32 |
| 03/07/2026 | MP018 | Manaus | AM | shopping | R$ 5747.15 | R$ 24.81 | 231 | 191 | 100 | 36 |
| 04/07/2026 | MP018 | Manaus | AM | shopping | R$ 7056.17 | R$ 22.73 | 310 | 251 | 111 | 49 |
| 05/07/2026 | MP018 | Manaus | AM | shopping | R$ 6150.36 | R$ 25.90 | 237 | 175 | 118 | 39 |
| 06/07/2026 | MP018 | Manaus | AM | shopping | R$ 4104.22 | R$ 25.24 | 162 | 128 | 62 | 22 |
| 07/07/2026 | MP018 | Manaus | AM | shopping | R$ 5740.04 | R$ 23.61 | 243 | 195 | 116 | 37 |
| 08/07/2026 | MP018 | Manaus | AM | shopping | R$ 5703.94 | R$ 23.19 | 245 | 191 | 110 | 40 |
| 09/07/2026 | MP018 | Manaus | AM | shopping | R$ 4868.21 | R$ 25.11 | 193 | 149 | 100 | 29 |
| 10/07/2026 | MP018 | Manaus | AM | shopping | R$ 5452.85 | R$ 23.43 | 232 | 179 | 119 | 37 |
| 11/07/2026 | MP018 | Manaus | AM | shopping | R$ 7274.48 | R$ 26.41 | 275 | 208 | 131 | 36 |
| 12/07/2026 | MP018 | Manaus | AM | shopping | R$ 6570.29 | R$ 25.40 | 258 | 191 | 110 | 42 |
| 13/07/2026 | MP018 | Manaus | AM | shopping | R$ 4035.07 | R$ 25.57 | 157 | 125 | 79 | 28 |
| 14/07/2026 | MP018 | Manaus | AM | shopping | R$ 4754.28 | R$ 24.62 | 193 | 150 | 72 | 29 |
| 15/07/2026 | MP018 | Manaus | AM | shopping | R$ 5477.60 | R$ 25.00 | 219 | 167 | 91 | 35 |
| 16/07/2026 | MP018 | Manaus | AM | shopping | R$ 5649.23 | R$ 22.88 | 246 | 198 | 89 | 40 |
| 17/07/2026 | MP018 | Manaus | AM | shopping | R$ 5813.56 | R$ 26.32 | 220 | 164 | 102 | 30 |
| 18/07/2026 | MP018 | Manaus | AM | shopping | R$ 6085.49 | R$ 24.71 | 246 | 209 | 103 | 45 |
| 19/07/2026 | MP018 | Manaus | AM | shopping | R$ 7069.03 | R$ 25.86 | 273 | 222 | 127 | 44 |
| 20/07/2026 | MP018 | Manaus | AM | shopping | R$ 4430.10 | R$ 25.47 | 173 | 126 | 83 | 28 |
| 21/07/2026 | MP018 | Manaus | AM | shopping | R$ 5767.43 | R$ 24.48 | 235 | 181 | 94 | 37 |
| 22/07/2026 | MP018 | Manaus | AM | shopping | R$ 5235.30 | R$ 26.37 | 198 | 189 | 77 | 33 |
| 23/07/2026 | MP018 | Manaus | AM | shopping | R$ 5650.30 | R$ 24.77 | 228 | 189 | 89 | 40 |
| 24/07/2026 | MP018 | Manaus | AM | shopping | R$ 6632.23 | R$ 25.56 | 259 | 181 | 117 | 33 |
| 25/07/2026 | MP018 | Manaus | AM | shopping | R$ 6013.42 | R$ 22.78 | 264 | 227 | 118 | 47 |
| 26/07/2026 | MP018 | Manaus | AM | shopping | R$ 6761.70 | R$ 24.17 | 279 | 219 | 141 | 44 |
| 27/07/2026 | MP018 | Manaus | AM | shopping | R$ 4543.10 | R$ 23.63 | 192 | 153 | 79 | 27 |
| 28/07/2026 | MP018 | Manaus | AM | shopping | R$ 5584.46 | R$ 24.64 | 226 | 187 | 90 | 41 |
| 29/07/2026 | MP018 | Manaus | AM | shopping | R$ 5425.96 | R$ 22.80 | 237 | 209 | 96 | 46 |
| 30/07/2026 | MP018 | Manaus | AM | shopping | R$ 4648.27 | R$ 22.88 | 203 | 164 | 87 | 33 |
| 01/07/2026 | MP019 | Cariri | CE | interior | R$ 1703.30 | R$ 16.41 | 103 | 81 | 52 | 0 |
| 02/07/2026 | MP019 | Cariri | CE | interior | R$ 1874.06 | R$ 16.31 | 114 | 95 | 39 | 0 |
| 03/07/2026 | MP019 | Cariri | CE | interior | R$ 2064.08 | R$ 16.52 | 124 | 99 | 61 | 0 |
| 04/07/2026 | MP019 | Cariri | CE | interior | R$ 2112.73 | R$ 16.51 | 127 | 107 | 45 | 0 |
| 05/07/2026 | MP019 | Cariri | CE | interior | R$ 2471.66 | R$ 14.61 | 169 | 139 | 82 | 0 |
| 06/07/2026 | MP019 | Cariri | CE | interior | R$ 1358.44 | R$ 16.34 | 83 | 63 | 42 | 0 |
| 07/07/2026 | MP019 | Cariri | CE | interior | R$ 1765.81 | R$ 15.45 | 114 | 94 | 48 | 0 |
| 08/07/2026 | MP019 | Cariri | CE | interior | R$ 1728.32 | R$ 15.18 | 113 | 88 | 44 | 0 |
| 09/07/2026 | MP019 | Cariri | CE | interior | R$ 1880.44 | R$ 15.11 | 124 | 93 | 62 | 0 |
| 10/07/2026 | MP019 | Cariri | CE | interior | R$ 2231.55 | R$ 15.15 | 147 | 117 | 65 | 0 |
| 11/07/2026 | MP019 | Cariri | CE | interior | R$ 2125.63 | R$ 16.89 | 125 | 109 | 56 | 0 |
| 12/07/2026 | MP019 | Cariri | CE | interior | R$ 2551.04 | R$ 16.41 | 155 | 121 | 70 | 0 |
| 13/07/2026 | MP019 | Cariri | CE | interior | R$ 1486.76 | R$ 16.36 | 90 | 65 | 43 | 0 |
| 14/07/2026 | MP019 | Cariri | CE | interior | R$ 1730.51 | R$ 15.81 | 109 | 90 | 55 | 0 |
| 15/07/2026 | MP019 | Cariri | CE | interior | R$ 1915.38 | R$ 17.02 | 112 | 91 | 59 | 0 |
| 16/07/2026 | MP019 | Cariri | CE | interior | R$ 1770.05 | R$ 15.25 | 116 | 97 | 56 | 0 |
| 17/07/2026 | MP019 | Cariri | CE | interior | R$ 2078.91 | R$ 14.56 | 142 | 112 | 56 | 0 |
| 18/07/2026 | MP019 | Cariri | CE | interior | R$ 2211.29 | R$ 16.11 | 137 | 114 | 56 | 0 |
| 19/07/2026 | MP019 | Cariri | CE | interior | R$ 2316.80 | R$ 16.49 | 140 | 117 | 49 | 0 |
| 20/07/2026 | MP019 | Cariri | CE | interior | R$ 1612.10 | R$ 15.16 | 106 | 79 | 43 | 0 |
| 21/07/2026 | MP019 | Cariri | CE | interior | R$ 1670.62 | R$ 15.41 | 108 | 100 | 42 | 0 |
| 22/07/2026 | MP019 | Cariri | CE | interior | R$ 1978.20 | R$ 14.54 | 136 | 122 | 52 | 0 |
| 23/07/2026 | MP019 | Cariri | CE | interior | R$ 1882.34 | R$ 14.80 | 127 | 99 | 60 | 0 |
| 24/07/2026 | MP019 | Cariri | CE | interior | R$ 2048.82 | R$ 14.69 | 139 | 128 | 59 | 0 |
| 25/07/2026 | MP019 | Cariri | CE | interior | R$ 2093.85 | R$ 16.86 | 124 | 108 | 56 | 0 |
| 26/07/2026 | MP019 | Cariri | CE | interior | R$ 2432.36 | R$ 15.48 | 157 | 128 | 83 | 0 |
| 27/07/2026 | MP019 | Cariri | CE | interior | R$ 1369.98 | R$ 14.87 | 92 | 73 | 47 | 0 |
| 28/07/2026 | MP019 | Cariri | CE | interior | R$ 1814.05 | R$ 15.64 | 116 | 97 | 58 | 0 |
| 29/07/2026 | MP019 | Cariri | CE | interior | R$ 1682.61 | R$ 15.33 | 109 | 97 | 45 | 0 |
| 30/07/2026 | MP019 | Cariri | CE | interior | R$ 1885.83 | R$ 15.34 | 122 | 88 | 58 | 0 |
| 01/07/2026 | MP020 | Iguatemi FTL | CE | shopping | R$ 4828.99 | R$ 25.60 | 188 | 147 | 91 | 26 |
| 02/07/2026 | MP020 | Iguatemi FTL | CE | shopping | R$ 5157.64 | R$ 24.13 | 213 | 191 | 76 | 34 |
| 03/07/2026 | MP020 | Iguatemi FTL | CE | shopping | R$ 5704.88 | R$ 23.58 | 241 | 174 | 108 | 36 |
| 04/07/2026 | MP020 | Iguatemi FTL | CE | shopping | R$ 7289.53 | R$ 25.27 | 288 | 233 | 100 | 44 |
| 05/07/2026 | MP020 | Iguatemi FTL | CE | shopping | R$ 6096.78 | R$ 23.51 | 259 | 209 | 107 | 44 |
| 06/07/2026 | MP020 | Iguatemi FTL | CE | shopping | R$ 4165.58 | R$ 26.42 | 157 | 117 | 64 | 23 |
| 07/07/2026 | MP020 | Iguatemi FTL | CE | shopping | R$ 5509.60 | R$ 23.52 | 234 | 201 | 89 | 35 |
| 08/07/2026 | MP020 | Iguatemi FTL | CE | shopping | R$ 4590.92 | R$ 25.80 | 177 | 146 | 92 | 32 |
| 09/07/2026 | MP020 | Iguatemi FTL | CE | shopping | R$ 5040.56 | R$ 25.01 | 201 | 172 | 85 | 31 |
| 10/07/2026 | MP020 | Iguatemi FTL | CE | shopping | R$ 6428.85 | R$ 22.63 | 284 | 233 | 97 | 45 |
| 11/07/2026 | MP020 | Iguatemi FTL | CE | shopping | R$ 6157.75 | R$ 26.09 | 236 | 198 | 112 | 34 |
| 12/07/2026 | MP020 | Iguatemi FTL | CE | shopping | R$ 6696.72 | R$ 23.20 | 288 | 254 | 110 | 49 |
| 13/07/2026 | MP020 | Iguatemi FTL | CE | shopping | R$ 3920.87 | R$ 25.22 | 155 | 114 | 69 | 20 |
| 14/07/2026 | MP020 | Iguatemi FTL | CE | shopping | R$ 4925.26 | R$ 26.00 | 189 | 146 | 72 | 26 |
| 15/07/2026 | MP020 | Iguatemi FTL | CE | shopping | R$ 4944.29 | R$ 24.16 | 204 | 156 | 101 | 29 |
| 16/07/2026 | MP020 | Iguatemi FTL | CE | shopping | R$ 4747.27 | R$ 23.32 | 203 | 178 | 91 | 36 |
| 17/07/2026 | MP020 | Iguatemi FTL | CE | shopping | R$ 6413.67 | R$ 25.66 | 249 | 232 | 103 | 44 |
| 18/07/2026 | MP020 | Iguatemi FTL | CE | shopping | R$ 6832.23 | R$ 24.44 | 279 | 244 | 127 | 47 |
| 19/07/2026 | MP020 | Iguatemi FTL | CE | shopping | R$ 6240.53 | R$ 23.79 | 262 | 220 | 92 | 47 |
| 20/07/2026 | MP020 | Iguatemi FTL | CE | shopping | R$ 3951.75 | R$ 26.43 | 149 | 129 | 58 | 29 |
| 21/07/2026 | MP020 | Iguatemi FTL | CE | shopping | R$ 5791.53 | R$ 22.93 | 252 | 203 | 119 | 44 |
| 22/07/2026 | MP020 | Iguatemi FTL | CE | shopping | R$ 5720.74 | R$ 22.76 | 251 | 211 | 127 | 46 |
| 23/07/2026 | MP020 | Iguatemi FTL | CE | shopping | R$ 5571.14 | R$ 23.93 | 232 | 213 | 92 | 38 |
| 24/07/2026 | MP020 | Iguatemi FTL | CE | shopping | R$ 6112.78 | R$ 25.70 | 237 | 216 | 89 | 37 |
| 25/07/2026 | MP020 | Iguatemi FTL | CE | shopping | R$ 7085.39 | R$ 26.25 | 269 | 226 | 113 | 40 |
| 26/07/2026 | MP020 | Iguatemi FTL | CE | shopping | R$ 7551.74 | R$ 26.00 | 290 | 230 | 132 | 45 |
| 27/07/2026 | MP020 | Iguatemi FTL | CE | shopping | R$ 3985.35 | R$ 23.45 | 169 | 133 | 68 | 22 |
| 28/07/2026 | MP020 | Iguatemi FTL | CE | shopping | R$ 5721.53 | R$ 23.33 | 245 | 197 | 91 | 44 |
| 29/07/2026 | MP020 | Iguatemi FTL | CE | shopping | R$ 5629.67 | R$ 23.81 | 236 | 182 | 90 | 40 |
| 30/07/2026 | MP020 | Iguatemi FTL | CE | shopping | R$ 5542.41 | R$ 25.86 | 214 | 201 | 81 | 38 |

### Eventos-chave de julho (relembrando o contexto)
- **03/jul** — lancamento Bowl Cupuacu Sertanejo em toda a rede
- **12-19/jul** — MP020 Iguatemi Fortaleza com praca de alimentacao em obra
- **15/jul** — concorrente local abre proximo a MP011 Sobral
- **MP009 Petrolina** e **MP019 Cariri** — nao venderam cupuacu no mes (falha de logistica interior)
- **Julho** — ferias escolares (trafego +18% FDS em capitais)

### O que o supervisor precisa decidir
1. Onde alocar investimento em campanha na proxima quinzena?
2. Que loja(s) precisam de intervencao emergencial?
3. Qual e o padrao replicavel das lojas que estao subindo forte?
4. A falha de cupuacu no interior e problema pontual ou estrutural?
5. Como o concorrente em Sobral afeta a decisao regional?
