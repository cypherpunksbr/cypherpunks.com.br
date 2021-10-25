---
title:  "Auditoria Confidencial"
date:   01-01-1998 -0300
categories:
  - Biblioteca
tags:
 - Nick Szabo
---
### Nick Szabo  


Copyright © 1997-1999 por Nick Szabo  
Permissão para redistribuir ;sem alteração por este concedida


* * *


A função de auditoria é uma parte vasta e indispensável da economia moderna. Os controles de auditoria permitem, entre outras coisas, os empregadores delegarem recursos e autoridade aos funcionários, franqueadores delegarem aos franqueados, acionistas para delegarem à administração, anunciantes para contarem os globos oculares, os comerciantes para reunirem mais dados confiável sobre os clientes, e possibilitar uma ampla variedade de outros relacionamentos. Controles de auditoria podem ser chamados de protocolos de segurança do capitalismo..

Uma recente pesquisa geral mostrou que **83%** dos americanos são "muito preocupados" com a sua privacidade na Internet. Pode-se esperar números ainda mais fortes dos clientes europeus, que têm mais experiência em primeira mão com dados privados, em grande parte originalmente compilado por razões inócuas, sendo usados para repressão política. As empresas reconhecem as deficiências de NDAs (termos de confidencialidade) e estão procurando maneiras mais confiáveis de proteger dados. A grande maioria dos clientes de e-commerce estão preocupados com a privacidade.

A auditoria está em profundo conflito com os esforços em direção a privacidade. Os auditores têm uma ética de registro, investigação, e reportar o máximo possível, e muitas vezes ver os esforços de privacidade como tentativas de impedir a auditoria e potencialmente encobrir a fraude. De fato, os recentes fracassos de bilhões de dólares do Banco Baring e o fundo da divisão Long Term Capital, e mais geralmente os recentes problemas com o "capitalismo de compadrio", que impediram os acionistas e credores de mais de US$ 1 trilhão, foram atribuídos a tais sigilos<sup>[3]</sup>. No topo da lista das atuais reformas do FMI está a "abertura", uma palavra de ordem para a introdução de controles de auditoria e requisitos de relatórios.

Desde que os controles de auditoria são usados para garantir trilhões de dólares de transações a cada ano, eles não estão indo embora, e de fato provavelmente vai crescer mais eficaz e intrusivo. Por outro lado, temos agora à nossa disposição as muitas inovações alcançadas nas últimas duas décadas na criptografia moderna. Podemos usar estes para obter um melhor equilíbrio entre auditoria e privacidade? Eu criei uma arquitetura que usa esses protocolos para melhorar muito essa troca: auditoria confidencial.

Podemos conseguir registros de auditorias após o compromisso através de timestamps (carimbos de tempo) seguros<sup>[1]</sup>. Podemos então alcançar em grande medida imperturbabilidade antes do compromisso, com segregação de funções através de restrições de integridade multipartidárias<sup>[2]</sup>. Nós então auditamos esses compromissos através de cálculos privados multipartidários<sup>[4]</sup>. Essa combinação permite uma ampla variedade de transações, conduzidas com eficiência normal, a ser observada e verificada por árbitros ou auditores, através de cálculos privados mais caros aplicados a compromissos aleatoriamente amostrados. Isso mantém um alto grau de confidencialidade para as entradas.

Os participantes deste protocolo de auditoria mutuamente confidencial podem verificar se os livros correspondem aos detalhes das transações armazenadas em um log de transação previamente confirmado e que os números adicionem corretamente. Os participantes podem calcular estatísticas de resumo em seus logs de transação compartilhados confidencialmente, incluindo verificação cruzada dos logs contra contrapartes de uma transação, sem revelar esses logs. Eles só aprendem o que pode ser inferido das estatísticas, não é possível ver os detalhes das transações.

Assumindo muitos detalhes práticos que eu encarei neste esboço (como a eficiência dos cálculos de auditoria, a disponibilidade de registros de transações digitais em formato padrão, etc.), a auditoria confidencial pode trazer uma melhoria substancial sobre as práticas atuais. Atualmente os detalhes de todas as transações da organização, incluindo, por exemplo, registros em um HMO (Health Maintenance Organization) e transações nos programas ultra-secretos do governo, ou são expostos diretamente aos auditores, ou são imunes de auditoria, permitindo fraude.

Com auditoria mutuamente confidencial, poderemos ganhar confiança na factualidade dos pedidos e relatórios das contrapartes sem revelar informações de identificação e outras informações detalhadas das transações subjacentes a esses relatórios. Isso fornecerá a base para sistemas sólidos de reputação e outros sistemas confiáveis de terceiros, que mantêm a integridade ao longo do tempo, comunicações, sumarização, e preservar a confidencialidade para os participantes da transação. Com auditoria confidencial, muitas vezes seremos capazes de ter abertura e privacidade.


* * *


<pre>    [1] BLLV98  A. Buldas, P. Laud, H. Lipmaa, J. Villemson, "Time-Stamping
        with Binary Linking Schemes", Crypto 98
    [2] Szabo, in progress
    [3] See recent back issues of _The Wall Street Journal_
    and _The Economist_
    [4] Overview, [http://szabo.best.vwh.net/msc.html](http://szabo.best.vwh.net/msc.html)
        Quorum systems model, [http://szabo.best.vwh.net/quorum.html](http://szabo.best.vwh.net/quorum.html)
    B91     D. Beaver, "Efficient Multiparty Protocols Using Circuit
                    Randomization", ACM STOC 91
    RB89   T. Rabin & M. Ben-Or, "Verifiable Secret Sharing
            and Multiparty Protocols with Honest Majority", ACM STOC 89
    GRR98   R. Gennaro, T. Rabin, & M. Rabin: "Simplified VSS
            and Fast-Track Multiparty Computations", PODC 98
  </pre>

<pre>  Fonte:[http://www.fon.hum.uva.nl/rob/Courses/InformationInSpeech/CDROM/Literature/LOTwinterschool2006/szabo.best.vwh.net/confidential.html](http://www.fon.hum.uva.nl/rob/Courses/InformationInSpeech/CDROM/Literature/LOTwinterschool2006/szabo.best.vwh.net/confidential.html)
</pre>

