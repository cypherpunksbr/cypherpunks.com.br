---
title:  "Glossário de Contratos inteligentes"
date:   01-01-1995 -0300
categories:
  - Biblioteca
tags:
  - Nick Szabo
---

# **Glossário de Contratos inteligentes**

**Nick Szabo**

**Originalmente publicado em 1995**

_Agente_: Uma pessoa ou organização, geralmente representada por um nome verdadeiro ou nym(nick). Além disso, um programa de computador executado por, ou agindo em nome de, um agente. De maneira mais genérica, é uma combinação de um nym com um padrão de comportamento persistente, sobre a qual pode-se identificar uma reputação. Note-se que isso difere das definições legais e comerciais de &quot;agente&quot;, mas corresponde mais precisamente ao emprego econômico e informático do termo.

_Contrato_: Um conjunto de acordos ou promessas entre agentes.

_Partes (também conhecidos por contratantes):_ Agentes que tenhamconcordado com a questão contratual.

_Terceiros_: Agentes que não tenham concordado com o contrato em questão.

_Execução_: Realização das promessas especificadas no contrato.

_Segurança Contratual_: Um paradigma para fazer acordos de segurança entre organizações, baseada em duas alegações: (1) o objetivo principal da segurança entre organizações é proteger e fazer cumprir a execução dos contratos, e (2) quando este objetivo é alcançado, a dependência da reputação, execução externa e outros fatores para a execução segura dos contratos dessa organização é minimizada.

_Distribuição de Chaves Contratuais_: Um modelo para distribuição de chaves entre indivíduos e organizações, no qual a distribuição de chaves e a estrutura de certificados refletem as disposições contratuais entre as partes.

_Protocolo_: Uma sequência de mensagens entre múltiplos agentes.

_Contrato inteligente_: Um conjunto de promessas, incluindo protocolos nos quais as partes cumprem essas promessas. Os protocolos são geralmente implementados por meio de programas em uma rede de computadores ou em outros tipos de equipamentos eletrônicos digitais. Portanto, estes contratos são &quot;mais inteligentes&quot; do que os seus antecessores em papel. Não está implícito a utilização de inteligência artificial.

_Alice e Bob_: Nosso exemplo das partes de um contrato inteligente.

_Eve_: Nosso exemplo de bisbilhoteiro, cujo objetivo é descobrir informações valiosas sobre um contrato e a sua execução sem pertencer a este contrato.

_Mallet_: Nosso exemplo de agressor ativo. O seu objetivo pode ser roubar algo valioso envolvido na execução de um contrato inteligente ou negá-lo às partes do contrato. Pode ser um agente economicamente racional em busca de puro ganho pessoal, ou um invasor pretencioso, na pior das hipóteses, que inflige o maior dano possível a uma ou mais partes, independentemente da perda pessoal.

_Mediador_: Um terceiro envolvido em tempo real nos protocolos entre as partes de um contrato inteligente, a quem foi confiado partes do conteúdo e/ou execução desse contrato.

_Árbitro_: Um terceiro a quem confiou-se parte do conteúdo e parte do histórico da execução de um contrato, gozando da confiança das partes contratadas para resolução justa de litígios decorrentes desse contrato.

_Desagregação_: O princípio da distribuição da confiança. A separação das funções de mediação e arbitragem separa tarefas, espalha o risco, minimiza a vulnerabilidade e reduz a probabilidade de vínculo, mas muitas vezes à custa de uma maior complexidade.

_Inimigo (também conhecido como agressor):_ Um agente cujas preferências podem causar danos a outro agente; um terceiro que influencia a execução de um contrato em detrimento de uma ou ambas as partes.

_Objeto_: Aqui usado para se referir genericamente a qualquer tipo de dados digitais, que podem ser uma chave, uma credencial, um contrato, um programa ou uma grande variedade de outras coisas.

_Credencial_: Uma alegação que um agente faz sobre outro.

_Credencial positiva:_ Uma alegação feita sobre um agente, que este prefere revelar, tal como a diplomação em uma escola de prestígio.

_Credencial negativa_: Uma alegação feita sobre um agente, que este preferiria não revelar, como por exemplo uma má avaliação de crédito.

