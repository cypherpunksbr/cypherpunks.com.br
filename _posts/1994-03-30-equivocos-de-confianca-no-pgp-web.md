---
title:  "Equívocos de confiança no PGP Web"
date:   30-03-1994 -0300
categories:
  - Biblioteca
tags:
  - Hal Finney
---

### Hal Finney


#### 30 de Março de 1994


Um dos principais conceitos amplamente usados ​​para descrever o PGP é a "rede de confiança". Isso traz à mente uma rede de conexões entre pessoas que conhecem e se comunicam umas com as outras. Duas pessoas que querem se comunicar podem fazê-lo com segurança se houver um caminho de conexões na forma de chaves assinadas que as unam.

Mas isso não está certo. O fato fundamental sobre as assinaturas de chaves do PGP, que muitas vezes é mal entendido, é o seguinte:

Você só pode se comunicar com segurança com alguém cuja chave é assinada por uma pessoa que você conhece, pessoalmente ou por reputação.

Em outras palavras, se eu quiser me comunicar com joe@abc.com, só posso fazê-lo se um dos signatários de sua chave for uma pessoa que conheço. Se não, não tenho como julgar a validade de sua chave.

Isso desmente interpretações simples da "teia da confiança". Eu posso ter assinado a chave de A, A assinou B, B assinou C, C assinou D e D assinou Joe, mas isso não tem valor a menos que eu saiba D. Só então posso confiar na chave de Joe.

Isso significa que, na imagem "web", só posso me comunicar com segurança com pessoas que estão no máximo dois saltos na rede de conexões. Eu posso me comunicar com as pessoas que conheço e posso me comunicar com as pessoas que elas conhecem, e é isso.

Isso é lamentável, porque o modelo da web simples se liga a alguma pesquisa famosa que sugere que quaisquer duas pessoas escolhidas aleatoriamente estão a apenas meia dúzia de passos de distância na rede de conexões quem-sabe-quem. (Este resultado de onde vem título do filme "Six Degrees of Separation"). Se você tivesse um sistema que realmente suportasse comunicações via tal modelo web, ele realmente teria a esperança de deixar duas pessoas se comunicarem que não tivessem um cadeia muito longa entre eles. Mas o PGP, com um comprimento máximo de cadeia de dois, não permitirá isso.

O que teria que ser adicionado para permitir que um verdadeiro modelo de web de confiança fosse usado em um programa como o PGP? Basicamente, o que é necessário é uma maneira de julgar a confiabilidade das assinaturas de pessoas que você não conhece. Isso seria mais plausivelmente fornecido pelas pessoas que assinaram as chaves. Por exemplo, se houvesse outro tipo de assinatura de chave que não apenas atestasse a identidade da pessoa, mas também sua confiabilidade e cuidado ao assinar chaves, uma cadeia de assinaturas poderia servir de base para uma verdadeira teia de confiança. Obviamente, tais assinaturas não poderiam ser distribuídas com a mesma facilidade com que temos agora, onde uma olhada na carteira de motorista de um estranho é sempre o que recebemos, mas elas podem ser dadas a amigos próximos e àqueles que conhecemos e confiamos.

Sistemas mais elaborados podem incluir classificações numéricas de confiabilidade que ajudariam a estimar a força de qualquer caminho dado. O ponto principal é que algumas informações desse tipo seriam necessárias para permitir a comunicação com pessoas distantes na rede de conexões.

Sem isso, acho que continuaremos a ter problemas com o PGP não sendo possível validar chaves de pessoas com as quais queremos nos comunicar. As pessoas coletarão enormes listas de assinaturas, na esperança de que quem quiser se comunicar com elas conheça uma dessas pessoas. Os validadores de chave centralizada aparecerão (como no caso do serviço SLED que está sendo iniciado agora, que assinará uma chave com base em uma verificação assinada com seu nome). O resultado pode ser uma escolha entre usar uma chave não assinada ou usar uma assinada por alguma burocracia sem rosto, o que não é melhor do que a concepção original do PEM.

(As pessoas podem ficar confusas com este ensaio porque achavam que o PGP já funcionava dessa maneira. O PGP tem um modelo de acompanhamento, mas isso é apenas para acompanhar assinaturas. No exemplo acima, onde eu queria falar com Joe e lá foi uma cadeia para ele através de A, B, C e D, temos que primeiro supor que eu conheço e confio em todos os A, B, C e D. Dado que, o que o PGP pode fazer é determinar se eu tenho chaves para todas essas pessoas.Ele notará que A assinou a chave de B, por isso é válido.Eu sei B e disse PGP ele era confiável, e ele assinou a chave de C, portanto, que um é válido.Além disso, eu sei C e eu conheço D para que o PGP possa seguir a cadeia através deles.Finalmente chegamos a Joe, a quem eu não sei, mas como sei que D e PGP seguiram a web para determinar que a chave de D é válida, o PGP pode determinar que a chave de Joe É válido, mas, novamente, isso foi apenas porque eu conhecia D e todos os demais da cadeia.O ponto principal é que eu só posso me comunicar com pessoas que conheçam alguém que conheço. )

Hal Finney  
_hal@rain.org_

[Página de Hal Finney](https://web.archive.org/web/20140207101454/http://finney.org/~hal/)

