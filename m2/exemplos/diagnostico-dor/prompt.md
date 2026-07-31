# Prompt · Diagnóstico de dor + plano de 30 dias

> Copia daqui até o fim e cola no Claude, Kimi ou DeepSeek. A transcrição
> da reunião já vem inline no final — funciona sem upload. Se preferir,
> faça upload do `insumo-transcricao-conversa-time.docx`.

---

# PAPEL
Você é uma consultora sênior de gestão e produtividade em times de
tecnologia, com 15 anos formando líderes técnicos. Passou pela Endeavor,
G2 Capital e trabalhou como coach de CTOs de scale-ups. Sua marca é ouvir
uma reunião confusa de time e devolver um plano de 30 dias com prioridade,
prazo e responsável — sem enrolar. Você não é "consultora de metodologia
ágil" — você é a pessoa que o CTO chama quando precisa transformar
desabafo em plano.

# CONTEXTO
Sou o CTO da Maria Pitanga (Ricardo Mendes). Convoquei ontem uma reunião
aberta com meus 5 diretos — Fernanda (líder dev), Bruno (dev pleno), Amanda
(sistemas), Diego (suporte N2) — pra mapear as dores do time. Não teve
pauta. Foi mais desabafo estruturado. A transcrição completa (42 minutos)
vem inline no final deste prompt.

Preciso apresentar sexta-feira (05/ago) um plano de ação consolidado pra
minha diretora executiva. O plano precisa: (a) mostrar que eu ouvi o time
de verdade; (b) priorizar por impacto real, não pelo que mais reclamou;
(c) diferenciar quick wins de projetos maiores; (d) ter dono e prazo em
tudo. Se eu chegar com lista de 30 itens sem prioridade, ela vai perceber
que eu não fiz o trabalho.

# TAREFA
Gere um **Artifact HTML self-contained** (uma página web imprimível A4)
chamado **"Plano de Ação · Time de TI · 30 dias"** com **5 blocos**:

## BLOCO 1 · CAPA + LEITURA DO ENCONTRO
- Kicker: "Plano executivo · Ricardo Mendes · CTO Maria Pitanga"
- Título grande: uma frase que sintetiza o diagnóstico
  (ex: "Time competente sufocado por legado, sem processo e sem investimento")
- Sub: participantes, data da reunião, data do plano
- Um bloco de "3 achados macro" — 3 frases curtas em big number style:
  quantas dores foram levantadas, quantas urgentes (que precisam resolver
  em 48h), quantas estruturais (que precisam de investimento)

## BLOCO 2 · O QUE OUVI (mapa das dores)
Um card grande com **todas as dores catalogadas**, agrupadas por tipo:
- **Emergências** (dores que precisam resolver em 48h — usar dot vermelho)
- **Estruturais** (dores que precisam projeto — dot amarelo)
- **Culturais/Gestão** (dores que precisam decisão do CTO/direção — dot roxo)

Cada dor com: título curto, 1 linha de descrição, quem levantou (só o
nome do funcionário).

## BLOCO 3 · MATRIZ IMPACTO × ESFORÇO (2×2)
Uma matriz 2×2 real, visual, com os 4 quadrantes:
- **Quick wins** (alto impacto, baixo esforço) — fazer JÁ
- **Projetos estruturantes** (alto impacto, alto esforço) — planejar bem
- **Ganhos incrementais** (baixo impacto, baixo esforço) — fazer se sobrar tempo
- **Apostas** (baixo impacto, alto esforço) — só se for estratégico

Distribua as dores/ações identificadas nos 4 quadrantes como pequenos cards
posicionados dentro dos quadrantes. Use SVG inline ou grid CSS.

## BLOCO 4 · PLANO DE 30 DIAS (timeline visual)
Um gantt visual horizontal, 4 semanas (S1 a S4), com barras coloridas.
Cada barra é uma iniciativa, com:
- Nome da iniciativa
- Semana(s) que ocupa
- Responsável (Ricardo, Fernanda, Amanda, Bruno ou Diego)
- Cor semântica pela categoria (emergência = vermelho, estrutural = amarelo, cultural = roxo)