_Protocolo criptográfico_: Um protocolo que utiliza chaves e princípios matemáticos para atingir as finalidades dos contratos inteligentes.

_Privity(privacidade)_: O princípio pelo qual apenas as partes de um contrato, incluindo os seus árbitros designados, precisam conhecer, controlar e executar esse contrato. A privacidade como objetivo de um contrato inteligente é uma generalização do princípio legal de privity. Ela formaliza a tradição do &quot;não é da sua conta&quot;. Os ataques contra a privacidade são representados por Eve, o bisbilhoteiro, um observador passivo do conteúdo ou da execução, e pelo vândalo malicioso Mallet, que interfere ativamente na execução ou furta algum valor. A privacidade e confidencialidade, ou a proteção do valor da informação sobre um contrato, das suas partes e da sua execução, de Eve, são assim classificadas sob sigilo. A privacidade entra frequentemente em conflito com a observabilidade e a verificabilidade.

_Observabilidade_: A capacidade das partes num contrato para observar a execução do contrato pela outra parte ou para provar sua execução à outra parte. Além disso, é a capacidade para diferenciar entre violações intencionais do contrato e erros de boa-fé. Um objetivo importante da concepção de contrato inteligente que muitas vezes entra em conflito com a privacidade.

_Verificabilidade_: A capacidade de uma parte provar a um árbitro que um contrato foi executado ou violado, e de diferenciar entre violação intencional e erros de boa-fé. Um objetivo importante da concepção de contrato inteligente, que muitas vezes entra em conflito com a privacidade.

_Nome respeitável_: Um nym ou nome verdadeiro que tenha uma boa reputação, geralmente por ter muitas credenciais positivas, possuir boa classificação de crédito ou ser altamente respeitado de alguma outra forma. As empresas se esforçam para manter marcas respeitáveis, enquanto profissionais como médicos e advogados se esforçam para ter muitas recomendações pessoais positivas. Boas reputações podem ser difíceis de transferir entre agentes, uma vez que a reputação presume uma persistência de comportamento, mas tal transferência pode às vezes ocorrer (por exemplo, a negociação de marcas entre empresas).

Nome verdadeiro: Um identificador que associa muitos tipos de informações distintas sobre um agente, como um nome de nascimento completo ou número da previdência social. Tal como na mágica, conhecer o nome verdadeiro de alguém pode conferir tremendo poder aos seus inimigos. Também pode ter enorme valor econômico entre aqueles que cooperam pacificamente, como no uso do marketing direto para direcionar as informações de um produto para os agentes mais interessados nesses produtos.

_Mix_: Um protocolo criptográfico para mensagens no qual a análise de quem está falando com quem (análise de tráfego) por Eve é impedida pela criptografia da mensagem do remetente com chaves públicas de cada operação de mistura na cadeia, além da mistura de mensagens por cada operador, fazendo a espionagem panóptica de Eve perder o rastro das mensagens. Apenas 1 em cada &#39;N&#39; operadores precisa conhecer as informações de tráfego. Embora às vezes Eve possa coletar estatísticas sobre muitas mensagens para eventualmente adivinhar quem está se comunicando com quem.

As partes comunicantes também podem ser mutuamente anônimas, e com a criptografia normal não precisam confiar o conteúdo das mensagens a outras partes. O envio de mensagens confidenciais é necessário para que algumas das características de privacidade das credenciais chaumianas e valores portadores sejam fortemente implementadas em uma rede real. Outro sistema de mensagens confidenciais é a rede &quot;Dining Cryptographers&quot;, também inventada por Chaum.

_Nym(nick)_: Um identificador que associa apenas uma pequena quantidade de informações relacionada a um indivíduo, geralmente informações que o titular do nym considera relevantes para uma determinada organização ou comunidade. Exemplos de nyms incluem apelidos de quadros de avisos eletrônicos, nomes de canetas, pseudônimos e nomes de marcas. Um nym pode ganhar reputação dentro da sua comunidade. Por exemplo, um conglomerado pode vender uma grande variedade de marcas, cada uma respeitável em seu próprio nicho de mercado. Com as credenciais chaumianas, um nym pode tirar proveito das credenciais positivas dos outros nyms do titular, como comprovadamente ligado pela credencial &quot;é-uma-pessoa.&quot;

