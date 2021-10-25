---
title:  "b-money"
date:   01-11-1998 -0300
categories:
  - Biblioteca
tags:
  - Wei Dai
---

  
### Wei Dai  
1 de Novembro de 1998


Eu estou fascinado pelo [manifesto criptoanarquista](https://cypherpunks.com.br/o-manifesto-criptoanarquista/) de Tim May. Ao contrário das comunidades tradicionalmente associadas com a palavra "anarquia", na criptoanarquia o governo não é temporariamente destruído, mas permanentemente proibido e permanentemente desnecessário. É uma comunidade onde a ameaça de violência é impotente porque a violência é impossível, e a violência é impossível porque os participantes não podem ser ligados a seus nomes reais ou localizações físicas.

Até agora não está claro, mesmo que teoricamente, como uma comunidade destas poderia funcionar. Uma comunidade é definida pela cooperação de seus participantes, e cooperação eficiente requer um meio de troca (dinheiro) e uma maneira de cumprir contratos. Tradicionalmente estes serviços são providos pelo governo ou instituições patrocinadas pelo governo, e somente para entidades legais. Neste artigo eu descrevo um protocolo pelo qual estes serviços podem ser disponibilizados por entidades irrastreáveis.

Na verdade, eu irei descrever dois protocolos. O primeiro não é prático, porque faz uso pesado de um canal de broadcast(transmissão) síncrono e impossível de ser bloqueado/saturado. Porém, ele dará motivo ao segundo protocolo, que é mais prático. Em ambos os casos eu irei presumir a existência de uma rede irrastreável, onde emissores e receptores são identificados somente por pseudônimos digitais (i.e. chaves públicas) e cada mensagem é assinada pelo emissor e encriptada para seu receptor.

No primeiro protocolo, cada participante mantém um banco de dados (separado) de quanto dinheiro pertence a cada pseudônimo. Estas contas coletivamente definem a posse do dinheiro, e como essas contas são atualizadas é o assunto deste protocolo.

**1\. A criação de dinheiro.**

Qualquer pessoa pode criar dinheiro ao fazer o broadcast(transmissão) da solução para um problema computacional que anteriormente não era resolvido. As únicas condições são que deve ser fácil determinar quanto esforço computacional que levou para resolver o problema e a solução deve não ter outro valor, prático ou intelectual. O número de unidades monetárias criadas é igual ao custo do esforço computacional, em relação a uma cesta básica de commodities.Por exemplo, se um problema leva 100 horas para ser resolvido no computador que o resolve de maneira mais econômica, e o custo para comprar 100 horas de poder computacional nesse computador é de 3 cestas básicas no mercado aberto, então quando a solução for transmitida para a rede, todo mundo credita o emissor da solução (broadcaster) em 3 unidades monetárias.

**2\. A transferência de dinheiro**

Se Alice (dona do pseudônimo **K<sub>A</sub>**) quer transferir X unidades de dinheiro para Bob (dono do pseudônimo **K<sub>B</sub>**), ela transmite (broadcast) a mensagem "Eu dou X unidades de dinheiro para **K<sub>B</sub>**",assinada por **K<sub>A</sub>**. Quando esta mensagem for emitida para rede, todo mundo debita da conta de **K<sub>A</sub>** em X unidades e credita para a conta de **K<sub>B</sub>** a quantia de X unidades, a não ser que isso fosse criar um saldo negativo na conta de **K<sub>A</sub>**. Neste caso, a mensagem é ignorada.

**3\. A efetivação de contratos**

Um contrato válido deve obrigatoriamente incluir uma reparação máxima no caso de falha por qualquer participante do mesmo. Ele deve também incluir uma parte que irá fazer a arbitragem caso haja um conflito. Todas as partes do contrato, incluindo o arbitrador devem transmitir para a rede suas assinaturas para que o contrato se torne efetivo. Quando ocorrer a transmissão do contrato e de todas assinaturas, cada participante do contrato debita (subtrai) de sua conta a quantia relativa ao valor máximo de reparação e credita a soma máxima destes valores a uma conta especial identificada por um hash seguro do contrato. O contrato se torna efetivo se o débito de cada parte ocorrer com sucesso sem produzir um saldo negativo, caso contrário o contrato é ignorado e as contas são retornadas a seu estado anterior. Um exemplo de contrato poderia ser assim:

**K_A** concorda em enviar a **K_B** a solução ao problema P antes de 00:00:00 01/01/2000\. **K_B** concorda em pagar a **K_A** 100 UM (unidades monetárias) antes de 00:00:00 01/01/2000\. **K_C** concorda em fazer a arbitragem no caso de conflitos. **K_A** concorda em pagar um valor máximo de 1000 UM em caso de quebra de contrato. **K_B** concorda em pagar um valor máximo de 200 UM em caso de quebra de contrato. **K_C** concorda em pagar um valor máximo de 500 UM em caso de quebra de contrato. **4\. A conclusão de contratos**

Se um contrato for concluído sem conflitos, cada parte transmite uma mensagem assinada "O contrato com o hash SHA-1 _H_ foi concluído sem reparações". Ou possivelmente "O contrato com o hash SHA-1 _H_ foi concluído com as seguintes reparações: ...". Ao ocorrer a transmissão de todas as assinaturas, cada participante credita a conta de cada parte pelo valor máximo de sua reparação, remove a conta do contrato, e credita ou debita a conta de cada parte de acordo com o calendário de reparação, caso exista um.

**5\. O cumprimento de contratos**

Se as partes de um contrato não conseguirem concordar em uma conclusão apropriada mesmo com ajuda de um arbitrador, cada parte transmite a rede uma sugestão de calendário de reparação/multa e quaisquer argumentos ou provas (evidências) em seu favor. Cada participante faz uma determinação sobre quais reparações ou multas, e modifica suas contas de acordo com isto.

No segundo protocolo, as contas com informações de quem tem quanto dinheiro são mantidas por um subconjunto de participantes (que serão chamados de servidores daqui pra frente) ao invés de todos. Estes servidores são ligados através de um canal de broadcast estilo Usenet. O formato das mensagens de transação transmitidas ao canal se mantém as mesmas do primeiro protocolo, mas os participantes afetados por cada transação devem verificar que a mensagem foi recebida e processada com sucesso por um conjunto aleatório selecionado de servidores.

Como servidores devem ser dados confiança até certo ponto, algum mecanismo é necessário para mantê-los honestos. Cada servidor é obrigado a depositar uma certa quantia de dinheiro em uma conta especial que será usada para possíveis multas ou recompensas por provas de conduta irregular. Também, cada servidor deve periodicamente publicar e se comprometer com suas bases de dados de criação de dinheiro e de propriedade monetária. Cada participante deve verificar se seu saldo está correto e que a soma do saldo da conta não é maior que a quantia total de dinheiro criada. Isso previne que os servidores, mesmo que estejam em total colisão/conflito, permanentemente expandam a base monetária. Novos servidores podem também usar os bancos de dados publicados para sincronizar com servidores existentes.

O protocolo proposto neste artigo permite que entidades irrastreáveis reconhecidas por pseudônimos cooperem entre si de maneira mais eficiente, ao fornecer a elas um meio de trocas e um método de efetivar contratos. O protocolo provavelmente pode ser feito mais eficiente e seguro, mas eu espero que este seja um passo no caminho de fazer a criptoanarquia uma possibilidade prática e teórica.

--------- **Apêndice A: criação alternativa de b-money**

Uma das partes problemáticas no protocolo b-money é a criação de dinheiro. Esta parte do protocolo requer que todos os proprietários de contas decidam e concordem com o custo de cálculos computacionais em particular. Infelizmente, já que a tecnologia de computação tende a avançar rapidamente e não sempre de maneira aberta ao público, esta informação pode estar indisponível, obsoleta ou não precisa, e tudo isto pode causar sérios problemas para o protocolo.

Então eu proponho um subprotocolo alternativo para criação de dinheiro, onde cada proprietário de conta (todos no primeiro protocolo, ou os servidores no segundo protocolo) decidem e concordam em relação a quantia de b-money a ser criada em cada período, com o custo de criar dinheiro sendo determinado por um leilão. Cada período de criação de dinheiro é dividido em quatro fases, a seguir:

**1\. Planejamento**

Os proprietários de contas computam e negociam entre si para determinar o aumento ideal da base monetária no próximo período. Independentemente de estes proprietários de contas chegarem ou não a um consenso, eles transmitem sua cota de criação de dinheiro e quaisquer cálculos macroeconômicos feitos para suportar seus resultados.

**2\. Lances**

Qualquer pessoa que quer criar b-money transmite um lance no formato de <x,y> onde x é a quantia de b-money ele quer criar, e y é um problema não resolvido de uma classe de problemas pré-determinados. Cada problema nesta classe deve ter um custo nominal (por exemplo em anos MIPS) a qual todos concordam publicamente.

**3\. Computação**

Após ver os lances, aqueles que deram lances na fase 2 agora podem resolver os problemas de seus lances e transmitir as soluções para a rede.

**4\. Criação de dinheiro**

Cada dono de conta aceita os lances mais altos (dentre os que realmente transmitiram suas soluções a rede) em relação ao custo nominal por unidade de b-money criado, e creditam as contas dos respectivos licitantes.

Fonte original: [https://nakamotoinstitute.org/b-money](https://nakamotoinstitute.org/b-money) [https://nakamotoinstitute.org/static/docs/b-money.txt](https://nakamotoinstitute.org/static/docs/b-money.txt)
