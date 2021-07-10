---
title:  "Criptoanarquia e o empreendedorismo libertário II"
date:   22-05-2013 -0300
categories:
  - Biblioteca
tags:
  - Daniel Krawisz
---


### Daniel Krawisz


#### Capitulo 2 - Criptografia de Chave Pública  
Daniel Krawisz  
May 22, 2013

![internet](../pages/img/internet.png)

### Criptografia de chave simétrica

Criptografia de chave pública é o maior instrumento de liberdade criado até hoje. A sua descoberta foi revolucionária. Antes dela, todas criptografias eram apenas truques. Ela foi desenvolvida em 1973 por Ellis, Cooks e Williamson como pesquisadores no GCHQ no Reino Unido, mas o trabalho foi confidencial até 1997\. Também foi desenvolvida de forma independente em 1976 por Rivesr, Shamir e Adleman no MIT. O trabalho deles foi publicado, porém protegido por patente até 2000\. Agora ele está livre.

Para entendê-la, entretanto, é necessário passar pelo básico de criptografia de chave simétrica, que é o tipo de criptografia que já estamos familiarizados, o tipo que existe desde da antiguidade. Uma vez entendida as limitações da criptografia de chave simétrica, a criptografia de chave pública vai parecer mágica.

Pense na ideia de uma cifra de substituição simples, ou seja, a mensagem é um texto e a encriptação consiste em trocar cada letra por uma outra. Por exemplo, você consegue solucionar o código abaixo?

<pre>  `JHBYEUXRBLPDWJXOBELNEHNTBFYDJHBWDCYUWJWLNUUWZBDJXLYERWRJRWEIBBCWEGJHBWDOYEBXWEJHBWDYSECYLIBJRUXRNEMBDRCYYEBD` 
</pre>

Duas coisas para se notar aqui. Primeiro, o algoritmo é inseguro. Não importa como as letras foram substituídas, seria fácil de decifrar, principalmente com um computador. Precisaremos de algo muito mais complicado para deixar a mensagem realmente secreta. Mais importante, entretanto, é que sabendo a sequência que foram trocadas é o suficiente tanto para descriptografar e para criptografar uma mensagem. É, de fato, impossível saber como criptografar uma mensagem sem ao mesmo tempo saber como descriptografá-la.

![symetry](../pages/img/symmetric.jpg)

Essa é a essência da criptografia de chave simétrica: é impossível saber como criptografar uma mensagem sem saber como descriptografar ela, e vice e versa. Isso é um grande problema. Se, por exemplo, meu inimigo conseguiu obter uma de minhas mensagens e decifrou ela, ele não apenas vai conseguir ler o resto de minhas mensagens como também vai conseguir fazer novas mensagens, talvez para enganar a mim e meus amigos.

O maior problema, entretanto, é que se apenas soubermos criptografia de chave simétrica, não existe jeito nenhum de mandar mensagens secretas. Dois aliados não tem como falar um com o outro de modo para estabelecer um protocolo que não o intruso não descubra tudo. Temos que ter meios de comunicação seguros para se combinar um código de chave simétrica, mas se já tivermos isso o problema de comunicação já estaria solucionado.

Criptografia de chave simples é bom para manter os seus segredo distante de todo mundo. A partir do momento que você revela ela para alguém, você criou um furo na segurança. Você não sabe se tinha alguém escutando e também não sabe se alguém vai conseguir extrair o segredo de seu aliado.

### Criptografia de chave assimétrica

Vamos pensar como poderíamos melhorar a cifra de substituição. Uma das coisas mais óbvias seria ao invés de trocar letra por letra, trocar em blocos de dois. Por exemplo, AA pode virar QF e BB pode virar LV. Isso seria bem mais seguro, ainda assim seria facilmente decifrado com a ajuda de um computador. Poderíamos também trocar em blocos de três em três ou quatro em quatro. Uma hora chegaríamos em um ponto que seria impossível até um computador decifrar em um tempo razoável.

