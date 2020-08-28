---
title:  "Criptografia Intrapolinomial"
date:   01-01-1999 -0300
categories:
  - Biblioteca
tags:
  - Nick Szabo
---

<small>Nick Szabo</small>

#### 1999


Pesquisadores têm proposto uma variedade de “desafios para clientes” e “trabalho pesado” como o hashcash, MicroMint, Bit Gold e a Postagem com Custo Computacional para criar uma moeda independente ou fazer o spam ficar custoso. A implicação matemática desta proposta é de que existe uma “criptografia intrapolinomial”. As 4 motivações para a teoria da criptografia intrapolinomial são (a) as novas construções como as mencionadas anteriormente, (b) estimativas mais acuradas sobre o custo para se quebrar uma cifra, (c) é possível que seja mais fácil provar os limites menores ao invés de apenas executá-los, como na criptografia superpolinomial (padrão), e (d) se não existe nenhuma função digestiva (one-way function), a criptografia padrão é intrapolinomial ao invés de superpolinomial.

Proponho a seguinte formalização:

    Assumindo que: 

        f: {0,1}* --> {0,1}* é chamada de Função k-benchmark forte

        para uma máquina de um modelo M e k>=1 se:

        1.f for processado no tempo O(p(n)) na máquina M, onde p é polinomial.
        2.f não reduza os dados inseridos mais do que q(n,k), onde q(n,k) é um polinômio de grau k.
        3.Para cada algoritmo aleatório A que seja processado em M em um tempo menor que q(n,k)p(n), existe um N tal que n > N
    Pr[A(f(x)) = f^-1(f(x))] < 1/q(n,k)p(n)

Em outras palavras, não existe um algoritmo mais rápido que q(n,k)p(n) que possa inverter f em um número significante de valores.

É possível definir casos médios, melhor dos casos e pior dos casos para a função de benchmark de grau k. O questionamento (análogo a questão da criptografia superpolinomial, se existe uma função de uma única via): Serã que podemos provar (3) os limites superiores e inferiores para um função qualquer e k>=1 em uma máquina real como a RAM-log?

Casos fortes e médios são os mais oportunos em casos relacionados a criptografia. Infelizmente, para estes propósitos nós também precisamos de:

1.  uma lista de máquinas que compreenda todos os modelos praticáveis de máquina, no sentido de que qualquer uma dessas máquinas possam ser simuladas com uma pequena sobrecarga, como uma constante ou O(log(n)).
2.  para provar os limites inferiores em uma função de benchmark para todos os modelos da lista.

Sabendo que isso é, no mínimo, muito chato, esperamos conseguir uma pequena lista que cubra todas as arquiteturas plausíveis. Isto pode funcionar para provar que a exposição total de um protocolo de quebra (cracking protocol) é menor que os custos de pesquisa e desenvolvimento de uma arquitetura para derrotar este mesmo protocolo. A análise criptográfica (cryptanalyis) deve descobrir quais arquiteturas são interessantes para quebrar uma cifra intrapolinomial.

Existe ao menos duas implicações práticas da análise anterior. A primeira é que existe pouquíssimo espaço para erro para a análise e implementação da postagem com custo computacional, hashcash, bit gold, MicroMint e outros modelos de criptografia intrapolinomiais. A segunda é que, a menos que o oponente tenha pouco dinheiro e esteja limitado a um computador pessoal, não faz sentido analisar a segurança ou o custo desses esquemas sem fazer referência a arquitetura da máquina. Por exemplo, propagadores de spam (spammers) poderiam acabar com o custo computacional usando placas artesanais otimizadas para resolver um problema particular.
