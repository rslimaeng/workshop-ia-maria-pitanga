# Prompt · Radar de voz do cliente (5 lojas Maria Pitanga)

> Copia tudo daqui até o final e cola no Claude, Kimi ou DeepSeek. O prompt já vem com os 150 reviews inline — não precisa fazer upload da planilha. Se seu chat travar com tanto texto, faça upload direto do arquivo `insumo-reviews-5-lojas.xlsx`.

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
Google Maps as **150 avaliações mais recentes** das minhas 5 lojas (30 por
loja), das últimas 4 semanas.

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
Analise as 150 reviews e gere um **Artifact HTML self-contained** (uma única
página, pronta pra abrir no navegador) com estas 5 seções:

## 1. QUADRO GERAL (topo)
Números grandes destacados:
- Total de reviews analisadas
- Nota média geral
- % de reviews negativas (nota ≤ 3)
- Loja com melhor e pior nota média (chip lado a lado)

## 2. TEMAS RECORRENTES (o coração do artefato)
Agrupe as 150 reviews em **6 a 9 temas** (exemplos possíveis: fila, sabor,
atendente específico, limpeza, preço, app/pagamento, produto novo, atendimento
internacional). Para cada tema:
- Nome do tema
- Quantas reviews citam
- Sentimento predominante (positivo/neutro/negativo)
- 2-3 trechos literais de exemplo (com nome do autor entre parênteses)

Ordene por frequência decrescente. Com 150 reviews você tem base pra
identificar tanto o padrão macro (fila é problema de rede) quanto o específico
(atendente Bruno é problema de Sobral).

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
(a) Quantas reviews leu por loja (deve dar 30 em cada)
(b) Sua leitura macro em 1 parágrafo (o que mais chamou atenção no conjunto)
(c) Quais foram os 6-9 temas que você agrupou

Espere meu OK. **Só depois** gera o Artifact HTML completo.

---

## DADOS · 150 reviews Google Maps (últimas 4 semanas)

