---
title:  "Criptoanarquia e Comunidades Virtuais"
date:   01-12-1994 -0300
categories:
  - Biblioteca
tags: 
  - Timothy C. May
---


### Timothy C. May


#### Dezembro de 1994


## Resumo Estendido

A combinação de criptografia de chave pública forte e inquebrável e comunidades de redes virtuais no ciberespaço produzirá mudanças interessantes e profundas na natureza dos sistemas econômicos e sociais. A criptoanarquia é a realização ciberespacial do anarco-capitalismo, transcendendo as fronteiras nacionais e libertando os indivíduos para fazer os arranjos econômicos que eles desejam fazer consensualmente.

Criptografia robusta, exemplificada pelo RSA (um algoritmo de chave pública) e pelo PGP (Pretty Good Privacy), fornece criptografia que essencialmente não pode ser quebrada com todo o poder computacional do universo. Isso garante segurança e privacidade. Criptografia de chave pública é justamente considerada uma revolução.

Misturas digitais (Mixers), ou remailers anônimos, usam criptografia para criar emails não rastreáveis, que tem muitos usos (Numerosos remailers anônimos, em vários países, estão operando agora. O tráfego de mensagens está crescendo exponencialmente).

Os pseudônimos digitais, a criação de personas de rede persistentes que não podem ser forjadas por outros e que não são vinculáveis ​​aos "nomes verdadeiros" de seus proprietários, estão encontrando grandes usos para garantir a liberdade de expressão, ao permitir que opiniões controversas sejam veiculadas para transações econômicas que não podem ser bloqueadas pelos governos locais. A tecnologia que está sendo implantada pelos Cypherpunks e outros, significa que suas identidades, nacionalidades e até mesmo em que continentes não são rastreáveis ​​- a menos que escolham revelar essas informações. Isso altera a "topologia de relacionamento" convencional do mundo, permitindo diversas interações sem regulamentação governamental, tributação ou interferência externa.

O dinheiro digital, não rastreável e anônimo (como dinheiro real), também está chegando, embora vários obstáculos técnicos e práticos permaneçam. "Bancos suíços no ciberespaço" tornarão as transações econômicas muito mais líquidas e muito menos sujeitas às regras e regulamentações locais. A evasão fiscal é provavelmente uma grande atração para muitos. Um exemplo de interesse local para Monte Carlo pode ser o trabalho em andamento para desenvolver sistemas anônimos e não rastreáveis ​​para "casinos do ciberespaço". Embora não seja tão atraente para muitos como cassinos elegantes, a popularidade de "jogos de números" e bookies em geral sugere uma oportunidade para prosseguir.

Os paraísos de dados e os mercados da informação já estão surgindo, usando os métodos descritos para tornar a informação recuperável anonimamente e sem rastreabilidade.

Os governos vêem seus poderes desgastados por essas tecnologias e estão tomando várias medidas bem conhecidas para tentar limitar o uso de criptografia forte por seus súditos. Os EUA têm vários esforços bem divulgados, incluindo o chip Clipper, a lei de grampos de telefonia digital e propostas de depósito "voluntário" de chaves criptográficas. Cypherpunks e outros esperam que esses esforços sejam contornados. A tecnologia deixou o gênio sair da garrafa. A criptoanarquia está liberando os indivíduos da coerção por seus vizinhos físicos - que não podem saber quem são na rede - e dos governos. Para os libertários, a criptografia forte fornece os meios pelos quais o governo será evitado.

A apresentação descreverá como vários desses sistemas funcionam, resumidamente, e delinearão as implicações prováveis ​​dessa combinação de criptoanarquia e comunidades virtuais do ciberespaço.

## 1\. Introdução

Este artigo descreve a combinação de duas tecnologias principais:

*   Critpgrafia Forte: incluindo criptografia, assinaturas digitais, dinheiro digital, mixagens digitais (remailers) e tecnologias relacionadas.
*   Comunidades virtuais ciberespaciais: incluindo redes, comunicações anônimas, MUDs e MOOs e realidades virtuais do tipo "Multiverse".

Este artigo descreve a combinação de duas tecnologias principais:

Essas áreas geralmente permaneceram separadas, pelo menos em artigos publicados. Certamente, os desenvolvedores de sistemas do ciberespaço, como MUDs, MOOs e sistemas semelhantes ao Habitat, apreciam a importância da criptografia para autenticação de usuários, segurança geral e, certamente, para (eventual) compra digital de serviços. Mas, na maior parte, a combinação dessas duas áreas tem sido a competência do escritor de ficção científica, notadamente escritores como Vernor Vinge, William Gibson, Bruce Sterling e Orson Scott Card.

