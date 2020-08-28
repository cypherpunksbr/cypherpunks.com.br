---
title:  "Bit Gold"
date:   29-12-2005 -0300
categories:
  - Biblioteca
tags:
  - Nick Szabo
---

  
### Nick Szabo  
29 de Dezembro de 2005


Há muito tempo, tive a ideia de usar ouro. O problema, em poucas palavras, é que nosso dinheiro atualmente depende [da confiança em um terceiro](http://nakamotoinstitute.org/literature/18/html/) pelo seu valor, como muitos episódios inflacionários e hiperinflacionários demonstrados durante o século XX. Da mesma forma, [a emissão de notas bancárias privadas](http://unenumerated.blogspot.com/2005/11/flying-money-brief-overview.html), embora tivesse várias vantagens e desvantagens, dependia igualmente de uma terceira parte confiável.

[Metais preciosos e colecionáveis](http://nakamotoinstitute.org/literature/22/html/) têm uma escassez inviável devido ao custo de sua criação. Isso, uma vez, proporcionou dinheiro cujo valor foi amplamente aceito, independente de qualquer terceiro confiável. Metais preciosos têm problemas, no entanto. É muito caro analisar metais repetidamente para transações comuns. Assim, um terceiro confiável (geralmente associado a um coletor de impostos que aceitou as moedas como pagamento) foi invocado para carimbar uma quantia padrão do metal em uma moeda. Transportar grandes valores de metal pode ser um assunto bastante inseguro, como os britânicos descobriram quando transportaram ouro através de um U-boat atravessou o Atlântico para o Canadá durante a Primeira Guerra Mundial para apoiar seu padrão-ouro. O que é pior, você não pode pagar online com metal.

Assim, seria muito bom se houvesse um protocolo em que bits inesgotáveis e onerosos pudessem ser criados online com dependência mínima de terceiros confiáveis e, então, armazenados, transferidos e analisados com confiança mínima semelhante. "Bit Gold".

Minha proposta para o Bit Gold baseia-se em calcular uma série de bits de uma sequência de bits de desafio, usando funções chamadas de "função de quebra-cabeça de cliente", "função de proof-of-work (prova de trabalho)" ou "[função de referência segura](http://szabo.best.vwh.net/intrapoly.html)". A sequência de bits resultante é a prova de trabalho (proof-of-work). Onde uma [função unidirecional](http://en.wikipedia.org/wiki/One_way_function) é uma função cujo cálculo é difícil de ser computado ao contrário, uma função de benchmark segura vem idealmente com um custo específico, medido em ciclos de computação, para computar de trás para frente.

Aqui estão os principais passos do sistema do Bit Gold que eu imagino:

1\. Uma sequência pública de bits, a "string de desafio", é criada (consulte a etapa 5). 2\. Alice em seu computador gera a prova de string de trabalho dos bits de desafio usando uma função de benchmark. 3\. A prova de trabalho é incluída com um [registro de tempo (timestamp) seguro](http://www.cs.ut.ee/~lipmaa/crypto/link/timestamping/). Isso deve funcionar de maneira distribuída, com vários serviços diferentes de registro de data e hora, para que nenhum serviço de registro de data e hora específico precise ser substancialmente confiável. 4\. Alice adiciona a string de desafio e a prova de data e hora da string de trabalho a um registro de título de propriedade distribuído para o "Bit Gold". Aqui, também, nenhum servidor único é substancialmente confiável para operar corretamente o registro. 5\. A última string criada de Bit Gold fornece os bits de desafio para a próxima string criada. 6\. Para verificar se Alice é a proprietária de uma cadeia específica de Bit Gold, Bob verifica a cadeia de títulos inutilizável no registro de títulos em Bit Gold 7\. Para avaliar o valor de uma string de Bit Gold, Bob checa e verifica os bits de desafio, a string de prova de trabalho e o registro de data e hora.

Note que o controle de Alice sobre seu Bit Gold não depende de sua posse exclusiva dos bits, mas sim de sua posição de líder na cadeia de título não falsificável (cadeia de assinaturas digitais) no registro de títulos.

Tudo isso pode ser automatizado por software. Os principais limites para a segurança do esquema são quão bem a confiança pode ser distribuída nas etapas (3) e (4), e o problema da arquitetura da máquina que será discutido abaixo.

Hal Finney implementou uma variante do Bit gold chamada RPOW (Reusable Proofs of Work). Isso depende da publicação do código de computador para o "mint", que é executado em um computador inviolável remoto. O comprador do Bit Gold pode então usar um atestado remoto, que Finney chama de técnica de servidor transparente, para verificar se um determinado número de ciclos foi realmente executado.

O principal problema de todos esses esquemas é que os esquemas de prova de trabalho dependem da arquitetura do computador, não apenas de uma matemática abstrata baseada em um "ciclo de computação" abstrato. ([Eu escrevi sobre isso obscuramente há vários anos.)](http://szabo.best.vwh.net/intrapoly.html) Assim, pode ser possível ser um produtor de custo muito baixo (por várias ordens de magnitude) e inundar o mercado com Bit Gold. No entanto, como o Bit Gold é _timestamped_ (tem um registro de tempo), o tempo criado e a dificuldade matemática do trabalho podem ser automaticamente comprovados. A partir disso, geralmente pode-se inferir qual foi o custo de produção durante esse período de tempo.

Ao contrário de átomos fungíveis de ouro, mas como acontece com itens de colecionador, uma grande oferta durante um determinado período de tempo reduzirá o valor desses itens específicos. A esse respeito, "Bit Gold" age mais como itens de colecionador do que como ouro. No entanto, a correspondência entre esse mercado exposto e o leilão que determina o valor inicial pode gerar um lucro muito substancial para o "minerador de bit gold", que inventa e implanta uma arquitetura de computador otimizada.

Assim, o Bit Gold não será fungível com base em uma função simples de, por exemplo, o comprimento da string. Em vez disso, para criar unidades fungíveis, os revendedores terão que combinar peças de Bit Gold de valor diferentes em unidades maiores de valor aproximadamente igual. Isso é análogo ao que muitos negociantes de commodities fazem hoje para tornar os mercados de commodities possíveis. A confiança ainda é distribuída porque os valores estimados de tais pacotes configuráveis ​​podem ser verificados independentemente por muitas outras partes de maneira ampla ou totalmente automatizada.

Em resumo, todo o dinheiro que a humanidade já usou foi inseguro de uma forma ou de outra. Essa insegurança se manifestou em uma ampla variedade de formas, desde a falsificação até o roubo, mas a mais perniciosa das quais provavelmente foi a inflação. O Bit Gold pode nos fornecer um dinheiro de segurança sem precedentes desses perigos. O potencial de sobrecargas de fornecimento inicialmente ocultas devido a inovações ocultas na arquitetura de máquinas é uma falha em potencial no Bit Gold, ou pelo menos uma imperfeição que os leilões iniciais e as exchanges de Bit Gold terão de resolver.

Fonte original: [https://nakamotoinstitute.org/bit-gold/](https://nakamotoinstitute.org/bit-gold/)