| Data | Loja | Cidade | Autor | Nota | Avaliação |
|---|---|---|---|---|---|
| 2026-07-29 | Aldeota | Fortaleza/CE | Marina Freitas | 5 | Melhor açaí da cidade. A Ana me atendeu e explicou os toppings novos com paciência, super simpática. Bowl de cupuaçu incrível. |
| 2026-07-28 | Aldeota | Fortaleza/CE | Rafael Costa | 4 | Ambiente limpíssimo, o pessoal cuida bem. Nota 4 só porque a fila no sábado à tarde tá enorme, uns 20 min de espera. |
| 2026-07-27 | Aldeota | Fortaleza/CE | Larissa Menezes | 5 | Ana é um espetáculo, virou meu ponto fixo depois do trabalho. Só acho que o preço deu uma subida esses meses, tá salgado. |
| 2026-07-26 | Aldeota | Fortaleza/CE | Pedro Nunes | 5 | Fui pela primeira vez experimentar o bowl novo de cupuaçu e me converti. Voltarei toda semana. |
| 2026-07-25 | Aldeota | Fortaleza/CE | Camila Rocha | 3 | Açaí bom mas o app travou na hora de pagar, tive que refazer no caixa. Perdi 15 min por causa disso. |
| 2026-07-24 | Aldeota | Fortaleza/CE | Diogo Alencar | 4 | Sempre limpo, sempre gostoso. Fila do fim de semana é o único ponto negativo. |
| 2026-07-23 | Aldeota | Fortaleza/CE | Isabella Farias | 5 | Loja mais bonita da rede em Fortaleza. Ambiente refrescante, atendimento impecável da Ana e da Priscila. |
| 2026-07-22 | Aldeota | Fortaleza/CE | João Pedro Lima | 4 | Bowl de cupuaçu tá dando o que falar mesmo. Só senti que o preço médio ficou um pouco acima do concorrente. |
| 2026-07-21 | Aldeota | Fortaleza/CE | Nathalia Braga | 5 | Peço pelo iFood 3x na semana, sempre entrega direitinho. Loja física também é ótima. |
| 2026-07-20 | Aldeota | Fortaleza/CE | Igor Fontes | 3 | Cheguei sábado 17h, fila até a rua. Fui embora, voltei domingo. Domingo tudo perfeito, mas sábado é impossível. |
| 2026-07-19 | Aldeota | Fortaleza/CE | Bianca Oliveira | 5 | Ana lembrou do meu pedido de sempre sem eu falar. Isso é atendimento nível hotel 5 estrelas. |
| 2026-07-18 | Aldeota | Fortaleza/CE | Marcelo Ribeiro | 4 | Cupuaçu virou meu vício. Único ponto: a bateria do app pra fidelidade nunca soma direito, sempre preciso reclamar. |
| 2026-07-17 | Aldeota | Fortaleza/CE | Sofia Cardoso | 5 | Ambiente familiar mesmo sendo cheio. Levei minha filha pequena e a Ana ainda deu um brinde. Amei. |
| 2026-07-16 | Aldeota | Fortaleza/CE | Vitor Sales | 4 | Loja bem servida de opções, mas o preço realmente subiu. Bowl médio hoje custa quase R$ 30, achei salgado. |
| 2026-07-15 | Aldeota | Fortaleza/CE | Laís Torres | 5 | Programa de fidelidade tá gerando resultado — juntei pontos e ganhei um bowl grátis semana passada. |
| 2026-07-14 | Aldeota | Fortaleza/CE | Bernardo Rocha | 3 | Fila enorme quarta-feira à noite. Antes era horário tranquilo, agora tá cheio sempre. Escala de atendimento tá curta. |
| 2026-07-13 | Aldeota | Fortaleza/CE | Priscila Andrade | 5 | O melhor da rede. Aline (gerente) sempre atenciosa. Cupuaçu novo virou o pedido oficial da casa. |
| 2026-07-12 | Aldeota | Fortaleza/CE | Antonio Vasques | 4 | Bom produto, bom atendimento, mas o preço tá se distanciando dos concorrentes locais. Cuidado com isso. |
| 2026-07-11 | Aldeota | Fortaleza/CE | Helena Vieira | 5 | Ana e Priscila são as melhores atendentes de qualquer lugar que eu já fui em Fortaleza. Toppings sempre no ponto. |
| 2026-07-10 | Aldeota | Fortaleza/CE | Guilherme Prado | 4 | Sempre limpo, sempre gostoso. Fila do fim de semana continua sendo o único ponto negativo — hora de expandir o balcão? |
| 2026-07-09 | Aldeota | Fortaleza/CE | Ana Clara Bezerra | 5 | Peguei o combo bowl cupuaçu + café gelado, experiência 10/10. Ambiente confortável para trabalhar. |
| 2026-07-08 | Aldeota | Fortaleza/CE | Ricardo Mota | 2 | Tentei pagar pelo app 3 vezes e travou. Tive que refazer no caixa e perdi meu horário. Chatiado. |
| 2026-07-07 | Aldeota | Fortaleza/CE | Juliane Aragão | 5 | Cupuaçu com castanha-do-pará é o melhor bowl que já comi. Ana me indicou baseado no que eu tinha pedido antes, arrasou. |
| 2026-07-06 | Aldeota | Fortaleza/CE | Felipe Souto | 4 | Loja moderna, atendimento simpático. O preço tá subindo, mas ainda vale. |
| 2026-07-05 | Aldeota | Fortaleza/CE | Luana Cavalcante | 5 | Melhor açaí de Fortaleza sem dúvida. Ana no atendimento sempre torna a experiência especial. |
| 2026-07-04 | Aldeota | Fortaleza/CE | Rodrigo Aguiar | 3 | Sábado 15h fila até a esquina. Fui embora sem esperar. Vocês precisam de mais gente na escala do fim de semana. |
| 2026-07-03 | Aldeota | Fortaleza/CE | Cintia Barros | 5 | Novidade de cupuaçu chegou e virou hit imediato. Parabéns pela escolha de sabor. |
| 2026-07-02 | Aldeota | Fortaleza/CE | Otávio Pinheiro | 4 | Bowl e atendimento sempre bons. Preço se tornou um ponto de atenção, tá pertinho de me fazer pensar antes de vir. |
| 2026-07-01 | Aldeota | Fortaleza/CE | Vanessa Franco | 5 | Vim comemorar aniversário com as amigas, Ana montou uma vela improvisada no bowl. Detalhes assim ficam guardados. |
| 2026-06-30 | Aldeota | Fortaleza/CE | Thiago Bezerra | 4 | Melhor loja da rede que já visitei — visitei Iguatemi e Sobral também. Aqui a operação é impecável, só a fila fim-semana atrapalha. |
| 2026-07-29 | Iguatemi | Fortaleza/CE | Beatriz Sampaio | 5 | O bowl de cupuaçu virou meu vício, obrigada Maria Pitanga por essa novidade! |
| 2026-07-28 | Iguatemi | Fortaleza/CE | Gustavo Lima | 2 | Esperei 25 minutos numa quarta 21h. Só tinha 2 pessoas atendendo com fila enorme. Perdi a paciência e fui embora. |
| 2026-07-27 | Iguatemi | Fortaleza/CE | Fernanda Vieira | 4 | Sabor de sempre bom, atendimento ok. Sinto que os preços subiram bastante desde o começo do ano. |
| 2026-07-26 | Iguatemi | Fortaleza/CE | Tiago Mendes | 5 | Levei os sobrinhos, todos amaram os toppings novos. Atendente super gentil. |
| 2026-07-25 | Iguatemi | Fortaleza/CE | Juliana Barbosa | 3 | Pagamento pelo app deu erro duas vezes seguidas. No caixa foi rápido. Vocês precisam arrumar esse app. |
| 2026-07-24 | Iguatemi | Fortaleza/CE | Marcos Andrade | 4 | Cupuaçu delicioso, mas o sorbet de manga tava um pouco duro, tive que esperar amolecer. |
| 2026-07-23 | Iguatemi | Fortaleza/CE | Danielle Cordeiro | 3 | Loja lotada em qualquer horário. Bruno (novato) tá bem inseguro no atendimento, cometeu 2 erros no meu pedido. |
| 2026-07-22 | Iguatemi | Fortaleza/CE | Alan Pereira | 2 | Fila de 30 min num domingo à noite. Não dá. Precisam abrir uma 2ª unidade no shopping. |
| 2026-07-21 | Iguatemi | Fortaleza/CE | Michele Gomes | 4 | Bowl bom, mas o sorbet realmente vem gelado demais. Já reclamei uma vez, achei que iam ajustar. |
| 2026-07-20 | Iguatemi | Fortaleza/CE | Carlos Nogueira | 3 | Comprei via iFood, chegou com sorbet totalmente derretido. Sabor bom mas experiência ruim. |
| 2026-07-19 | Iguatemi | Fortaleza/CE | Renata Peixoto | 5 | Cupuaçu com castanha-do-pará, combo perfeito. Voltarei toda semana. |
| 2026-07-18 | Iguatemi | Fortaleza/CE | Lucas Bento | 2 | Cheguei 20h30 e o cupuaçu já tinha esgotado. 3ª vez que acontece esse mês. Preciso mesmo? |
| 2026-07-17 | Iguatemi | Fortaleza/CE | Amanda Correia | 4 | Atendimento OK, loja lotada como sempre. Perceptível a queda no atendimento desde que a Ana saiu. |
| 2026-07-16 | Iguatemi | Fortaleza/CE | Ricardo Xavier | 3 | Sorbet de manga quebrou minha colherzinha de tão duro. Já é a segunda vez que reclamo isso. |
| 2026-07-15 | Iguatemi | Fortaleza/CE | Patrícia Lopes | 4 | Bom produto, movimento intenso. Cupuaçu vale a pena, mas prepare-se pra fila em horário de pico. |
| 2026-07-14 | Iguatemi | Fortaleza/CE | Bruno Sales | 2 | Pagamento pelo app trava toda vez que eu tento. Ridículo em 2026 ter esse problema recorrente. |
| 2026-07-13 | Iguatemi | Fortaleza/CE | Karolina Freire | 4 | Loja bem servida de opções veganas, isso pesa positivo. Só o fluxo intenso que atrapalha um pouco a experiência. |
| 2026-07-12 | Iguatemi | Fortaleza/CE | Eduardo Barreto | 3 | Bowl entregue certinho mas 22 min de espera num terça 19h. Escala insuficiente. |
| 2026-07-11 | Iguatemi | Fortaleza/CE | Sabrina Melo | 5 | Novo bowl de cupuaçu é obra de arte. Vale a fila. |
| 2026-07-10 | Iguatemi | Fortaleza/CE | Luiz Henrique Cruz | 2 | Rodrigo (que era bom) saiu, o pessoal novo tá cru. Padrão caiu. |
| 2026-07-09 | Iguatemi | Fortaleza/CE | Denise Coelho | 4 | Sempre bom mas o app é uma pena. Se resolvessem essa questão eu daria 5. |
| 2026-07-08 | Iguatemi | Fortaleza/CE | Fabio Pontes | 3 | Loja produtiva mas o novo atendente Bruno mistura os toppings. 3ª vez que meu pedido veio errado. |
| 2026-07-07 | Iguatemi | Fortaleza/CE | Aline Sales | 5 | Combo cupuaçu + coco raspa nível divino. Preço médio, atendimento correto. |
| 2026-07-06 | Iguatemi | Fortaleza/CE | Kaio Melo | 2 | Domingo 14h, esgotou 3 sabores diferentes de sorbet. Vocês estão errando a gestão de estoque? |
| 2026-07-05 | Iguatemi | Fortaleza/CE | Lorena Chagas | 4 | Loja lotada em qualquer dia, isso é bom sinal, só sinto que a operação não tá dando conta. |
| 2026-07-04 | Iguatemi | Fortaleza/CE | Marcelo Feitosa | 3 | Vim 3x essa semana, 3x o app deu erro na hora de pagar. Uma delas o cupuaçu tinha esgotado. Frustrante. |
| 2026-07-03 | Iguatemi | Fortaleza/CE | Camille Amaral | 5 | Bowl cupuaçu virou meu momento premium da semana. Preço vale, produto entrega. |
| 2026-07-02 | Iguatemi | Fortaleza/CE | Rogério Costa | 2 | Cheguei sexta 20h, fila até o corredor do shopping. Fui embora. Vocês precisam repensar horário-pico. |
| 2026-07-01 | Iguatemi | Fortaleza/CE | Simone Vasconcelos | 4 | Loja com energia boa, mas dá pra sentir que o time novo ainda tá se ajustando. Padrão da rede ainda existe, só oscila. |
| 2026-06-30 | Iguatemi | Fortaleza/CE | Jefferson Ramos | 3 | Sorbet duro é praticamente marca da casa aqui. Sabor bom, temperatura ruim. Resolvam. |
| 2026-07-29 | Cariri Garden | Juazeiro do Norte/CE | Ana Paula Cruz | 2 | Cheguei no domingo à tarde e o chão estava pegajoso, mesa suja não limpa. Açaí é bom mas o ambiente afasta. |
| 2026-07-28 | Cariri Garden | Juazeiro do Norte/CE | Rodrigo Silva | 4 | O açaí em si é excelente, o pessoal simpático. Só precisam melhorar a manutenção da loja, tá desleixada. |
| 2026-07-27 | Cariri Garden | Juazeiro do Norte/CE | Vanessa Oliveira | 5 | Sabor divino, o novo bowl de cupuaçu tá arrasando aqui em Juazeiro. Voltarei sempre! |
| 2026-07-26 | Cariri Garden | Juazeiro do Norte/CE | Carlos Eduardo | 3 | Açaí bom, mas os banheiros da loja estavam num estado ruim. Falta zelo. |
| 2026-07-25 | Cariri Garden | Juazeiro do Norte/CE | Renata Alves | 4 | Atendimento rápido, sem fila num terça de tarde. Preço tá subindo demais. |
| 2026-07-24 | Cariri Garden | Juazeiro do Norte/CE | Felipe Martins | 5 | Melhor doce da cidade. Único ponto: o app às vezes trava, mas no caixa vão super rápido. |
| 2026-07-23 | Cariri Garden | Juazeiro do Norte/CE | Bruna Nascimento | 3 | Fui almoçar e tinha 3 mesas sujas. Solicitei limpeza, atendente veio de má vontade. Produto bom, atendimento oscilante. |
| 2026-07-22 | Cariri Garden | Juazeiro do Norte/CE | Márcio Duarte | 4 | Bowl de cupuaçu vale a pena. Só melhorem a limpeza do salão em horário pós-almoço. |
| 2026-07-21 | Cariri Garden | Juazeiro do Norte/CE | Silvana Barros | 2 | Banheiro sem papel, chão molhado. Salão OK mas a manutenção pesada tá abandonada. Difícil recomendar assim. |
| 2026-07-20 | Cariri Garden | Juazeiro do Norte/CE | Erick Menezes | 5 | Cupuaçu com granola caseira é sensacional. Fico feliz que chegou a Juazeiro. |
| 2026-07-19 | Cariri Garden | Juazeiro do Norte/CE | Talita Pereira | 4 | Loja com bom atendimento nos dias úteis, mas o preço em Juazeiro tá salgado pro público local. Cuidem. |
| 2026-07-18 | Cariri Garden | Juazeiro do Norte/CE | Wagner Souza | 3 | Produto bom, mas fila no domingo pós-igreja é impossível. Chegou tarde, esgotou meia dúzia de opções. |
| 2026-07-17 | Cariri Garden | Juazeiro do Norte/CE | Camila Nobre | 5 | Ambiente aconchegante quando limpo. Cupuaçu me conquistou. Só cuidem melhor da manutenção. |
| 2026-07-16 | Cariri Garden | Juazeiro do Norte/CE | Guilherme Pinto | 2 | Cheguei sábado 16h, banheiro fedorento. Café gelado que pedi tava morno. Padrão da rede aqui não existe. |
| 2026-07-15 | Cariri Garden | Juazeiro do Norte/CE | Débora Alves | 4 | Bowl bom, atendimento cortês. Só a manutenção da loja precisa de atenção — parece que faz tempo que não passa por reforma. |
| 2026-07-14 | Cariri Garden | Juazeiro do Norte/CE | Rafael Nunes | 3 | Preço alto pra realidade de Juazeiro. Bowl de 350g custa quase R$ 27, meu almoço custa isso na cidade. |
| 2026-07-13 | Cariri Garden | Juazeiro do Norte/CE | Amélia Correia | 5 | Levei minhas amigas do coral, todas amaram o cupuaçu. Vamos virar clientes de sábado após ensaio. |
| 2026-07-12 | Cariri Garden | Juazeiro do Norte/CE | Anderson Lima | 3 | Bom produto mas o WiFi da loja é péssimo — vim trabalhar aqui e não deu. Pra shopping novo é vergonhoso. |
| 2026-07-11 | Cariri Garden | Juazeiro do Norte/CE | Vitória Sampaio | 4 | Atendimento simpático, cupuaçu delicioso. Chão da entrada precisa passar pano com mais frequência. |
| 2026-07-10 | Cariri Garden | Juazeiro do Norte/CE | Márcia Freire | 2 | Fui no domingo 19h, várias mesas sujas, funcionários conversando em vez de limpar. Padrão de rede não existe aqui. |
| 2026-07-09 | Cariri Garden | Juazeiro do Norte/CE | Elias Batista | 5 | Melhor doce que abriu no Cariri em anos. Cupuaçu é o carro-chefe agora. |
| 2026-07-08 | Cariri Garden | Juazeiro do Norte/CE | Isabelle Rocha | 4 | Loja com potencial gigante, atendimento cordial. Precisam cuidar da limpeza fim de semana e podem ter fã fiel. |
| 2026-07-07 | Cariri Garden | Juazeiro do Norte/CE | Douglas Aragão | 3 | Preço já beira R$ 30 no bowl médio. Público de Juazeiro sente muito. Vale reavaliar o mix. |
| 2026-07-06 | Cariri Garden | Juazeiro do Norte/CE | Karla Andrade | 5 | Cupuaçu com castanha-do-pará é uma explosão. Amei. Ambiente confortável no horário matinal. |
| 2026-07-05 | Cariri Garden | Juazeiro do Norte/CE | Roberto Sales | 2 | Banheiro sem sabonete, sem toalha de papel. Já reclamei há 2 semanas, tudo igual. Onde tá a gerência? |
| 2026-07-04 | Cariri Garden | Juazeiro do Norte/CE | Julia Cavalcante | 4 | Cupuaçu delicioso, atendimento OK. Preço tá esticado pro perfil da cidade — cuidado com o público local. |
| 2026-07-03 | Cariri Garden | Juazeiro do Norte/CE | Marcelo Barreto | 5 | Peguei o combo cupuaçu grande + café, saí feliz. Só a manutenção do salão que precisa de mais atenção. |
| 2026-07-02 | Cariri Garden | Juazeiro do Norte/CE | Luciana Prado | 3 | Fila em horário pós-missa domingo. Padrão da rede sai um pouco de foco quando a loja fica cheia. |
| 2026-07-01 | Cariri Garden | Juazeiro do Norte/CE | Cristian Bezerra | 4 | Bowl com bom sabor, loja com potencial. Faltam ajustes de manutenção — vitrine com poeira, banheiro precário. |
| 2026-06-30 | Cariri Garden | Juazeiro do Norte/CE | Nadia Pinheiro | 2 | 3ª vez que venho e encontro loja mal cuidada. Sabor ótimo, mas ambiente não convida a voltar. Perdendo cliente aqui. |
| 2026-07-29 | Sobral Centro | Sobral/CE | Thiago Rodrigues | 2 | Sorbet chegou tão duro que quebrei a colherzinha tentando comer. Terceira vez que isso acontece nessa loja. |
| 2026-07-28 | Sobral Centro | Sobral/CE | Karina Sousa | 1 | Fui atendida pelo Bruno de um jeito grosso, mal olhou pra mim. Não volto mais. |
| 2026-07-27 | Sobral Centro | Sobral/CE | Ricardo Batista | 3 | Açaí ok. O sorbet vem sempre muito congelado, precisa esperar 10 min. Vocês estão errando o freezer? |
| 2026-07-26 | Sobral Centro | Sobral/CE | Larissa Freitas | 5 | O bowl de cupuaçu novo salvou minha experiência aqui, delicioso demais! |
| 2026-07-25 | Sobral Centro | Sobral/CE | Bruno Cavalcanti | 2 | Sorbet duro de novo. Já reclamei da última vez, aparentemente não mudou nada. |
| 2026-07-24 | Sobral Centro | Sobral/CE | Amanda Ribeiro | 3 | Loja limpa, açaí bom. Só que o atendente Bruno é seco, não sorri, parece que tá fazendo favor. |
| 2026-07-23 | Sobral Centro | Sobral/CE | Fernando Sales | 1 | Bruno atendeu de mau humor total. Chamei o gerente, gerente não apareceu. Última vez que venho. |
| 2026-07-22 | Sobral Centro | Sobral/CE | Rosana Barros | 2 | Sorbet de manga tão duro que precisei esperar 15 min pra conseguir comer. Segunda vez que isso acontece. |
| 2026-07-21 | Sobral Centro | Sobral/CE | Igor Almeida | 4 | Bowl de cupuaçu me impressionou de verdade. Só os problemas de congelamento do sorbet e o atendimento oscilante que atrapalham. |
| 2026-07-20 | Sobral Centro | Sobral/CE | Priscila Aragão | 2 | Cheguei sábado 14h, Bruno atendeu no automático, mal reconheceu que existia. Sorbet tarde da tarde já estava esgotado. |
| 2026-07-19 | Sobral Centro | Sobral/CE | Vinícius Melo | 1 | Pior atendimento que já tive em qualquer loja da Maria Pitanga (frequento em Fortaleza e aqui). Bruno é um problema. Gerente ausente. |
| 2026-07-18 | Sobral Centro | Sobral/CE | Cíntia Torres | 5 | O cupuaçu novo é maravilhoso. Só peço pra vocês resolverem o problema do freezer. |
| 2026-07-17 | Sobral Centro | Sobral/CE | Marcos Aurélio | 3 | Loja bem localizada, produto bom. Sorbet duro e atendimento do Bruno são pontos que jogam a experiência pra baixo. |
| 2026-07-16 | Sobral Centro | Sobral/CE | Wesley Ferreira | 2 | Terceira vez que o sorbet vem pedra. Vocês precisam calibrar o freezer ou trocar por outro. |
| 2026-07-15 | Sobral Centro | Sobral/CE | Andreia Silva | 4 | Bowl cupuaçu 10/10. Atendimento oscilante — quando é a Cintia (outra atendente) é ótimo, quando é o Bruno é uma lástima. |
| 2026-07-14 | Sobral Centro | Sobral/CE | Roberto Neto | 1 | Bruno cortou minha fala, foi grosseiro. Chamei o gerente 3 vezes, ninguém apareceu. Vou reclamar formalmente. |
| 2026-07-13 | Sobral Centro | Sobral/CE | Kaline Vidal | 3 | Loja com bom produto mas atendimento comprometido pela presença do Bruno. Já reclamei antes. |
| 2026-07-12 | Sobral Centro | Sobral/CE | Diego Aragão | 5 | Cupuaçu com granola caseira, sensacional. Pena que o resto da experiência com sorbet duro atrapalha. |
| 2026-07-11 | Sobral Centro | Sobral/CE | Sabrina Menezes | 2 | Sorbet vem sempre gelado demais. Vocês têm alguém na área técnica pra ver a temperatura do freezer? |
| 2026-07-10 | Sobral Centro | Sobral/CE | Otávio Nunes | 2 | Peguei cupuaçu, chegou meio derretido no topping mas duro no meio. Máquinas descalibradas. |
| 2026-07-09 | Sobral Centro | Sobral/CE | Larissa Vilas | 1 | Bruno me atendeu com celular na mão. Só perguntou o pedido sem olhar, sem sorrir, sem falar 'obrigado'. Zero. |
| 2026-07-08 | Sobral Centro | Sobral/CE | Marcelo Aguiar | 3 | Cupuaçu salva a experiência aqui. Sorbet duro continua sendo o problema recorrente. Já é padrão. |
| 2026-07-07 | Sobral Centro | Sobral/CE | Denise Barros | 2 | Terceiro sorbet duro seguido nesse mês. Já sei que vou ter que esperar 10 min. Isso é operação ruim, não é 'freezer novo'. |
| 2026-07-06 | Sobral Centro | Sobral/CE | Aline Mendes | 4 | Bowl de cupuaçu é o melhor produto novo dos últimos anos. Loja precisa urgente melhorar quesito equipe. |
| 2026-07-05 | Sobral Centro | Sobral/CE | Elton Cunha | 1 | Bruno é o funcionário mais desagradável que já encontrei. Como esse cara ainda tá empregado? |
| 2026-07-04 | Sobral Centro | Sobral/CE | Vitor Pereira | 3 | Cupuaçu ótimo. O resto oscila muito — dependendo de quem tá atendendo, a experiência muda 100%. |
| 2026-07-03 | Sobral Centro | Sobral/CE | Clara Rodrigues | 2 | Sorbet duro. Bruno grosso. Cupuaçu bom. Padrão de qualidade da rede aqui em Sobral não existe. |
| 2026-07-02 | Sobral Centro | Sobral/CE | Adriana Lopes | 5 | Cintia atendeu maravilhosamente. Cupuaçu incrível. Estrelas pelo produto e pela Cintia — o resto da equipe precisa melhorar. |
| 2026-07-01 | Sobral Centro | Sobral/CE | Rafael Aragão | 2 | Vim 4x nas últimas 3 semanas. Sorbet duro em 3 delas. Bruno atendeu mal em 2. Perdendo cliente antigo. |
| 2026-06-30 | Sobral Centro | Sobral/CE | Michele Ramos | 1 | Terrível. Bruno me tratou como se eu estivesse atrapalhando. Nunca mais. |
| 2026-07-29 | Iguatemi Lisboa | Lisboa/PT | João Marques | 5 | Que saudade! Um pedacinho do Brasil aqui em Lisboa. O bowl de cupuaçu tá idêntico ao do Ceará. |
| 2026-07-28 | Iguatemi Lisboa | Lisboa/PT | Sofia Almeida | 3 | Achei o açaí muito doce para o paladar português. Meu marido brasileiro amou, eu nem tanto. |
| 2026-07-27 | Iguatemi Lisboa | Lisboa/PT | Mariana Prata | 4 | Ambiente lindo, atendimento cortês. Só a fila aos sábados que é uma loucura, uns 30 min de espera. |
| 2026-07-26 | Iguatemi Lisboa | Lisboa/PT | André Fernandes | 5 | Melhor açaí de Portugal, sem dúvidas. Tenho vindo toda semana desde que abriu. |
| 2026-07-25 | Iguatemi Lisboa | Lisboa/PT | Patrícia Nogueira | 2 | Preço muito alto comparado ao do Brasil. Um bowl médio aqui custa quase 12 euros, absurdo. |
| 2026-07-24 | Iguatemi Lisboa | Lisboa/PT | Ricardo Sá | 4 | Sorbet vem duro às vezes, precisa esperar. Sabor é ótimo, atendimento também. |
| 2026-07-23 | Iguatemi Lisboa | Lisboa/PT | Beatriz Costa | 5 | Levei minha família portuguesa, todos experimentaram cupuaçu pela primeira vez. Ficaram encantados. Excelente iniciativa da marca. |
| 2026-07-22 | Iguatemi Lisboa | Lisboa/PT | Rui Tavares | 3 | Sabor bom mas o preço em euros é proibitivo. 11 euros num bowl é dinheiro que dá pra jantar num sítio decente. |
| 2026-07-21 | Iguatemi Lisboa | Lisboa/PT | Carla Sousa | 4 | Loja bem posicionada no shopping. Atendimento simpático. A doçura ainda é um ponto a ajustar pro paladar local. |
| 2026-07-20 | Iguatemi Lisboa | Lisboa/PT | Manuel Ribeiro | 5 | Fui recomendado por amigo brasileiro. Cupuaçu virou obsessão. Preço é alto mas vale a experiência. |
| 2026-07-19 | Iguatemi Lisboa | Lisboa/PT | Isabel Pinto | 2 | Sábado 18h, fila de 40 min. Volume não corresponde à capacidade de atendimento. |
| 2026-07-18 | Iguatemi Lisboa | Lisboa/PT | Nuno Cardoso | 4 | Bowl é único em Portugal — nenhuma outra loja tem cupuaçu assim. Preço em euros pesa, mas o produto compensa. |
| 2026-07-17 | Iguatemi Lisboa | Lisboa/PT | Helena Gomes | 5 | Comprei pra minha filha experimentar sabores brasileiros. Ela adorou o cupuaçu. Voltaremos. |
| 2026-07-16 | Iguatemi Lisboa | Lisboa/PT | Bruno Vasconcelos | 3 | Sábado impossível de vir, fila até fora do shopping. Prefiro sextas — mas aí muitas opções esgotam. |
| 2026-07-15 | Iguatemi Lisboa | Lisboa/PT | Cristina Lopes | 4 | Adoro o cupuaçu. Só o preço em euros que continua sendo um desafio, principalmente pra quem vem em família. |
| 2026-07-14 | Iguatemi Lisboa | Lisboa/PT | Tiago Barbosa | 5 | Melhor abertura de food service em Lisboa em 2025. Cupuaçu virou o produto favorito da minha esposa. |
| 2026-07-13 | Iguatemi Lisboa | Lisboa/PT | Sara Andrade | 3 | Sorbet duro persistente. Sempre preciso esperar 5-10 min pra comer. Isso não deveria acontecer numa loja premium. |
| 2026-07-12 | Iguatemi Lisboa | Lisboa/PT | Filipa Neves | 4 | Ambiente aconchegante, atendimento cortês. Preço é o único ponto — 12€ num bowl é o preço de um almoço em Lisboa. |
| 2026-07-11 | Iguatemi Lisboa | Lisboa/PT | José Antunes | 5 | Cupuaçu com castanha-do-pará é uma revelação em Portugal. Parabéns pela expansão internacional. |
| 2026-07-10 | Iguatemi Lisboa | Lisboa/PT | Maria João Costa | 3 | Muito doce pro meu paladar. Meu marido brasileiro adorou. Talvez adaptar uma versão low-sugar pro público local? |
| 2026-07-09 | Iguatemi Lisboa | Lisboa/PT | Pedro Sousa | 5 | Cupuaçu é a estrela. Sabor autêntico do Brasil aqui em Lisboa. Vale cada centavo. |
| 2026-07-08 | Iguatemi Lisboa | Lisboa/PT | Ana Filipa | 2 | Fila enorme aos sábados. Vim 3 vezes, todas esperei mais de 25 min. Precisam melhorar a operação. |
| 2026-07-07 | Iguatemi Lisboa | Lisboa/PT | Duarte Correia | 4 | Loja bem cuidada, atendimento profissional. Preço alto mas justifica a qualidade. |
| 2026-07-06 | Iguatemi Lisboa | Lisboa/PT | Vera Mota | 5 | Melhor doce que abriu em Lisboa nos últimos anos. Cupuaçu é obra-prima. |
| 2026-07-05 | Iguatemi Lisboa | Lisboa/PT | Miguel Ferreira | 3 | Sabor bom mas preço proibitivo pra frequência semanal. 12 euros é muito pra doce. |
| 2026-07-04 | Iguatemi Lisboa | Lisboa/PT | Rita Machado | 4 | Amei o cupuaçu, atendimento simpático. Sorbet vem gelado demais às vezes, mas nada que impossibilite. |
| 2026-07-03 | Iguatemi Lisboa | Lisboa/PT | Alexandre Torres | 5 | Trouxe meus pais brasileiros que estão de visita. Choraram de saudade comendo cupuaçu aqui. Isso é levar cultura junto. |
| 2026-07-02 | Iguatemi Lisboa | Lisboa/PT | Inês Coelho | 2 | Preço em euros continua sendo o grande problema. Se abrirem em Cascais ou Sintra com preços mais acessíveis, o crescimento seria explosivo. |
| 2026-07-01 | Iguatemi Lisboa | Lisboa/PT | Rodrigo Bettencourt | 4 | Sabor bom, loja bonita, fluxo alto. Preço é caro mas único player com esse produto — segura o valor. |
| 2026-06-30 | Iguatemi Lisboa | Lisboa/PT | Diana Ferraz | 5 | Cupuaçu tá redefinindo padrões de doce em Lisboa. Continuem inovando. |
