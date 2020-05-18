### Fluxo para tradução de textos

1. Criar o _fork_ do repositório e adicionar este aos _upstreams_.
2. Selecionar o artigo que desejar traduzir, este deverá estar presente na lista de artigos que ainda estão em **TO_TRANSLATE**.
3. Criar uma nova _branch_ com um nome associado ao artigo que se está traduzindo, preferencialmente iniciado por **traducao**, seguido do nome genérico do artigo.
4. Realizar um _pull request_ deste arquivo de tradução, movendo-o de **TO_TRANSLATE** para **TRANSLATING**.
5. Aguardar até que a _pull request_ seja aceita para iniciar a tradução.
6. Realizar a tradução do artigo.
7. Realizar um _pull request_ do artigo traduzido, modificando o status de **TRANSLATING** para **TRANSLATED**.

### Fluxo para revisão de textos

1. Criar o fork do repositório e adicionar este aos _upstreams_.
2. Selecionar os artigos que se deseja criar a revisão.
3. Criar uma _branch_ iniciada por **revisao**.
4. Realizar a mudança de uma lista de **TO_REVISE**, para **REVISING**.
5. Diferentemente da tradução, este _commit_ poderá ocorrer dentro do mesmo pull que a revisão, sem a necessidade de se aguardar a aprovação. A tese é de que revisões vão alterar uma parte pequena do texto, e caso ocorra um conflito, a última pessoa poderá ser responsável por realizar um _merge_ e alterar a quantidade de revisões do mesmo texto.
6. Realizar um _pull request_ da última versão do texto, modificando seu status de **REVISING** para **REVISED**
7. Após o limite de 20 revisões, o texto receberá o status de FINAL.

### Fluxo para submeter novos textos para tradução

1. Criar o _fork_ do repositório e adicionar este aos _upstreams_.
2. Verificar se já não há um texto com o mesmo título e autor na lista, independente do seu status.
3. Criar uma proposta de inserção de texto através de uma **Issue** para validar se existe consenso em incluir o texto na lista de artigos.
4. Caso o texto tenha resposta positiva, o propositor deverá criar uma _pull request_ contendo o título do texto a ser traduzido, o autor, o ano (tendo em vista que ocorrem revisões das versões finais destes artigos) com o status de **TO_TRANSLATE**.
5. Caso já exista algum arquivo base para a tradução, seja um PDF, HTML, TXT, MD ou qualquer outro formato que possa ser consumido para equipe tradutora, este arquivo deverá ser postado na pasta de arquivos **TO_TRANSLATE**, sendo feito dentro do mesmo _pull request_. Para arquivos que precisem de mais de uma unidade (ex: PDFs divididos, imagens), o artigo deverá ser inserido usando-se uma pasta.