O problema com esse método, entretanto, é que quanto maior o bloco que usamos maior fica a lista de substituições. Um bloco de dois requer 26^2=676 substituições, um bloco de três requer 17.576 substituições, já para um bloco de quatro seriam necessários quase que meio milhão de substituições. Um computador não conseguiria decifrar um código destes, porém se comunicar com uma lista desse tamanho seria imprático de se fazer seguramente.

Poderíamos, alternativamente, fazer um algoritmo que misturasse o bloco de quatro letras de algum jeito que fosse difícil de se decifrar, mas ao mesmo tempo uma mensagem bem curta. Isso abre novas possibilidades: como a cifra de substituição é simplesmente uma lista de substituições, ela é inerentemente simétrica. Entretanto, se a cifra é dada como um algoritmo e se conjunto de substituição é tão grande que praticamente não poderia ser enumerado, então as propriedade do algoritmo podem modificar muito as propriedades das cifras.

Por exemplo, suponha que você consiga desenhar um algoritmo que pode ser executado para frente em uma fração de segundos, porém o inverso dele leva milhões de anos. Se você tivesse algo assim, você poderia explicar para qualquer um com segurança sem ter medo que alguém decifrasse. Não é muito útil, pois ninguém, nem meus amigos, conseguiriam descriptografar a mensagem! Entretanto, ainda é bem interessante.

Existe uma melhoria que faria essa ideia ser útil. Suponha que existem dois algoritmos que um é o inverso do outro. Ambos são rápidos para frente, mas lentos no inverso. Um algoritmo pode ser usado para criptografar e o outro para descriptografar. Eu deixo o algoritmo de descriptografar em segredo, mas deixo meus amigos verem o de criptografar. Agora eles podem me enviar mensagens que só eu posso ler, e eu não revelei nenhum segredo que não posso me dar ao luxo de ter comprometido. Na verdade, eu posso deixa meus inimigos verem meu algoritmo de criptografar. Ele não podem fazer nada com ele a não ser mandar mensagens para mim.

![](../pages/img/public-key.jpg)

O produto final é que todo mundo tem dois algoritmos. Todos mantem um deles em segredo e o outro publico. Como é que podemos descobrir tantos algoritmos assim? Geralmente, há uma classe de algoritmos, cada um especificado por um número ou chave. Então cada um de nós tem uma chave pública e uma chave privada. Isto é a criptografia de chave privada.

Agora as duas pessoas podem se comunicar com segurança, mesmo que de início elas não tenham um canal de comunicação seguro. O inimigo pode estar escutando do nosso lado, porém ele não vai conseguir entender nada o que estamos falando entre nós uma vez que trocamos as chaves privadas.

### Criando comunidades com criptografia de chave pública

A beleza da criptografia de chave pública vem do fato que ela dá a habilidade de alguém pode provar que tem um segredo sem revelá-lo. Pare um pouco e pense o quão paradoxal isto é, mesmo assim é fácil de entender agora. Se eu quiser verificar sua identidade eu simplesmente mando uma mensagem criptografada usando sua chave pública e pergunto o que estava escrito. Somente quem tem a chave privada vai conseguir responder esta pergunta.

Isso não é algo intuitivo para nós, pois nossa tecnologia não se baseia nisso. O fato que atualmente ainda usamos tecnologias primitivas como cartões de créditos, que tem o número gravado neles, ou formas de identificação como as social security numbers is backwards. Isso está obsoleto fazem décadas. Não deveria existir um motivo para que você precise mostrar o número do seu passaporte ou da sua identidade para outra pessoa, nunca.

A razão que a criptografia de chave privada é tão empoderadora ao indivíduo é que com ela você só consegue provar sua identidade com seu consentimento. Uma chave privada não é como um RG que pode ser requerido ou forçado de você a qualquer momento. Você escolhe os grupos que deseja participar e mantém sua identidade em segredo.

