# Prompt · Radar de voz do cliente (5 lojas Maria Pitanga)

> Copia tudo daqui até o final e cola no Claude, Kimi ou DeepSeek. O prompt já vem com os 30 reviews inline — não precisa fazer upload da planilha.

---

# PAPEL
Você é uma analista sênior de experiência do cliente em uma rede de franquias
de alimentação, especialista em transformar avaliações desorganizadas em
insights acionáveis para gerência de operações. Trabalhou 8 anos com CX em
grandes redes de food service. Sabe que review isolada é ruído — o que importa
é o padrão que se repete entre lojas.

# CONTEXTO
Sou supervisor regional de 5 lojas da Maria Pitanga (rede de +200 franquias
de açaí e gelatos com unidades no Brasil, Portugal e Espanha). Baixei do
Google Maps as 30 avaliações mais recentes das minhas 5 lojas (6 por loja),
das últimas 3 semanas.

As 5 lojas são:
- **Aldeota** (Fortaleza/CE) — loja vitrine, praça nobre, público classe A/B
- **Iguatemi** (Fortaleza/CE) — shopping, fluxo alto de família e adolescente
- **Cariri Garden** (Juazeiro do Norte/CE) — cidade menor, praça em desenvolvimento
- **Sobral Centro** (Sobral/CE) — praça de rua, fluxo comercial
- **Iguatemi Lisboa** (Lisboa/PT) — loja internacional, público brasileiro expat + local

Tenho reunião de operação segunda-feira 8h com os 5 gerentes. Quero chegar
com um mapa claro: onde tá o problema, o que é padrão de rede vs específico
de uma loja, e o que a gente aciona nas próximas 2 semanas.

# TAREFA
Analise as 30 reviews e gere um **Artifact HTML self-contained** (uma única
página, pronta pra abrir no navegador) com estas 5 seções:

## 1. QUADRO GERAL (topo)
3 números grandes destacados:
- Nota média geral
- % de reviews negativas (nota ≤ 3)
- Loja com melhor e pior nota média (chip lado a lado)

## 2. TEMAS RECORRENTES (o coração do artefato)
Agrupe as 30 reviews em **5 a 7 temas** (exemplos possíveis: fila, sabor,
atendente, limpeza, preço, app/pagamento, produto novo). Para cada tema:
- Nome do tema
- Quantas reviews citam
- Sentimento predominante (positivo/neutro/negativo)
- 1-2 trechos literais de exemplo (com nome do autor entre parênteses)

Ordene por frequência decrescente.

## 3. HEATMAP LOJA × TEMA
Matriz visual em tabela HTML: 5 linhas (lojas) × N colunas (temas). Cada
célula colorida por intensidade e sentimento:
- Verde forte: tema muito citado positivamente naquela loja
- Verde claro: tema citado, positivo
- Amarelo: neutro ou dividido
- Vermelho claro: negativo, poucas menções
- Vermelho forte: negativo, muitas menções
- Cinza: tema não apareceu na loja

Deve permitir bater o olho e ver "Sobral tá com problema no tema X, Aldeota
brilha no tema Y".

