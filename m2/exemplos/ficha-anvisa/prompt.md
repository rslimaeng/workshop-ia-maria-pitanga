# Prompt · Ficha ANVISA + copy Instagram · Sorbet Umbu-Cajá do Sertão

> Copia daqui até o fim e cola no Claude, Kimi ou DeepSeek. O briefing da
> fábrica já vem inline no final do prompt — funciona sem upload. Se
> preferir, faça upload do `insumo-briefing-novo-sorbet.docx`.

---

# PAPEL
Você é uma nutricionista e regulatory affairs sênior com 10 anos em rótulo
e conformidade sanitária de food service — trabalhou na Vigor, Danone e
Häagen-Dazs Brasil. Domina a RDC 429/2020 da ANVISA (rotulagem nutricional
frontal), a RDC 727/2022 (declaração de alergênicos) e o Guia para
Elaboração de Informação Nutricional. Também escreve copy de social pra
marca — não a nutricionista chata que só sabe falar de "opção saudável".

# CONTEXTO
Sou nutricionista chefe da Maria Pitanga (Dra. Cristiane Aguiar · CRN-3
12.847). A rede está lançando um sorbet novo — Umbu-Cajá do Sertão — em
setembro. Recebi o briefing da fábrica hoje: produto, ingredientes,
público-alvo, estimativa nutricional. O time de marketing precisa até
05/agosto de 2 entregas: (1) a ficha técnica formatada no padrão ANVISA
pronta pra imprimir no rótulo, e (2) a copy de lançamento pra Instagram
(feed + stories).

O briefing completo com todas as informações do produto vem inline no
final deste prompt.

# TAREFA
Gere um **Artifact HTML self-contained** (uma única página, imprimível A4)
chamado **"Sorbet Umbu-Cajá · Ficha Regulatória + Kit de Lançamento"**
com **3 blocos**:

## BLOCO 1 · FICHA TÉCNICA ANVISA (imprimível, formato oficial)
Uma seção formatada como documento regulatório oficial. Contém, na ordem:

### 1.1 Identificação do produto
- Denominação de venda (obrigatório: descrição legal do produto)
- Marca comercial
- Lote-piloto (deixar campo "LOTE: ____ · FAB: __/__/__ · VAL: __/__/__")
- Peso líquido (em g e ml)
- Fabricante e CNPJ (usar dado fictício MP)
- SAC / atendimento consumidor

### 1.2 Lista de ingredientes (ordem decrescente por peso)
Formato oficial: "INGREDIENTES: [ingrediente1], [ingrediente2]...".
Usar as estimativas do briefing. Não esquecer estabilizante entre parênteses.

### 1.3 Declaração de alergênicos (RDC 727/2022)
Painel obrigatório mesmo quando não há alergênicos. Formato:
"NÃO CONTÉM GLÚTEN. NÃO CONTÉM LACTOSE. PODE CONTER..." (avaliar se
compartilha linha com produtos que contêm leite/frutas oleaginosas — assumir
que sim, é linha compartilhada, e declarar).

### 1.4 Tabela nutricional (RDC 429/2020)
Duas colunas: **"Porção de 100g"** e **"Porção de 150g (1 porção comercial)"**.
Linhas obrigatórias: valor energético (kcal e kJ), carboidratos totais,
açúcares totais, açúcares adicionados, proteínas, gorduras totais, saturadas,
trans, fibra alimentar, sódio, vitamina C. Coluna de %VD ao lado. Fontes:
os números do briefing. Usar tabela formatada em preto/branco (padrão oficial).

### 1.5 Rotulagem frontal (RDC 429/2020)
Lupa preta com fundo branco indicando "ALTO EM AÇÚCARES ADICIONADOS" se o
produto ultrapassar o limite de **15g de açúcar adicionado por 100g** em
alimento sólido (regra RDC 429/2020 · Anexo XXVII). Avaliar o briefing e
decidir — mostrar o cálculo em rodapé pequeno pra Cristiane conferir.
Formato oficial da lupa (não desenhar emoji — usar CSS/SVG).

