# Verificação de integridade e autenticidade
***

Por vezes torna-se importante averiguar a integridade e autenticidade de arquivos baixados. Para se ter a certeza da origem e que o mesmo não corrompeu durante o download.

Alguns sites colocam como opção de verificação somente o **hash** do arquivo. Alguns outros colocam o arquivo assinado por uma chave **GPG**. Outros colocam um misto, ou seja, disponibilizam para download o **hash** do arquivo assinado por uma chave.


## Verificação por hash

O **hash** é também chamado de **checksum** ou **soma de verificação**.
Utilizaremos como nosso primeiro exemplo o Linux [Kodachi]. Os desenvolvedores e mantenedores decidiram deixar como método de verificação somente através de **hash**. Antes de tudo, baixaremos os seguintes arquivos:

* [Kodachi ISO]
* [Kodachi hash]

Após efetuar o download dos arquivos, abra o arquivo ```Kodachi-hash.txt``` e observe que temos várias opções de **hash**: **MD5**, **SHA1**, **CRC32**, **SHA-256**, **SHA-512** e **SHA-384**. Para verificar a ISO, faça o seguinte:

**No Windows** 
Utilizaremos o programa [Hash Generator]. Depois de baixá-lo e instalá-lo, clique com o botão direito do mouse em cima da ISO e escolha a opção ```Hash Generator```. Se o programa já estiver aberto, apenas selecione o arquivo. Então clique no botão ```Generate Hash``` e espere até ter o resultado.
Então copie o(s) **hash(es)** gerador pelo programa e cole no final do arquivo ```Kodachi-hash.txt```. Então use a função localizar do bloco de notas e confirme se o programa identifica os dois **hashes**.

**No Linux**
Abra o terminal no diretório em que se encontram os arquivos e digite:
```
sha512sum kodachi-6.0-64.iso
```
A saída será:
```
b73aee2d0ba3b5fc85389e7a0b88bca58a3a558327cf6ddb98f83fe463afbee86a9efcbbe7d73ed511e14eb6e2d830733502f21b946318bfd07fc7f759c9df02  kodachi-6.0-64.iso
```
Copie a saída e cole no no final do arquivo ```Kodachi-hash.txt``` e verifique se coincidem, assim como explicado antes.

No Linux é possível verificar o hash e comparar simultaneamente se o arquivo estiver com o **hash** no formato gerado no terminal. Por exemplo, usando o comando:

```
sha512sum -c arquivo-hash.txt arquivo-verificar.zip
```

A saída gerada é:

```
arquivo-verificar.zip: OK
```
 

Verifique um ou mais **hashes** se preferir.


## Verificação por assinatura digital

Verificaremos o programa [KeePassXC]. O método disponibilizado para verificar o arquivo é através de assinatura digital.
Para isso utilizaremos o programa [GPG4Win] para Windows ou Kleopatra para Linux. Antes de tudo, baixe o [programa GPG4Win] e verifique o **hash** antes de instalar no Windows. Se estiver usando Linux baixe o programa Kleopatra.

Faremos a verificação do programa para Windows
* [KeePassXC Program]
* [KeePassXC Public Key] ou ID CFB4C2166397D0D2
* [KeePassXC Signature]
 
Primeiramente abra o terminal no diretório em que se encontram os arquivos e digite:
```
gpg --import keepassxc_master_signing_key.asc
```
Este comando pode ser substituído por ```gpg --import CFB4C2166397D0D2```, que referencia a chave pública do desenvolvedor. A saída deverá ser:
```
gpg: key CFB4C2166397D0D2: 41 signatures not checked due to missing keys
gpg: key CFB4C2166397D0D2: public key "KeePassXC Release <release@keepassxc.org>" imported
gpg: Número total processado: 1
gpg:               importados: 1
gpg: no ultimately trusted keys found
```

Depois de importada a chave, digite:
```
gpg --verify KeePassXC-2.3.4-Win64.exe.sig KeePassXC-2.3.4-Win64.exe
```

Após isso espere a saída do programa que será:
```
gpg: Signature made 08/23/18 15:54:05 Hora oficial do Brasil
gpg:                using RSA key C1E4CBA3AD78D3AFD894F9E0B7A66F03B59076A8
gpg: Good signature from "KeePassXC Release <release@keepassxc.org>" [unknown]
gpg: AVISO: Esta chave não está certificada com uma assinatura confiável!
gpg:          Não há indicação de que a assinatura pertence ao dono.
Impressão da chave primária: BF5A 669F 2272 CF43 24C1  FDA8 CFB4 C216 6397 D0D2
      Impressão da subchave: C1E4 CBA3 AD78 D3AF D894  F9E0 B7A6 6F03 B590 76A8
```

A linha que nos importa é ```gpg: Good signature from "KeePassXC Release <release@keepassxc.org>" [unknown]```. 

**Atenção**
A linha que contém o aviso ```gpg: AVISO: Esta chave não está certificada com uma assinatura confiável!``` indica ninguém certificou essa chave com uma assinatura. Apesar da linha ```gpg:          Não há indicação de que a assinatura pertence ao dono.```, a verificação foi concluída com sucesso indicando que o desenvolvedor assinou o arquivo com a chave dele.

