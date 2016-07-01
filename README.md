# (Escravizando) MacOS

Olá, seja Bem-vindo! Aqui você encontrará um guia passo-a-passo para transformar uma máquina MacOS em um escravo do jenkins.  :metal:

## Pré-requisitos

* Uma máquina [MacOS](http://www.apple.com/br)
* Um Jenkins rodando sua aplicação, seus testes, etc.
* Muitas configurações  :scream:
* Muita paciência  :pray:


## Vamos ao trabalho  :wrench:

Primeiro de tudo, quando a máquina for ligada, atualize o sistema para evitar qualquer imprevisto.

Depois disso, acesse a Apple Store utilizando e/ou criando uma nova conta, e instale o [XCode](https://itunes.apple.com/us/app/xcode/id497799835?mt=12&v0=WWW-NAUS-ITUHOME-NEWAPPLICATIONS&ign-mpt=uo%3D2) que ira fazer o processo de debug das aplicações ios.

Agora que você tem o [XCode](https://itunes.apple.com/us/app/xcode/id497799835?mt=12&v0=WWW-NAUS-ITUHOME-NEWAPPLICATIONS&ign-mpt=uo%3D2) instalado, vamos agora instalar o [HomeBrew](http://brew.sh/), que servirá para instalarmos pacotes que vocẽ irá precisar mas a Apple não. O [HomeBrew](http://brew.sh/) é um gerenciador de pacotes para OS X :tiger:

Para instalar o [HomeBrew](http://brew.sh/) podemos seguir este [Tutorial](https://github.com/Homebrew/brew/blob/master/share/doc/homebrew/Installation.md#installation) ou abrir um Terminal e digitar o seguinte comando:

~~~
$ /usr/bin/ruby -e "$(curl -fsSL https://raw.githubusercontent.com/Homebrew/install/master/install)"
~~~

Depois de instalar o [HomeBrew](http://brew.sh/), vamos instalar o [rbenv](https://gist.github.com/leandrocp/1845803), um gerenciador de versões ruby, similar ao rvm, porém mais "limpo". Pelo terminal, digite: 
~~~
$ brew update
$ brew install rbenv ruby-build
~~~

Logo após a instalação do [rbenv](https://gist.github.com/leandrocp/1845803), Quando a instalação terminar, será preciso adicionar o script de inicialização ao seu arquivo de inicialização do terminal. Execute os comandos à seguir para fazer isso:

~~~
$ echo 'export PATH="$HOME/.rbenv/bin:$PATH"' >> ~/.bash_profile
$ echo 'eval "$(rbenv init -)"' >> ~/.bash_profile
~~~
Reinicie o seu terminal para carregar estas novas configurações, ou execute o comando: 
~~~
$ source ~/.bash_profile.
~~~
Com essas alteração, o [rbenv](https://gist.github.com/leandrocp/1845803) estará pronto.

Se tudo deu certo, você já pode instalar quantas versões do [Ruby](https://www.ruby-lang.org/en/) você quiser. Para saber quais versões estão disponíveis, execute o comando rbenv install -l

~~~
$ rbenv install -l
Available versions:
  1.8.6-p383
  1.8.6-p420
  1.8.7-p249
  1.8.7-p302
  1.8.7-p334
~~~

Neste caso, a versão que será instalada do [Ruby](https://www.ruby-lang.org/en/) será a 1.9.3-p0, podemos mudar para a versão que mais seja apropriada para nosso projeto.

Para não termos problemas com as versões que iremos utilizar, vamos definir e fixar a versão que iremos utilizar. No terminal digite:

~~~
$ rbenv local 1.9.3-p0
$ rbenv global 1.9.3-p0
~~~

Isso fará com que minha versão de [Ruby](https://www.ruby-lang.org/en/) padrão de todo o sistema seja a 1.9.3-p0

Calma que está acabando(essa parte), agora vamos instalar as gems :gem:, um gerenciador de pacotes para a linguagem de programação [Ruby](https://www.ruby-lang.org/en/), no terminal digite:

~~~
$ bundle install
~~~

Agora sim o [Ruby](https://www.ruby-lang.org/en/) está pronto.

Para ajudar na documentação das nossas aplicações, utilizamos [Markdown]() e o [MacDown](http://macdown.uranusjr.com/) ajuda muito nessa tarefa, é um dos melhores editores gratuitos para a plataforma OS X :tiger:. [Clique aqui](http://macdown.uranusjr.com/) para baixar.

Para Facilitar ainda mais nosso trabalho e agilizar nossa instalação do ambiente de desenvolvimento, vamos instalar uma aplicação muito útil, [faststrap](https://github.com/thiagolioy/faststrap)  :running: :dash:, com ele podemos configurar e inicializar nosso ambiente Mac OS para o desenvolvimento com poucos cliques. :computer:

no terminal digite o comando:

~~~
$ faststrap ios
~~~
~~~
We have the follow actions for ios:

INSTALLERS Group:
 - Homebrew
 - Carthage
 - Cocoapods

COMAND_LINE Group:
 - Git
 -XcodeCmdTools
 -bash-completion

TESTS Group:
 - Calabash
 - lcov
 - xctools

CI Group:
 - Fastlane
 - Jenkins

Type the actions you want to install separated by comma (eg. git,xctools) or type * for everything :
~~~

Aqui iremos escolher quais componentes iremos instalar, separando-os por vírgula e com letras minúsculas. Ex: calabash,lcov, xctools,fastlane

Instalaremos agora o Java JDK  :hotsprings:, uma abreviação para Java Development Kit, que é um conjunto de utilitários cuja a finalidade é a permissão para criação de jogos e programas para a plataforma Java. [Clique aqui](http://www.oracle.com/technetwork/java/javase/downloads/jdk8-downloads-2133151.html) para instalar a versão mais recente.

 :warning: **Baixe a versão para MacOS X :tiger:. Exemplo:** ***jdk-8u91-macosx-x64.dmg***
 
Instalaremos também o VirtualBox  :partly_sunny: , uma ferramenta virtualização da Oracle que permite instalar e executar diferentes sistemas operacionais em um único computador sem complicações. [Clique aqui](download.virtualbox.org/virtualbox/5.0.24/VirtualBox-5.0.24-108355-OSX.dmg) para baixar a última versão para OS X  :tiger: ou [Clique aqui](https://www.virtualbox.org/wiki/Downloads) para escolher a versão que preferir.

Agora, para começarmos a pensar nos testes das nossas aplicações [Android](https://developer.android.com/index.html), precisaremos instalar o ambiente de desenvolvimento e seus respectimos emuladores.

Começaremos instalando o Android SDK :wrench:, uma caixa de ferramentas para desenvolvermos e testarmos nossas aplicações [Android](https://developer.android.com/index.html). [Clique aqui](https://dl.google.com/android/android-sdk_r24.4.1-macosx.zip) para baixar a útima versão para OS X :tiger:.

 :white_check_mark: Um outro modo de instalarmos o Android SDK :wrench: é baixarmos pelo brew. No terminal digite:

~~~
$ brew install android-sdk
~~~

Com o comando acima, o Android SDK :wrench: será instalado nesse local: `/usr/local/Cellar/android-sdk/`



Iremos agora instalar o [Genymotion](https://www.genymotion.com/), um dos melhores emuladores :iphone: para testar aplicações [Android](https://developer.android.com/index.html).
 
 :warning: **Antes de começarmos a instalação do [Genymotion](https://www.genymotion.com/), temos que fazer um pequeno cadastro com e-mail :e-mail: e senha :key:**
 
Instalaremos um componente chamado Gerenciador de hardware acelerado [(Intel® HAXM)](https://software.intel.com/en-us/android/articles/intel-hardware-accelerated-execution-manager), um mecanismo de virtualização assistida por hardware (hypervisor) que usa tecnologia de virtualização Intel® (VT) para acelerar o desenvolvimento para [Android](https://developer.android.com/index.html). [Clique aqui]([Android](https://developer.android.com/index.html)) para instalar a última versão.

