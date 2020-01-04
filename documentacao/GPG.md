# GPG
***

## Passo a passo simplificado

###### 1. Criar o par de chaves
```
gpg --full-generate-key
```

###### 2. Escolher o tipo de chave
```
Por favor selecione o tipo de chave desejado:
   (1) RSA and RSA (default)
   (2) DSA and Elgamal
   (3) DSA (apenas assinatura)
   (4) RSA (apenas assinatura)
Opção? 2
```

###### 3. Escolher o comprimento de chave
```
DSA chaves podem ter o seu comprimento entre 1024 e 3072 bits.
Que tamanho de chave você quer? (2048) 3072
```

###### 4. Definir a validade da chave
```
Por favor especifique por quanto tempo a chave deve ser válida.
         0 = chave não expira
      <n>  = chave expira em n dias
      <n>w = chave expira em n semanas
      <n>m = chave expira em n meses
      <n>y = chave expira em n anos
A chave é valida por? (0) 0
```

###### 5. Confirmar a validade
```
A chave não expira nunca
Está correto? (s/n) s
```

###### 6. Preencher os dados que identificarão a chave. Comentário é opcional.
```
GnuPG precisa construir uma ID de usuário para identificar sua chave.

Nome completo: Satoshi Nakamoto
Endereço de correio eletrônico: satoshin@gmx.com
Comentário: Apenas teste
```

###### 7. Confirmar os dados
```
Você selecionou este identificador de utilizador:
    "Satoshi Nakamoto (Apenas teste) <satoshin@gmx.com>"

Mudar (N)ome, (C)omentário, (E)ndereço ou (O)k/(S)air? o
```

###### 8. Defina uma senha para a chave na janela que se abre e confirme-a clicando em ```ok```

###### 9. Certificado de revogação

Este certificado está guardado em
```
/home/satoshi/.gnupg/openpgp revocs.d/0D37DDC70358BD306685E18083048A80F80A2DB5.rev
```
Caso queira gerar manualmente digite:
```
gpg --output revoke.asc --gen-revoke mykey
```

###### 10. Backup e restauração das chaves

Listar as chaves públicas e privadas respectivamente:
```
gpg --list-keys
gpg --list-secret-keys
```

Salvar as chaves pública e privada respectivamente:
```
gpg -ao public.mypgp.key --export ID_da_chave
gpg -ao private.mypgp.key --export-secret-keys ID_da_chave
```

Agora se você precisar restaurar as chaves é só fazer:
```
gpg --import public.mypgp.key
gpg --import private.mypgp.key
```

###### 11.Enviar a chave pública para um servidor de chaves
```
gpg --keyserver pgp.mit.edu --send-keys ID_da_chave
```

***
## Passo a passo detalhado

### Criação das chaves

Para criar o par de chaves digite:
```
gpg --full-generate-key
```

Após apertar ```Enter```, aparecerá na tela:
```
gpg (GnuPG) 2.2.10; Copyright (C) 2018 Free Software Foundation, Inc.
This is free software: you are free to change and redistribute it.
There is NO WARRANTY, to the extent permitted by law.

Por favor selecione o tipo de chave desejado:
   (1) RSA and RSA (default)
   (2) DSA and Elgamal
   (3) DSA (apenas assinatura)
   (4) RSA (apenas assinatura)
Opção?
```

Escolha a opção ```(2) DSA e Elgamal```, digitando ```2``` e apertando ```Enter```

```
DSA chaves podem ter o seu comprimento entre 1024 e 3072 bits.
Que tamanho de chave você quer? (2048)
```

Neste momento digite ```3072``` que é o comprimento máximo da chave.

```
Por favor especifique por quanto tempo a chave deve ser válida.
         0 = chave não expira
      <n>  = chave expira em n dias
      <n>w = chave expira em n semanas
      <n>m = chave expira em n meses
      <n>y = chave expira em n anos
A chave é valida por? (0)
```

Agora devemos escolher a validade da chave. Neste exemplo, optamos por escolher uma chave que nunca expira, utilizando a opção ```(0)``` e, logo em seguida, confirmando com ```s```.

```
A chave não expira nunca
Está correto? (s/n)
```

Em seguida você precisará preencher os dados para identificar sua chave. O comentário é opcional.
```
GnuPG precisa construir uma ID de usuário para identificar sua chave.

Nome completo: Satoshi Nakamoto
Endereço de correio eletrônico: satoshin@gmx.com
Comentário: Apenas teste
```

A seguir aparecerão os dados da sua chave
```
Você selecionou este identificador de utilizador:
    "Satoshi Nakamoto (Apenas teste) <satoshin@gmx.com>"

Mudar (N)ome, (C)omentário, (E)ndereço ou (O)k/(S)air?
```
Escolha a opção correspondente a letra destacada e tecle ```Enter```

Logo a seguir aparecerá uma tela pedindo para você criar uma senha e confirmá-la. Sugerimos que crie uma que seja fácil para você memorizar e difícil para outros deduzirem, além de ser longa, ter caracteres especiais, números, letras maiúsculas e minúsculas. Não é obrigatório ter todos esses requisitos, mas é altamente recomendável.
Após clicar em ```OK``` mova o mouse e aperte em teclas aleatórias para que o gerador de números aleatórios ganhe entropia suficiente, de acordo com a mensagem que aparece no terminal.

