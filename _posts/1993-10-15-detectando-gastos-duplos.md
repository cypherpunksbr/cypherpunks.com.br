---
title:  "Detectando Gastos Duplos"
date:   22-11-1992 -0300
categories:
  - Biblioteca
tags:
  - Hal Finney
---


### Hal Finney

#### 15 de outubro de 1993  
(revisado em 13 de março de 1996)


Aqui está uma tentativa de descrever o dinheiro digital de Chaum a partir de seu trabalho, Untraceable Electronic Cash, de Chaum, Fiat e Naor, do processo Crypto 88\. Esse dinheiro tem a propriedade de que o usuário do dinheiro pode permanecer anônimo, desde que não o gaste mais de uma vez, mas se ela gastar duas vezes, sua identidade será revelada.

É assim que funciona em termos gerais: Alice abre uma conta com um banco de forma não anônima. Ela mostra a identidade para que o banco saiba quem ela é; tanto ela como o banco sabem o número da sua conta. Quando ela sacar dinheiro, ela vai ao banco ou entra em contato com eles eletronicamente e apresenta uma prova de quem ela é e qual é o seu número de conta, e o banco lhe dá algum dinheiro digital. O dinheiro digital é um padrão de informação, talvez armazenado em um arquivo de computador em um cartão inteligente ou disco magnético. Mais tarde, ela gasta o dinheiro digital enviando ou dando para Bob, um comerciante. Bob pode verificar e verificar se o dinheiro deve ter vindo do banco. Ele aceita o dinheiro se for válido, dando a Alice a mercadoria. Mais tarde, ele envia o dinheiro para o banco para ser adicionado à sua própria conta.

Note que isso basicamente poderia ser feito com uma simples assinatura RSA. O banco poderia dar a Alice uma declaração dizendo: "vale 1 dólar", assinada pela chave secreta do banco. Bob poderia verificar se a declaração estava de fato assinada pelo banco e, portanto, saber que ninguém mais do que o banco poderia ter criado essa declaração. Ele aceita e envia para o banco, que o homenageia porque reconhece sua própria assinatura.

Um problema com esse dinheiro trivial é que o gasto duplo não pode ser detectado ou evitado, já que todo o dinheiro parece igual. Isso pode ser remediado com o dinheiro incluir um número de série exclusivo. Agora, quando Bob vai aceitar o dinheiro de Alice, ele pode ligar para o banco e dizer: alguém mais depositou o número de série 123456? Se não, ele aceita o dinheiro e deposita-o. Isso é chamado de dinheiro eletrônico on-line; o comerciante deve verificar com o banco para cada transação.

No entanto, esse sistema simples melhorado não merece ser chamado de caixa, porque não possui a característica distintiva do dinheiro digital: ele não é anônimo. Quando o banco recebe dinheiro com o número de série 123456 que está sendo depositado, o banco reconhece que essa foi a mesma fatura que Alice retirou. O banco pode, portanto, deduzir que Alice gastou o dinheiro na casa de Bob e, a partir desse tipo de informação, um dossiê poderia ser construído com todos os tipos de informações destruidoras de privacidade sobre ela.

Para permitir o anonimato, precisamos entrar na matemática. O que queremos é que Alice e o banco coletivamente criem uma assinatura RSA do banco que não pode ser falsificada, mas que o banco não reconhecerá como proveniente de Alice. Esta é a primeira coisa que o artigo de Chaum discute.

O dinheiro neste sistema é da forma (x, f (x) ^ (1/3)) mod n, onde n é o módulo público do banco. f () (e, abaixo, g ()) é uma função unidirecional, que pode ser calculada facilmente, mas para a qual é inviável calcular o inverso. Também deve ser inviável encontrar dois y diferentes, z tais que f (y) = f (z). Atualmente, existem várias opções adequadas para funções unidirecionais, sendo as mais comuns o algoritmo MD5 da RSA e o Secure Hash Algorithm (SHA) do governo dos EUA.

