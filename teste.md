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

**Comandos Git**

Alguns comandos no Git podem ser feitos utilizando sua autenticação de usuário e senha, chave SSH e token de acesso. O primeiro passo é adicionar um repositório no GitHub, para isso você pode ir a [plataforma](http://www.github.com) e criar. 

Proximo passo é iniciar o Git no diretório que você pretende enviar para o GitHub. Nesse caso utilizamos o seguinte comando.

> git init

Após, configuraremos o git com alguns dados que serão inseridos no commit para identificar futuras alterações feitas por você. Nestes passos utilizar os mesmos dados que utilizaram para criar sua conta no GitHub, pois facilita em não precisar alterar os dados no futuro, caso seja necessário.

> git config --global user.email "exemplo@exemplo.com.br" 
>
> git config --global user.name "seu usuário GitHub"

Agora, adicionaremos todos os arquivos e diretórios a serem "comitados" pelo Git.

> git add *

Comitaremos o(os) aquivo(os) com alguma mensagem que o(os) identifique(m) para uma melhor compreensão de quem visualiza seu código no GitHub, utilizando o seguinte comando:

> git commit - m "sua mensagem"

Para visualizar o status do git, utilize o comando:

> git status

Caso você tenha configurado seus dados no git diferente dos dados utilizados no GitHub, você pode fazer a alteração, removendo os dados anteriore e re-inserindo os novos dados. Para remover os dados anteriores utilizamos os seguintes comandos:

> git config --global --unset user.name 
>
> git config --global --unset user.email

Para enviar o seu repositório local para o GitHub (comumente chamado de repositório remoto), devemos escolher o método: autenticação https (utilizando usuário e senha do GitHub), chave SSH ou token de acesso. Você deve escolher a melhor opção, pois isso influenciará o "link" que o GitHub lhe fornecerá para inserir no git em seu terminal. Para vincular o seu repositório local ao remoto, utilizamos o seguinte comando:

> git remote add origin (link fornecido pelo GitHub)

Após, podemos enviar (fazer upload) nosso repositório local para o GitHub (repositório remoto) através do comando:

> git push origin master

Caso precisemos realizar alguma mudança em nosso código, devemos simplesmente modificar nossos arquivos, adicionar os arquivos a serem "comitados", comitar e enviar os arquivos. Como o GitHub é uma plataforma de hospedagem de código-fonte e arquivos com controle de versão usando o Git, ele permite que programadores, utilitários ou qualquer usuário cadastrado na plataforma contribuam em projetos privados e/ou Open Source de qualquer lugar do mundo. Caso o seu código do seu repositório remoto tiver sido alterado por alguém e você tambem o tiver alterado, e você queira manter tanto a mudança feita por algum colaborador quanto a sua, você deverá baixar (fazer download) os arquivos do seu repositório no GitHub, modificá-los, adicionar para serem "comitados", "comitá-los" e só depois enviá-los (fazer upload) para o seu repositório remoto. Para baixar os seus arquivos você utiliza o seguinte comando:

> git pull origin master

Caso você esteja querendo baixar o repositório de alguém da plataforma, você utiliza o comando:

> git clone (aqui você utiliza o link fornecido pelo GitHub)
