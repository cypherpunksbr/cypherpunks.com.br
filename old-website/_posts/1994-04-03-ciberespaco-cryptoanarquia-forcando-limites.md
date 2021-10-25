---
title:  "Ciberespaço, Crypto Anarquia e Forçando Limites"
date:   03-04-1994 -0300
categories:
  - Biblioteca
tags:
  - Timothy C. May
---


### Tim May

<pre>Assunto: Ciberespaço, Crypto Anarquia e Forçando Limites
De: tcmay@netcom.com (Timothy C. May)
Para: cypherpunks@toad.com
Data: Domingo, 3 de Abril de 1994 19:16:49 -0700 (Horário de verão do pacífico)
Cc: tcmay@netcom.com (Timothy C. May)
</pre>
  
Timothy C. May

#### 3 de Abril de 1994


Esta mensagem aborda dois tópicos de interesse recente (para alguns), são eles:

1.  Configurando sistemas de pagamento para transmissão de mensagens, para lidar com as questões de "mailbombing" e "flooding" de maneira mais natural (localidade de referência, usuário de um serviço nacional, evitando os efeitos de explosão do "Morris Worm" que poderiam ter acontecido com Detweiler nos bombardeou, como Hal notou).

2.  A questão geral do "ciberespaço". Esta é a raiz de algumas controvérsias e merece mais discussão. A criptografia fará disso uma questão de cúspide muito real nos próximos anos.

Por que debater isso agora? O que poderia sair desse debate?

Acontece que eu estou lendo um novo livro maravilhoso de Kip Thorne, intitulado "Buracos Negros e Espasmos do Espaço". Isso está amplamente disponível em livrarias, no livro de capa dura apenas neste momento. (30 dólares, mas é um ótimo livro, e comprei na Barnes and Noble por 24 dólares). Falando da Barnes and Noble, a Santa Clara está vendendo o livro "Introdução a complexidade Kolmogorov" de Li e Vitanyi por US $ 44, antes dos 20\. % de desconto em capa dura, que pode estar com preço errado, paguei 60 dólares pela minha.Verifique se você estiver interessado ... acho que havia duas cópias.)

Thorne passou 30 anos estudando o colapso gravitacional e os buracos negros, e foi coautor do famoso livro de 1973 sobre "Gravitação", que eu usei em uma forma Xerox para minha aula de relatividade geral em 1973.

O ponto? Thorne descreve seu envolvimento com Carl Sagan na elaboração da física da viagem no tempo através de buracos de minhoca. Thorne teve uma epifania: por mais improvável que seja a engenharia ou o financiamento de alguma coisa, há algo de valioso a ser ganho ao examinar os limites absolutos do que é possível sem levar em conta os aspectos práticos da engenharia. Assim, ele e seus alunos analisaram as implicações de uma civilização extremamente avançada capaz de, de alguma forma, abrir a boca de um buraco de minhoca. As conclusões são fascinantes e levam a uma nova linha de pensamento sobre a estrutura do espaço-tempo.

Forçar limites e ver um comportamento “ideal” é revigorante.

A conexão com a criptografia é esta: talvez devêssemos estar pensando mais sobre as implicações e efeitos da criptografia forte, do dinheiro digital, dos remailers ideais, etc., assumindo que certos problemas práticos que nos atormentam hoje são, ou logo serão resolvidos. Até certo ponto, já fazemos isso, como quando discutimos as misturas ideais de Chaum da mesma forma que os engenheiros discutem amplificadores operacionais ideais - uma útil abstração de comportamento no limite em que implementações menores do mundo real podem ser contrastadas.

E é claro que muitos de nós descobrimos que os “Verdadeiros Nomes” de Vernor Vinge são um excelente (e rapidamente legível) tratamento de como as coisas poderiam funcionar em um mundo de comunicação rápida, barata e segura. Outros escritores viram as coisas de maneira diferente (por exemplo, “Cavaleiro da Onda de Choque”, “1984”, “Acidente de neve”).

Aqui, para ir direto ao assunto, estão algumas breves declarações do que eu vejo como o “comportamento nos limites”. Eu não vou elabora-los melhor agora.

*   "Pague conforme você vai" é a maneira natural de lidar com a maioria das transações econômicas. Há exceções, é claro, como seguro, contratos para desempenho futuro, etc., mas a maior parte do dinheiro é usada para mediar as trocas imediatas. Para um exemplo oportuno, por que seus inimigos não podem “bombardear o lixo eletrônico” com um volume enorme de lixo eletrônico? O lixo eletrônico, como nós o chamamos, é em volumes relativamente pequenos (no máximo uma caixa de correio cheia, exceto talvez para celebridades) por causa de uma coisa simples: alguém tem que pagar pela entrega! Não há possibilidade de um modo “livre” de “fazer 19 cópias dessa tonelada de lixo e enviá-las para seus inimigos”. Isso existe com o software - o bombardeio de Remailer por Detweiler, o Morris Worm de 1988, o “Dave Rhodes”. ”Correntes de caracteres - é devido a algumas falhas no modelo Net atual:

    *   os custos da transmissão de mensagens não são diretamente suportados pelos remetentes (estimulam o uso excessivo de alguns recursos escassos, a la a “tragédia dos comuns”).

    *   os sites e os remailers responderão às “instruções” para enviar a mensagem, para fazer cópias dela, etc.

