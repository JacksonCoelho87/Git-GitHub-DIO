# **Desafio de Projeto Git / GitHub DIO**

### Comandos Básicos no Terminal (Windows & GNU/Linux)

- dir -> Lista os diretórios do local atual (windows)
- ls -> Lista os diretórios do local atual (GNU/Linux)
- ls -a -> Lista arquivos e diretórios, incluindo os ocultos (GNU/Linux)
- cd -> "Change Directory", usado para mudar de diretório (Windows & GNU/Linux)
- cd..-> Volta para o diretório anterior
- cls -> "Clear Screen", comando para limpar a tela do terminal (Windows)
- clear ou CTRL+L -> Comando para limpar a tela do terminal (GNU/Linux)
- mkdir -> "Make Directory", comando para criar um diretório (Windows & GNU/Linux)
- del -> deleta um arquivo (Windows)
- rmdir -> ''Remove Directory", comando para remover um diretório (Windows)
- rm -> "Remove", comando para deletar arquivos e diretórios (GNU/Linux)

***

### Objetos Internos do Git (*Blobs / Tree / Commit*)

* **Blobs**

Contém metadados, através do blob o git especifica: tipo, tamanho e o conteúdo do arquivo.

* **Trees**

Armazenam blobs, montam a estrutura de onde está localizado o arquivo, diretórios e outras árvores.

* **Commit**

Aponta para uma tree, contém o autor, mensagem e outros metadados.

***

### Criptografia

**SHA**

Secure Hash Algorithm (Algoritmo de Hash Seguro), é um conjunto de funções hash criptográficas projetadas pela NSA (Agência de Segurança Nacional dos EUA). Funções hash criptográficas são operações matemáticas executadas em dados digitais; comparando o *hash* computado (a saída de execução do algoritmo) a um valor de hash  conhecido e esperado, uma pessoa pode determinar a integridade dos  dados. Por exemplo, calcular o hash de um arquivo baixado e comparar o  resultado com um resultado hash publicado anteriormente pode mostrar se o download foi modificado ou adulterado.

***

**Chave SSH**

É a sigla para Secure Socket Shell (Couraça de Soquete Seguro), sendo um dos protocolos  específicos de segurança de troca de arquivos entre cliente e servidor  de internet, usando criptografia. O objetivo do SSH é permitir que  desenvolvedores ou outros usuários realizem alterações em sites e  servidores utilizando uma conexão simples e segura. Sendo assim, o protocolo estabelece uma conexão segura (encriptada) entre 2 (duas) máquinas e conta com 2 (duas) chaves: 1 pública e 1 privada.

*Criar chave SSH (windows & GNU/Linux)* 

> ssh-keygen -t ed25519 -C (adicione o seu email, preferencialmente o cadastrado no GitHub)

O terminal solicitará o nome para as suas senhas e logo após uma senha, que o protocolo utilizará ao executar a sua senha privada para descriptografar os arquivos.

Para visualizar a sua chave púbica, para inserí-la no GitHub, por exemplo, utilizamos o comando:

> cat (nome da chave).pub

Para inicar o SSH-Agent (processo que roda em nosso PC e verifica a utilização de chaves SSH) devemos utilizar o comando:

> eval $ ssh-agent -s

Em seguida adicionamos a nossa chave privada, na qual o protocolo utilizará para descriptografia, mediante a nossa senha que inserimos na sua criação. Então, usamos o seguinte comando:

> ssh-add (nome da chave privada, não tem o .pub)

***

**Token de Acesso**

É uma outra forma de segurança ao utilizar os serviços do Git / GitHub. Esse método é feito totalmente pela plataforma do GitHub. Segure-se de guardar o seu token de acesso pois ele ficará visível apenas no momento da sua criação, caso perca-o será necessário revogar o token atual e gerar um novo.

***