Priorize backup (essa é EMERGÊNCIA — dia 1), depois quick wins, depois
inícios de projetos. Não é razoável colocar refatoração de legado em 30 dias
inteiros — só planejamento e módulo-piloto.

## BLOCO 5 · 3 DECISÕES QUE O CTO PRECISA LEVAR PRA DIREÇÃO
Cards grandes, warm, um por decisão. Cada card com:
- Nome da decisão (verbo no infinitivo)
- Contexto em 2 linhas (por que essa decisão precisa acontecer)
- O que muda se a direção aprovar
- O que perdemos se a direção não aprovar

Foque em decisões que envolvem headcount, orçamento novo, ou mudança de
governança. Não misturar aqui coisa que o próprio CTO consegue resolver.

## FECHO · assinatura
"Ricardo Mendes · CTO · Maria Pitanga · 30/jul/2026" com um parágrafo curto
de warm-up sobre gratidão ao time pela franqueza.

# ESTILO DE SAÍDA
- Página HTML self-contained (tudo inline)
- Formato A4 imprimível, respiro editorial generoso
- Fundo **off-white creme #F0EEE6**, texto **#141413**
- Accent **roxo Maria Pitanga #6B2E7A**
- Semântica: vermelho `#B85C5C` (emergência), amarelo `#B8860B` (estrutural),
  roxo `#6B2E7A` (cultural/gestão)
- Tipografia: Inter no corpo, JetBrains Mono nos labels/kickers
- Matriz 2×2 e timeline em SVG inline ou CSS grid (sem lib externa)
- Cards com sombra suave, sem borda grossa colorida (usar fundo tingido e
  dot 6px via ::before no título)
- Sem dark mode, sem gradientes, sem emoji decorativo
- `@media print` embutido pra imprimir A4 limpo

# LINGUAGEM
Português-BR executivo. Frase direta. Zero "vale destacar", "é importante
notar", "cabe ressaltar". Você está escrevendo pro CTO apresentar pra
diretora executiva — que decide em 5 minutos se o plano é sério ou é
teatro.

# ANTES DE GERAR
Confirme em 4 bullets:
(a) Sua leitura macro do time em 1 frase
(b) A EMERGÊNCIA que precisa entrar como primeira barra do gantt
    (o backup — mas com sua justificativa)
(c) Os 2-3 quick wins mais óbvios que você viu na transcrição
(d) Uma das 3 decisões executivas que você já sabe que vai propor

Espere meu OK. **Só depois** gera o Artifact HTML completo.

---

## DADOS · Transcrição da reunião de dores do time de TI

**Data:** 24/jul/2026 · **Duração:** 42 min · **Local:** sala Sertão · Matriz MP
**Participantes:** Ricardo Mendes (CTO) · Fernanda Torres (líder dev) ·
Bruno Kaique (dev pleno) · Amanda Ribeiro (analista de sistemas) ·
Diego Sá (suporte N2)
**Transcrição:** automatizada via Otter.ai, revisão manual pelo Diego

### Contexto (adicionado pelo Diego após a reunião)
O CTO Ricardo Mendes convocou uma reunião aberta para mapear as dores do
time. O sistema legado de gestão de franquias (o "FranqueaPRO", desenvolvido
em 2016 em .NET Framework 4.5) tá gerando cada vez mais chamados, e a
franqueadora começou a pressionar por respostas mais rápidas. Não teve pauta
formal — foi mais um desabafo estruturado.

### Transcrição

[00:00] **Ricardo Mendes:** Bom pessoal, obrigado por vir. Vou ser direto: a franqueadora tá reclamando que a gente demora demais pra entregar coisa nova, e o meu chefe tá querendo saber por quê. Antes de eu inventar resposta, quero ouvir de vocês o que tá pegando. Fernanda, começa você.

[00:38] **Fernanda Torres:** Ricardo, honestamente? O legado tá me matando. A gente perde 60% do sprint arrumando bug no FranqueaPRO. É código de 2016, sem teste, sem doc, e cada vez que a gente encosta em uma tela ela quebra em outro lugar. Semana passada o Bruno mexeu na tela de comissão do franqueado e derrubou o relatório de vendas — que não tinha nada a ver.

