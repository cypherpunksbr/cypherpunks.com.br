---
title:  "A ideia de Contratos Inteligentes"
date:   01-01-1997 -0300
categories:
  - Biblioteca
tags:
  - Nick Szabo
---
### Nick Szabo  




Qual o significado e o propósito de “segurança”? Como ela se relaciona com os relacionamentos que temos? Eu argumento que a formalização de nossos relacionamentos—especialmente contratos—fornece o modelo para a segurança ideal.

Muitos tipos de cláusulas contratuais (tais como garantia, colaboração, delineação de direitos de propriedade, etc.) podem ser embutidas no hardware e software que convivemos, de uma forma a tornar a quebra de contrato cara (e se desejado, as vezes de forma proibitiva) para o infrator. Um exemplo regular da vida real, que podemos considerar como o ancestral primitivo de contratos inteligentes, é a máquina de venda automática. Dentro de uma quantidade limitada de perda potencial (a quantidade na caixa deve ser menor que o custo de violar o mecanismo), a máquina recebe moedas, e através de um mecanismo simples, o qual se utiliza de problema calouro de ciência da computação em um design mecênico limitado, dispensar mudanças e fornecer o produto de acordo com o preço exibido. A máquina de venda automática é um contrato com o portador: qualquer um com moedas pode participar de uma troca com o fornecedor. O cofre e outros mecanismos de segurança protegem as moedas armazenadas e os produtos de infratores, suficientemente para permitir a implantação lucrativa de máquinas de venda automática em uma ampla variedade de áreas.

Contratos inteligentes vão além da máquinas de venda, propõe a incorporação de contratos em todas as formas de propriedades valiosas e controladas por meios digitais.

Como outro exemplo, considere a hipótese de um sistema de segurança de automóveis. A estratégia de design do contrato inteligente sugere que nós refinamos protocolos de segurança suscetivamente para englobar em propriedades os termos que se aplicam a ela. Esses protocolos iriam dar a chave criptográfica para controlar a propriedade à pessoa que legitimamente é dona daquela propriedade, baseado nos termos do contrato. Em uma implementação direta, o carro seria inoperável a menos que o protocolo de resposta ao desafio correto seja concluído pelo seu legítimo proprietário, assim impedindo o roubo.

Se o carro está sendo usado como garantia, implementações de segurança de forma tradicional iriam dar dor de cabeça para o credor – o cobrador não teria como confiscar a dívida do produto. Para corrigir esse problema, podemos criar um simples protocolo inteligente de garantia: se o dono não paga, o contrato inteligente chama o protocolo de garantia, que da o controle da chave do carro ao banco. Esse protocolo deve ser mais barato e mais efetivo que um cobrador. A possível reificação do produto removeria a garantia quando o aluguel for quitado, além de justificar as dificuldades e exceções operacionais. Por exemplo, seria errado revogar a operação do carro enquanto o mesmo estiver numa estrada.

Nesse processo de refinamento constante, nós fomos de um sistema de segurança simples para um contrato refinado:

<pre>(1) Uma chave para seletivamente deixar o dono entrar e excluir terceiros;
(2) Uma porta dos fundos para permitir a entrada do credor;
(3a) Acesso ao credor liberado apenas com o não pagamento durante um certo período de tempo; e
(3b) Um pagamento eletrônico final fecha completamente a porta dos fundos. 
</pre>

Sistemas de segurança antigos terão comportamento diferente para contratos diferentes. Continuando com nosso exemplo, se o contrato do nosso automóvel for por locação, o pagamento final irá desligar o acesso a locação; em compras com crédito, iria desligar o acesso do credor. Um sistema de segurança, por ser constantemente redesenhado, alcança cada vez mais a lógica de um contrato que rege os direitos e obrigações de cada objeto, informação, ou cálculo a ser protegido. Termos contratuais qualitativamente diferentes, assim como diferenças tecnológicas entre propriedades, dão força a necessidade de protocolos diferentes.

(Derivado de ["Formalizando e protegendo relações em redes públicas"](/formalizing-securing-relationships/), por Nick Szabo) Um [artigo relacionado discute uma linguagem](/contract-language/) formal para analisar contratos e especificar contratos inteligentes.

* * *

Por favor, envie seus comentários para nszabo (at) law (dot) gwu (dot) edu Copyright © 1997 por Nick Szabo Permissão para redistribuir sem nenhuma alteração por este concedida. Fonte: [https://nakamotoinstitute.org/the-idea-of-smart-contracts/](https://nakamotoinstitute.org/the-idea-of-smart-contracts/)