```
Precisamos gerar muitos bytes aleatórios. É uma boa ideia realizar outra
actividade (escrever no teclado, mover o mouse, usar os discos) durante a
geração dos números primos; isso dá ao gerador de números aleatórios
uma hipótese maior de ganhar entropia suficiente.

gpg: AVISO: alguns programas OpenPGP não podem manipular uma chave DSA com esse tamanho de resumo
```

Em seguida serão exibidas todas as informações da chave criada

```
gpg: chave 83048A80F80A2DB5 marcada como plenamente confiável
gpg: revocation certificate stored as '/home/satoshi/.gnupg/openpgp-revocs.d/0D37DDC70358BD306685E18083048A80F80A2DB5.rev'
chaves pública e privada criadas e assinadas.

pub   dsa3072 2018-12-12 [SC]
      0D37DDC70358BD306685E18083048A80F80A2DB5
uid                      Satoshi Nakamoto (Apenas teste) <satoshin@gmx.com>
sub   elg3072 2018-12-12 [E]
```

Observe a linha que contém ```gpg: revocation certificate stored as '/home/satoshi/.gnupg/openpgp-revocs.d/0D37DDC70358BD306685E18083048A80F80A2DB5.rev'```

Foi criado um certificado de revogação da chave. Se você esquecer sua frase secreta ou se sua chave privada estiver comprometida ou perdida, esse certificado de revogação poderá ser publicado para notificar outras pessoas de que a chave pública não deve mais ser usada. Uma chave pública revogada ainda pode ser usada para verificar assinaturas feitas por você no passado, mas não pode ser usada para criptografar mensagens futuras para você. Também não afeta sua capacidade de descriptografar mensagens enviadas para você no passado, se você ainda tiver acesso à chave privada.

**Importante** > Se você decidir deletar sua chave, use esse certificado de revogação para a finalidade mencionada. Não apague sua chave do servidor de chaves, pois um atacante poderia criar uma chave semelhante a sua chave antiga e se passar por você.

Caso você precise executar o comando para gerar o certificado, digite:
```
gpg --output revoke.asc --gen-revoke mykey
```
O argumento ```mykey``` deve ser um especificador de chave, o ID da chave do seu par de chaves principal ou qualquer parte de um ID de usuário que identifique o seu par de chaves. O certificado gerado será deixado no arquivo ```revoke.asc```. Se a opção ```--output``` for omitida, o resultado será colocado na saída padrão. Como o certificado é curto, você pode imprimir uma cópia impressa do certificado para armazenar em algum lugar seguro, como o seu cofre. **O certificado não deve ser armazenado onde outros possam acessá-lo, pois qualquer pessoa pode publicar o certificado de revogação e tornar inútil a chave pública correspondente**.

### Backup das chaves

Para visualizar as chaves públicas instaladas, digite:
```
gpg --list-keys
```

Será exibido
```
/home/satoshi/.gnupg/pubring.kbx
--------------------------------
pub   dsa3072 2018-12-12 [SC]
      0D37DDC70358BD306685E18083048A80F80A2DB5
uid                      Satoshi Nakamoto (Apenas teste) <satoshin@gmx.com>
sub   elg3072 2018-12-12 [E]
```

Para visualizar as chaves privadas, digite:
```
gpg --list-secret-keys
```

Será exibido
```
/home/satoshi/.gnupg/pubring.kbx
--------------------------------
sec   dsa3072 2018-12-12 [SC]
      953004AE353BE95533D7F66B83E41A950939024D
uid           [ultimate] Satoshi Nakamoto (Apenas teste) <satoshin@gmx.com>
ssb   elg3072 2018-12-12 [E]
```

Para salvar a chave pública o comando é:
```
gpg -ao public.mypgp.key --export ID_da_chave
```

Para salvar a chave privada:
```
gpg -ao private.mypgp.key --export-secret-keys ID_da_chave
```
Operações envolvendo a chave privada sempre será pedida a senha para confirmar.

**Lembre-se de guardar as chaves em algum local seguro, de preferência criptografado.**

Agora se você precisar restaurar as chaves é só fazer:
```
gpg --import public.mypgp.key
gpg --import private.mypgp.key
```

**Para fazer backup de todas as chaves basta copiar o diretório ```~/.gnupg``` e salvar em outro local.**

### Enviar a chave pública para um servidor de chaves

Para exportar a chave para um servidor de chaves digite:
```
gpg --keyserver pgp.mit.edu --send-keys ID_da_chave
```

Ao teclar ```Enter``` aparecerá
```
gpg: enviando chave 83048A80F80A2DB5 para hkp://pgp.mit.edu
```

O ```83048A80F80A2DB5``` é o ID da chave de exemplo.


**Servidores famosos:**
* [pgp.mit.edu](pgp.mit.edu)
* [keys.gnupg.net](keys.gnupg.net)
* [subkeys.pgp.net](subkeys.pgp.net)
* [keyserver.pgp.com](keyserver.pgp.com)
* [keyserver.ubuntu.com](keyserver.ubuntu.com)
* [sks-keyservers.net](sks-keyservers.net)
* [outros](https://sks-keyservers.net/status/)