Existe um pequeno problema aqui. Se uma terceira parte estiver observando quando vocês trocarem as chaves públicas, ele vai ver as chaves publicas que foram trocadas. Mesmo que ele não veja você provando sua identidade, isso não é o suficiente para que ele deduzir que a chave pública corresponde a privada? Isso é facilmente resolvido, pois a chave que você usa para autenticação não precisa ser a mesma que você usa para estabelecer um canal de comunicação seguro. Você pode gerar uma nova chave aleatória para cada conversa e autenticar você com a chave privada permanente.[2]

E tem mais, se você usar a sua chave privada em uma mensagem criptografada usando sua chave pública, você consegue ler a mensagem original. Por os algoritmos serem o inverso um dos outros, você poderia criptografar uma mensagem usando sua chave privada e ela só poderia ser descriptografada usando sua chave pública. O resultado seria uma mensagem legível que seria inegavelmente minha. Essa é a ideia por trás de assinatura digital.

A comunidade pode solicitar o uso da assinatura digital para alguns tipos de comunicação, para tudo que ela julgar necessário para estabelecer a reputação dos membros. Mensagens podem ser assinadas por várias pessoas, assim elas podem servir como contratos ou registros de uma transação. A história de cada membro é pública e eterna.

Na realidade uma assinatura digital é um pouco mais complexa do que eu descrevi aqui. Normalmente alguém não criptografa uma mensagem inteira, mas sim um encurtamento da mensagem. A mensagem seria enviada com seu hash criptografado. No fim o efeito é o mesmo, pois a mensagem está ligada ao remetente.

Um comunidade que combina sigilo criptográfico, autenticação de chave pública e assinatura digital, é uma comunidade voluntária unida por contratos de reputação. Ela não necessita de uma autoridade central, pois os arquivos que ela necessita para estabelecer a reputação das pessoas podem ser armazenados em vários computadores. Portanto, segura contra ataques governamentais. Banimento é a única punição que a comunidade tem.

Isto é libertarianismo, é exatamente o que os libertários sempre desejaram. Se nós quisermos que as pessoas aceitam a possibilidade de colocar o governo de lado e que liberdade de associação e privacidade são inerentes a natureza da realidade, todos nós precisamos montar comunidades criptográficas. Não existe a necessidade de falar, até ficarmos sem ar, em termos abstratos com as pessoas que não escutam. Apenas construa as redes e as pessoas vão ser atraídas para elas. Uma vez que elas se acostumarem, vai começar a surgir demanda por elas.

Existe um serviço que talvez as pessoas desejam que não falei: anonimidade. Um intruso pode não saber o que você está falando, mas ele pode saber que você faz parte daquela comunidade. Talvez um espião vire um membro da comunidade para conectar uma pessoa real a uma chave pública. Idealmente, você provavelmente deve fazer tal que suas comunicações não sejam linkadas a comunidade de forma alguma. Anonimidade é um pouco mais difícil de se conseguir, porém é possível com serviços como Tor. Eu não quero entrar nos detalhes sobre o que é possível, mas é suficiente dizer que existe muito a se construir em cima da estrutura básica que falei aqui.

### Notas:

1.  Veja Stallings, W., Cryptography and Network Security: Principles and Practice, 5th ed., Pearson Education, 2011 para uma introdução a criptografia que explica tudo que introduzi aqui. Ou leia a [Wikipedia](http://en.wikipedia.org/wiki/Public-key_cryptography)
2.  Na verdade você provavelmente usaria algo chamado chave de Diffie-Hellman para estabelecer um canal de comunicação. O principio é basicamente um mesmo, porém com algumas pequenas diferenças do que eu expliquei

Fonte: [Crypto-Anarchy and Libertarian Entrepreneurship - Chapter 2: Public-Key Cryptography](https://nakamotoinstitute.org/mempool/crypto-anarchy-and-libertarian-entrepreneurship-2/)
