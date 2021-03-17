---
title:  "Bitcoin: Um sistema de dinheiro eletrônico peer-to-peer"
date:   31-10-2008 -0300
categories:
  - Biblioteca
tags:
  - Satoshi Nakamoto
---


Satoshi Nakamoto
31 de outubro de 2008

---

## Abstract

Uma versão puramente peer-to-peer do dinheiro eletrônico permitiria que pagamentos on-line fossem enviados diretamente de uma parte para outra sem passar por uma instituição financeira. Assinaturas digitais fornecem parte da solução, mas os principais benefícios são perdidos se um terceiro confiável ainda for necessário para evitar o gasto duplo. Propomos uma solução para o problema do gasto duplo usando uma rede peer-to-peer. A rede registra as transações de data e hora, transformando-as em uma cadeia contínua de prova de trabalho baseada em hash, formando um registro que não pode ser alterado sem refazer a prova de trabalho. A cadeia mais longa não serve apenas como prova da sequência de eventos testemunhada, mas prova de que ela veio do maior conjunto de poder da CPU. Enquanto a maioria da energia da CPU é controlada por nós que não estão cooperando para atacar a rede, eles Vai gerar os atacantes de cadeia e de saída mais longos. A rede em si requer estrutura mínima. As mensagens são transmitidas com base no melhor esforço, e os nós podem sair e se juntar à rede à vontade, aceitando a mais longa cadeia de prova de trabalho como prova do que aconteceu enquanto eles estavam fora.

## 1. Introdução

O comércio na Internet passou a depender quase exclusivamente de instituições financeiras que servem como terceiros confiáveis ​​para processar pagamentos eletrônicos. Enquanto o sistema funciona bem o suficiente para a maioria das transações, ele ainda sofre com as fraquezas inerentes do modelo baseado em confiança. Transações completamente não reversíveis não são realmente possíveis, uma vez que as instituições financeiras não podem evitar a mediação de disputas. O custo da mediação aumenta os custos de transação, limitando o tamanho mínimo prático da transação e eliminando a possibilidade de pequenas transações casuais, e há um custo mais amplo na perda da capacidade de efetuar pagamentos não reversíveis para serviços não reversíveis. Com a possibilidade de reversão, a necessidade de confiança se espalha. Os comerciantes devem ter cuidado com seus clientes, pedindo mais informações do que precisariam. Uma certa porcentagem de fraude é aceita como inevitável. Esses custos e incertezas de pagamento podem ser evitados pessoalmente usando moeda física, mas não existe nenhum mecanismo para efetuar pagamentos em um canal de comunicação sem uma parte confiável.

O que é necessário é um sistema de pagamento eletrônico baseado em prova criptográfica em vez de confiança, permitindo que duas partes interessadas negociem diretamente entre si sem a necessidade de um terceiro confiável. As transações que são computacionalmente impraticáveis ​​de reverter protegeriam os vendedores de fraude, e mecanismos de depósito de rotina poderiam ser facilmente implementados para proteger os compradores. Neste artigo, propomos uma solução para o problema do gasto duplo usando um servidor de timestamp distribuído peer-to-peer para gerar prova computacional da ordem cronológica das transações. O sistema é seguro desde que os nós honestos controlem coletivamente mais energia da CPU do que qualquer grupo colaborador de nós atacantes.

## 2. Transações

Nós definimos uma moeda eletrônica como uma cadeia de assinaturas digitais. Cada proprietário transfere a moeda para a próxima assinando digitalmente um hash da transação anterior e a chave pública do próximo proprietário e adicionando-os ao final da moeda. Um beneficiário pode verificar as assinaturas para verificar a cadeia de propriedade.

