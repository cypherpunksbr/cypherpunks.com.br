---
title:  "Contratos com Titular"
date:   01-01-1997 -0300
categories: 
  - Biblioteca
tags:
  - Nick Szabo
---


### Nick Szabo


Originalmente publicado em 1997


## Certificados de Titular

"Certificado digital de titular" é um termo amplamente desenvolvido por este autor<sup>[[1]](#fn1)</sup> incorporando pelo menos duas tecnologias emergentes: dinheiro digital e capacidades distribuídas (referências seguras de objetos distribuídos). Primeiro descreverei o protocolo chaumiano e seu recurso inovador de privacidade. Em seguida, discutirei como essas ideias são mapeadas para o mundo das capacidades na seção sobre direitos genéricos versus direitos específicos. Alterei a terminologia de dinheiro digital para certificado de titular ou token, de casa da moeda para emissor ou agente de transferência, e assim por diante, para refletir a capacidade dos protocolos de Chaum de generalizar. Os certificados de titular de Chaum implementam direitos padronizados transferíveis independentemente da identidade do titular. Cada tipo de contrato (por exemplo, cada denominação de "moeda" em dinheiro digital) corresponde a uma assinatura digital, assim como cada emissão de títulos da Reserva Federal ou certificados de ações corresponde a uma determinada conta.

No protocolo chaumiano mais direto, o emissor e o agente de transferência (a mesma entidade, para os nossos propósitos, embora possam ser facilmente separados) criam um número de série (na verdade, um grande número aleatório, ao invés de uma sequência), e o anexam a uma lista de certificados emitidos. O agente de transferência libera uma transferência (ou seja, resgata o certificado) verificando a assinatura para identificar a classe de contrato de titular e verificar se ela foi feita, em seguida, examinando a lista emitida desse contrato para garantir que o número de série esteja lá e então, remover o número de série. Alternativamente, o emissor pode deixar a emissão formar o número de série e, quando estiver removido, verificar a assinatura e colocar o número na lista de certificados removidos. A assinatura fornece a garantia de que o certificado é de fato o tipo específico de contrato com o titular, enquanto o número de série assegura que a mesma instância desse contrato não seja compensada ou resgatada mais de uma vez. Nessas versões simples, o agente de transferência pode vincular o cessionário ao receptor para todas as transferências. Para implementar as características de privacidade de moedas e certificados de titular físico, precisamos adicionar recursos de desvinculação.

## Assinaturas Ofuscadas ("Blind Signatures")

Conheça a maior equação simples desde e=mc<sub>2</sub>:

<pre>gSf(m) = S(m)</pre>

`S` é uma assinatura digital. `f` é a função de ofuscamento, e `g` uma função de desofuscamento. As funções de ofuscamento são geralmente baseadas em um número aleatório secreto chamado "fator de ofuscação". `m` é outro número aleatório, um identificador único que pode, por exemplo, referir-se a uma instância de algum objeto.

A ideia é muito inteligente, mas muito simples. Pode ser contra-intuitivo porque a mais simples metáfora do mundo físico deste e-commerce primitivo altamente útil parece um tanto quanto inútil: Alice pode fazer com que Carol assine um cheque em branco! Veja como:

1.  Alice gera `m` e o ofusca. O "ofuscar" é apenas uma criptografia one-time-pad para si mesmo, `f(m)`. Ela envia isso para Carol. É como pegar um pedaço de papel e selá-lo dentro de um envelope que Carol não pode abrir ou ver.
2.  Carol então assina: `Sf(m)`, e manda de volta para Alice. É como se Carol estivesse assinando o lado de fora do envelope.
3.  Alice desvenda: `gSf(m) = S(m)`. Carol também assinou o papel que Alice colocou dentro do envelope!

O gênio por trás dessa descoberta: o guru da criptografia, David Chaum. O brilhantismo está no passo 3: Chaum descobriu que algumas assinaturas têm a propriedade de serem "comutativas" com as funções de ofuscamento: Alice pode desofuscar na ordem inversa à qual a ofuscação e a assinatura foram aplicadas, deixando apenas a assinatura de n. É como se Alice colocasse um pedaço de papel carbono dentro do envelope!

Em particular para assinaturas RSA, com chave pública (pq, e) e chave privada d, as funções de assinatura ofuscada são o seguinte módulo pq:

<pre>S(x) = x<sup>d</sup>
g(x) = xk<sup>-1</sup>
f(x)= xk<sup>e</sup>
</pre>

Podemos verificar se a propriedade de assinatura ofuscada contém: `gSf(m) = (m(k<sup>e</sup>))<sup>d</sup> * k<sup>-1</sup> = m<sup>d</sup> * k * k<sup>-1</sup> = m<sup>d</sup>`, qual é a assinatura RSA válida da chave privada d em m.

## Transferências Desvinculadas

Se pode distinguir entre um contador ou um terceiro rastreando o nome verdadeiro de uma pessoa, por falta ou deficiência no mix de comunicações, ou com um terceiro vinculando duas entidades (pseudônimo usando mais de uma vez o mesmo endereço, números de contas ou nomes verdadeiros), como estando envolvido na mesma transação. Por desvinculadas aqui queremos dizer o último. A meta em que nomes verdadeiros são usados (isso ocorre, por exemplo, ao usar contas de nome verdadeiro ou não usar boas misturas de comunicação), é impedir a vinculação de terceiros de duas pessoas que fazem negócios entre si. Onde pseudônimo são usados, o objetivo é minimizar a liberação de informações de tráfego, evitar o acúmulo indesejado de padrões de comportamento únicos, que poderiam ser usados para vincular pseudônimo (incluindo seus nomes verdadeiros), ou poderiam aumentar outros meios de violação de privacidade. Ofuscamento ajuda especialmente quando os detentores de direitos desejam manter contas públicas ou de terceiros expressas em direitos genéricos. Nesse caso, um mix de comunicação nem em princípio nos dá o que o disfarce faz.

Além de proteger contra o agente de transferência, os protocolos de transferidor, transferência e duplo ofuscamento chaumiano protegem contra a conivência de uma parte com um agente de transferência para identificar parte da conta ou pseudônimo.

A desvinculação pode ser fornecida pela combinação de uma lista de certificados limpos com assinaturas ofuscadas e um delay na mistura. Exemplos suficientes de um contrato padronizado são emitidos durante um período de tempo para criar um mix. Entre a emissão e a liberação de um certificado, muitos outros certificados com a mesma assinatura serão apagados, tornando altamente improvável que uma compensação específica possa ser vinculada a uma determinada entrega por meio da assinatura. Existe uma troca entre o efeito de mistura e a exposição ao roubo de um "pacote" por um problema específico: quanto menor a entrega, menor a exposição, mas maior a conectividade; uma entrega maior tem maior exposição e maior confidencialidade.

As assinaturas ofuscadas podem ser usadas para tornar as transferências de certificado não vinculáveis através do número de série. A privacidade do agente de transferência pode tomar a forma de transferência, desvinculação, não-vinculação do transferidor ou "duplo disfarce", em que tanto o cedente quanto o cessionário não podem ser vinculados pelo agente de transferência ou colusão de um agente de transferência e contraparte.

Um mix de comunicação com uso único de endereços, mais a previsão de qualquer ganho de reputação de manter contas, em teoria também nos compra de desvinculação, mas um mix de comunicações é fraco e muito caro.

Os certificados de titular vêm em uma versão "on-line", limpa durante cada transferência e, portanto, verificável e observável, e uma versão "off-line", que pode ser transferida sem ser compensada, mas só é verificável quando finalmente liberada, revelando qualquer detentor intermediário que transferiu o objeto várias vezes (uma quebra de contrato).

Essa desvinculação é muitas vezes chamada de "anonimato", mas a questão de se as contas são emitidas para nomes reais ou pseudônimos e se o transferidor e o cessionário se identificam é ortogonal à não-vinculação pelo agente de transferência no modelo on-line. No modelo off-line, a identificação da conta (ou pelo menos um pseudônimo altamente confiável e/ou seguro) é necessária: passar um certificado off-line pela segunda vez revela essa identidade. Além disso, os canais de comunicação podem permitir que a transação anterior vincule o transferidor e o cessionário, a menos que eles tomem a precaução de usar um retransmissor anônimo. A compensação on-line faz da falta de identificação uma opção razoável para muitos tipos de transações, embora as situações comuns de crédito e garantia geralmente sejam beneficiadas ou até mesmo exijam identificação.

Ao confrontar uma tentativa de compensação de um número de série vazio, enfrentamos um dilema de erro ou fraude semelhante ao que encontramos acima na contabilidade de dupla entrada. O protocolo ecash™ do DigiCash atualmente aproveita propositalmente para se recuperar de uma falha de rede. Quando os certificados são perdidos pela rede, não é claro para o transmissor se eles foram recebidos ou compensados pelo cessionário ou não. A segunda transferência diretamente com o agente de transferência resolve a ambigüidade. Isso só funciona com o protocolo online. A questão de distinguir erro de fraude é urgente no protocolo off-line, mas ainda não há uma solução altamente satisfatória. Este problema é muitas vezes intratável devido à subjetividade da intenção.

Com a comunicação anônima bidirecional ideal entre as chaves de uso único e a compensação totalmente sem conta, a não-conectividade por meio de assinaturas ofuscadas se torna redundante. Este caso ideal ainda não foi abordado de perto com a tecnologia implementada e envolve necessariamente longos atrasos nas comunicações, que muitas vezes são intoleráveis. Misturas de comunicação realmente imperfeitas e tokens ofuscados menos caros se complementam.

## Objetos Conservados

A emissão e a transferência limpa de referências a um objeto distribuído conservam o uso desse objeto. Esse objeto se torna "escasso" em termos econômicos, assim como o uso de objetos físicos é finito. Objetos conservados fornecem a base para uma economia de software que mais se assemelha à economia de objetos físicos escassos. Objetos conservados podem ser usados para excluir seletivamente não apenas recursos físicos escassos (como tempo de CPU, largura de banda de rede e tempo de resposta, etc.), mas também frutos de trabalho intelectual – contanto que alguém esteja disposto a pagar o preço para interagir com essa informação pela rede em vez de localmente (cf. gerenciamento de direitos de conteúdo). A conservação imuniza objetos e os recursos que eles encapsulam para ataques de negação de serviço. Os protocolos de certificado de portador podem ser usados para transferir referências para uma instância específica ou conjunto de instâncias de um objeto, assim como podem ser usadas para transferir outros tipos de direitos padronizados.

Para implementar uma transação completa de pagamento por serviços, muitas vezes precisamos de mais do que apenas o protocolo de dinheiro digital; precisamos de um protocolo que garanta que o serviço será prestado se o pagamento for feito e vice-versa. Os sistemas comerciais atuais usam uma ampla variedade de técnicas para realizar isso, como correspondência certificada, troca cara a cara, confiança em histórico de crédito e agências de cobrança para conceder crédito, etc. Eu discuto tais questões em meu artigo sobre [Contratos Inteligentes](http://nakamotoinstitute.org/formalizing-securing-relationships.html).

#### Credenciais

Uma credencial é uma reivindicação feita por uma parte sobre outra. Uma credencial positiva é uma que a segunda parte prefere revelar, como um grau de uma escola de prestígio, enquanto essa parte prefere não revelar uma credencial negativa, como uma classificação de crédito ruim.

Uma credencial chaumiana é um protocolo criptográfico para provar que o pseudônimo de alguém (por exemplo, o número de identificação usado em um sistema de saúde) possui credenciais emitidas para outros pseudônimos, sem revelar ligações entre esses pseudônimos ou entre pseudônimo e nome verdadeiro. Baseia-se em torno da credencial de nome verdadeiro, usada para provar, sem revelar, a ligação entre pseudônimos e para evitar a transferência de pseudônimos entre as partes.

#### Direitos Genéricos vs. Direitos Específicos

Discutiremos o mapeamento entre os certificados chaumianos e os recursos distribuídos, conforme implementado, por exemplo em [E-Rights](http://www.erights.org/) onde introduzo uma terminologia diferente, parcialmente sobreposta: genérico vs. específico, exclusivo versus não exclusivo, agente de transferência x provedor, token versus hash.

Os direitos podem ser genéricos ou específicos. Os direitos genéricos correspondem a uma classe de objetos, direitos específicos a uma instância. Portanto, um direito específico é implementado com um hash, um grande número aleatório. Os números assinados correspondem aos direitos genéricos que chamarei de "tokens".

Os direitos também podem ser exclusivos ou não-exclusivos. Qualquer objeto que deve ser conservado ou finalmente alocado para um usuário específico é "exclusivo".

Exemplo simples: o direito a um bloqueio exclusivo em 1 MB de memória é genérico e exclusivo. O direito a um bloqueio exclusivo no espaço de endereço específico 100-101 é específico e exclusivo. O direito a cotação de duas dúzias de ações particulares às 12h22min de hoje é específico e não exclusivo.

A principal motivação para essas distinções são mecanismos diferentes de transferência indestrutível desses direitos, descritos a seguir.

Por simplicidade, os direitos genéricos são todos "de uso único": o ciclo de vida de um token consiste em emissão, seguido por uma série de transferências, seguidas de consumo. Ciclos de vida mais sofisticados, como transferência e consumo alternados, provavelmente são possíveis com algum protocolo extra.

Com um mix de comunicações perfeito, incluindo endereços de retorno obedecendo ao uso único e sem criação de reputação, não precisaríamos de tokens ofuscados. No entanto, os mixes de comunicações são caros e queremos a opção de ter certos registros públicos para construir reputações, mas fazer certas transferências de direitos em particular. Por esses motivos, devemos permitir que os clientes ofusquem transferências de token, além de fornecer um mix de comunicações.

Para transferência barata, não-vinculável e verificável de direitos genéricos exclusivos, usando tokens disfarçados, deve haver uma quantidade significativa de direitos genéricos intercambiáveis. Tais direitos combinados com direitos específicos não-excludentes também podem ser transferidos de maneira barata, uma vez que a compensação on-line não é necessária para o segundo. A transferência não vinculável e verificável de direitos específicos exclusivos parece exigir a compensação on-line através de um mix de comunicações caro.

Dois tipos de TTPs: um agente de transferência (AT) e um provedor. O AT funciona como um Banco Central do dinheiro digital mesmo sem possuir conta, limpando a transferência de tokens para direitos genéricos. O dinheiro digital é um caso especial: o dinheiro é o mais genérico dos direitos.

O Provedor é responsável por atualmente manter o objeto, que pode conter um estado exclusivo. O Provedor emite um hash, ou melhor, uma descrição assinada do direito específico e seu hash. Essa assinatura permite a verificação off-line do direito não excludente em que o Provedor é confiável. O AT emite um token para os direitos genéricos correspondentes.

Chaum também desenvolveu outros meios para lidar com um estado único<sup>[[2]](#fn2)</sup>.

Estou supondo que o AT e o Provedor tenham usado assinaturas confiáveis. A confiança ou reputação necessária para garantir a correção da transferência entre Provedor, AT e usuários é deixada em parte para análise posterior. Os dois principais objetivos aqui são garantir que os usuários possam verificar seus direitos (incluindo a exclusividade dos transferentes quando prometidos) e manter total privacidade dos ATs e Provedores. Algumas outras suposições de confiança provavelmente são feitas aqui e precisam ser explicadas e analisadas.

Para implementar transferências exclusivas, o AT mantém uma lista de números de tokens revogados (cancelados). O AT corresponde a um "Banco Central" no protocolo de dinheiro digital on-line chaumiano (veja acima). Uma classe de direitos genéricos corresponde a uma "designação" da moeda. O Provedor também pode manter uma lista de hashs pendentes ou usados, como um registrador E.

Aqui está outro exemplo de um direito genérico, ou classe de objetos fungíveis: "Um banco de dados SQL desejável com até 10 MB de armazenamento, e certas garantias de tempo de resposta padrão".

O AT vê apenas classes de objetos fungíveis. O Provedor e os usuários vêem instâncias particulares com estado exclusivo, por exemplo, um banco de dados preenchido com informações exclusivas.

O Provedor age de maneira análoga a uma "loja". É apenas outro cliente de tokens para o AT, que, como outros clientes, pode transferir ou receber tokens. Sua função especial é que ele é responsável pela emissão, onde informa ao TA sobre uma nova instância, obtém um novo token e o transfere para o cliente para quem o novo direito genérico está sendo emitido. O TA gera e destrói o fornecimento de token apenas a pedido do Provedor; caso contrário, todas as suas transferências conservam o fornecimento de um determinado direito genérico. O Provedor também é responsável pela entrega do serviço ao cliente que possui o(s) direito(s) prometido(s), momento em que o Provedor "deposita" o(s) token(s) genérico(s), instruindo o TA a diminuir o fornecimento do token. Na terminologia de dinheiro digital, o Provedor é a única entidade que tem que manter algo como uma conta bancária. Os detentores de direitos também podem manter uma conta, se quiserem usá-la para ajudar a construir reputação, ou podem simplesmente usar o TA para transferência de direitos conservados sem conta.

O Provedor emite junto com o token de direitos genéricos inicial um juramento assinado, máquina ou humanamente legível, descrevendo aspectos do objeto que podem ser não-exclusivos ou exclusivos, juntamente com o hash dessa instância e a chave pública do(s) direito(s) genérico(s) para os quais é(são) válido(s). Por exemplo, pode-se dizer "um banco de dados contendo cotações dessas duas dúzias de ações listadas às 12:22 de segunda-feira", sem conter as cotações. Muitas vezes, essa descrição vale mais quando agrupada com direitos exclusivos genéricos, como o direito a um tempo de resposta rápido. Os direitos específicos podem elaborar de maneira única os direitos genéricos, desde que essas elaborações não sejam tomadas para definir direitos exclusivos. Os direitos genéricos permitem que os ATs garantam exclusividade aos usuários e conservação de recursos aos Provedores, enquanto os direitos específicos descrevem o estado único para qualquer grau desejado de elaboração. O Provedor deve estar preparado para atender a qualquer promessa específica que tenha emitido, desde que seja acompanhado pelos tokens genéricos conservados adequados.

Esse método de composição de direitos específicos e genéricos, transferidos como um pacote, mas com átomos genéricos exclusivos liberados por diferentes ATs, permite que pacotes de direitos arbitrariamente sofisticados, referindo-se a objetos com estado arbitrariamente exclusivo, sejam transferidos de forma não vinculante. Uma grande variedade de derivados e combinações são possíveis. A única restrição é que a obtenção de direitos a recursos exclusivos específicos deve ser adiada para a fase de consumo ou transferida com compensação on-line por meio de mix de comunicações caras.

Se o Provedor desejasse garantir a exclusividade de um direito específico, a transferência parece exigir um mix de comunicações dispendiosas entre o Provedor e o cessionário, em vez de um token ofuscado barato. Por exemplo, "Deep Space Station 60 de 0500-0900 domingo" ou "um bloqueio no autoexec.bat agora" exige exclusividade para um direito específico e, portanto, parece exigir um mix de comunicações para transferir de forma não vinculativa. Por outro lado, "Um bloco de uma hora no DSS-60 em maio" e "o direito de travar o autoexec.bat em algum momento" são genéricos e podem ser transferidos de forma privada com o ofuscamento muito mais barato, dada uma população suficiente de outros tokens para essa classe de direito genérico transferido entre a emissão e o consumo de um determinado token.

Os clientes podem lidar com o AT sem um mix de comunicação. Eles lidam com o provedor por meio de um mix de comunicação. Se os titulares inicial e final não conseguissem fazer isso, o Provedor poderia vinculá-los. Se apenas o detentor final não o fizesse, o Provedor poderia identificá-lo como o usuário real do recurso. Assim, para a privacidade total, transferências genéricas são baratas, e transferências não-exclusivas são baratas, enquanto transferências exclusivas específicas e, na verdade, o uso do objeto parecem exigir o dispendioso mix de comunicações.

## Agradecimentos

Meus agradecimentos a David Chaum, a Mark Miller, a Bill Frantz, a Norm Hardy e a muitos outros por dedicarem tempo para me dar informações valiosas sobre essas questões.

## Referências

1.  As primeiras referências públicas a essa ideia podem ser encontradas [aqui](http://www.i-m.com/archives/9412/0179.html), [aqui](http://szabo.best.vwh.net/smart.contracts.html). Eu também me referi a essa ideia durante esse período em muitas comunicações pessoais, usando as frases "instrumento titular digital", "certificado titular digital", "objeto escasso" e "objeto conservado". A idéia de certificados de titular digital como uma proposta séria para o setor financeiro foi popularizada, com muitas idéias adicionais <span style="background-color: #ffd133; color: #301747">intruigentes</span>, por Bob Hettinga.

    As frases "certificado titular digital" e "povoado titular digital (DBS)" foram logo depois popularizadas por um correspondente meu, Robert Hettinga, como se referindo a uma ideia legal/institucional de assentamento instantâneo e irrevogável tornada possível tanto pela limpeza imediata quanto características de privacidade desta tecnologia. [↩](#ref1)

2.  David Chaum, [Online Cash Checks](http://www.digicash.com/news/archive/online.html) [↩](#ref2)
3.  ["Blind Signatures for Untraceable Payments,"](http://nakamotoinstitute.org/literature/blind-signatures/) D. Chaum, Advances in Cryptology Proceedings of Crypto 82, D. Chaum, R.L. Rivest, & A.T. Sherman (Eds.), Plenum, pp. 199-203.

4.  [The E distributed object language](http://www.erights.org/)

* * *

Por favor, envie seus comentários para nszabo (at) law (ponto) gwu (ponto) edu Copyright © 1997, 1999 por Nick Szabo Permissão para redistribuir sem alteração por este concedida. Fonte: [https://nakamotoinstitute.org/contracts-with-bearer/](https://nakamotoinstitute.org/contracts-with-bearer/)