Além disso, na tabela nutricional, calcule o **%VD dos açúcares adicionados**
usando 50g/dia como referência (RDC 429/2020) — ex: 18g/100g = 36%VD.
Não deixe essa célula em branco.

### 1.6 Instruções de conservação
"Conservar congelado a -18°C. Após aberto, consumir em até 15 dias.
Não recongelar após descongelamento."

## BLOCO 2 · POST DO FEED INSTAGRAM (1080×1080)
Um card visual 1:1, embutido na página. Preview visual real (não wireframe).
Contém:
- Foto/ilustração (placeholder colorido roxo/amarelo remetendo à fruta)
- Título grande do produto
- Subtítulo curto com posicionamento ("Da cooperativa Sertão Vivo pra sua colher")
- Data de lançamento em destaque
- Tag @mariapitanga no rodapé
- Design limpo, sem "flyer 2010"

Ao lado do post, a **legenda pronta pra colar** em block de código
selecionável. Máximo 4 parágrafos curtos, com hashtags no final (10 tags
relevantes), CTA claro, tom regional-premium sem cair em caricatura
sertaneja.

## BLOCO 3 · SEQUÊNCIA DE 3 STORIES (1080×1920)
3 cards verticais lado a lado (empilhados no mobile). Cada card 9:16.
Preview visual real.
- **Story 1 · Teaser** — apenas o nome do produto e a data. Design misterioso.
- **Story 2 · O sabor + a história** — 2 linhas sobre umbu-cajá, com foto
  placeholder e menção à cooperativa
- **Story 3 · O CTA** — "Estará em todas as lojas em setembro" + sticker
  fictício de pergunta "qual sabor você quer testar?" + tag @mariapitanga

# ESTILO DE SAÍDA
- Página HTML self-contained (tudo inline)
- Formato A4 imprimível pra ficha, mas responsivo pros mockups de social
- Fundo geral **off-white creme #F0EEE6**, texto **#141413**
- Accent **roxo Maria Pitanga #6B2E7A**, complementar amarelo-umbu **#E5A932**
- Ficha ANVISA usa preto no branco (é documento oficial — não pode ter cor
  decorativa nem accent), com fontes serifadas ou sans-serif condensadas
- Mockups do Instagram usam paleta MP + amarelo-umbu
- Tipografia: Inter no corpo, JetBrains Mono nos campos técnicos, um serif
  no título do produto pra dar sensação de premium regional
- Sem dark mode, sem gradientes desnecessários (só se remeter à fruta)
- `@media print` embutido: ficha imprime A4 limpo, mockups social ocultam no print

# LINGUAGEM
Português-BR. Na ficha: técnica, precisa, sem enfeite (é documento oficial).
Na copy: quente, com alma de sertão sem caricatura. Zero "delícia irresistível",
zero "não perca essa oportunidade". Fale como se estivesse contando pra uma
amiga que valoriza produto de história.

# CONFIDENCIALIDADE
Custos e margem estão no briefing mas NÃO podem aparecer na ficha nem no
Instagram.

# ANTES DE GERAR
Confirme em 4 bullets:
(a) Sua leitura do produto em 1 frase (posicionamento)
(b) Se o produto vai ou não precisar da lupa "alto em açúcares" (com o cálculo)
(c) O ângulo da história que você vai destacar no Instagram
(d) Como você vai fazer o sotaque regional aparecer sem virar caricatura

Espere meu OK. **Só depois** gera o Artifact HTML completo.

---

## DADOS · Briefing do produto (fábrica → nutrição)

**Documento:** brainstorm interno · área de Desenvolvimento de Produto · 28/jul/2026
**Responsável:** Dra. Cristiane Aguiar · Nutricionista chefe · CRN-3 12.847
**Data-alvo entrega:** 05/agosto/2026 (para fábrica iniciar impressão do rótulo)