![](https://nakamotoinstitute.org/static/img/bitcoin/transactions.svg)

O problema, é claro, é que o beneficiário não pode verificar se um dos donos não gastou duas vezes a moeda. Uma solução comum é introduzir uma autoridade central confiável, que verifica todas as transações para gastos duplicados. Após cada transação, a moeda deve ser devolvida à casa da moeda para emitir uma nova moeda, e somente as moedas emitidas diretamente da casa da moeda são confiáveis para não serem gastas duas vezes. O problema com esta solução é que o destino de todo o sistema monetário depende da empresa que opera a casa da moeda, com cada transação tendo que passar por eles, assim como um banco.

Precisamos de uma maneira de o beneficiário saber que os proprietários anteriores não assinaram nenhuma transação anterior. Para nossos propósitos, a primeira transação é a que conta, por isso não nos importamos com as tentativas posteriores de gastar duas vezes. A única maneira de confirmar a ausência de uma transação é estar ciente de todas as transações. No modelo baseado em hortelã, a casa da moeda estava ciente de todas as transações e decidiu qual delas chegava primeiro. Para conseguir isso sem uma parte confiável, as transações devem ser anunciadas publicamente [1] , e precisamos de um sistema para os participantes concordarem em um único histórico da ordem em que foram recebidos. O beneficiário precisa comprovar que, no momento de cada transação, a maioria dos nós concordou que foi a primeira recebida.

## 3. Servidor de registro de data/hora

A solução que propomos começa com um servidor de timestamp. Um servidor de timestamp trabalha pegando um hash de um bloco de itens a ser timestamped e publicando amplamente o hash, como em um jornal ou post Usenet<sup>[[2-5]](#fn2)</sup>. O timestamp prova que os dados devem ter existido no momento, obviamente, para entrar no hash. Cada timestamp inclui o timestamp anterior em seu hash, formando uma cadeia, com cada timestamp adicional reforçando os anteriores.

![](https://nakamotoinstitute.org/static/img/bitcoin/timestamp-server.svg)

## 4. Prova de trabalho

Para implementar um servidor de timestamp distribuído em uma base peer-to-peer, precisaremos usar um sistema de prova de trabalho semelhante ao Hashcash de Adam Back<sup>[[6]](#fn6)</sup> , ao invés de postagens de jornal ou Usenet. A prova de trabalho envolve a verificação de um valor que, quando com hash, como no SHA-256, o hash começa com um número de bits zero. O trabalho médio necessário é exponencial no número de bits zero requerido e pode ser verificado pela execução de um único hash.

Para nossa rede de registro de data e hora, implementamos a prova de trabalho incrementando um nonce no bloco até que seja encontrado um valor que forneça ao hash do bloco os bits zero necessários. Uma vez que o esforço da CPU tenha sido gasto para satisfazer a prova de trabalho, o bloco não pode ser alterado sem refazer o trabalho. Como os blocos posteriores são encadeados depois disso, o trabalho para mudar o bloco incluiria refazer todos os blocos depois dele.

![](https://nakamotoinstitute.org/static/img/bitcoin/proof-of-work.svg)

A prova de trabalho também resolve o problema de determinar a representação na tomada de decisão por maioria. Se a maioria fosse baseada em um endereço IP, um voto, ele poderia ser subvertido por qualquer pessoa capaz de alocar muitos IPs. Prova de trabalho é essencialmente um CPU-um-voto. A decisão da maioria é representada pela cadeia mais longa, que tem o maior esforço de prova de trabalho investido nela. Se a maioria da potência da CPU for controlada por nós honestos, a cadeia honesta crescerá mais rápido e ultrapassará as cadeias concorrentes. Para modificar um bloco anterior, um invasor teria que refazer a prova de trabalho do bloco e todos os blocos após ele e, em seguida, alcançar e superar o trabalho dos nós honestos. Nós mostraremos mais tarde que a probabilidade de um atacante mais lento se aproximar diminui exponencialmente à medida que os blocos subseqüentes são adicionados.

Para compensar o aumento da velocidade do hardware e o interesse variável em executar nós ao longo do tempo, a dificuldade de prova de trabalho é determinada por uma média móvel visando um número médio de blocos por hora. Se eles são gerados muito rápido, a dificuldade aumenta.

## 5. Rede

As etapas para executar a rede são as seguintes:

1.  Novas transações são transmitidas para todos os nós.
2.  Cada nó coleta novas transações em um bloco.
3.  Cada nó trabalha para encontrar uma prova de trabalho difícil para o seu bloco.
4.  Quando um nó encontra uma prova de trabalho, ele transmite o bloco para todos os nós.
5.  Os nós aceitam o bloco somente se todas as transações nele forem válidas e já não tiverem sido gastas.
6.  Os nós expressam sua aceitação do bloco trabalhando na criação do próximo bloco da cadeia, usando o hash do bloco aceito como o hash anterior.

Os nós sempre consideram a cadeia mais longa a correta e continuarão trabalhando para estendê-la. Se dois nós transmitem versões diferentes do próximo bloco simultaneamente, alguns nós podem receber um ou outro primeiro. Nesse caso, eles trabalham no primeiro que receberam, mas salvam o outro ramo no caso dele se tornar mais longo. O empate será quebrado quando a próxima prova de trabalho for encontrada e uma ramificação ficar mais longa; os nós que estavam trabalhando na outra ramificação passarão para o mais longo.

Novas transmissões de transmissões não precisam necessariamente atingir todos os nós. Contanto que eles atinjam muitos nós, eles entrarão em um bloco em pouco tempo. As transmissões de bloco também são tolerantes a mensagens descartadas. Se um nó não receber um bloco, ele o solicitará quando receber o próximo bloco e perceber que perdeu um.

## 6. Incentivo

Por convenção, a primeira transação em um bloco é uma transação especial que inicia uma nova moeda pertencente ao criador do bloco. Isso adiciona um incentivo para que os nós suportem a rede e fornece uma maneira de distribuir moedas inicialmente em circulação, uma vez que não há autoridade central para emiti-las. A adição constante de uma constante de quantidade de novas moedas é análoga aos mineradores de ouro que gastam recursos para adicionar ouro à circulação. No nosso caso, é o tempo de CPU e a eletricidade que é gasta.

O incentivo também pode ser financiado com taxas de transação. Se o valor de saída de uma transação for menor que seu valor de entrada, a diferença será uma taxa de transação que é adicionada ao valor de incentivo do bloco que contém a transação. Uma vez que um número predeterminado de moedas tenha entrado em circulação, o incentivo pode transitar inteiramente para as taxas de transação e ser completamente livre de inflação.

O incentivo pode ajudar a encorajar os nós a permanecerem honestos. Se um atacante ganancioso é capaz de reunir mais poder de CPU do que todos os nós honestos, ele teria que escolher entre usá-lo para fraudar as pessoas, roubando seus pagamentos, ou usando-o para gerar novas moedas. Ele deveria achar mais lucrativo jogar de acordo com as regras, regras que o favorecem com mais moedas novas do que todos os demais, do que prejudicar o sistema e a validade de sua própria riqueza.

## 7. Recuperando espaço em disco

Depois que a transação mais recente em uma moeda é enterrada em blocos suficientes, as transações gastas antes dela podem ser descartadas para economizar espaço em disco. Para facilitar isso sem quebrar o hash do bloco, as transações são divididas em uma árvore Merkle <sup>[[7]](#fn7)</sup><sup>[[2]](#fn2)</sup><sup>[[5]](#fn5)</sup> , com apenas a raiz incluída no hash do bloco. Blocos antigos podem então ser compactados arrancando galhos da árvore. Os hashes interiores não precisam ser armazenados.

![](https://nakamotoinstitute.org/static/img/bitcoin/reclaiming-disk-space.svg)

Um cabeçalho de bloco sem transações seria de cerca de 80 bytes. Se supusermos que blocos são gerados a cada 10 minutos, 80 bytes * 6 * 24 * 365 = 4,2 MB por ano. Com os sistemas de computador vendendo normalmente com 2 GB de RAM a partir de 2008, e a Lei de Moore prevendo um crescimento atual de 1,2 GB por ano, o armazenamento não deve ser um problema, mesmo que os cabeçalhos dos blocos sejam mantidos na memória.

## 8. Verificação Simplificada de Pagamento

É possível verificar pagamentos sem executar um nó de rede completo. Um usuário só precisa manter uma cópia dos cabeçalhos de bloco da maior cadeia de prova de trabalho, o que ele pode fazer consultando os nós da rede até convencê-lo de ter a cadeia mais longa e obter a ramificação Merkle que vincula a transação ao bloco Ele não pode verificar a transação por si mesmo, mas ligando-a a um lugar na cadeia, ele pode ver que um nó de rede aceitou e bloqueou adicionado depois de confirmar que a rede aceitou a transação.

![](https://nakamotoinstitute.org/static/img/bitcoin/simplified-payment-verification.svg)

Como tal, a verificação é confiável desde que os nós honestos controlem a rede, mas seja mais vulnerável se a rede for dominada por um invasor. Embora os nós de rede possam verificar as transações por conta própria, o método simplificado pode ser enganado pelas transações fabricadas por um invasor enquanto o invasor puder continuar a dominar a rede. Uma estratégia para proteger contra isso seria aceitar alertas de nós de rede quando detectarem um bloco inválido, solicitando que o software do usuário baixe o bloco inteiro e alertou as transações para confirmar a inconsistência. As empresas que recebem pagamentos freqüentes provavelmente ainda precisarão executar seus próprios nós para obter uma segurança mais independente e uma verificação mais rápida.

## 9. Combinando e dividindo valor

Embora fosse possível lidar com moedas individualmente, seria difícil fazer uma transação separada para cada centavo em uma transferência. Para permitir que o valor seja dividido e combinado, as transações contêm várias entradas e saídas. Normalmente, haverá uma única entrada de uma transação anterior maior ou várias entradas combinando quantidades menores e no máximo duas saídas: uma para o pagamento e outra retornando a alteração, se houver, de volta ao remetente.

![](https://nakamotoinstitute.org/static/img/bitcoin/combining-splitting-value.svg)

Deve-se notar o espalhamento, onde uma transação depende de várias transações, e essas transações dependem de muito mais, não é um problema aqui. Nunca há a necessidade de extrair uma cópia autônoma completa do histórico de uma transação.

## 10. Privacidade

O modelo bancário tradicional atinge um nível de privacidade ao limitar o acesso à informação às partes envolvidas e ao terceiro de confiança. A necessidade de anunciar todas as transações exclui publicamente esse método, mas a privacidade ainda pode ser mantida quebrando o fluxo de informações em outro lugar: mantendo as chaves públicas anônimas. O público pode ver que alguém está enviando uma quantia para outra pessoa, mas sem informações vinculando a transação a ninguém. Isso é semelhante ao nível de informações divulgadas pelas bolsas de valores, onde o tempo e o tamanho dos negócios individuais, a "fita", são tornados públicos, mas sem dizer quem eram as partes.

![](https://nakamotoinstitute.org/static/img/bitcoin/privacy.svg)

Como um firewall adicional, um novo par de chaves deve ser usado para cada transação para impedir que elas sejam vinculadas a um proprietário comum. Algumas ligações ainda são inevitáveis ​​com transações com múltiplos inputs, que necessariamente revelam que suas entradas eram de propriedade do mesmo proprietário. O risco é que, se o proprietário de uma chave for revelado, a vinculação poderá revelar outras transações pertencentes ao mesmo proprietário.

## 11. Cálculos

Consideramos o cenário de um invasor tentando gerar uma cadeia alternativa mais rapidamente que a cadeia honesta. Mesmo que isso seja feito, ele não abre o sistema para mudanças arbitrárias, como a criação de valor a partir do nada ou a obtenção de dinheiro que nunca pertenceu ao invasor. Os nós não aceitarão uma transação inválida como pagamento e os nós honestos nunca aceitarão um bloco que os contenha. Um invasor só pode tentar alterar uma de suas transações para receber o dinheiro que gastou recentemente.

A corrida entre a cadeia honesta e uma cadeia atacante pode ser caracterizada como uma Caminhada Aleatória Binomial. O evento de sucesso é a cadeia honesta sendo estendida por um bloco, aumentando sua liderança em +1, e o evento de falha é a cadeia do atacante sendo estendida por um bloco, reduzindo o intervalo em -1.

A probabilidade de um atacante se recuperar de um dado déficit é análoga ao problema da Ruína do Jogador. Suponha que um jogador com crédito ilimitado comece com um déficit e jogue potencialmente um número infinito de tentativas para tentar alcançar o ponto de equilíbrio. Podemos calcular a probabilidade de ele chegar ao ponto de equilíbrio, ou de que um atacante alcança a cadeia honesta, como segue [8] :

$$
\begin{eqnarray*}
\large p &=& \text{probabilidade de um nó honesto encontrar o próximo bloco} \\
\large q &=& \text{probabilidade de um atacante encontrar o próximo bloco}\\
\large q_z &=& \text{probabilidade que o atacante irá recuperar $z$ blocos}
\end{eqnarray*}
$$

$$
\large q_z = \begin{Bmatrix}
1 & \textit{if}\; p \leq q\\
(q/p)^z & \textit{if}\; p > q
\end{Bmatrix}
$$

Considerando nossa suposição de que $p \gt q$, a probabilidade cai exponencialmente à medida que o número de bloqueios que o invasor tem para alcançar aumenta. Com as probabilidades contra ele, se ele não der um golpe de sorte para a frente logo no início, suas chances se tornam cada vez menores, já que ele fica ainda mais para trás.

Consideramos agora quanto tempo o destinatário de uma nova transação precisa esperar antes de ter certeza de que o remetente não pode alterar a transação. Assumimos que o remetente é um invasor que quer fazer com que o destinatário acredite que ele o pagou por um tempo, depois o substitui para pagar a si mesmo após algum tempo. O receptor será alertado quando isso acontecer, mas o remetente espera que seja tarde demais.

O receptor gera um novo par de chaves e fornece a chave pública ao remetente logo antes de assinar. Isso evita que o remetente prepare uma cadeia de blocos com antecedência, trabalhando nela continuamente até que tenha a sorte de chegar longe o suficiente e depois executar a transação naquele momento. Depois que a transação é enviada, o remetente desonesto começa a trabalhar em segredo em uma cadeia paralela contendo uma versão alternativa de sua transação.

O destinatário aguarda até que a transação seja adicionada a um bloco e $z$ blocos foram ligados depois. Ele não sabe a quantidade exata de progresso que o invasor fez, mas supondo que os blocos honestos tenham demorado o tempo médio esperado por bloco, o progresso potencial do atacante será uma distribuição de Poisson com o valor esperado:

$\large \lambda = z \frac qp$

Para obter a probabilidade que o atacante ainda pode alcançar agora, multiplicamos a densidade de Poisson para cada quantidade de progresso que ele poderia ter feito pela probabilidade que ele poderia alcançar a partir desse ponto:

$\large \sum_{k=0}^{\infty} \frac{\lambda^k e^{-\lambda}}{k!} \cdot \begin{Bmatrix} (q/p)^{(z-k)} & \textit{if}\;k\leq z\\ 1 & \textit{if} \; k > z \end{Bmatrix}$

Reorganizando para evitar somar a cauda infinita da distribuição ...

$\large 1 - \sum_{k=0}^{z} \frac{\lambda^k e^{-\lambda}}{k!} \left ( 1-(q/p)^{(z-k)} \right )$

Convertendo em código C...

```
#include double AttackerSuccessProbability(double q, int z)
{
	double p = 1.0 - q;
	double lambda = z * (q / p);
	double sum = 1.0;
	int i, k;
	for (k = 0; k <= z; k++)
	{
		double poisson = exp(-lambda);
		for (i = 1; i <= k; i++)
			poisson *= lambda / i;
		sum -= poisson * (1 - pow(q / p, z - k));
	}
	return sum;
}
```

Depois de alguns resultados, podemos ver a probabilidade cair exponencialmente com $z$.

```
q=0.1
z=0    P=1.0000000
z=1    P=0.2045873
z=2    P=0.0509779
z=3    P=0.0131722
z=4    P=0.0034552
z=5    P=0.0009137
z=6    P=0.0002428
z=7    P=0.0000647
z=8    P=0.0000173
z=9    P=0.0000046
z=10   P=0.0000012
```
```
q=0.3
z=0    P=1.0000000
z=5    P=0.1773523
z=10   P=0.0416605
z=15   P=0.0101008
z=20   P=0.0024804
z=25   P=0.0006132
z=30   P=0.0001522
z=35   P=0.0000379
z=40   P=0.0000095
z=45   P=0.0000024
z=50   P=0.0000006
```

Resolvendo para P menores que 0.1%...

```
P < 0.001
q=0.10   z=5
q=0.15   z=8
q=0.20   z=11
q=0.25   z=15
q=0.30   z=24
q=0.35   z=41
q=0.40   z=89
q=0.45   z=340
```

## 12. Conclusão

Propusemos um sistema para transações eletrônicas sem depender da confiança. Começamos com a estrutura usual de moedas feitas a partir de assinaturas digitais, que fornece um forte controle de propriedade, mas é incompleta sem uma maneira de evitar o gasto duplo. Para resolver isso, propusemos uma rede peer-to-peer usando prova de trabalho para registrar um histórico público de transações que rapidamente se torna impraticável para um invasor mudar se os nós honestos controlarem a maior parte da energia da CPU. A rede é robusta em sua simplicidade não estruturada. Os nós trabalham todos de uma vez com pouca coordenação. Eles não precisam ser identificados, pois as mensagens não são roteadas para nenhum lugar específico e precisam ser entregues apenas com base no melhor esforço. Os nós podem sair e se juntar à rede à vontade, aceitando a cadeia de prova de trabalho como prova do que aconteceu enquanto estiveram fora. Eles votam com seu poder de CPU, expressando sua aceitação de blocos válidos trabalhando em estendê-los e rejeitando blocos inválidos, recusando-se a trabalhar neles. Quaisquer regras e incentivos necessários podem ser aplicados com este mecanismo de consenso.

## Referências

1.  W. Dai, ["b-money,"](http://nakamotoinstitute.org/b-money/) [http://www.weidai.com/bmoney.txt](http://www.weidai.com/bmoney.txt), 1998. [↩](#ref1 "Jump back to [1]")

2.  H. Massias, X.S. Avila, and J.-J. Quisquater, ["Design of a secure timestamping service with minimal trust requirements,"](http://nakamotoinstitute.org/secure-timestamping-service.pdf) In _20th Symposium on Information Theory in the Benelux_, May 1999. [↩](#ref2 "Jump back to [2-5]") [↩](#ref2-2 "Jump back to [2]")

3.  S. Haber, W.S. Stornetta, ["How to time-stamp a digital document,"](http://nakamotoinstitute.org/time-stamp-digital-document.pdf) In _Journal of Cryptology_, vol 3, no 2, pages 99-111, 1991. [↩](#ref2 "Jump back to [2-5]")

4.  D. Bayer, S. Haber, W.S. Stornetta, ["Improving the efficiency and reliability of digital time-stamping,"](http://nakamotoinstitute.org/improving-time-stamping.pdf) In _Sequences II: Methods in Communication, Security and Computer Science_, pages 329-334, 1993. [↩](#ref2 "Jump back to [2-5]")

5.  S. Haber, W.S. Stornetta, ["Secure names for bit-strings,"](http://nakamotoinstitute.org/secure-names-bit-strings.pdf) In _Proceedings of the 4th ACM Conference on Computer and Communications Security_, pages 28-35, April 1997. [↩](#ref2 "Jump back to [2-5]") [↩](#ref5 "Jump back to [5]")

6.  A. Back, ["Hashcash - a denial of service counter-measure,"](http://nakamotoinstitute.org/hashcash.pdf) [http://www.hashcash.org/papers/hashcash.pdf](http://www.hashcash.org/papers/hashcash.pdf), 2002. [↩](#ref6 "Jump back to [6]")

7.  R.C. Merkle, ["Protocols for public key cryptosystems,"](http://nakamotoinstitute.org/public-key-cryptosystems.pdf) In _Proc. 1980 Symposium on Security and Privacy_, IEEE Computer Society, pages 122-133, April 1980. [↩](#ref7 "Jump back to [7]")

8.  W. Feller, ["An introduction to probability theory and its applications,"](http://nakamotoinstitute.org/introduction-probability-theory-vol-i.pdf) 1957. [↩](#ref8 "Jump back to [8]")