Não é necessário que você tenha criado um par de chaves, pois não precisaremos da chave privada para isso. Mesmo usando interface gráfica, o programa identifica o certificado digital e, clicando nela, abrirá uma janela com os detalhes do certificado. Usando interface gráfica o processo é semelhante, mas não será abordado.


## Verificação por assinatura e hash em conjunto

Esse é outro modo comum de verificar arquivos, se disponível no site do arquivo que se pretende baixar. Aqui não há nada de diferente quanto ao modo de verificar:

* Verificar primeiro a assinatura do arquivo contendo o **checksum**
* Calcular o **hash** do arquivo e comparar com o conteúdo do arquivo de **hash** assinado

De modo geral é assim que se verifica. Aqui como exemplo usaremos uma ISO do Debian. Para verificar qualquer ISO do Debian há um procedimento um pouco diferente, mas que se mostra igualmente útil.

Primeiramente baixe os arquivos de exemplo:

* [Debian ISO]
* [Debian hash]
* [Debian hash sign]
* Certificado será importado depois

No Linux digite no terminal no mesmo diretório dos arquivos baixados:
```
sha512sum --ignore-missing -c SHA512SUMS debian-9.8.0-amd64-netinst.iso
```
O parâmetro ```--ignore-missing``` serve para evitar que se verifique qualquer outro arquivo cuja soma de verificação esteja neste arquivo e faltando no diretório, evitando uma saída desnecessariamente longa no terminal.

A saída que aparecerá é:
```
debian-9.8.0-amd64-netinst.iso: OK
```
Isso mostra apenas que o download não corrompeu o arquivo. 
No Windows o passo a passo já sabemos: verificar os **hashes** através do Hash Generator e conferir usando o bloco de notas.

Agora será necessário verificar se o **hash** foi realmente assinado pelo desenvolvedor. Para isso, digite:
```
gpg --verify SHA512SUMS.sign
```

A saída que aparecerá é a seguinte:
```
gpg: assuming signed data in 'SHA512SUMS'
gpg: Signature made dom 17 fev 2019 12:10:30 -03
gpg:                using RSA key DF9B9C49EAA9298432589D76DA87E80D6294BE9B
gpg: Can't check signature: No public key
```

A mensagem mostra o ID da chave pública (```DF9B9C49EAA9298432589D76DA87E80D6294BE9B```) e diz que não existe essa chave no nosso chaveiro. Vamos verificar se existe essa chave no _keyring server_ do Debian e importá-la. Para isso digite:
```
gpg --keyserver keyring.debian.org --recv DF9B9C49EAA9298432589D76DA87E80D6294BE9B
````

A saída será algo assim:
```
gpg: key DA87E80D6294BE9B: 5 signatures not checked due to missing keys
gpg: key DA87E80D6294BE9B: public key "Debian CD signing key <debian-cd@lists.debian.org>" imported
gpg: marginals needed: 3  completes needed: 1  trust model: pgp
gpg: depth: 0  valid:   1  signed:   0  trust: 0-, 0q, 0n, 0m, 0f, 1u
gpg: Total number processed: 1
gpg:               imported: 1
```

Agora verificaremos a assinatura do **hash** com o comando:
```
gpg --verify SHA512SUMS.sign SHA512SUMS
```

A saída será:
```
gpg: Signature made dom 17 fev 2019 12:10:30 -03
gpg:                using RSA key DF9B9C49EAA9298432589D76DA87E80D6294BE9B
gpg: Good signature from "Debian CD signing key <debian-cd@lists.debian.org>" [unknown]
gpg: WARNING: This key is not certified with a trusted signature!
gpg:          There is no indication that the signature belongs to the owner.
Primary key fingerprint: DF9B 9C49 EAA9 2984 3258  9D76 DA87 E80D 6294 BE9B
```

O que nos importa é a linha ```gpg: Good signature from "Debian CD signing key <debian-cd@lists.debian.org>" [unknown]```, mostrando que a verificação deu certo.


[Kodachi]: https://www.digi77.com/index.php
[Kodachi ISO]: https://sourceforge.net/projects/linuxkodachi/files/latest/download
[Kodachi hash]: https://www.digi77.com/software/kodachi/Kodachi-hash.txt
[Hash Generator]: https://securityxploded.com/hashgenerator.php
[KeePassXC]: https://keepassxc.org
[KeePassXC Program]: https://github.com/keepassxreboot/keepassxc/releases/download/2.3.4/KeePassXC-2.3.4-Win64.exe
[KeePassXC Public Key]: https://keepassxc.org/keepassxc_master_signing_key.asc
[KeePassXC Signature]: https://github.com/keepassxreboot/keepassxc/releases/download/2.3.4/KeePassXC-2.3.4-Win64.exe.sig
[GPG4Win]: https://www.gpg4win.org/
[programa GPG4Win]: https://www.gpg4win.org/thanks-for-download.html
[Debian ISO]: https://cdimage.debian.org/debian-cd/current/amd64/iso-cd/debian-9.8.0-amd64-netinst.iso
[Debian hash]: https://cdimage.debian.org/debian-cd/current/amd64/iso-cd/SHA512SUMS
[Debian hash sign]: https://cdimage.debian.org/debian-cd/current/amd64/iso-cd/SHA512SUMS.sign
