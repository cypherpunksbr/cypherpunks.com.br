# Contribuições

<<<<<<< HEAD
### Por onde começar?

**1.** Escolha um [arquivo](https://github.com/cypherpunksbr/cypherpunks.com.br/tree/master/todo) para traduzir ou [revisar](https://github.com/cypherpunksbr/cypherpunks.com.br/tree/master/posts). Verifique se o arquivo já não está sendo traduzido por alguém [aqui](https://github.com/cypherpunksbr/cypherpunks.com.br/blob/master/todo/README.md). 

**2. [Importante]** Atualize [este arquivo](https://github.com/cypherpunksbr/cypherpunks.com.br/blob/master/todo/README.md) informando que você está traduzindo um determinado artigo. Isto é muito importante, pois evita que duas pessoas traduzam o mesmo arquivo. Lembre-se de atualizá-lo também quando você terminar de traduzir :)

**3.** [Entenda nosso fluxo](#fluxo).

**4.** [Leia e pratique as boas práticas](#boas-pr%C3%A1ticas).

**5.** Submeta um pull request. Não sabe como fazer isto? Veja este [tutorial](https://#) ou este [vídeo](https://#).

**6.** Parabéns! Você acaba de contribuir para o projeto :) Seu nome será adicionado na lista de contribuintes em breve por algum moderador.

### Complicado?

Escolha um artigo para traduzir [nesta página](https://github.com/cypherpunksbr/cypherpunks.com.br/tree/master/todo) e envie o seu artigo para avelino (at) cypherpunks.com.br ou informe da sua tradução no nosso [grupo de telegram](https://t.me/criptologia)

### Fluxo

É muito fácil contribuir para o projeto. Qualquer tipo de ajuda (seja ela grande ou pequena) é bem-vinda. Se encontrar qualquer parte dos posts/artigos que possam ser melhoradas, essa é uma grande oportunidade para participar ([aqui](https://github.com/cypherpunksbr/cypherpunks.com.br/issues?q=is%3Aopen+is%3Aissue+label%3Amelhorias) é um ótimo lugar para achar coisas que possam ser melhoradas). Caso não saiba por onde começar:

**1.** Faça referência ao repositório oficial após o _fork_

```
git remote add upstream git@github.com:cypherpunksbr/cypherpunks.com.br.git
```

**2.** Antes de iniciar o processo de contribuição, crie uma nova branch para fazer suas alterações.

Alguns exemplos:

- Para tradução: `git checkout -b traducaoArtigoX`
- Para revisões: `git checkout -b traducaoArtigoX`
- Para erros: `git checkout -b traducaoArtigoX`

> Use qualquer nome que seja coerente com a contribuição que está sendo feita.
> `X` representa um nome de artigo.

**3.** Após realizar as alterações, é hora de fazer um commit com uma mensagem coerente do que foi feito. Exemplo:

```
git add --all
git commit -am ‘Adiciona tradução/revisão/melhoria artigo X linha/linhas Y’
git push origin traducaoArtigoTal
```

**4.** Envie um _Pull Request_ com as alterações feitas, fazendo referência para o `master` do repositório oficial.

**5.** Sua contribuição será analisada pela comunidade. Em alguns casos pediremos algumas alterações antes de dar merge.

Após o merge:

- Delete a branch utilizada:

```
git checkout master
git push origin :traducaoArtigoX
git branch -D traducaoArtigoX
```

- Atualize seu repositório com o repositório oficial:

```
git fetch upstream
git rebase upstream/master
git push -f origin master
```

**6.** Quando iniciar uma nova contribuição, inicie repita o processo pelo passo 2.

### Boas práticas

- Antes de enviar sua contribuição, certifique-se de que está enviando apenas um **único** commit que represente o que foi feito. Caso tenha feito vários commits, [esmague-os](http://gitready.com/advanced/2009/02/10/squashing-commits-with-rebase.html) antes de fazer o _Pull Request_.
- Caso tenha qualquer tipo de dúvida, abre uma [_Issue_](https://github.com/cypherpunksbr/cypherpunks.com.br/issues) que faremos o possível para te ajudar.
- Contribua com as discussões.


### Dúvidas em tradução de termos, palavras, expressões etc…
=======
### Fluxo

É muito fácil contribuir para o projeto. Qualquer tipo de ajuda (seja ela grande ou pequena) é bem-vinda. Se encontrar qualquer parte dos posts/artigos que possam ser melhoradas, essa é uma grande oportunidade para participar. Aqui em [melhorias] é um ótimo lugar para achar coisas que possam ser melhoradas). Caso não saiba por onde começar, veja o passo a passo usando [Git e GitHub].

### Por onde começar?

**1.** Escolha um arquivo para [traduzir] ou [revisar]. Sempre verifique se o arquivo não está sendo traduzido para evitar trabalho dobrado desnecessário.

**2. [Importante]** Atualize este [README.md], informando que você está traduzindo um determinado artigo. Após terminar a tradução, atualize-o novamente. O motivo foi dito no item anterior, evitar que duas pessoas façam o mesmo artigo :smile:

**3.** Siga o passo a passo do uso do [Git e GitHub].

**4.** Parabéns! Você acaba de contribuir para o projeto :) Seu nome será adicionado na lista de contribuintes em breve por algum moderador.

### Complicado?

Escolha um artigo para [traduzir] nesta página e envie o seu artigo para avelino (at) cypherpunks.com.br ou informe da sua tradução no nosso [grupo de telegram].

### Dúvidas em tradução de alguma palavra ou expressão
>>>>>>> mudanças de template

Quando estiver em uma situação em que você não sabe exatamente como traduzir uma palavra, termo ou expressão, nós recomendamos que siga os seguintes passos:

**1.** Abra uma _Issue_ com um título descritivo como por exemplo: “_Como traduzir a palavra/termo “x”?_” e coloque uma descrição fazendo referência à linha e o capítulo que esteja trabalhando.

**2.** Adicione uma tag `[TODO: ref #<número-da-issue-da-discussão>]<palavra/termo não traduzido>[/TODO]` e continue trabalhando no arquivo enquanto não há uma conclusão na _Issue_. Esse processo é importante para facilitar o acesso a itens pendentes e ter uma referência clara onde está ocorrendo a discussão.

**3.** Após a conclusão da discussão na _Issue_, feche-a. Em seguida, remova a tag adicionada no passo 2 e atualize a palavra/termo não traduzido.

<<<<<<< HEAD
**4.** Como mantemos um arquivo de [glossário](https://github.com/cypherpunksbr/cypherpunks.com.br/blob/master/GLOSSARIO.md), faça um _Pull Request_ adicionando o novo termo, colocando a referência `#<número-da-issue>` no termo/palavra em questão para fácil acesso no futuro.

**5** Deixe o termo, palavra, expressões do modo como está escrito nos seguintes casos:
-  São termos comuns que usamos em inglês sem problemas de entendimento;
-  Termos, palavras, expressões etc que ficam estranhas quando traduzidas. Nesse caso, pode-se colocar a tradução ao lado do que se está traduzindo entre parêntesis, somente na primeira vez que aparece no texto.
=======
**4.** Como mantemos um arquivo de [glossário], faça um _Pull Request_ adicionando o novo termo, colocando a referência `#<número-da-issue>` no termo/palavra em questão para fácil acesso no futuro.

**5** Deixe o termo do modo como está escrito nos seguintes casos:
-  São termos comuns que usamos em inglês sem problemas de entendimento;
-  Termos que ficam estranhos quando traduzidos. Nesse caso, pode-se colocar a tradução ao lado do que se está traduzindo entre parêntesis, somente na primeira vez que aparece no texto.
>>>>>>> mudanças de template

***

Obrigado! :heart: :heart: :heart:

<<<<<<< HEAD
=======

[melhorias]: https://github.com/cypherpunksbr/cypherpunks.com.br/issues?q=is%3Aopen+is%3Aissue+label%3Amelhorias
[Git e GitHub]: https://github.com/cypherpunksbr/cypherpunks.com.br/blob/master/documentacao/GITGITHUB.md
[traduzir]: https://github.com/cypherpunksbr/cypherpunks.com.br/tree/master/todo
[revisar]: https://github.com/cypherpunksbr/cypherpunks.com.br/tree/master/posts
[README.md]: https://github.com/cypherpunksbr/cypherpunks.com.br/blob/master/todo/README.md
[glossário]: https://github.com/cypherpunksbr/cypherpunks.com.br/blob/master/GLOSSARIO.md
[grupo de telegram]: https://t.me/criptologia
>>>>>>> mudanças de template