A razão pela qual a expressão acima seria aceita como dinheiro é dupla. Primeiro, apenas o banco pode calcular qualquer coisa ^ (1/3) mod n. Esta é basicamente a operação de assinatura RSA para o expoente de 3\. Ninguém mais pode encontrar raízes cúbicas. A razão f (x) é usada é isso. Suponha que nós propusemos que (x, x ^ (1/3)) deveria ser o dinheiro, para algum x aleatório, raciocinando que somente o banco poderia encontrar a raiz cúbica de x. Você pode ver como forjar dinheiro assim? (Dedique alguns instantes e tente ver como você pode construir um par como este, mesmo que você não consiga criar raízes cúbicas.)

A resposta é que é fácil forjar isso escolhendo primeiro um y aleatório e exibindo o par (y ^ 3, y). Agora temos um número e depois sua raiz cúbica. No entanto, não precisamos ter raízes cúbicas para encontrá-lo. É por isso que esse tipo de dinheiro não seria bom.

O sistema de Chaum evita isso pegando a raiz cúbica de uma função unidirecional de x. Para forjar sem ter uma raiz cúbica, você teria que produzir (finv (y ^ 3), y), que corresponderia ao padrão acima, mas não é possível inverter a função unidirecional como essa. Portanto, apenas o banco pode criar dinheiro da forma apropriada. Isso pode ser pensado como a forma formal e matemática do meu "dinheiro" informal, acima do qual havia uma nota assinada digitalmente com um número de série. Aqui, x é o número de série e é assinado digitalmente desta maneira especial. Nada mais é necessário.

A coisa boa sobre esse dinheiro é que ele permite cegar, um método de fazer com que o banco assine o valor sem saber que valor ele está assinando. Funciona assim. Alice escolhe x, que será o x no dinheiro. Ela calcula f (x), mas em vez de enviá-la ao banco para ser assinada (aumentada para 1/3 de poder) ela escolhe primeiro um número aleatório r e envia f (x) * r ^ 3 para o banco. O banco leva esse número para 1/3 da potência, obtendo r * f (x) ^ (1/3). Lembre-se, porém, que o banco não vê r ou f (x) separadamente, mas apenas seu produto. Não sabe o que r ou f (x) é. Eles poderiam ser qualquer coisa, na verdade.

O banco envia este r * f (x) ^ (1/3) de volta para Alice, e ela divide por r, que ela sabe. Isso dá a ela f (x) ^ (1/3), e ela coloca isso junto com x para obter seu dinheiro digital: (x, f (x) ^ (1/3)). Ela tem um dinheiro que só poderia ter sido assinado pelo banco, mas o banco não o reconhece quando é depositado.

Outras coisas, não matemáticas, acontecem quando esta retirada continua. Alice deve provar sua identidade ao banco, como mencionado acima. E o banco debitará sua conta pelo valor do dinheiro. Neste sistema, assumimos por simplicidade que todo o dinheiro tem o mesmo valor. Em um sistema real, diferentes valores podem ser codificados por expoentes diferentes de 3.

Quando Alice deposita o dinheiro, Bob deve ligar para o banco para se certificar de que não foi depositado antes, sendo este um sistema "on-line". Embora o banco não reconheça x (nunca se ouve falar dele) ele se lembrará de todos os x's que foram depositados e assim poderá alertar Bob se o dinheiro tiver sido gasto anteriormente. Tanto Bob quanto o banco podem verificar a assinatura digital sobre o dinheiro e, assim, honrá-lo.

Todo o material acima ocupa menos de uma página do artigo de nove páginas de Chaum. Para Chaum, isso é trivial. Agora chegamos à parte interessante. Agora vamos ver o esquema que permite que os gastadores de casal percam seu anonimato. Isso permitirá dinheiro eletrônico "off-line"; Bob não precisará mais verificar com o banco se o dinheiro já foi gasto. Ele aceita de Alice sabendo que, se ela trapaceia, o banco vai honrar o dinheiro e processar Alice para compensar a perda.

(Para tornar esta explicação mais fácil de seguir, descreverei uma versão ligeiramente simplificada do dinheiro off-line de Chaum. A versão que eu descrevo requer o uso de uma função unidirecional não-invertível como na f () usada acima. não requer uma suposição tão forte e fornece uma rastreabilidade "incondicional" mesmo se a função unidirecional for quebrada.)