[01:12] **Bruno Kaique:** Verdade. E o pior é que ninguém sabe o que aquele código faz. O cara que escreveu saiu em 2019. Tem função com 800 linhas que faz três coisas ao mesmo tempo. Eu passo mais tempo lendo do que escrevendo.

[01:42] **Ricardo Mendes:** Tá. Fernanda, você tinha me falado outro dia que a gente tá pensando em migrar. Fala mais.

[01:55] **Fernanda Torres:** É. Minha visão é: a gente precisa refatorar o FranqueaPRO por módulos. Começar pelo que mais dá dor de cabeça — que é o módulo de comissionamento — e ir substituindo por API em .NET 8 com testes. Não dá pra reescrever tudo de uma vez, é suicídio. Mas se a gente começar por 1 módulo, em 3 meses a gente prova que dá.

[02:33] **Amanda Ribeiro:** Ricardo, eu quero levantar outra coisa. Não é só o legado. A gente não tem ambiente de homologação. Todo deploy vai direto de dev pra produção. Se der ruim, a gente descobre porque o franqueado ligou reclamando. Isso é a coisa mais absurda que eu já vi em 8 anos de carreira, desculpa a franqueza.

[03:08] **Ricardo Mendes:** Não, tá certo. Isso é vergonhoso. Quanto custaria montar homolog?

[03:18] **Amanda Ribeiro:** Se for na AWS, uns R$ 800/mês de infra. Mas o custo maior é o setup — a gente teria que refazer o processo de deploy pra ter duas etapas. Uma semana de trabalho meu ou do Bruno, sem interrupção.

[03:44] **Diego Sá:** Enquanto vocês falam de tecnologia, deixa eu falar da dor real que chega no suporte. Todo santo dia às 8:15 da manhã, o painel do franqueado cai. É o job de sincronização com o cardápio que trava. A gente reinicia manualmente, o franqueado espera 20 minutos. Isso acontece HÁ DOIS ANOS. Já abri chamado 42 vezes. Ninguém arruma porque "não é prioridade".

[04:15] **Ricardo Mendes:** Espera, isso acontece todo dia? Por que eu não sei disso?

[04:22] **Diego Sá:** Porque cai só no franqueado, não cai no dashboard executivo. Se caísse em vocês, teria sido corrigido em 2 dias. É clássico.

[04:36] **Fernanda Torres:** Diego tá certo. Tem 30 bugs pequenos assim que a gente sabe da existência mas nunca prioriza. Cada um sozinho parece pouco. Somados, o franqueado acha que a gente é amador.

[04:58] **Ricardo Mendes:** OK, anotei. Amanda, você falou de homolog. Bruno, você falou de código velho. Diego, você falou de bug crônico. Fernanda, você falou de refatoração modular. O que mais? Tem alguma coisa que não é técnica que atrapalha vocês?

[05:32] **Bruno Kaique:** Ricardo, eu vou ser sincero. Eu não sei o que a franqueadora quer da gente. Toda semana chega demanda nova sem prioridade. "Faz isso pra ontem." Ontem chegou pedido pra fazer relatório novo pro comitê de expansão. Eu larguei um bug crítico no meio pra fazer o relatório. Isso é rotina.

[06:02] **Amanda Ribeiro:** Isso é gestão de demanda. Não tem backlog compartilhado. Cada área da franqueadora liga direto pra gente e pede. E cada uma acha que a sua é a mais urgente.

[06:24] **Ricardo Mendes:** Certo. Eu preciso montar um comitê de priorização com marketing, financeiro e operações. Isso é meu problema, não de vocês. Anotei.

[06:44] **Fernanda Torres:** E o time em si? A gente tá em 5 pessoas há 3 anos, com a rede crescendo 40% ao ano. Não dá conta. Cada nova área que a franqueadora abre — Portugal, Espanha — vira demanda extra pra gente sem headcount novo.

[07:18] **Bruno Kaique:** Verdade. E eu já tô procurando fora. Não é ameaça, é fato. Se eu não vejo crescimento em 6 meses, eu saio.

[07:30] **Ricardo Mendes:** Bruno, valorizo a franqueza. Isso vai virar prioridade minha na próxima quinzena. Vamos continuar mapeando, depois eu volto com plano.