_Espaço para nomes_: Um conjunto de identificadores curtos com uma sintaxe simples, tais como números de telefone, endereços de internet legíveis por computador, nomes de domínio de internet legíveis por humanos, etc.

_Credenciais chaumianas_: Um protocolo criptográfico para comprovar posse de reivindicações feitas sobre si mesmo por outros nyms, sem revelar as relações entre esses nyms.

_Credencial é-uma-pessoa_: Nas credenciais chaumianas, a credencial de nome verdadeiro é usada para comprovar a relação entre nyms que de outra forma não poderiam ser relacionados, além de impedir a transferência de nyms entre agentes.

_Chave_: Um centro de escuridão e controle; um número aleatório extraído de um espaço de nome tão grande que um palpite baseado na sorte é altamente improvável. A metade da chave pública de um par de chaves assimétricas também pode agir como um nym.

_Biometria_: Padrão de informação utilizado para identificar um determinado corpo, como uma impressão digital, autógrafo, varredura de retina, senha etc.

_Autenticação_: Prova de que você está se comunicando com um agente que possui uma determinada chave.

_Criptografia de chave secreta (simétrica):_ Utiliza uma chave partilhada entre agentes para se comunicar com confidencialidade e autenticação.

_Criptografia de chave pública (assimétrica):_ Utiliza duas chaves, a chave privada e a chave pública. A chave pública é utilizada para criptografar objetos e verificar assinaturas digitais. A chave privada é usada para decodificar e assinar objetos, sendo geralmente mantida em segredo por um ou mais portadores das chaves. Permite a distribuição da chave sem expor a chave.

_Compartilhamento secreto_: Método para dividir uma chave (e assim qualquer objeto criptografado com essa chave) em &#39;N&#39; partes, das quais apenas &#39;M&#39; são necessárias para recriar a chave, mas menos que &#39;M&#39; das partes não fornece quaisquer informações sobre a chave. Uma ferramenta poderosa para distribuir o controle sobre os objetos entre os agentes.

_Assinatura digital_: Protocolo criptográfico baseado em criptografia de chave pública que prova que um objeto estava em contato ativo com a chave privada correspondente a assinatura: o objeto foi ativamente &quot;assinado&quot; com essa chave. Provavelmente deveria ter sido chamado de &quot;estampa digital&quot; ou &quot;selo digital&quot;, já que sua função é mais semelhante a esses métodos do que um autógrafo.

_Um pouco de compromisso:_ Uma variante das assinaturas digitais, usada para comprometer um objeto, como uma promessa ou previsão, sem revelar esse objeto até um momento futuro. É impossível violar o protocolo sem querer ou modificar o objeto após ele ter sido comprometido.

_Assinatura ofuscada:_ Protocolos de assinatura digital e criptografia de chave secreta que juntos têm a propriedade matemática da comutabilidade, de modo que possam ser extraídos na ordem inversa de sua aplicação. O efeito prático é que Bob &quot;assina&quot; um objeto, para que possa verificá-lo de forma geral, mas não consegue visualizar seu conteúdo específico. Normalmente a chave da assinatura define o significado do objeto assinado, ao invés do conteúdo do objeto assinado, para que Bob não acabe assinando um cheque em branco. Usado em instrumentos digitais de portador, onde Bob é o agente compensador, e nas credenciais chaumianas, onde Bob é o emissor das credenciais.