*   Assim, considero imperativo que desenvolvamos o mais rapidamente possível o seguinte:

    *   sistemas de pagamento para transmissão de mensagens (eu defendo “selos digitais” como primeira e comparativamente fácil aplicação de dinheiro digital, outros também têm, e Ray Cromwell acaba de emitir sua própria proposta ... é hora de começarmos E para que você não pense que eu estou pedindo por altruísmo aqui, acho que algumas fortunas serão feitas nessa área.)

    *   protocolos anônimos ou obscuros de identidade, ao modo Chaum.

    *   um afastamento geral dos sistemas orientados aos “comuns”, que geram as noções de “acesso justo” e coisas do tipo. Se o “problema” é que as pessoas pobres não podem - supostamente - pagar uma conexão de 17 dólares por mês (o que a Netcom cobra em cerca de 25 cidades), então minha solução seria simplesmente _subsidiar_ sua conta. (Eu não estou defendendo isso, nem acho prudente subsidiar as contas de telefone, Net ou jantar de ninguém, mas é melhor do que "nacionalizar" as redes e, assim, criar mais confusão e menos eficiência para todos.)

*   A conectividade será alterada dramaticamente. A “distância” no ciberespaço já não está correlacionada com a distância física. (Não surpreendentemente, como isso ficou aparente com o telefone. Mas uma maneira útil de olhar para o ciberespaço, como sendo um espaço de conectividades e distâncias radicalmente alteradas.)

*   O acesso local ao serviço, o telefone ou as linhas de cabo que chegam à casa ou ao escritório, é um potencial gargalo. Mas uma vez que uma conexão é feita com um nó local onde existem múltiplos concorrentes (ou seja, uma vez além do monopólio concedido pelo governo local), a possibilidade de “censura” diminui rapidamente, por várias razões.

    *   Assim, empurre as linhas de "acesso criptografado" de um nó terminal (casa, escritório) para um ponto com conectividade ilimitada.

    *   Esta é a situação que agora tenho com minha linha PacBell e Netcom: PacBell não se importa com o que eu uso a linha local, e uma vez fora, eu posso discar um Netcom sem-censor em vez de um AOL ou Prodigy Big Brotherizado.

*   O ciberespaço é infinitamente colonizável. Não há limites para o crescimento. (Suposição: a realização do ciberespaço está em várias máquinas e redes, que não são livres, nem infinitas. Mas o “sem limites” vem da facilidade com que aqueles próximos a um “limite” podem simplesmente ultrapassar esse limite com mais recursos de CPU. redes, etc.).

*   Criptografia significa que o acesso a “regiões” pode ser controlado por “proprietários”:

    *   “Minha casa, minhas regras” aplicadas localmente, sem autoridade do governo central

    *   segurança essencialmente inquebrável (no sentido da criptografia)

*   Aliás, a forte criptografia é o “material de construção” do ciberespaço… a argamassa, os tijolos, as vigas de suporte, as paredes. Nada mais pode fornecer a "permanência" ... sem criptografia, as paredes estão sujeitas ao colapso no primeiro toque por uma pessoa ou agência maliciosa. Com a criptografia, nem mesmo uma bomba H de 100 megaton pode romper as paredes.

    (Se você acha que estou exagerando, faça alguns cálculos sobre a energia para quebrar um módulo com 1000 dígitos decimais).

*   Nenhuma “lei de zoneamento” será necessária, ou possível, no ciberespaço. ("Acidente de neve", de Neil Stephenson, enquanto uma leitura maravilhosa e instigante, deu errado aqui: o ciberespaço é muito extensível e controlável localmente.)

*   A localização física dos locais do ciberespaço será cada vez mais difícil de definir. Um vasto "labirinto de salas e corredores" pode ser fisicamente instanciado em um computador na Malásia, enquanto um "salão de jogos virtual" está sendo executado por meio de recortes criptográficos (remailers) do quarto de alguém em Provo, Utah..

*   A conversa sobre as “regras de acesso” é, portanto, insignificante, a menos que os governos reprimam redes, criptografia e sistemas privados de uma forma muito além de qualquer coisa que esteja sendo falada agora..

Essa é a “cripto anarquia” sobre a qual escrevo desde 1988\. O ciberespaço vai se revelar uma fronteira muito mais vasta do que _qualquer coisa_ que vimos até agora. Com “apenas” 10 ^ 70 partículas em todo o universo, há muito mais “espaço” (espaço de endereço, espaço-chave, etc.) até mesmo em um conjunto relativamente pequeno de dígitos. O ciberespaço é um espaço matemático e seu espaço é verdadeiramente ilimitado.

E nós estaremos movendo nosso comércio, nosso entretenimento e grande parte de nossas vidas no ciberespaço muito mais rápido do que estaremos nos movendo lentamente para a órbita baixa da Terra e além. Na verdade, considero que já estou na metade do caminho. Em alguns anos, com a conectividade de um toque da Mosaic, com uma infinidade de opções de rede, com remailers seguros e ferramentas similares para anonimizar minhas transações, estar tão longe aí vai voltar atrás.

Isso é suficiente para tais observações por enquanto. Acho que faz sentido ter uma visão um pouco mais abrangente das tendências inevitáveis, para ver para onde estamos indo, para ver quais problemas precisam de mais trabalho.

Espero que alguns de vocês concordem comigo.

--Tim May