### 1. O que estamos criando
Um sorbet de fruta 100% natural com base em polpa de umbu com cajá —
combinação clássica do sertão nordestino, praticamente ausente do mercado
formal. Textura mais firme que o sorbet de manga que já temos, cor
amarelo-alaranjada intensa, sabor ácido-doce marcante. Público-alvo:
cliente adulto (25-45) que já compra nossos gelatos premium.

### 2. Ingredientes previstos (ordem decrescente estimada)
- Polpa de umbu integral (Cooperativa Sertão Vivo, Petrolina/PE) — ~42%
- Polpa de cajá integral (mesma cooperativa) — ~28%
- Açúcar cristal orgânico — ~18%
- Água filtrada — ~10%
- Estabilizante natural (goma xantana) — ~1,5%
- Suco de limão-taiti (equilíbrio do pH) — ~0,5%
- SEM leite. SEM ovo. SEM glúten. SEM lactose. Vegano-friendly.

### 3. Perfil sensorial
Aroma cítrico-tropical intenso. Sabor inicial doce (umbu maduro) seguido
de acidez marcante (cajá). Retrogosto que lembra bala de sertão. Textura
firme, cristalização controlada. Cor amarelo-alaranjada saturada, forte
apelo visual em vitrine.

### 4. Gap na linha atual
Nossa linha de sorbets tem 6 sabores (manga, morango, maracujá,
abacaxi-hortelã, coco, limão-siciliano). Todos com apelo tropical genérico.
Falta um sabor com história, regional, que o cliente do Nordeste identifique
como "meu sabor".

### 5. Público-alvo detalhado
- Primário: mulher 30-45, classe A/B, foodie, compra pra levar (linha 500ml)
- Secundário: homem 25-40, público "nostalgia sertão"
- Terciário: turista que quer sabor que não vê no estado dele

### 6. Custo, preço e margem (confidencial — não sai da conversa)
Custo unitário: R$ 4,80 (100g). Preço sugerido: R$ 16,90 (100g), R$ 24,90
(150g), R$ 42,00 (500g pra levar). Margem prevista: 68%.

### 7. Diferencial de marketing
Cooperativa Sertão Vivo em destaque no rótulo e nas peças. Cooperativa de
47 famílias em Petrolina há 12 anos. História de sustentabilidade real —
o umbu, se não colhido, apodrece na árvore.

### 8. Restrições regulatórias já conhecidas
- Precisa RDC 429/2020 (rotulagem nutricional frontal)
- Precisa declarar alergênicos (RDC 727/2022) — mesmo sem, é obrigatório
- Precisa tabela nutricional por porção (100g e 150g)
- Selo vegano: certificação separada, meta Q4/2026
- Validade estimada: 6 meses congelado (-18°C)

### 9. Estimativa nutricional (por 100g)
- Valor energético: ~148 kcal (620 kJ)
- Carboidratos: 34g (dos quais açúcares totais: 28g, açúcares adicionados: 18g)
- Proteínas: 0,8g
- Gorduras totais: 0,2g (saturadas: 0g · trans: 0g)
- Fibra alimentar: 1,4g
- Sódio: 8mg
- Vitamina C: 22mg (25% VD)

### 10. Pedido do marketing
- Ficha técnica ANVISA formatada pra imprimir no rótulo
- Copy pra Instagram: 1 legenda pro feed + sequência 3 stories
- Público: perfil regional-premium
- Tom: quente, com sotaque sem caricatura. Nada de emoji sertanejo genérico

### 11. Dados fictícios do fabricante (para o rótulo)
- Fabricante: Maria Pitanga Indústria e Comércio de Sorvetes Ltda.
- CNPJ: 12.345.678/0001-90
- Endereço: Rod. BR-020, km 42 · Distrito Industrial · Eusébio/CE · 61760-000
- SAC: 0800 300 1976 · sac@mariapitanga.com.br
