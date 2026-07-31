# Prompt · Treinamento de 30 min pra atendente novo

> Copia daqui até o fim e cola no Claude, Kimi ou DeepSeek. O manual da rede já vem inline no final do prompt — funciona sem upload. Se preferir, faça upload do `insumo-manual-padrao-atendimento.docx`.

---

# PAPEL
Você é uma head de treinamento de rede de franquia food service, com 15 anos de
carreira em Chilli Beans, McDonald's e Boticário. Sua marca é transformar
manual longo e cansativo em treinamento de 30 minutos que o atendente **quer**
fazer — porque é claro, direto, com exemplo real, e ele sai treinando o
colega no dia seguinte. Você odeia PPT de 40 slides que ninguém termina.

# CONTEXTO
Sou supervisora de RH da Maria Pitanga (Marina Torres), rede de +200 franquias
de açaí e gelatos. Toda semana temos 8-12 atendentes novos entrando em lojas
diferentes. Hoje o treinamento é uma reunião de 2h com o gerente, sem
material padrão — resultado: cada loja treina de um jeito, cliente sente
diferença. Preciso criar um treinamento de 30 minutos, replicável, que o
gerente da loja consiga rodar sozinho no primeiro dia do atendente novo.

Vou anexar no final do prompt o **manual de padrão de atendimento da rede**
(documento oficial, versão 3.2). São 6 momentos definidos: recepção, escuta
ativa, sugestão de topping, cross-sell, resolução de reclamação, encerramento.
Cada um com frase-âncora, atitude esperada e o que NÃO fazer.

# TAREFA
Gere um **Artifact HTML self-contained** (uma única página web) chamado
**"Treinamento · Padrão Maria Pitanga · 30 minutos"** contendo **3 blocos**:

## BLOCO 1 · Deck de apresentação (5 slides)
5 slides visuais no formato 16:9, cada um com título grande, 3-4 bullets
curtos, e uma frase de fecho. Ordem obrigatória:
1. **Boas-vindas** — quem sou, por que Maria Pitanga, o que você leva daqui
2. **Os 6 momentos do atendimento MP** — visão geral com timeline horizontal
3. **A frase-âncora de cada momento** — grid 2×3 com as 6 frases-chave
4. **Como resolver reclamação em 3 passos** — passo 1 acolher, passo 2 explicar, passo 3 resolver
5. **O que fazer no primeiro dia** — checklist de 5 ações + próxima etapa

Os slides devem ser navegáveis com setas do teclado ou botões visíveis. Layout:
título grande no topo, corpo centralizado, footer discreto com "Slide N / 5"
e a marca Maria Pitanga.

## BLOCO 2 · Apostila do aluno (formato A4 imprimível)
Uma seção logo abaixo dos slides, formatada como página A4 imprimível. Contém:
- Cabeçalho com foto do produto (usar placeholder colorido roxo/creme)
- Nome do treinamento e nome do atendente (campo em branco pra preencher)
- Resumo dos 6 momentos em 1 linha cada
- Espaço pra anotação em cada momento (3 linhas em branco)
- Cardápio âncora resumido (5 produtos-chave)
- Rodapé com "Marina Torres · Supervisora RH" e espaço pra assinatura

## BLOCO 3 · Roteiro do supervisor (2 páginas)
Uma seção final formatada como documento executivo, destinada ao gerente da
loja que vai rodar o treinamento. Contém, na ordem:
- **Objetivo do treinamento** em 1 parágrafo
- **Tempo total: 30 min** com breakdown por bloco (5 min boas-vindas + 15 min
  os 6 momentos + 5 min role-play de reclamação + 5 min fechamento)
- **O que preparar antes** (checklist de 5 itens materiais + espaço)
- **Script literal do que dizer** em cada bloco (não perguntinhas — o que
  falar palavra por palavra), com timestamps sugeridos
- **Perguntas frequentes** do atendente novo (3-4 perguntas com resposta)
- **Como avaliar se funcionou** — 3 sinais concretos no dia seguinte

# ESTILO DE SAÍDA
- Página HTML self-contained (tudo inline: CSS, JS de navegação dos slides)
- Fundo **off-white creme #F0EEE6**, texto **#141413**
- Accent **roxo Maria Pitanga #6B2E7A**
- Tipografia sans-serif limpa (Inter/system-ui)
- Slides ocupam a tela inteira quando ativos (min-height 100vh)
- Apostila e roteiro em cards com respiro editorial
- Sem dark mode, sem gradientes, sem emoji decorativo
- `@media print` embutido: apostila e roteiro imprimem A4 limpo, slides ocultam no print
- Navegação dos slides via botões visíveis + setas do teclado (esquerda/direita)
- Contador "Slide N de 5" discreto no rodapé de cada slide

# LINGUAGEM
Português-BR direto, tom de rede que valoriza o operacional. Sem "vale
destacar", sem "é importante notar". Fale como se estivesse escrevendo pro
gerente da loja de Fortaleza que tem 30 anos de casa mas nunca deu treinamento
formal. Prático, não formal.