O grupo "Cypherpunks", uma lista de discussão anárquica e um grupo de hackers, foi formado por vários de nós em 1992 como um grupo para tornar concretas algumas das idéias abstratas frequentemente apresentadas em conferências. Nós tivemos alguns sucessos e alguns fracassos. <sup>[[1]](https://cypherpunks.com.br/criptoanarquia-e-comunidades-virtuais/#fn1)</sup> O grupo Cypherpunks também apareceu em um momento fortuito, como o PGP estava se tornando popular, como apareceu a revista Wired (eles apareceram na capa da segunda edição), e como a publicidade (hype?) Sobre a Information Superhighway e a A World Wide Web alcançou um _crescendo_.

O site ftp.csua.berkeley.edu tem vários ensaios e arquivos, incluindo arquivos criptográficos, no diretório pub/cypherpunks. Eu também escrevi/compilei um FAQ de 1.3 MB muito grande sobre estas questões, o Cyphernomicon, disponível em vários sites, incluindo meu diretório ftp, ftp.netcom.com, no diretório pub/ tc/tcmay.

O grupo Cypherpunks também é um ótimo exemplo de uma "comunidade virtual". Espalhados pelo mundo, comunicando-se eletronicamente em questão de minutos e aparentemente alheios às leis locais, os Cypherpunks são de fato uma comunidade e são virtuais. Muitos membros usam pseudônimos e usam remailers anônimos para se comunicar com a lista. A própria lista comporta-se assim como um "pool de mensagens", um lugar onde informações de todo tipo podem ser anonimamente depositadas - e a anonimamente recebidas (já que todos veem a lista inteira, como um jornal, o destinatário pretendido é anonimizado).

Aviso legal: Consulte as leis locais antes de aplicar qualquer um dos métodos descritos aqui. Em algumas jurisdições, pode ser ilegal ler artigos como esse (é sério). Em particular, eu geralmente não vou dar endereços de sites ftp para cópias de PGP, acesso a remailer, sistemas de dinheiro digital, etc. Estes são bem cobertos em fóruns mais atuais, por exemplo, sci.crypt ou talk.politics.crypto, e há algumas questões não resolvidas sobre se dar o endereço de tais sites constitui (ou "ajudas e abets") violação de várias leis de exportação e munições (criptografia é considerada uma munição nos EUA e provavelmente em outro lugar....algumas nações consideram uma impressora a laser para ser um item de munições!).

## 2\. Criptografia Moderna

As últimas duas décadas produziram uma revolução na criptografia (cripto, resumindo) a ciência da criação de códigos e cifras. Além de simples cifras, úteis principalmente para manter as comunicações secretas, a criptografia moderna inclui diversas ferramentas para autenticação de mensagens, para registro digital de documentos, para esconder mensagens em outros documentos (esteganografia) e até mesmo para esquemas de dinheiro digital.

Criptografia de chave pública, a criação de Diffie e Hellman, alterou dramaticamente o papel da criptografia. Chegando ao mesmo tempo que a conversão de atacado para redes de computadores e comunicações em todo o mundo. Tem sido um elemento-chave de segurança, confiança e sucesso. O papel da criptografia só se tornará mais importante nas próximas décadas.

Pretty Good Privacy, PGP, é uma versão popular do algoritmo desenvolvido por Rivest, Shamir e Adleman, conhecido como RSA. O algoritmo RSA recebeu uma patente nos EUA, embora não em nenhum país europeu, e é licenciado comercialmente. <sup>[[2]](https://cypherpunks.com.br/criptoanarquia-e-comunidades-virtuais/#fn2)</sup>

Essas ferramentas são descritas em detalhes em vários textos e anais de conferências, e não são o assunto deste artigo. <sup>[[3]](https://cypherpunks.com.br/criptoanarquia-e-comunidades-virtuais/#fn3)</sup> O foco aqui é sobre as implicações da forte criptografia para o ciberespaço, especialmente em comunidades virtuais.

Deve-se mencionar o papel de David Chaum na definição dos principais conceitos aqui. Em vários artigos seminais (por exemplo, <sup>[[4]](https://cypherpunks.com.br/criptoanarquia-e-comunidades-virtuais/#fn4)</sup> <sup>[[5]](https://cypherpunks.com.br/criptoanarquia-e-comunidades-virtuais/#fn5)</sup> ), Chaum introduziu as idéias de usar métodos de criptografia de chave pública para e-mail anônimo, não rastreável, para sistemas de dinheiro digital nos quais a identidade do remetente não é revelada e em esquemas relacionados a estes. (Eu não faço reivindicações, é claro, que Chaum concorda com minhas conclusões sobre as implicações políticas e socioeconômicas desses resultados).

## 3\. Comunidades Virtuais

Notas: ciberespaço, Habitat, VR, Vinge, etc. Cripto sustenta as "paredes" dessas realidades ciberespaciais.Controle de acesso, direitos de acesso, privilégios de modificação.

Comunidades virtuais são as redes de indivíduos ou grupos que não estão necessariamente intimamente conectados geograficamente. O "virtual" tem a intenção de implicar uma ligação não física, mas não deve ser entendido como significando que são menos semelhantes às comunidades do que as comunidades físicas convencionais.

Exemplos incluem igrejas, organizações de serviço, clubes, gangues criminosas, cartéis, grupos de fãs, etc. A Igreja Católica e os Escoteiros são exemplos de comunidades virtuais que atravessam o globo, transcendem as fronteiras nacionais e criam um senso de lealdade, de pertença. e um senso de "comunidade". Da mesma forma, a Máfia é uma comunidade virtual (com seus mecanismos de imposição, suas próprias regras extra-legais, etc.). Muitos outros exemplos: Maçons, Tríades, Cruz Vermelha, Interpol, Islamismo, Judaísmo, Mórmons, Sindero Luminoso, o IRA, cartéis de drogas, grupos terroristas, Nação Ariana, Greenpeace, a Frente de Libertação Animal, e assim por diante. Existem, sem dúvida, muito mais comunidades virtuais do que estados-nação, e os laços que os ligam são, na maior parte, muito mais fortes do que as emoções do nacionalismo chauvinista. Qualquer grupo em que os interesses comuns do grupo, seja uma ideologia compartilhada ou um interesse particular, são suficientes para criar uma comunidade coesa.

As corporações são outro excelente exemplo de uma comunidade virtual, com sites espalhados, canais de comunicação privados (geralmente inacessíveis ao mundo exterior, incluindo as autoridades) e seus próprios objetivos e métodos. De fato, muitos autores de ficção "cyberpunk" (não cypherpunk) erram, penso eu, ao supor que o mundo futuro será dominado por "estados" megacorporativos transnacionais. Na verdade, as corporações são apenas um exemplo - de muitas - dessas comunidades virtuais que estarão efetivamente em igualdade com os estados-nação. (Note especialmente que quaisquer leis destinadas a limitar o uso da criptografia causam problemas imediatos e profundos para corporações - países como a França e as Filipinas, que tentaram limitar o uso da criptografia, foram em grande parte ignoradas pelas corporações. Qualquer tentativa de proibir criptografia produzirá uma onda de "incorporações" repentinas, conquistando assim para os novos membros corporativos a égide da privacidade corporativa.

Em um ambiente acadêmico, "faculdades invisíveis" são as comunidades de pesquisadores.

Essas comunidades virtuais normalmente são "opacas" para pessoas de fora. As tentativas de obter acesso aos internos dessas comunidades raramente são bem-sucedidas. As agências policiais e de inteligência (como a NSA nos EUA, a Chobetsu no Japão, a SDECE na França e assim por diante, em todos os países) podem se infiltrar nesses grupos e usar a vigilância eletrônica (ELINT) para monitorar essas comunidades virtuais. Não é de surpreender que essas comunidades sejam pioneiras na adoção de tecnologia de criptografia, que vão desde celulares embaralhados até criptografia PGP completa. <sup>[[6]](https://cypherpunks.com.br/criptoanarquia-e-comunidades-virtuais/#fn6)</sup>

O uso de criptografia por grupos "malignos", como pornógrafos infantis, terroristas, abortadores, manifestantes do aborto, etc., é citado por aqueles que desejam limitar o acesso civil a ferramentas de criptografia. Nós os chamamos de "Quatro Cavaleiros do Infocalypse", como eles são tão frequentemente citados como a razão pela qual as unidades cidadãs comuns do Estado-nação não têm acesso à criptografia.

Este é claramente um argumento perigoso a se fazer, por várias boas razões. O direito básico da liberdade de expressão é o direito de falar em um idioma que os vizinhos ou os líderes do governo podem não achar compreensível: discurso criptografado. Não há espaço suficiente aqui para entrar em muitos bons argumentos contra um limite no acesso à privacidade, ferramentas de comunicação e criptografia.

O advento de sistemas de comunicação com recursos completos para comunidades virtuais mediadas por computador terá implicações ainda mais profundas. MUDs e MOOs (domínios multiusuários, etc.) e realidades virtuais em 3D são uma avenida, e as comunicações líquidas centradas em texto são outras. (Algum dia, em breve, eles se fundirão, conforme descrito no romance profético de Vernor Vinge de 1980, True Names.)

## <span style="background-color: #c5c5c5; color: #373737">4\. Observabilidade e Vigilância</span>

Uma maneira interessante de visualizar problemas de visibilidade da rede é em termos da "transparência" de nós e links entre nós. Transparente significa visível para pessoas de fora, talvez aquelas na aplicação da lei ou na comunidade de inteligência. Meio opaco significa não transparente, não visível. Um cartão postal é transparente, uma carta lacrada é opaca. O inventor do PGP, Phil Zimmermann, comparou a exigência de transparência à ordem de usar cartões postais para toda a correspondência, com criptografia equivalente a um envelope opaco (envelopes podem ser abertos, é claro e por muito tempo).

Links e nós transparentes são a norma em um estado policial, como a URSS, o Iraque, a China e assim por diante. Os canais de comunicação são utilizados e o uso privado de computadores é restrito. (Isso está se tornando cada vez mais difícil de fazer, mesmo para os estados policiais; muitos citam a disseminação de opções de comunicação como uma causa próxima do colapso do comunismo nos últimos anos.)

Existem "químicas" ou "álgebras" interessantes de links e nós transparentes versus opacos. O que acontece se os links devem ser transparentes, mas os nós podem ser opacos? (A resposta: o resultado é como se links e nós opacos fossem permitidos, i.e., implicações completas de criptografia forte. Portanto, qualquer tentativa de banir a criptografia de comunicações enquanto ainda permite que CPUs privadas existam...)

Se Alice e Bob estiverem livres para se comunicar e escolher caminhos de roteamento, Alice poderá usar a "arbitragem criptográfica" (uma variação do termo "arbitragem regulatória", o termo usado por Eric Hughes para capturar essa idéia de transferir transações para outras jurisdições) para se comunicar com sites - talvez em outros países - que terão o desempenho desejado. Isso pode significar reencaminhamento, mixagem, etc. Como exemplo, cidadãos canadenses são informados de que não podem acessar informações sobre o caso Homolka-Teale (um caso controverso em que o juiz ordenou a mídia no Canadá e entrou no Canadá, não para discutir os detalhes podres), no entanto, tem uma vasta gama de opções, incluindo o uso de telnet, gopher, ftp, web, etc., para acessar sites em muitos outros países - ou mesmo em nenhum país em particular.

A maioria das conseqüências descritas aqui provêm dessa química de links e nós: a menos que quase todos os nós e links sejam forçados a serem transparentes, incluindo links para outras nações e os nós nessas nações, o resultado é que a comunicação privada ainda pode ocorrer. Resultado da criptoanarquia.

## 5\. Criptoanarquia

"A rede é uma anarquia." Esse truísmo é o núcleo da criptoanarquia. Nenhum controle central, nenhum governante, nenhum líder (exceto pelo exemplo, reputação), nenhuma "lei". Nenhuma nação única controla a rede, nenhum órgão administrativo estabelece políticas. O <span id="CONTENT">Ayatollah</span> no Irã é impotente para impedir que um grupo de notícias - alt.wanted.moslem.women ou alt.wanted.moslem.gay venha à mente - ele não gosta, já que o presidente da França está tão impotente para parar, digamos, abuso de francês em soc.culture.french. Da mesma forma, a CIA não pode parar grupos de notícias, sites ou páginas da Web, que revelam seus segredos. Pelo menos não em termos da própria rede... que passos "não-net" podem ser tomados é deixado como um exercício para os paranóicos e os cautelosos.

Essa anarquia essencial é muito mais comum do que muitos pensam. Anarquia - a ausência de um governante dizendo a alguém o que fazer - é comum em muitos setores da vida: escolha de livros para ler, filmes para ver, amigos para socializar, etc. Anarquia não significa liberdade total - afinal, pode-se apenas leia os livros que alguém escreveu e publicou - mas significa liberdade da coerção externa. A anarquia como conceito, no entanto, foi contaminada por outras associações.

Primeiro, a "anarquia" aqui não é a anarquia da concepção popular: ilegalidade, desordem, caos e "anarquia". Tampouco é a anarquia de arremesso de bombas dos anarquistas "negros" do século XIX, geralmente associada à Rússia e aos movimentos trabalhistas. Nem é a anarquia da "bandeira negra" do anarco-sindicalismo e escritores como Proudhon. Em vez disso, a anarquia que se fala aqui é a anarquia da "ausência de governo" (literalmente, "um arco", sem chefe ou chefe).

Este é o mesmo sentido de anarquia usado no "anarco-capitalismo", a ideologia do livre mercado libertário que promove transações econômicas voluntárias e não coagidas. <sup>[[7]](https://cypherpunks.com.br/criptoanarquia-e-comunidades-virtuais/#fn7)</sup> Eu inventei o termo cryptoanarchy (criptoanarquia) como um trocadilho com criptografia, que significa "escondido", sobre o uso de "criptografia" em combinação com visões políticas (como na famosa acusação de Gore Vidal a William F. Buckley: "Você é fascista!") e, claro, porque a tecnologia de criptografia torna possível essa forma de anarquia. A primeira apresentação disso foi em um "Manifesto" de 1988, modelado por caprichos de outro famoso manifesto. <sup>[[8]](https://cypherpunks.com.br/criptoanarquia-e-comunidades-virtuais/#fn8)</sup> Talvez um termo mais popularmente compreensível, como "liberdade cibernética", possa ter algumas vantagens, mas a criptoanarquia tem seu próprio charme, eu acho.

E a anarquia, neste sentido, não significa que as hierarquias locais não existam, nem significa que não existam governantes. Grupos fora do controle direto das autoridades governamentais locais ainda podem ter líderes, governantes, presidentes de clube, corpos eleitos, etc. Muitos não o farão.

Politicamente, as comunidades virtuais fora do escopo do controle governamental local podem apresentar problemas de aplicação da lei e cobrança de impostos. (Alguns de nós gostamos desse aspecto.) Evitar transações coercivas pode significar evitar impostos, evitar leis que dizem quem pode vender e quem não pode, e assim por diante. É provável que muitos estejam insatisfeitos com o fato de alguns usarem criptografia para evitar leis destinadas a controlar o comportamento.

As fronteiras nacionais estão se tornando mais transparentes do que nunca para os dados. Uma enxurrada de bits cruza as fronteiras da maioria dos países desenvolvidos - linhas telefônicas, cabos, fibras, links para cima/para baixo de satélites e milhões de disquetes, fitas, CDs, etc. Parar os dados nas bordas é menos do que impossível.

Finalmente, a capacidade de mover dados em todo o mundo à vontade, a capacidade de se comunicar com locais remotos à vontade, significa que uma espécie de "arbitragem regulatória" pode ser usada para evitar obstáculos legais. Por exemplo, reencaminhamento para os EUA a partir de um site nos Países Baixos... quais leis se aplicam? (Se alguém acha que as leis dos EUA devem se aplicar a sites na Holanda, a lei iraquiana se aplica nos EUA? E assim por diante.)

Essa arbitragem regulatória também é útil para evitar a confusão de leis e regulamentações que as operações em um país podem enfrentar, incluindo as ações "profundas" que tantos nos EUA enfrentam. A movimentação de operações na rede fora de uma jurisdição litigiosa é um passo para reduzir esse passivo comercial. Como os bancos suíços, mas diferentes.

## 6\. Nomes Verdadeiros e Sistemas Anônimos

Algo precisa ser dito sobre o papel do anonimato e dos pseudônimos digitais. Este é um tópico para um ensaio em si, é claro.

Os nomes verdadeiros são realmente necessários? Por que eles são solicitados? O Estado-nação tem algum motivo válido para exigir que eles sejam usados?

As pessoas querem saber com quem estão lidando, por razões psicológicas / evolutivas e para garantir melhor a rastreabilidade caso precisem localizar uma pessoa para impor os termos de uma transação. A pessoa puramente anônima talvez seja justificadamente vista com suspeita.

E, no entanto, os pseudônimos são bem-sucedidos em muitos casos. E raramente sabemos se alguém que se apresenta por algum nome é "realmente" essa pessoa. Autores, artistas, famosos, etc., geralmente usam pseudônimos. O que importa é persistência e não aplicabilidade. A criptografia fornece isso.

Na lista de Cypherpunks, pseudônimos digitais bem respeitados apareceram e não são considerados menos do que seus colegas "reais".

Toda a área de reputações autenticadas digitalmente e o "capital de reputação" que se acumula ou é afetado pelas opiniões dos outros, é uma área que combina economia, teoria dos jogos, psicologia e expectativas. Muito mais estudo é necessário.

Não está claro se os governos passarão para um sistema de exigência de "Licenças de Dirigir para Rodovia da Informação", figurativamente falando, ou como sistemas como esse poderiam ser aplicados. (A química dos nós opacos e links, novamente.)

## 7\. Exemplos e Usos

Surpreende muitas pessoas que alguns desses usos já estejam sendo intensamente explorados. Os repostadores anônimos são usados ​​por dezenas de milhares de pessoas - e talvez sejam abusados. <sup>[[9]](https://cypherpunks.com.br/criptoanarquia-e-comunidades-virtuais/#fn9)</sup> E, é claro, a criptografia, via RSA, PGP, etc., é muito comum em algumas comunidades. (Hackers, usuários da Net, combatentes da liberdade, separatistas brancos, etc ... Eu não faço julgamentos morais aqui sobre aqueles que usam esses métodos).

Remailers são um bom exemplo para se ver com mais detalhes. Existem dois tipos principais de remailers:

1.  Reempacotamentos estilo "Cypherpunk", que processam mensagens de texto para redirecionar e-mails para outros sites, usando uma sintaxe de comando que permite o aninhamento arbitrário de reencaminhamento (como muitos sites), com criptografia PGP em cada nível de aninhamento.
2.  Remailer (s) ao estilo "Julf", baseado no trabalho original de Karl Kleinpaste e operado/mantido por Julf Helsingius, na Finlândia. Nenhuma criptografia e apenas um desses sites no momento. (Este sistema tem sido amplamente utilizado para mensagens postadas na Usenet e é basicamente bem-sucedido. O modelo é baseado na confiabilidade do operador e sua localização na Finlândia, além do alcance de ordens judiciais e intimações da maioria dos países.)

Os remailers do Cypherpunks são atualmente cerca de 20, com mais sendo adicionados a cada mês. Não há razão para não esperar centenas desses reencaminhadores em poucos anos.

Um "mercado de informações" experimental é o BlackNet, um sistema que surgiu em 1993 e que permite trocas de informações de todos os tipos, totalmente anônimas e bidirecionais. Há relatos de que as autoridades americanas investigaram isso por causa de sua presença em redes nos laboratórios de pesquisa do Departamento de Defesa. Não há muito o que fazer sobre isso, é claro, e mais entidades desse tipo são esperadas.

(As implicações para a espionagem são profundas e quase incontroláveis. Qualquer pessoa com um computador doméstico e acesso à Internet ou à Web, de várias formas, pode usar esses métodos para se comunicar com segurança, anonimamente ou pseudonimamente e com pouco receio de detecção. "Digital dead drops" podem ser usadas para postar informações obtidas, muito mais seguramente do que as velhas "dead drops"... não há mais mensagens em latas de Coca-Cola nas bases de árvores em estradas remotas.)

O whistleblowing é outro uso crescente de remailers anônimos, com pessoas temendo retaliação usando remailers para postar informações publicamente. (Claro, há uma linha tênue entre denúncia, vingança e espionagem).

Paraísos de dados, para o armazenamento e comercialização de informações controversas, é outra área de provável crescimento futuro. Praticamente qualquer tipo de informação, médica, religiosa, química, etc., é ilegal ou proscrita em um ou mais países, então aqueles que buscam essas informações ilegais recorrem a sistemas anônimos de mensagens para acessar - e talvez comprar, com dinheiro digital anônimo - este em formação. Isso pode incluir bancos de dados de crédito, arquivos de locatários, mercados de bancos de órgãos, etc. (são todas as coisas que têm várias restrições sobre eles nos EUA, por exemplo ... não se pode compilar bancos de dados de crédito ou listas de locatários , sem encontrar várias restrições, um bom motivo para movê-las para o ciberespaço, ou pelo menos fora dos EUA, e depois vender o acesso por meio de remailers.)

A correspondência de compradores e vendedores de órgãos é outro desses mercados. Uma enorme demanda (vida e morte), mas várias leis que controlam rigidamente esses mercados.

Esforços de caixa digital. Muito tem sido escrito sobre dinheiro digital. <sup>[[10]](https://cypherpunks.com.br/criptoanarquia-e-comunidades-virtuais/#fn10)</sup> <sup>[[11]](https://cypherpunks.com.br/criptoanarquia-e-comunidades-virtuais/#fn11)</sup> A empresa de David Chaum, DigiCash, possui a tecnologia mais interessante e recentemente iniciou testes de mercado. A Stefan Brands pode ou não ter um sistema concorrente que contorna algumas das patentes da Chaum. (A atitude dos criptoanarquistas pode tomar sobre patentes é outro tópico para discussão. Basta dizer que as patentes e outras questões de propriedade intelectual continuam a ter relevância no mundo prático, apesar da erosão pelas tendências tecnológicas.)

Sistemas baseados em cartões de crédito, como o sistema First Virtual, não são exatamente dinheiro digital, no sentido chaumiano de notas cegas, mas oferecem algumas vantagens que o mercado pode achar útil até que sistemas mais avançados estejam disponíveis.

Espero ver muitos mais experimentos desse tipo nos próximos anos, e alguns deles provavelmente serão sucessos de mercado.

## 8\. Comércio e Colonização do Ciberespaço

Como essas idéias afetarão o desenvolvimento do ciberespaço?

"Você não pode comer ciberespaço" é uma crítica muitas vezes nivelada à discussão sobre o papel do ciberespaço na vida cotidiana. O argumento feito é que o dinheiro e os recursos "acumulados" em algum futuro sistema ciberespacial (ou futuro próximo) não poderão ser "lavados" no mundo real. Mesmo um tal pensador presciente como Neal Stephenson, em _Snow Crash_ , teve seu protagonista, um homem muito rico em "O Multiverso", mas quase indigente no mundo físico.

Isso é implausível por vários motivos. Primeiro, vemos rotineiramente transferências de riqueza do mundo abstrato de dicas de ações, conhecimento de consultoria arcana, etc., para o mundo real. "Consultoria" é a palavra operativa. Segundo, uma variedade de meios de lavagem de dinheiro, através de faturas falsas, empréstimos não cobrados, objetos de arte, etc., são bem conhecidos daqueles que lavam dinheiro... esses métodos, e os mais avançados que estão por vir, provavelmente serão usados por aqueles que desejam que seus lucros no ciberespaço sejam transferidos para o mundo real.

(Fazer isso anonimamente, sem rastreio, é outra complicação. Pode haver métodos para fazer isso - as propostas parecem bastante sólidas, mas é necessário mais trabalho.)

A World Wide Web está crescendo em um ritmo explosivo. Combinado com a comunicação criptograficamente protegida e o dinheiro digital de alguma forma (e há vários que estão sendo experimentados), isso deve produzir a muito esperada colonização do ciberespaço.

A maioria dos internautas e usuários da Web já presta pouca atenção às leis putativas de suas regiões ou nações locais, aparentemente se vendo mais como membros de várias comunidades virtuais do que como membros de entidades governadas localmente. Esta tendência está se acelerando.

Mais importante, as informações podem ser compradas e vendidas (anonimamente também) e usadas no mundo real. Não há razão para esperar que essa não seja a principal razão para entrar no ciberespaço.

## 9\. Implicações

Eu falei sobre as implicações em vários lugares. Muitas pessoas atenciosas estão preocupadas com algumas das possibilidades evidenciadas por fortes sistemas de comunicação cripto-anônimos. Alguns estão propondo restrições ao acesso a ferramentas de criptografia. O recente debate nos Estados Unidos sobre "Clipper" e outros sistemas de depósito de chaves mostra a força das emoções nesta questão.

Mercados abomináveis ​​podem surgir. Por exemplo, sistemas anônimos e dinheiro digital não rastreável têm algumas implicações óbvias para a organização de assassinatos por contrato e outros. (O maior risco na organização de tais acessos é que as reuniões físicas expõem os compradores e vendedores de tais serviços a picadas. A criptoanarquia diminui ou até mesmo elimina esse risco, diminuindo assim os custos de transação. Os riscos para os verdadeiros gatilhos não são diminuídos, mas este é um risco que os compradores não precisam se preocupar. Pense em serviços de depósito anônimos que detêm o dinheiro digital até que a ação seja feita. Muitas questões aqui. É lamentável que essa área seja tão pouco discutida... as pessoas parecem tem aversão por explorar as consequências lógicas em tais áreas.)

As implicações para a espionagem corporativa e nacional já foram abordadas. Combinado com mercados líquidos de informação, isso pode tornar os segredos muito mais difíceis de manter. (Imagine um "Digital Jane's", depois dos manuais de armas militares, compilados anonimamente e vendidos por dinheiro digital, além do alcance de vários governos que não querem que seus segredos sejam contados.)

Novas abordagens de lavagem de dinheiro são, obviamente, outra área a ser explorada.

Algo que é inevitável é o aumento do papel dos indivíduos, levando a um novo tipo de elitismo. Aqueles que estão confortáveis ​​com as ferramentas descritas aqui podem evitar as restrições e impostos que outros não podem. Se as leis locais podem ser contornadas tecnologicamente, as implicações são bastante claras.

As implicações para a liberdade pessoal são, naturalmente, profundas. Os Estados-nação não podem mais dizer a suas unidades de cidadãos aquilo a que podem ter acesso, não se esses cidadãos puderem acessar o mundo do ciberespaço por meio de sistemas anônimos.

## 10\. quão provável?

Não estou fazendo previsões ousadas de que essas mudanças varrerão o mundo tão cedo. A maioria das pessoas ignora esses métodos e os métodos em si ainda estão em desenvolvimento. Uma conversão por atacado para "viver no ciberespaço" simplesmente não está nos cartões, pelo menos não nas próximas décadas.

Mas para um grupo cada vez maior, a Net é a realidade. É onde os amigos são feitos, onde os negócios são negociados, onde a estimulação intelectual é encontrada. E muitas dessas pessoas estão usando ferramentas de criptoanarquia. Remailers anônimos, pools de mensagens, mercados de informações. A consulta via pseudônimos começou a aparecer e deve crescer. (Como de costume, a falta de um robusto sistema de caixa digital está atrasando as coisas.

A criptoanarquia pode ser parada? Embora a evolução futura não seja clara, como o futuro quase sempre é, parece improvável que as tendências atuais possam ser revertidas:

*   Aumentos dramáticos na largura de banda e no poder de computação local.
*   Aumento exponencial do número de usuários da rede.
*   Explosão em "graus de liberdade" em escolhas pessoais, gostos, desejos, objetivos.
*   Incapacidade dos governos centrais de controlar economias, tendências culturais, etc. <sup>[[12]](https://cypherpunks.com.br/criptoanarquia-e-comunidades-virtuais/#fn12)</sup>

A Rede está integralmente ligada às transações econômicas, e nenhum país pode se dar ao luxo de se "desconectar" dela. (A URSS não poderia fazê-lo, e eles estavam anos-luz atrás dos EUA, Europa e países asiáticos. E em poucos anos, nenhuma esperança de limitar essas ferramentas, algo que o USFBI reconheceu. <sup>[[13]](https://cypherpunks.com.br/criptoanarquia-e-comunidades-virtuais/#fn13)</sup>

Inevitabilidade Tecnológica: Essas ferramentas já estão em uso generalizado, e somente passos draconianos para limitar o acesso a computadores e canais de comunicação podem afetar significativamente o uso futuro. (Cenários para restrições no uso privado da criptografia.)

Como John Gilmore observou, "a Net tende a interpretar a censura como um dano e as rotas ao seu redor". Isso se aplica também às tentativas de legislar o comportamento na Internet. (A impossibilidade absoluta de regulamentar a rede mundial, com pontos de entrada em mais de cem nações, com milhões de máquinas, ainda não é totalmente reconhecida pela maioria dos governos nacionais. Eles ainda falam em termos de "controlar" a rede, quando de fato as leis de uma nação geralmente têm pouco uso em outros países.)

Dinheiro digital em suas várias formas é provavelmente o elo mais fraco neste momento. A maioria das outras peças é operacional, pelo menos em formas básicas, mas o dinheiro digital é (compreensivelmente) mais difícil de implantar. Experimentos com Hobbys ou "brinquedos" foram incômodos, ea natureza "brinquedo" é dolorosamente óbvia. Não é fácil usar sistemas de dinheiro digital neste momento ("Para usar o Magic Money, primeiro crie um cliente..."), especialmente em comparação com as alternativas de fácil compreensão. <sup>[[14]](https://cypherpunks.com.br/criptoanarquia-e-comunidades-virtuais/#fn14)</sup> As pessoas estão compreensivelmente relutantes em confiar dinheiro real a tais sistemas. E ainda não está claro o que pode ser comprado com dinheiro digital (um dilema de galinha ou ovo, que provavelmente será resolvido nos próximos anos).

E o dinheiro digital, os bancos digitais, etc., são um alvo provável dos movimentos legislativos para limitar a implantação da criptoanarquia e das economias digitais. Seja por meio de regulamentação bancária ou leis fiscais, não é provável que o dinheiro digital seja implantado com facilidade. "Crianças, não tente isso em casa!" Alguns dos esquemas atuais também podem incorporar métodos para relatar transações para as autoridades fiscais e podem incluir recursos de "custódia de chaves de software" que tornam as transações total ou parcialmente visíveis para as autoridades.

## 11\. Conclusões

Criptografia forte fornece novos níveis de privacidade pessoal, o que é ainda mais importante em uma era de maior vigilância, monitoramento e a tentação de exigir provas de identidade e permissão. Algumas das "credenciais sem identidade" trabalho de Chaum e outros podem diminuir esse movimento em direção a uma sociedade de vigilância.

As implicações são, a meu ver, que o poder dos estados-nação será reduzido, as políticas de arrecadação de impostos terão que ser mudadas, e as interações econômicas serão baseadas mais em cálculos pessoais de valor do que em mandatos sociais.

Isto é uma coisa boa? Principalmente sim. A criptoanarquia tem alguns aspectos confusos, disso pode haver pouca dúvida. De coisas relativamente sem importância, como fixação de preços e informações privilegiadas, a coisas mais sérias, como espionagem econômica, o enfraquecimento da propriedade do conhecimento corporativo, a coisas extremamente obscuras, como mercados anônimos de assassinatos.

Mas não esqueçamos que os estados-nação, sob o disfarce de nos proteger dos outros, mataram mais de 100 milhões de pessoas só neste século. Mao, Stalin, Hitler e Pol Pot, apenas para citar os exemplos mais extremos. É difícil imaginar qualquer nível de assassinatos por contrato digital chegando perto da barbárie do estado. (Mas eu concordo que isso é algo que não podemos falar com precisão; não acho que tenhamos muita escolha em aceitar a criptoanarquia ou não, então eu escolho focar no lado positivo.)

É difícil argumentar que os riscos de mercados anônimos e evasão fiscal são justificativas para a supressão mundial das ferramentas de comunicação e criptografia. As pessoas sempre se mataram, e os governos não pararam com isso (sem dúvida, elas tornam o problema muito pior, como as guerras deste século mostraram).

Além disso, existem vários passos que podem ser tomados para diminuir os riscos da criptoanarquia impingir à segurança pessoal. <sup>[[15]](https://cypherpunks.com.br/criptoanarquia-e-comunidades-virtuais/#fn15)</sup>

A criptografia forte fornece um meio tecnológico de garantir a liberdade prática de ler e escrever o que se deseja. (Embora talvez não em seu nome verdadeiro, como a democracia do estado-nação provavelmente ainda tentará controlar o comportamento através de votos majoritários sobre o que pode ser dito, não dito, lido, não lido, etc.) E, claro, se a fala é livre Assim, muitas classes de interação econômica estão essencialmente ligadas à liberdade de expressão.

Uma mudança de fase está chegando. As comunidades virtuais estão em ascensão, substituindo as noções convencionais de nacionalidade. A proximidade geográfica não é mais tão importante quanto antes.

Muito trabalho permanece. A criptografia técnica ainda não resolveu todos os problemas, o papel das reputações (tanto positivas quanto negativas) precisa de um estudo mais aprofundado, e as questões práticas que envolvem muitas dessas áreas mal foram exploradas.

Nós seremos os colonizadores do ciberespaço.

## 12\. Agradecimentos

Meus agradecimentos aos meus colegas do grupo Cypherpunks, todos os 700 deles, passados ​​ou presentes. Bem mais de 100 megabytes de lista de tráfego passou pela lista de discussão Cypherpunks, então tem havido muitas idéias estimulantes. Mas, especialmente, meu apreço vai para Eric Hughes, Sandy Sandfort, Duncan Frissell, Hal Finney, Perry Metzger, Nick Szabo, John Gilmore, Whit Diffie, Carl Ellison, Bill Stewart e Harry Bartholomew. Obrigado também a Robin Hanson, Ted Kaehler, Keith Henson, Chip Morningstar, Eric Dean Tribble, Mark Miller, Bob Fleming, Cherie Kushner, Michael Korns, George Gottlieb, Jim Bennett, Dave Ross, Gayle Pergamit e - especialmente - o falecido Phil Salin. Finalmente, obrigado por valiosas discussões, às vezes breves, às vezes longas, com Vernor Vinge, David Friedman, Rudy Rucker, David Chaum, Kevin Kelly e Steven Levy.

## 13\. Referências e Notas

1.  1.  O grupo Cypherpunks foi formado principalmente por Eric Hughes, Tim May e John Gilmore. Começou com reuniões físicas, na área da baía (São Francisco) e em outros lugares, e reuniões virtuais em uma lista de mala direta não moderada. O nome foi fornecido por Judith Milhon, como uma peça sobre o gênero "cyberpunk" e a ortografia britânica da cifra. A lista de discussão pode ser assinada enviando a mensagem única para assinar cypherpunks no corpo de uma mensagem para majordomo@toad.com. Espere pelo menos 50 mensagens por dia. Cerca de 600 assinantes em muitos países estão atualmente na lista. Alguns são pseudônimos. [↩](https://cypherpunks.com.br/criptoanarquia-e-comunidades-virtuais/#ref1)
    2.  A RSA Data Security Inc., em Redwood Shores, Califórnia, é a administradora da licença. Entre em contato para obter detalhes. [↩](https://cypherpunks.com.br/criptoanarquia-e-comunidades-virtuais/#ref2)
    3.  Muitos textos criptográficos existem. Uma boa introdução é a _Criptografia Aplicada de_ Bruce Schneier, John Wiley and Sons, 1994\. Este texto inclui indicadores para muitas outras fontes. Os Anais de "Criptografia" (Avanços em Criptologia, Springer-Verlag, anualmente) são referências essenciais. A conferência anual da Crypto em Santa Bárbara, e as conferências Eurocrypt e Auscrypt, são onde a maioria dos resultados de criptografia são apresentados. [↩](https://cypherpunks.com.br/criptoanarquia-e-comunidades-virtuais/#ref3)
    4.  David Chaum, ["Correio eletrônico não rastreável, endereços de retorno e pseudônimos digitais",](literature/untraceable-electronic-mail/) Comm. ACM 24, 2, Fevereiro de 1981, pp. 84-88\. Remailers estilo Cypherpunks são uma forma de "mixagens digitais" de Chaum, embora longe do ideal. [↩](https://cypherpunks.com.br/criptoanarquia-e-comunidades-virtuais/#ref4)
    5.  David Chaum, "Segurança sem Identificação: Sistemas de Transação para tornar o Big Brother Obsoleto", Comm. ACM 28, 10, outubro de 1985\. Este é um artigo antigo sobre dinheiro digital... não deixe de consultar artigos mais recentes. [↩](https://cypherpunks.com.br/criptoanarquia-e-comunidades-virtuais/#ref5)
    6.  A oposição política em Myan Mar - antiga Birmânia - está usando Pretty Good Privacy rodando em laptops DOS nas selvas para comunicação entre os rebeldes, de acordo com Phil Zimmermann, autor de PGP. Este uso de vida ou morte ressalta o papel da criptografia. [↩](https://cypherpunks.com.br/criptoanarquia-e-comunidades-virtuais/#ref6)
    7.  David Friedman, _A maquinaria da liberdade_ , 2a edição. Um teórico importante do anarcocapitalismo. (Hayek foi outro.)
    8.  Tim May, [The Crypto Anarchist Manifesto](https://cypherpunks.com.br/o-manifesto-criptoanarquista/) , Julho de 1988, distribuído na Usenet e em várias listas de discussão. [↩](https://cypherpunks.com.br/criptoanarquia-e-comunidades-virtuais/#ref8)
    9.  Abuso, segundo alguns pontos de vista, dos remailers já está ocorrendo. Um remailer do tipo Cypherpunks foi usado para enviar uma função de hash proprietária da RSA Data Security, Inc. para a Usenet. (Deixe-me apressar para adicionar que não era um remailer eu opero, ou tenho controle sobre, etc.)
    10.  artigo sobre dinheiro digital, _The Economist_ , 26 de novembro de 1994\. pp. 21-23\. [↩](https://cypherpunks.com.br/criptoanarquia-e-comunidades-virtuais/#ref10)
    11.  artigo sobre dinheiro digital, Steven Levy, _Wired_ . Dezembro de 1994\. [↩](https://cypherpunks.com.br/criptoanarquia-e-comunidades-virtuais/#ref11)
    12.  Veja Kevin Kelly's _Out of Control_ , 1994, para uma discussão de como o controle central está falhando, e como o paradigma moderno é um dos mecanismos de mercado, escolha pessoal e empoderamento tecnológico. [↩](https://cypherpunks.com.br/criptoanarquia-e-comunidades-virtuais/#ref12)
    13.  Durante o debate "Digital Telephony Bill", uma autoridade do FBI disse que o fracasso em determinar as capacidades de escuta nos próximos 18 meses tornaria tudo discutível, já que o custo subiria além de qualquer orçamento razoável (atualmente US$ 500 milhões para custos de retrofit). [↩](https://cypherpunks.com.br/criptoanarquia-e-comunidades-virtuais/#ref13)
    14.  "Magic Money" foi uma implementação experimental do sistema de dinheiro digital de Chaum. Ele foi codificado por "Priduct Cypher", um membro pseudônimo da lista Cypherpunks - nenhum de nós sabe sua identidade real, como ele usou os remailers para se comunicar com a lista, e assinou digitalmente seus posts. Muitos de nós acham muito difícil de usar, o que é mais uma medida das profundas questões envolvidas no uso de análogos digitais (sem trocadilhos) para dinheiro real e físico. [↩](https://cypherpunks.com.br/criptoanarquia-e-comunidades-virtuais/#ref14)
    15.  Robin Hanson e David Friedman escreveram extensivamente sobre cenários para lidar com as ameaças de extorsionistas, pretensos assassinos, etc. Espero que algum trabalho deles seja publicado algum dia. (Grande parte da discussão foi em 1992-3, na lista de discussão "Extropians".) [↩](https://cypherpunks.com.br/criptoanarquia-e-comunidades-virtuais/#ref15)

    * * *

    ### Timothy C. May

    <address>535 Monterey Drive Aptos, CA 95003 EUA tcmay@netcom.com Dezembro de 1994</address>

    Fonte: [https://nakamotoinstitute.org/virtual-communities/](https://nakamotoinstitute.org/virtual-communities/)