_Instrumentos digitais ao portador_: Objetos identificados por uma chave única e emitidos, compensados e resgatados por um agente de processamento. Quando um objeto é transferido, o destinatário da transferência pode solicitar ao agente de processamento que verifique se a chave nunca foi apagada antes, emitindo, assim, uma nova chave. O agente de processamento impede o processamento múltiplo de objetos individuais, mas pode ser impedido de relacionar determinados objetos a um ou aos dois nyms de processamento que transferiram esse objeto. Esses instrumentos apresentam-se numa variedade &quot;on-line&quot;, processada durante cada transferência e, portanto, tanto verificável como observável, e numa variedade &quot;offline&quot;, que pode ser transferida sem ser processada, mas só verificável quando finalmente processada, ao revelar qualquer nym de processamento de qualquer titular intermediário que transferiu o objeto múltiplas vezes (uma quebra de contrato). A privacidade do agente de processamento pode tomar a forma de &#39;transferido-desvinculabilidade&#39;, &#39;transferidor- desvinculabilidade&#39;, ou &#39;duplamente-ofuscada&#39;, onde tanto o transferidor quanto o transferido são desvinculáveis pelo agente de processamento. O dinheiro digital é uma forma popular de instrumento digital ao portador.

_Localidade:_

·         Imediatismo, tal como oferecido pelo processamento online de instrumentos digitais ao portador

·         Negocia com os agentes que melhor se conhecem.

·         Negocia na sua área de especialização.

_Backup imediato:_ Um serviço de backup que fica online em caso de falha do serviço principal. Normalmente acionado por um interruptor automático.

_Teste interativo de conhecimento zero (ZKIP):_ Um protocolo criptográfico que pode ser utilizado para provar que um agente possui uma chave (e por implicação menor, que os agentes que normalmente funcionam de uma outra maneira e que têm um incentivo para responder adequadamente ao desafio, mas não conseguem fazê-lo, não possuem a chave), sem revelar qualquer informação sobre essa chave. Atualmente utilizado para autenticação e em armas inteligentes para identificação de amigos ou inimigos (IFF).

_Propriedade inteligente_: Software ou dispositivos físicos trazendo as características desejadas de propriedade embutidas; por exemplo, dispositivos de valor muito menor que podem ser entregues aos agentes que não possuem uma chave, como demonstrado por um teste interativo de conhecimento zero. Os métodos de implementação de propriedade inteligente podem incluir OND (cf.), e dispositivos imobilizantes ou destrutivos registrados para frustrar as tentativas de burlar a propriedade.

_Dados Necessários Para a Operação (OND):_ Dados necessários para o funcionamento da propriedade inteligente. Por exemplo, uma sequência de disparo complexa e proprietária necessária para operar um motor computadorizado, um arquivo CAD necessário para fabricar uma peça especializada etc. Para evitar roubo de serviço, o ZKIP deve abrir um canal criptografado para o dispositivo. Para evitar vazamento do OND para Eve, a detecção de violação combinada com um interruptor automático pode ser usada na extremidade do dispositivo do canal.

_Smart__Lien_: Compartilha o controle de propriedade inteligente entre as partes, geralmente duas partes chamadas de proprietário e titular do direito. Esta propriedade pode estar na posse imediata do proprietário ou do titular do direito, correspondendo às noções de direito comum de &quot;titularidade do inquilino&quot; e &quot; titularidade do hospedeiro&quot; respectivamente. Pode ser usado para assegurar linhas de crédito, apólices de seguro e muitos outros tipos de contratos que envolvam propriedade inteligente.

_Segurança:_ Representa um bem básico, tal como uma parte da propriedade (ações) ou uma dívida (obrigações, dinheiro).

_Contrato contingente:_ Contém termos que dependem da escolha de uma das partes ou de um estado do mundo. Uma opção é um exemplo de um contrato contingente.

_Derivado:_ Uma opção de call ou put, um ativo futuro ou sintético; tal contrato é &quot;derivado&quot; de um bem subjacente básico.

_Ativo sintético_: Um derivativo construído ou &quot;sintetizado&quot; pela combinação de bens e outros derivativos. Os fluxos de caixa para sintéticos sofisticados podem ser calculados com alta precisão por árvores de decisão altamente complexas.

Fluxo de caixa: A sequência esperada de pagamentos de acordo com os termos de um contrato. Por meio do fluxo de caixa podem ser calculados as metas financeiras básicas de um contrato, como o valor líquido atual.

* * *

Por favor envie seus comentários para nszabo (at) law (dot) gwu (dot) edu

Copyright © 1995 por Nick Szabo

Permissão para redistribuir sem alterações aqui concedida