# ANTES DE GERAR
Confirme em 3 bullets:
(a) Sua estratégia pedagógica pros 30 min (o que vai priorizar dos 6 momentos)
(b) Que role-play concreto você vai propor no bloco de reclamação
(c) Como você vai fazer a apostila ter valor mesmo em preto-e-branco impresso

Espere meu OK. **Só depois** gera o Artifact HTML completo.

---

## DADOS · Manual Padrão Maria Pitanga de Atendimento (v3.2 · jul/2026)

**Responsável:** Marina Torres · Supervisora RH · marina.torres@mariapitanga.com.br

### Sobre o padrão
O padrão MP resume o atendimento em 6 momentos, do cliente entrar na loja até
sair. Cada momento tem uma **frase-âncora** (o que dizer), uma **atitude**
(postura corporal esperada) e um **sinal de alerta** (o que NÃO fazer). O
objetivo é que qualquer cliente, em qualquer uma das 200+ lojas, tenha a
mesma experiência.

### Momento 1 · Recepção (primeiros 5 segundos)
- Frase-âncora: "Oi, bem-vinda à Maria Pitanga!" (com contato visual)
- Atitude: parar o que está fazendo por 1 segundo, sorrir, cumprimentar. Se estiver atendendo, virar a cabeça.
- NÃO fazer: continuar mexendo no caixa sem olhar. Dizer "pois não" (soa telemarketing).

### Momento 2 · Escuta ativa (do primeiro pedido)
- Frase pra cliente novo: "É a primeira vez aqui? Posso te contar como funciona?"
- Frase pra cliente recorrente: "O de sempre ou quer testar o novo Cupuaçu Sertanejo?"
- Atitude: escutar até o cliente terminar. Não interromper com sugestão antes dele falar.
- NÃO fazer: falar "temos açaí, sorbet, gelato" de cara. Tratar cliente novo como se já soubesse.

### Momento 3 · Sugestão de topping (upsell suave)
- Frase-âncora: "Vai de topping? A gente tem granola, castanha do Pará torrada, e um cacau em pedaço que é sensacional."
- Atitude: mencionar 2-3 opções concretas, não a lista inteira. Deixar cliente escolher sem pressionar.
- NÃO fazer: perguntar "quer topping?" sem opção. Falar tudo (paralisa). Insistir se cliente disse não.
- Dado: 70% do ticket médio de R$ 22,40 vem dos toppings.

### Momento 4 · Cross-sell (bebida ou 2ª porção)
- Frase-âncora: "Uma água ou suco pra acompanhar? Ou um chikito pra levar depois?"
- Atitude: mencionar 1 vez, com sorriso. Se cliente disse não, seguir o fluxo.
- NÃO fazer: oferecer mais de 1 vez. Sugerir combo que dobra o valor sem explicar.

### Momento 5 · Resolução de reclamação (quando algo dá errado)
Os 3 passos da rede: **acolher · explicar · resolver**.
- Passo 1 (acolher): "Entendi. Que ruim ter passado por isso." (sem "mas")
- Passo 2 (explicar): "Vou entender aqui o que aconteceu e já te trago a solução."
- Passo 3 (resolver): oferecer nova porção, cortesia, ou troca. Acima de R$ 30, chamar gerente.
- Atitude: baixar tom de voz, olho no olho, não sorrir (cliente reclamando não quer sorriso). Escutar até o fim.
- NÃO fazer: dizer "é assim mesmo" ou "é o sistema". Chamar cliente de "minha querida" (soa debochado). Prometer o que não tem autonomia.

### Momento 6 · Encerramento (a última impressão fica)
- Frase-âncora: "Volta sempre! Bom fim de dia." (nome do cliente se souber)
- Atitude: olhar pra ele saindo, não pro próximo já. Sorriso natural. Sacola na mão dele, não sobre o balcão.
- NÃO fazer: dizer só "tchau" e virar. Continuar mexendo no caixa antes do cliente sair de vista.

### Regras de higiene e apresentação (não negociáveis)
- Uniforme completo, limpo, camisa por dentro da calça, sapato fechado
- Cabelo preso e touca durante a manipulação de alimentos
- Unhas curtas, sem esmalte vermelho ou artificial
- Celular fica na mochila. Consulta pessoal só no intervalo
- Nunca comer, beber ou mascar chiclete no salão

### Cardápio âncora — TODO atendente sabe decorado
- Bowl Açaí Signature (300g) — R$ 22,90 — base da casa, 4 toppings inclusos
- Bowl Cupuaçu Sertanejo (350g) — R$ 26,90 — lançamento, sabor amazônico com granola artesanal
- Sorbet do Dia (150g) — R$ 14,90 — sabor rotativo, checar quadro do dia
- Gelato Casca de Cacau (100g) — R$ 12,50 — item premium, público adulto
- Combo Kids (bowl mini + suco) — R$ 19,90 — apenas até 18h

### Meta do treinamento
Ao final dos 30 minutos, o atendente novo deve ser capaz de:
1. Receber cliente na porta com a frase-âncora certa
2. Diferenciar cliente novo de recorrente e adaptar a escuta
3. Fazer sugestão de topping sem parecer forçado
4. Resolver reclamação simples usando os 3 passos
5. Encerrar com padrão da rede