Vamos começar com a forma do dinheiro em si. É o produto dos números k / 2, onde k é um "parâmetro de segurança" que afeta a chance de sucesso de um trapaceiro. Cada número é da forma g (xi, yi) ^ (1/3), onde g é uma função unidirecional de dois argumentos semelhante à f acima. (O "xi", "yi", "ai", etc. aqui são valores separados para cada i de 0 ak / 2.)

xi e yi são assim: xi = f (ai), onde ai é um número aleatório, e f é outra função unidirecional. yi é meio complicado. É f (ai xor <info>), onde <info>, a chave para toda essa operação, está identificando informações sobre a conta de Alice! É o número da sua conta concatenado com um número de série para o dinheiro.</info></info>

Agora, por que passar por tudo isso? Aqui está o porquê. Se você pudesse descobrir ai e (ai xor <info>), para algum eu, você saberia a identidade de Alice. (Xor'ing eles produziriam <info>.) Quando Alice double-gasta, ambos ai e ai xor <info>serão revelados.</info></info></info>

O que acontece quando Alice gasta a moeda é isso. Para cada i de 0 a k / 2, Bob escolhe 0 ou 1 aleatoriamente. Se ele escolhe 1, ele é informado de ai e yi. Se ele escolher 0, ele será informado (ai xor <info>) e xi. Isso permitirá que ele verifique a assinatura do dinheiro, conforme descrito em mais detalhes abaixo.</info>

Note que quando Bob receber essa informação, ele saberá um monte de ai's, e ele saberá um monte de (ai xor <info>), mas eles são para i's diferentes. Ele não sabe ai e (ai xor <info>) para qualquer um i. Então ele não pode quebrar o anonimato de Alice.</info></info>

Quando Bob deposita o dinheiro no banco, ele repassa as informações que recebeu de Alice sobre o ai e tal.

Agora, suponha que Alice trapaceie. Ela gasta o dinheiro de novo em algum outro lugar, no Charlie's. Charlie passa pelo mesmo procedimento que Bob, escolhendo 0 ou 1 aleatoriamente para cada valor de i. Aqui está o truque. Como ele está escolhendo aleatoriamente, seria muito improvável que ele escolhesse exatamente os mesmos 0s e 1s que Bob escolheu. (Aqui é onde o tamanho de k importa - tornando-se maior, torna menos provável que Charlie e Bob escolham o mesmo padrão de 0 e 1\. Mas faz com que os cálculos demorem mais tempo.) Isso significa que para um ou mais valores de i, Charlie provavelmente escolherá um 0 onde Bob escolheu um 1, ou vice-versa.

Por causa disso, se o Bob tiver um ai para esse i, o Charlie irá obter ai xor <info>. Ou se Bob tiver ai xor <info>, Charlie vai ter ai. De qualquer forma, quando Charlie envia seu registro dessas informações para o banco, o banco coloca as informações de Bob e Charlie juntas e obtém os dois ai e ai xor <info>. Xor'ing estes juntos revela <info>, e Alice é pego! Essa é a ideia principal.</info></info></info></info>

(Chaum sugere não apenas depender da chance aleatória para garantir que Bob e Charlie usem conjuntos diferentes de 1 e 0\. Pelo menos alguns dos bits podem ser atribuídos a Bob e Charlie pelo banco de tal forma que todos obtenham um número diferente. Desta forma, seria garantido que Bob e Charlie escolheriam valores opostos para alguns i.)

A razão para o dinheiro ter a forma que ele faz é para que Bob possa verificar se ele está assinado pelo banco. Para cada valor de i, Alice precisa fornecer informações suficientes para calcular xi e yi. Se Bob escolher um 1, ela dá a ele ai e yi. Dado ai Bob pode calcular xi (= f (ai)), e com isso e yi ele pode calcular g (xi, yi). Se Bob escolher um 0, ela lhe dará (ai xor <info>), como descrito anteriormente, e também xi. Dado (ai xor <info>), Bob calcula yi (= f (ai xor <info>)), e com isso e xi ele pode calcular g (xi, yi).</info></info></info>

Então, para cada i, se Bob dá um 0 ou um 1, ele recebe informações suficientes para calcular g (xi, yi). Ele multiplica estes todos juntos e confirma que eles são iguais ao valor "dinheiro" original de Alice quando é levado ao 3º poder (lembre-se que o dinheiro foi produto de g (xi, yi) ^ (1/3) para todo i). Somente o banco poderia ter produzido uma assinatura nesta função unidirecional cujos argumentos assumem essa forma especial.

Mais uma complicação existe. (Bem, na verdade, um número quase infinito de complicações existe se você procurar bastante. Mas vamos nos focar em mais uma.) Alice precisa obter essa forma especial de dinheiro do banco de tal forma que o banco ganhou ' t reconhecê-lo. Isso significa que ela tem que cegar. Mas neste caso, o banco quer ter certeza de que o dinheiro é da forma adequada quando o assina; em particular, ele quer ter a certeza de que a <info>de Alice, que está enterrada em todos esses f's de g, é na verdade a mais adequada para ela. Mas como o banco não consegue ver o que está assinando, isso é difícil de fazer.</info>

Chaum usa corte-e-escolha para isso. Ele faz com que Alice prepare todos esses f e gs de acordo com o formulário acima, inserindo cuidadosamente sua própria <info>incriminadora em cada uma delas. Então ela multiplica cada g (xi, yi) por um fator de cegueira ri ^ 3 como no primeiro dinheiro. Estes são o que ela envia ao banco para ser assinado.</info>

O truque, porém, é que ela envia o dobro do que será usado. Ela envia k deles, mas apenas k / 2 será usado. (É por isso que o loop acima usou k / 2 como limite). O banco escolhe k / 2 aleatoriamente do k que ela enviou como os que realmente serão usados. Alice então tem que enviar os valores de ri cegantes para aqueles que o banco não escolheu.

A ideia é que, se Alice tentar enganar, incorporando "Bozo" em vez de "Alice" no campo <info>, ela está dando uma chance. Primeiro, para ser útil, ela terá que incorporá-lo em muitos campos <info>para valores diferentes de i. Quando Bob e Charlie comparam notas depois que ela gasta duas vezes, cada valor de i para o qual eles escolheram diferentes 0s e 1s, que estarão na metade média deles, revelará um campo <info>. Se ela só finge algumas, é provável que sua verdadeira identidade ainda seja revelada.</info></info></info>

Mas se ela falsificar muitos deles, então quando o banco escolher metade, as chances são de que pelo menos alguns dos falsos estarão no set que o banco não escolheu. Então, quando Alice tiver que revelar seus rms ofuscantes, o gabarito estará pronto. O banco irá cegar todos aqueles g (xi, yi) que não estão sendo usados ​​e ver os falsos campos <info>.</info>

Essa metodologia de corte-e-escolha tem a desvantagem de que Alice precisa fazer o dobro de trabalho na preparação do dinheiro, metade da qual será jogada fora. Mas é uma maneira simples e "bruta" de certificar-se de que assinaturas ofuscantes estão sendo feitas em dados corretamente formados.

Então, você tem isso. Anonimato, desde que você não trapaceie, e os que gastam com o dobro sejam pegos. É um pouco complicado, mas é para isso que os computadores são; Bob e Alice não fariam tudo isso a mão. Alice pressionaria o botão "gerar um candidato a dinheiro" e obteria algo para ser enviado ao banco (muitos dos novos PDAs têm comunicações sem fio infravermelhas que seriam perfeitas para transações face a face). Bob apertava o botão "cheque de dinheiro" quando Alice o gastava e ele piscava vermelho ou verde. Contanto que os cálculos não demorem muito tempo, o que eles realmente não fariam neste caso, apesar desta longa explicação, as pessoas envolvidas podem ignorar os detalhes.

Hal Finney  
_hal@rain.org_

[Página de Hal Finney](http://finney.org/~hal/)