## 4. TOP-3 AÇÕES SUGERIDAS PRA REUNIÃO
3 cards, cada um com:
- Ação concreta (verbo no infinitivo, específica — não "melhorar
  comunicação")
- Loja(s) afetada(s)
- Impacto esperado em 2-4 semanas
- Quem toca (supervisão / gerente da loja / RH / operação central)

## 5. RESPOSTAS-PADRÃO PRONTAS
Pra os 3 temas negativos mais recorrentes, gere 1 texto pronto de resposta
pra colar no Google Maps. Regras:
- Máximo 4 linhas
- Empático, sem culpa nem desculpa genérica
- Termina com ação concreta (não "vamos melhorar")
- Assinado "Equipe Maria Pitanga"

# ESTILO DE SAÍDA (importante)
- Página HTML self-contained (tudo inline: CSS, sem CDN, sem JS complexo)
- Fundo **creme #F0EEE6**, texto escuro #141413, tipografia Inter
  (fallback sans-serif)
- Accent **roxo Açaí #6B2E7A**
- Cards com sombra suave (não borda grossa colorida)
- Header com "Radar de voz do cliente · Semana 30" e chip de contexto
- Tudo em uma tela vertical, sem paginação
- Pronto pra imprimir A4 (usar `@media print`)
- **Não use dark mode**, não use gradientes, não use emojis em bloco decorativo

# LINGUAGEM
Português-BR direto. Sem "vale destacar", "cabe mencionar", "é importante
notar". Se pra falar, fala.

# ANTES DE GERAR O HTML
Confirme em 3 bullets curtos:
(a) Quantas reviews leu por loja
(b) Sua leitura macro em 1 parágrafo (o que mais chamou atenção no conjunto)
(c) Quais foram os 5-7 temas que você agrupou

Espere meu OK. **Só depois** gera o Artifact HTML completo.

---

## DADOS · 30 reviews Google Maps (últimas 3 semanas)

| Data | Loja | Cidade | Autor | Nota | Avaliação |
|---|---|---|---|---|---|
| 2026-07-28 | Aldeota | Fortaleza/CE | Marina Freitas | 5 | Melhor açaí da cidade. A Ana me atendeu e explicou os toppings novos com paciência, super simpática. Bowl de cupuaçu incrível. |
| 2026-07-26 | Aldeota | Fortaleza/CE | Rafael Costa | 4 | Ambiente limpíssimo, o pessoal cuida bem. Nota 4 só porque a fila no sábado à tarde tá enorme, uns 20 min de espera. |
| 2026-07-22 | Aldeota | Fortaleza/CE | Larissa Menezes | 5 | Ana é um espetáculo, virou meu ponto fixo depois do trabalho. Só acho que o preço deu uma subida esses meses, tá salgado. |
| 2026-07-19 | Aldeota | Fortaleza/CE | Pedro Nunes | 5 | Fui pela primeira vez experimentar o bowl novo de cupuaçu e me converti. Voltarei toda semana. |
| 2026-07-15 | Aldeota | Fortaleza/CE | Camila Rocha | 3 | Açaí bom mas o app travou na hora de pagar, tive que refazer no caixa. Perdi 15 min por causa disso. |
| 2026-07-10 | Aldeota | Fortaleza/CE | Diogo Alencar | 4 | Sempre limpo, sempre gostoso. Fila do fim de semana é o único ponto negativo. |
| 2026-07-27 | Iguatemi | Fortaleza/CE | Beatriz Sampaio | 5 | O bowl de cupuaçu virou meu vício, obrigada Maria Pitanga por essa novidade! |
| 2026-07-25 | Iguatemi | Fortaleza/CE | Gustavo Lima | 2 | Esperei 25 minutos numa quarta 21h. Só tinha 2 pessoas atendendo com fila enorme. Perdi a paciência e fui embora. |
| 2026-07-21 | Iguatemi | Fortaleza/CE | Fernanda Vieira | 4 | Sabor de sempre bom, atendimento ok. Sinto que os preços subiram bastante desde o começo do ano. |
| 2026-07-18 | Iguatemi | Fortaleza/CE | Tiago Mendes | 5 | Levei os sobrinhos, todos amaram os toppings novos. Atendente super gentil. |
| 2026-07-14 | Iguatemi | Fortaleza/CE | Juliana Barbosa | 3 | Pagamento pelo app deu erro duas vezes seguidas. No caixa foi rápido. Vocês precisam arrumar esse app. |
| 2026-07-09 | Iguatemi | Fortaleza/CE | Marcos Andrade | 4 | Cupuaçu delicioso, mas o sorbet de manga tava um pouco duro, tive que esperar amolecer. |
| 2026-07-29 | Cariri Garden | Juazeiro do Norte/CE | Ana Paula Cruz | 2 | Cheguei no domingo à tarde e o chão estava pegajoso, mesa suja não limpa. Açaí é bom mas o ambiente afasta. |
| 2026-07-24 | Cariri Garden | Juazeiro do Norte/CE | Rodrigo Silva | 4 | O açaí em si é excelente, o pessoal simpático. Só precisam melhorar a manutenção da loja, tá desleixada. |
| 2026-07-20 | Cariri Garden | Juazeiro do Norte/CE | Vanessa Oliveira | 5 | Sabor divino, o novo bowl de cupuaçu tá arrasando aqui em Juazeiro. Voltarei sempre! |
| 2026-07-16 | Cariri Garden | Juazeiro do Norte/CE | Carlos Eduardo | 3 | Açaí bom, mas os banheiros da loja estavam num estado ruim. Falta zelo. |
| 2026-07-12 | Cariri Garden | Juazeiro do Norte/CE | Renata Alves | 4 | Atendimento rápido, sem fila num terça de tarde. Preço tá subindo demais. |
| 2026-07-08 | Cariri Garden | Juazeiro do Norte/CE | Felipe Martins | 5 | Melhor doce da cidade. Único ponto: o app às vezes trava, mas no caixa vão super rápido. |
| 2026-07-28 | Sobral Centro | Sobral/CE | Thiago Rodrigues | 2 | Sorbet chegou tão duro que quebrei a colherzinha tentando comer. Terceira vez que isso acontece nessa loja. |
| 2026-07-25 | Sobral Centro | Sobral/CE | Karina Sousa | 1 | Fui atendida pelo Bruno de um jeito grosso, mal olhou pra mim. Não volto mais. |
| 2026-07-22 | Sobral Centro | Sobral/CE | Ricardo Batista | 3 | Açaí ok. O sorbet vem sempre muito congelado, precisa esperar 10 min. Vocês estão errando o freezer? |
| 2026-07-18 | Sobral Centro | Sobral/CE | Larissa Freitas | 5 | O bowl de cupuaçu novo salvou minha experiência aqui, delicioso demais! |
| 2026-07-15 | Sobral Centro | Sobral/CE | Bruno Cavalcanti | 2 | Sorbet duro de novo. Já reclamei da última vez, aparentemente não mudou nada. |
| 2026-07-10 | Sobral Centro | Sobral/CE | Amanda Ribeiro | 3 | Loja limpa, açaí bom. Só que o atendente Bruno é seco, não sorri, parece que tá fazendo favor. |
| 2026-07-27 | Iguatemi Lisboa | Lisboa/PT | João Marques | 5 | Que saudade! Um pedacinho do Brasil aqui em Lisboa. O bowl de cupuaçu tá idêntico ao do Ceará. |
| 2026-07-25 | Iguatemi Lisboa | Lisboa/PT | Sofia Almeida | 3 | Achei o açaí muito doce para o paladar português. Meu marido brasileiro amou, eu nem tanto. |
| 2026-07-21 | Iguatemi Lisboa | Lisboa/PT | Mariana Prata | 4 | Ambiente lindo, atendimento cortês. Só a fila aos sábados que é uma loucura, uns 30 min de espera. |
| 2026-07-17 | Iguatemi Lisboa | Lisboa/PT | André Fernandes | 5 | Melhor açaí de Portugal, sem dúvidas. Tenho vindo toda semana desde que abriu. |
| 2026-07-13 | Iguatemi Lisboa | Lisboa/PT | Patrícia Nogueira | 2 | Preço muito alto comparado ao do Brasil. Um bowl médio aqui custa quase 12 euros, absurdo. |
| 2026-07-09 | Iguatemi Lisboa | Lisboa/PT | Ricardo Sá | 4 | Sorbet vem duro às vezes, precisa esperar. Sabor é ótimo, atendimento também. |
