# Contexto · Modelo do Relatório Semanal MP

> Este é o **modelo oficial** de relatório de fechamento semanal da rede.
> Todo gerente e supervisor MP recebe neste formato. Não invente estrutura
> nova — siga este template rigorosamente.
>
> No Claude Projects, cole este arquivo em **Project knowledge**.
> No Custom GPT, cole em **Knowledge**. Na versão gratuita, cole junto do
> system prompt antes do comando.

---

## Nome do documento

**Relatório Semanal · Maria Pitanga · Loja [código] · Semana [período]**

## Estrutura obrigatória (6 blocos, nessa ordem)

### Bloco 1 · Capa
- Logo/mark MP no topo (usar bloco chapado 40×40 roxo `#6B2E7A` com "MP" em branco)
- Título: "Relatório Semanal · [Loja MP0XX] · [Cidade/UF]"
- Semana e período (ex: "Semana 3 · 20/07 a 26/07/2026")
- Nome do responsável (deixar campo em branco pra preencher)
- Data de emissão (usar data de hoje)

### Bloco 2 · Manchete da semana (1 frase forte)
Uma única frase, em fonte grande, que resume a semana. Exemplos de boa manchete:
- "Semana forte: faturamento +18% com Cupuaçu Sertanejo virando top 2."
- "Semana travada pela quebra do congelador na quarta — perda de R$ 1.240 na janela do jantar."
- "Volume estável, ticket subindo: topping bombando mesmo com dias de menos fluxo."

**Não pode** ser vago tipo "semana positiva" ou "semana desafiadora".

### Bloco 3 · Big numbers (3 números, cards lado a lado)
Cada card:
- Número grande (ex: "R$ 12.422")
- Label pequeno abaixo (ex: "Faturamento da semana")
- Variação vs. semana anterior em pill colorido (verde se subiu, vermelho se caiu, cinza se estável)

Os 3 números canônicos são:
1. **Faturamento da semana** (com % vs. semana anterior)
2. **Ticket médio** (com R$ e % vs. semana anterior)
3. **Cupons emitidos** (com % vs. semana anterior)

### Bloco 4 · O que aconteceu (narrativa em 3 parágrafos)

**Parágrafo 1 · Volume e ticket** — o que os big numbers estão dizendo. Um
parágrafo de 3-4 linhas. Compare com semana anterior.

**Parágrafo 2 · Produto** — quem foi top, quem cresceu, quem caiu, quem
apareceu novo. Cite produto pelo nome exato. Fale de mix, não só de top 1.

**Parágrafo 3 · Operação** — se teve evento excepcional (feriado, ruptura de
estoque, quebra de equipamento, mudança de escala), explique aqui como ele
mexeu com o número. Se não teve, escreva "sem intercorrências operacionais
relevantes na semana" e pula.

### Bloco 5 · 3 recomendações pra próxima semana

Cada recomendação vira um card. Cada card tem:
- **Título** — 1 linha, ação específica (ex: "Aumentar preparo de Cupuaçu 30% nas sextas")
- **Por que** — 1-2 linhas explicando de onde saiu o insight (com número)
- **Como fazer** — 1 linha operacional (o que o gerente pede pra quem)
- **Como medir** — 1 linha (o KPI que vai dizer se funcionou na semana seguinte)

Regra da recomendação: **precisa ter nome de produto + dia da semana ou
horário específico + ação verificável.** Recomendação genérica não entra.

### Bloco 6 · Rodapé
- "Relatório gerado com apoio de IA · dados fornecidos pela loja"
- Assinatura da head de operações (placeholder "Head de Operações · Rede MP")
- Contato do escritório (fictício MP)

---

## Estilo visual (obrigatório)

- Fundo **off-white creme `#F0EEE6`**, texto `#141413`
- Accent **roxo Maria Pitanga `#6B2E7A`** (só nos números grandes, labels de bloco, pill de variação)
- Tipografia sans-serif limpa (Inter ou system-ui)
- Big numbers em fonte grande (48-64px), peso 600-700
- Cards com bordas sutis (1px `rgba(20,20,19,.10)`) e cantos `10px`
- Sem gradientes, sem dark mode, sem emoji decorativo
- `@media print` embutido: imprime A4 limpo, sem cortar entre blocos importantes
- Formato responsivo: desktop = 3 cards de big number lado a lado, mobile empilha

## O que NUNCA colocar no relatório
- Tabela crua de vendas linha a linha (isso é o dado bruto, não o produto final)
- Gráfico de pizza (desperdício de espaço, use barras horizontais)
- Marca d'água, "gerado por IA" em destaque (só rodapé discreto)
- Emoji decorativo em card
- Cor decorativa fora do accent roxo MP (só verde/vermelho/cinza semânticos)