[07:48] **Diego Sá:** Ah, mais uma coisa que ninguém falou. O sistema de ticket que a gente usa é o Zendesk, tá custando R$ 4.200/mês pra 3 usuários. Existe alternativa 10x mais barata. Ninguém revisou isso desde 2019.

[08:12] **Amanda Ribeiro:** E o backup do banco de dados. Rodrigo, o antigo, deixou script agendado na máquina dele. Máquina dele foi formatada mês passado. A gente tá sem backup automatizado há 6 semanas e ninguém notou. Descobri semana passada por acaso.

[08:38] **Ricardo Mendes:** Amanda, PARA TUDO. Sem backup HÁ 6 SEMANAS?

[08:44] **Amanda Ribeiro:** Sim.

[08:47] **Ricardo Mendes:** Isso é a primeira coisa a resolver. Amanda, hoje à tarde. Reserva a agenda inteira. Não me interessa mais nada. Se o banco cair essa semana a gente perde tudo desde junho.

[09:03] **Amanda Ribeiro:** Beleza. Bloqueio a tarde.

[09:12] **Fernanda Torres:** Ricardo, aproveitando: a documentação. A gente não tem doc de nada. Onboarding de dev novo leva 3 semanas de perde-tempo porque cada um tem que descobrir sozinho como o sistema funciona. Se um dia eu sair, o Bruno fica sozinho e a rede quebra em 15 dias.

[09:42] **Bruno Kaique:** Confirmo.

[09:52] **Ricardo Mendes:** Fernanda, quanto tempo pra documentar o essencial? Não a Bíblia — só o mapa do sistema, os fluxos críticos, quem chama o quê.

[10:12] **Fernanda Torres:** Se eu me dedicar meio-período por 3 semanas, dá pra documentar 80%. Se for o Bruno e eu revisando, 4 semanas.

[10:28] **Ricardo Mendes:** Vamos fazer. É investimento que se paga em 2 meses de tempo economizado no próximo dev.

[10:44] **Diego Sá:** Ricardo, só pra fechar: e capacitação? A gente não fez curso há 2 anos. O Bruno tá pagando um curso de Kubernetes do bolso dele.

[11:02] **Bruno Kaique:** Verdade.

[11:08] **Ricardo Mendes:** Isso eu resolvo agora. Vou aprovar R$ 3 mil por pessoa por ano de capacitação. Retroativo. Bruno, me manda o comprovante do teu curso.

[11:24] **Fernanda Torres:** Ricardo, uma última: a gente precisa parar de tratar TI como custo. Toda vez que a gente pede investimento, o financeiro corta. Aí vira apagar incêndio. Se a franqueadora entender que TI é o que segura a expansão da rede, tudo muda.

[11:52] **Ricardo Mendes:** Fernanda, é meu trabalho fazer essa venda pra cima. E eu tô falhando nisso. Anotei. Vou levar dado real pra próxima reunião do comitê executivo. Não vai mais ser opinião.

[12:14] **Ricardo Mendes:** Pessoal, resumindo o que eu ouvi: (1) legado quebrando, precisa refatoração modular; (2) sem ambiente de homolog; (3) bugs crônicos ignorados; (4) sem backup automático — vamos resolver hoje; (5) sem doc; (6) sem processo de priorização; (7) time subdimensionado; (8) sem capacitação; (9) TI vista como custo. É isso?

[12:52] **Fernanda Torres:** É isso. E uma décima: a gente precisa de mais autonomia técnica. Toda decisão de arquitetura passa por 4 pessoas.

[13:08] **Ricardo Mendes:** Anotei décima. Vamos parar por aqui. Eu vou consolidar isso num plano de 30 dias. Vocês recebem sexta.

[13:22] **[fim]** reunião encerrada · próxima em 05/ago com plano consolidado do Ricardo

### Nota do transcritor
Transcrição gerada automaticamente. Diego revisou manualmente as falas dos
5 primeiros minutos e amostragem do restante. Erros de reconhecimento de
voz podem existir. Rodrigo (antigo) e "comitê expansão" são referências
históricas, não estavam na reunião.
