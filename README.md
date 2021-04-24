<!-- omit in toc -->
# Aprenda Rails da maneira Fácil
<!-- omit in toc -->
> Colocando a internet nos trilhos
----

<!-- omit in toc -->
## Indice

- [1. Agradecimento](#1-agradecimento)
- [2. O motivo desse livro](#2-o-motivo-desse-livro)
  - [2.1. A internet descarrilhou](#21-a-internet-descarrilhou)
  - [2.2. Trazendo a simplicidade de Volta](#22-trazendo-a-simplicidade-de-volta)
- [3. Para quem é esse livro?](#3-para-quem-é-esse-livro)
- [4. Como ler esse livro?](#4-como-ler-esse-livro)
  - [4.1. Pratico](#41-pratico)
  - [4.2. Links de Referências](#42-links-de-referências)
- [5. Preparando o Ambiente](#5-preparando-o-ambiente)
  - [5.1. Como instalar o Ruby](#51-como-instalar-o-ruby)
    - [5.1.1. Windows](#511-windows)
    - [5.1.2. Linux](#512-linux)
  - [5.2. Como instalar o Rails](#52-como-instalar-o-rails)
  - [5.3. Como instalar o NodeJS](#53-como-instalar-o-nodejs)
  - [5.4. Editor de Código](#54-editor-de-código)
    - [5.4.1. VSCode](#541-vscode)
    - [5.4.2. Outros Editores](#542-outros-editores)
- [6. O projeto](#6-o-projeto)
- [7. Iniciando o projeto](#7-iniciando-o-projeto)
  - [7.1. Estrutura de Diretórios](#71-estrutura-de-diretórios)
- [8. Tela de Listas de Mercado](#8-tela-de-listas-de-mercado)
  - [8.1. Gerando o primeiro Controller](#81-gerando-o-primeiro-controller)
    - [8.1.1. Explicando o conceito do Controller](#811-explicando-o-conceito-do-controller)
  - [8.2. Escrevendo teste automatizado do Controller](#82-escrevendo-teste-automatizado-do-controller)
    - [8.2.1. A importância dos Testes](#821-a-importância-dos-testes)
  - [8.3. Roteando a requisição](#83-roteando-a-requisição)
    - [8.3.1. O que é uma API RESTFUL?](#831-o-que-é-uma-api-restful)
    - [8.3.2. Usando rake routes](#832-usando-rake-routes)
  - [8.4. Escrevendo a primeira Action](#84-escrevendo-a-primeira-action)
  - [8.5. Escrevendo a primeira View](#85-escrevendo-a-primeira-view)
- [9. Verificando a cobertura de Testes, Sintaxe e Desempenho](#9-verificando-a-cobertura-de-testes-sintaxe-e-desempenho)
  - [9.1. O que são Gemas](#91-o-que-são-gemas)
    - [9.1.1. Fontes que ajudam](#911-fontes-que-ajudam)
  - [9.2. Simplecov](#92-simplecov)
  - [9.3. Rubocop](#93-rubocop)
  - [9.4. Breakman](#94-breakman)

## 1. Agradecimento

## 2. O motivo desse livro

### 2.1. A internet descarrilhou

A década de 2000 começou com o grande estouro da bolha “.com”, porém não foi esse evento que determinou o descarrilhamento da mesma, muito pelo contrário.

Após esse evento começou o que considero a década de ouro da internet e do desenvolvimento de software. Tivemos logo em sequência a assinatura do documento mais importante do século, o famoso manifesto ágil (que assim como a internet também saiu dos trilhos).

Esse documento nos mostrou como devemos desenvolver software, colocou no papel, em poucas palavras, o que devemos valorizar mais e os princípios que devemos seguir.

Junto com ele, poucos anos depois, surge o Rails, framework que colocou em um único lugar as convenções que um software web de deveria seguir. Fazendo com que o desenvolvedor tivesse que focar no seu negócio ao invés de ter que tomar dezenas de micro-decisões técnicas que geram nenhum valor para o cliente final, mas que são necessárias para por um software de pé.

Esses 2 acontecimentos no início da década permitiram um boom de surgimento de novas startups que sem dúvida mudaram o mundo: Twitter, Github, Shopify, Gitlab, Groupon e Airbnb para citar algumas...

Porém, mais um evento importante ocorreu na década de 2000, o surgimento do V8. O motor de leitor de JavaScript do Google permitiu que a linguagem que antes era destina a manipular o DOM da página HTML, funcionasse também no servidor e extremamente rápido.

Com o V8 em mãos, os desenvolvedores decidiram que era hora de mudar tudo, criaram o nodeJs e rapidamente reescreveram (várias vezes cada uma) suas ferramentas favoritas em JavaScript, porém sem nunca gerar convenções, forçando com que cada novo projeto, um mundo de coisas tenham que ser configuradas em conjunto.

Em conjunto com a quebra de convenções no backend, surgiu o Angular e com ele veio junto o conceito de Single Page Aplication (SPA). A ideia era que ao invés deixar o browser controlar as navegações entre páginas, que causavam o mesmo ter que reinterpretar todo o JavaScript/CSS novamente. Você baixava todo o JavaScript uma única vez e por meio do próprio JavaScript você fazia esse controle do que mostrar ou não da página, indo no servidor somente para consultar dados.

Resumindo o SPA, alguém teve a brilhante ideia de reescreve o que o browser já fazia bem em JavaScript, gerando tantos problemas quanto você pode imaginar.

E a partir daí, o desenvolvimento web passou a ser reescrever libs para resolver problemas que antes não existiam.

---

1. https://pragdave.me/blog/2014/03/04/time-to-kill-agile.html

2. https://dayssincelastjavascriptframework.com/

3. https://hackernoon.com/how-it-feels-to-learn-javascript-in-2016-d3a717dd577f

4. https://medium.com/@jmanrubia/escaping-the-spa-rabbit-hole-with-turbolinks-903f942bf52c

### 2.2. Trazendo a simplicidade de Volta

O intuito desse livro é mostrar que a internet pode ser simples, que podemos voltar a desenvolver software focando no problema dos nossos clientes.

Que usando boas convenções para juntar bibliotecas e as funcionalidades que o browser/protocolos já nos fornecem, podemos escrever software sem complicações.

E mesmo assim entregar softwares que funcionam, são dinâmicos, responsivos e funcionam em varias plataformas.

## 3. Para quem é esse livro?

Esse livro é para todos que acreditam em soluções simples e que desejam focar em gerar valor para seus clientes mais do que usar a tecnologia modinha do momento.

Não é necessário ter conhecimento prévio de Ruby, nem de como a internet funciona. Mas é ideal que tenha alguma lógica de programação.

Não iremos cobrir nesse livro a sintaxe em si, mas tentaremos escrever código tão simples que o básico de conhecimento prévio de programação já será o suficiente.

## 4. Como ler esse livro?

### 4.1. Pratico

Eu não sei se acredito na teoria das 10 mil horas, porém tenho plena convicção que programação é uma atividade que demanda prática. “Quando você já resolveu 1000 casos, fica fácil resolver o 1001” Sherlock Holmes

Por isso a ideia desse livro é que ele seja lido em frente a um computador, escrevendo, modificando e testando os códigos aqui propostos.

Iremos juntos concluir um projeto desde o seu início até o fim, passando por todo o desenvolvimento web, como fazer deploy até a geração de um aplicativo mobile.

### 4.2. Links de Referências

No livro eu cobrirei o que é necessário para a conclusão do nosso projeto, porém todo capítulo terá seus links de referência para você se aprofundar mais no assunto caso ache necessário.

Infelizmente a internet ainda é escrita primariamente em inglês, mas sempre que for possível irei procurar links que expliquem em português.

## 5. Preparando o Ambiente

### 5.1. Como instalar o Ruby

O Ruby é uma linguagem dinâmica, fortemente tipada porém com tipagem implícita, conhecida por buscar [maximizar a felicidade do programador](https://rubyonrails.org/doctrine/#optimize-for-programmer-happiness). Foi criada em 1995, no Japão, mas mesmo assim ganhou o ocidente por conta da capacidade que ela dá para o desenvolvedor se expressar.

Difernete do Python que busca ter uma única maneira de fazer algo, o Ruby buscar das as ferramentas necessárias para o desenvolvedor se expressar através de código.

---

1. https://rubyonrails.org/doctrine/#optimize-for-programmer-happiness

#### 5.1.1. Windows

Em construção...

#### 5.1.2. Linux

Provavelmente esse vai ser o primeiro capitulo do livro que pode gerar um pouco de nariz torcido dentro da comunidade do Ruby. Grande parte de comunidade prefere usar o ruby através do [rbenv](https://github.com/rbenv/rbenv).

Fique a vontade de seguir esse caminho, mas eu aprendi à muito tempo atrás a instalar usando o [rvm](https://rvm.io/rvm/install) e ele nunca me falhou ou gerou qualquer dor de cabeça. Então ensinarei aqui nesse livro usando o mesmo.

O Rvm, assim como o Rbenv, é um gerenciador de versões do Ruby, ele permite ter diversas versões diferentes do ruby instaladas ao mesmo tempo no seu computador e isso é muito útil para evitar problemas quando você está trabalhando em projetos diferentes, ou mesmo quando você quer por exemplo testar uma versão mais recente no seu projeto atual.

Abra o seu terminal e digite:

```sh
gpg --keyserver hkp://pool.sks-keyservers.net --recv-keys 409B6B1796C275462A1703113804BB82D39DC0E3 7D2BAF1CF37B13E2069D6956105BD0E739499BDB
```

Esse comando irar adicionar as cahves GPD para verificação do pacote.

Depois basta rodar o comando:

```sh
\curl -sSL https://get.rvm.io | bash
```

Assim que a instalação do rvm iniciar, você pode configurar o perfil do seu terminal para iniciar como login.

Para isso, basta apertar botão direito no seu terminal.

Clicar em preferências > Profiles > Command e marcar o run as login shell.

![configurando terminal como login shell](configurando_terminal_como_login_shell.png)

Por último, pode fechar o terminal e abrir novamente e estamos prontos para instalar o ruby:

```sh
rvm install 3.0
```

A operação pode demorar um pouco pois o rvm irá instalar todas as dependências necessárias.

Assim que finalizar, você pode testar se tudo está correto verificando a versão do ruby.

```sh
ruby --version
    > ruby 3.0.0p0 (2020-12-25 revision 95aff21468) [x86_64-linux]
```

---

1. https://medium.com/@phinfonet/primeiros-passos-com-ruby-instala%C3%A7%C3%A3o-com-rbenv-ab705559fc5c
2. https://rvm.io/rvm/install

### 5.2. Como instalar o Rails

O [Rails](https://rubyonrails.org/) é um framework web MVC que é sem dúvida o carro chefe que move a comunidade ruby.

Existe outros projetos na comunidade que usam o poder de se expressar do ruby. Mas nenhum projeto chega perto da popularidade e da importância do Rails.

Ele ganhou espaço principalmente por **pregar** o conceito de convensão sobre configuração em um momento que os desenvolvedores tinham que gastas semanas configurando XMLs para colocar um projeto Java no ar.

Mas a **doutrina** do rails vai muito além de boas convenções, ele é uma framework com opinião muito forte e aconselho todos a pararem esse livro nesse momento e lerem sobre as opiniões nesse link: https://rubyonrails.org/doctrine/.

O Rails é distribuído através de uma Gema (gem em inglês), que são a forma mais comum de encapsular código no mundo do ruby.

Na prática, além do código do seu negócio, você irá trabalhar com algumas dezenas de gemas direta ou indiretamente no seu código.

As gemas podem ser instaladas através do comando "gem install nome_gem" que já foi disponibilizado junto com a instalação do ruby pelo rvm.

```sh
gem install rails
```

Para testar se a instalação funcionou como esperado.

```sh
rails --version
    > Rails 6.1.3.1
```

Repare que junto com a instalação do rails, outras 37 gemas foram instaladas no processo, que são as dependências que o rails possui.

Iremos mais na frente aprender como gerenciar de forma mais eficiente as gemas que nosso projeto depende. Caso você queira ler mais a fundo na documentação oficial sobre a instalação do rails, segue o link: https://guides.rubyonrails.org/getting_started.html#creating-a-new-rails-project-installing-rails

---

1. https://rubyonrails.org/
2. https://rubyonrails.org/doctrine/
3. https://rubygems.org/
4. https://guides.rubyonrails.org/getting_started.html#creating-a-new-rails-project-installing-rails

### 5.3. Como instalar o NodeJS

Apesar da comunidade de javascript ter, digamos, inovado além da conta. Eles criaram as melhoras ferramentas para lidar com o frontend (afinal foi para isso que o Javascript foi criado).

E o rails não briga contra isso, muito pelo contrário, ele busca abraçar as novidades, mas colocando **convenções** nas mesmas para o desenvolvedor não ter que se preocupar com as centenas de configurações que essas novidades independentemente requerem.

Uma das mudanças recentes do Rails foi adicionar o [Webpack](https://webpack.js.org/) (não se preocupe com ele agora, o rails vai deixar ele pronto para uso) como seu gerenciador de módulos de Javascript padrão.

Por conta dessa decisão, e de outras libs de javascript que o Rails utiliza, vem a necessidade da instalação do [NodeJS](https://nodejs.org/en/).

* No Windows basta baixar o instalador no site oficial:
https://nodejs.org/en/download/

* No linux, a instalação depende da sua distribuição, mas está  tudo muito bem documentado no link
https://nodejs.org/en/download/package-manager/

Além do NodeJS, também é necessário instalar o Yarn, que é um dos seus ~~muitos~~ gerenciadores de dependência.

```sh
npm install --global yarn
```

E para verificar se a instalação funcionou:

```sh
yarn --version
    > 1.22.10
```

PS: Essa decisão de colocar o Webpack por padrão não veio [sem questionamentos](https://rossta.net/blog/why-does-rails-install-both-webpacker-and-sprockets.html), mas no fim acho que foi uma escolha sensata para abraçar os projetos que dependem de muito Javascript **no frontend**.

---

1. https://webpack.js.org/
2. https://nodejs.org/en/
3. https://nodejs.org/en/download/
4. https://nodejs.org/en/download/package-manager/
5. https://rossta.net/blog/why-does-rails-install-both-webpacker-and-sprockets.html

### 5.4. Editor de Código

Uma dúvida que sempre escuto de pessoas que estão iniciando uma nova linguagem de programação, é qual a IDE utilizar para programar nessa linguagem.

Para programar em Ruby, você não precisa de uma IDE que consuma mais memória do que o seu sistema operacional, um editor de texto, com destaque de sintaxe já é suficiente.

#### 5.4.1. VSCode

Porém na última década, os próprios editores de texto evoluiram e um deles, na minha humilde opinião, ganhou o espaço por balancear funcionalidades para o desenvolvedor e consumo de máquina.

E esse editor foi o [VSCode](https://code.visualstudio.com/). É o editor que eu uso no meu dia a dia profissional, ele é gratuito e se encaixa muito bem em outras extensões adjacentes que vamos usar, como o próprio Javascript, scss, e o próprio html.

Para instalar o VSCode basta entrar no site do mesmo https://code.visualstudio.com/#alt-downloads e realizar o download para o sistema operacional que você esteja utilizando.

---

1. https://code.visualstudio.com/
2. https://code.visualstudio.com/#alt-downloads

#### 5.4.2. Outros Editores

1. [**RubyMine**](https://www.jetbrains.com/pt-br/ruby/): Caso você procure um editor mais poderoso e esteja disposto a pagar por isso. O rubymine sem dúvida é o que há de melhor na comunidade.
2. [**TextMate**](https://macromates.com/): Foi onde a comunidade começou. Editor de texto poderoso, extensível, mas que infelizmente só existe para o Mac.
3. [**Sublime**](https://www.sublimetext.com/): Na linha do TextMate, editor de texto poderoso que por muito tempo foi o queridinho da comunidade.
4. [**Vim**](https://www.vim.org/): Aguns dos grandes desenvolvedores que eu conheço, optam por ficar o mais próximo possível do terminal. O vim é na minha opinião o editor mais poderoso embutido no terminal e no mínimo você deveria conhecer caso precise editar algum código dentro de um servidor, ou [tenha que fechar o mesmo](https://stackoverflow.blog/2017/05/23/stack-overflow-helping-one-million-developers-exit-vim/).
5. [**Emacs**](https://www.gnu.org/software/emacs/): Caso você queira que seu editor seja praticamente o seu sistema operacional, esse é o caminho.

---

1. https://www.jetbrains.com/pt-br/ruby/
2. https://macromates.com/
3. https://www.sublimetext.com/
4. https://www.vim.org/
5. https://stackoverflow.blog/2017/05/23/stack-overflow-helping-one-million-developers-exit-vim/
6. https://www.gnu.org/software/emacs/

## 6. O projeto

O projeto que iremos fazer durante os capítulos desse livro foi pensado para passar por diversas características diferentes que um software web pode ter.

Com isso é possível pegar o conhecimento adquirido nesse livro e transportar para outros softwares sem nenhuma dificuldade.

Foi escolhido então o desafio de desenvolver uma lista de mercado, pois é um problema que acredito que grande parte dos leitores já teve e essa experiência prévia ajuda a pensar em nova funcionalidades para serem implementadas como treino a parte desse livro.

## 7. Iniciando o projeto

O rails vem com uma série de comandos de terminal que agilizam muito o desenvolvimento do sistema, o primeiro dele é o que gera o template de um novo projeto.

```sh
rails new rails new simple_market_list
```

Com esse comando, o rails irá criar a estrutura de diretórios da sua aplicação, além disso, irá instalar mais algumas dependências necessárias para o seu projeto rodar. Sejam as dependências de backend, as gemas, seja dependências do frontend, com o yarn.

---

1. https://guides.rubyonrails.org/getting_started.html#creating-the-blog-application

### 7.1. Estrutura de Diretórios

Ao entrar no diretório criado (simple_market_list), você verá que o rails já definiu uma série de pastas onde os seus códigos devem ir.

Acredito que seja bom você ao menos conhecer para que serve cada uma dessas paster e por isso vou colocar a descrição de cada pasta/arquivo criado automaticamente.

Mas caso você esteja ansioso para começar a programar, uma sugestão é que você pule essa parte e volte nela quando estiver relendo esse livro.

```sh
cd simple_market_list
code .
```

*"code ."* é o comando para abrir o VSCode na pasta para começarmos a desenvolver nosso projeto.

![Estrutura de pastas](esturutra_de_pastas.png)

| Pasta / Arquivo                   | Propósito                                                                                                                                                                                                                                                                      |
| --------------------------------- | ------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------ |
| app                               | Nessa pasta é onde o código da sua aplicação irá ser colocado, é nela e na de testes que esforço deve ser gasto                                                                                                                                                                |
| > assets                          | Nesta pasta é onde suas imagens e folhas de estilo irão ser armazenados                                                                                                                                                                                                        |
| > channels                        | Mais a frente nesse livro iremos ver como atualizar a página do usuário quando algum dado no servidor mudar, é nessa pasta que estarão os canais que irão levar as informações de mudança para o usuário                                                                       |
| > controllers                     | Os controllers são a cola entre os seus modelos e suas telas (views).                                                                                                                                                                                                          |
| > helpers                         | São códigos que podem ser rodados em diferentes views. Com o objetivo de reaproveitar a lógicas.                                                                                                                                                                               |
| > javascript                      | É nessa página que o Webpacker irá buscar os seus javascript para disponibilizar os mesmos para o usuário                                                                                                                                                                      |
| > jobs                            | Dentro da estrutura do Rails nos temos o Job para realizar operações assíncronas, que não vivem dentro do ciclo de vida da requisição web                                                                                                                                      |
| > mailers                         | Os mailers são responsáveis por gerenciar os envios de e-mails da sua aplicação                                                                                                                                                                                                |
| > models                          | Aqui vive a lógica da sua aplicação, seus modelos são os responsáveis por buscar, salvar e manipular os seus dados                                                                                                                                                             |
| > views                           | As views são o que o seu usuário vê, são elas que serão processadas pelo servidor e enviadas para o browser                                                                                                                                                                    |
| bin                               | Nessa pasta reside alguns binários utilizados internamente pelo rails                                                                                                                                                                                                          |
| config                            | Convenção sobre configuração não significa 0 configuração. O rails permite alterar todas as configurações de acordo com o que seu projeto necessita e essas configurações ficam nessa pasta.                                                                                   |
| > environments                    | O Rails permite definir diversos ambientes diferentes, cada um podendo ter sua própria configuração. É comum por exemplo no ambiente de desenvolvimento você mostrar a linha que um erro ocorreu, mas você não quer que o seu usuário final veja isso no ambiente de produção. |
| > initializers                    | Ao iniciar o servidor Web o rails executa todos os códigos que estão nessa pasta.                                                                                                                                                                                              |
| > locales                         | O rails já vem preparado para você fazer um site que seja 100% traduzível, com uma ferramenta de I18n muito poderosa, é nessa pasta que fica os arquivos de tradução da sua aplicação                                                                                          |
| > webpack                         | Assim como a pasta environments, a pasta do webpack permite você configurar o mesmo para diferentes ambientes. No geral o Rails já cuidou de tudo                                                                                                                              |
| > application.rb                  | É o arquivo que todos os ambientes "herdam" por padrão                                                                                                                                                                                                                         |
| > boot.rb                         | Esse arquivo carrega todas as suas gemas.                                                                                                                                                                                                                                      |
| > cable.yml                       | É o arquivo que configura qual adaptador o ActionCable, módulo que gerencia como o rails lida com Websocket, irá usar                                                                                                                                                          |
| > credentials.yml.enc             | É normal em aplicações Web você lidar com APIKeys ou outros dados que devem permaneser secretos, mas devem ser compartilhado com todo o time. O arquivo de credêntials é um arquivo criptografado que facilita esse gerenciamente                                              |
| > database.yml                    | É o arquivo que gerencia sua conexão com o banco de dados                                                                                                                                                                                                                      |
| > environment.rb                  | É o arquivo que inicializa sua aplicação                                                                                                                                                                                                                                       |
| > master.key                      | Esse arquivo **não** deve ser versionado, é ele que descriptografa o arquivo de credenciais                                                                                                                                                                                    |
| > puma.rb                         | O rails usa por padrão o webservice puma. É um webservice muito poderoso e é o usado normalmente também em produção. Esse é o arquivo que configura o mesmo                                                                                                                    |
| > routes.rb                       | O arquivo de rotas é o que recebe a requisição Web e decide qual controller#action(método do controller) chamar.                                                                                                                                                               |
| > spring.rb                       | O spring é uma ferramenta introduzida recentemente pelo rails para agilizar a inicialização do sistema.                                                                                                                                                                        |
| > storage.yml                     | Esse arquivo é o responsável por informar para o Rails como/onde anexar seus arquivos.                                                                                                                                                                                         |
| > webpacker.yml                   | É o arquivo de configuração padrão do webpacker                                                                                                                                                                                                                                |
| db                                | É a pasta onde o código referente ao seu banco de dado vai. Vamos ver ela mais a fundo quando falarmos de migração                                                                                                                                                             |
| > seed.rb                         | Esse arquivo é usado para popular o seu banco de dados com dados iniciais que sejam necessários para sua aplicação funcionar                                                                                                                                                   |
| lib                               | Nessa pasta vão extensões do seu código                                                                                                                                                                                                                                        |
| > assets                          | Bibliotecas de frontend que não fazem parte diretamente do seu projeto. Por exemplo uma biblioteca interna da sua empresa que é compartilhada entre diversos projetos devem vir aqui.                                                                                          |
| > tasks                           | Nessa pasta vão as suas Rake tasks, vamos falar um pouco de rake tasks ao longo desse livro. Mas resumidamente são uma maneira simples de criar rotinas que podem ser chamadas na linha de comando.                                                                            |
| log                               | Nesta pasta irá os logs da sua aplicação                                                                                                                                                                                                                                       |
| node_modules                      | Nesta pasta irá as bibliotecas baixadas pelo Yarn                                                                                                                                                                                                                              |
| public                            | Nesta pasta irá o código público e estático da sua aplicação, que pode ser acessado diretamente sem passar por nenhuma camada do rails.                                                                                                                                        |
| storage                           | Está é a pasta padrão onde os arquivos que forem feitos uploads pela sua aplicação vão parar                                                                                                                                                                                   |
| test                              | Esta pasta vai conter os testes automatizados da sua aplicação                                                                                                                                                                                                                 |
| > channels                        | Está pasta irá os testes automatizados dos seus canais                                                                                                                                                                                                                         |
| > controllers                     | Está pasta irá os testes automatiados dos seus controllers                                                                                                                                                                                                                     |
| > fixtures                        | Está pasta irá os dados que seus testes irão carregar no banco de dados. Após cada teste, o banco sempre volta para o estado definido nos fixtures                                                                                                                             |
| > helpers                         | Está pasta irá os testes automatizados dos seus helpers                                                                                                                                                                                                                        |
| > integration                     | Aqui vão os testes pre tendendem testar como várias partes da aplicação se integram                                                                                                                                                                                            |
| > mailers                         | Está pasta irá os testes automatizados dos seus mailers                                                                                                                                                                                                                        |
| > models                          | Está pasta irá os testes automatizados dos seus modelos                                                                                                                                                                                                                        |
| > system                          | Está pasta irá os testes que simulam a utilização do usuário. Necessário um browser sem interface gráfica                                                                                                                                                                      |
| > application_system_test_case.rb | Este arquivo configura qual motor será usado para os testes de sistema                                                                                                                                                                                                         |
| > test_helper.rb                  | Este arquivo vão os métodos comuns que todos os testes podem executar                                                                                                                                                                                                          |
| tmp                               | Está pasta é uma pasta temporária da sua aplicação, os arquivos contidos nela deveriam poder ser deletados                                                                                                                                                                     |
| > cache                           | Está pasta é onde os caches da sua aplicação, se forem definidos para serem salvos em arquivo, vão parar                                                                                                                                                                       |
| > miniprofiler                    | Está pasta é onde os arquivos temporários da gema rack-mini-profiler vão parar                                                                                                                                                                                                 |
| > pids                            | Quando o puma inicia um servidor, ele gera um pid para evitar que dois serviços sejam rodados                                                                                                                                                                                  |
| > storage                         | Está pasta conterá os arquivos temporários criados para realizar upload                                                                                                                                                                                                        |
| > development_secret.txt          | O rails possui uma chave secreta para assinar os cookies criados (ou qualquer coisa que você deseje encriptar), em desenvolvimento/test essa chave é gerada randomicamente nesse arquivo                                                                                       |
| vendor                            | Esta pasta vão os códigos de terceiros que não estão encapsulados em gemas                                                                                                                                                                                                     |
| .browserslistrc                   | Este arquivo descreve quais browsers sua aplicação suporta                                                                                                                                                                                                                     |
| .gitattributes                    | Este arquivo é onde configuramos atributos do git, por padrão o rails marca alguns arquivos para não entrarem na estatistica de linguagem do repositório                                                                                                                       |
| .gitignore                        | Este arquivo contem os arquivos que devem ser ignorados pelo seu sistema                                                                                                                                                                                                       |
| .ruby-version                     | Este arquivo contem a versão do ruby que deve ser usada para rodar seu sisema. Com esse arquivo o rvm já sabe automaticamente qual ruby usar caso você possua mais de um.                                                                                                      |
| babel.config.js                   | Esse é o arquivo de configuração do Babel que é usado para portar o código de javascript moderno para versões antigas dos browsers.                                                                                                                                            |
| config.ru                         | Esse arquivo configura o Rack, que é o middleware utilizado pelo rails para tratar as requisições web. Com o rack é possível por exemplo você ter certeaz requisições sendo processadas pelo Rails e outras por uma outra framework qualquer (Não faça isso)                   |
| Gemfile                           | Esse arquivo vão as gemas que sua aplicação precisa                                                                                                                                                                                                                            |
| Gemfile.lock                      | Após instalar as gemas, as versões instaladas vão para esse arquivo, com o intuito de garantir que todos que estão no projeto utilizem a mesma versão                                                                                                                          |
| package.json                      | Esse arquivo vão as bibliotecas de javascript que sua aplicação precisa                                                                                                                                                                                                        |
| postcss.config.js                 | Esse arquivo é utilizado pelo webpacker para configurar o postcss                                                                                                                                                                                                              |
| Rakefile                          | Esse arquivo é carregado quando você roda as suas tasks criadas dentro da pasta lib                                                                                                                                                                                            |
| README.md                         | Esse é o arquivo que deveria ir o mínimo que os desenvolvedores deveriam saber sobre seu projeto                                                                                                                                                                               |
| yarn.lock                         | Após instalar as bibliotecas de javascript, as versões instaladas vão para esse arquivo, com o intuito de garantir que todos que estão no projeto utilizem a mesma versão                                                                                                      |

Como você pode ver o Rails tomou algumas dezenas de decisões, seja de gemas padrões, estrutura de pastas, configurações padrões dessas gemas, etc.

Durante a vida de um projeto, é comum que algumas dessas configurações sejam alteradas para atender a necessidade do mesmo.

Mas essa decisão de alteração deve ser tomada conforme o projeto cresce e suas especificidades vão surgindo, um desenvolvedor não deveria ter que se preocupar com elas antes mesmo de gerar uma única tela.

## 8. Tela de Listas de Mercado

Agora que já estamos, no terminal, dentro da pasta do projeto, vamos iniciar o servidor

```sh
rails s
```

O *rails s* é uma abreviatura de *rails server*

Agora entre no seu browser preferido e acesse a url: http://127.0.0.1:3000

![você está no rails](voce_esta_no_rails.png)

Pronto, agora podemos começar a escrever nossa própria aplicação.

### 8.1. Gerando o primeiro Controller

O rails vem com uma série de geradores de código ([generators](https://guides.rubyonrails.org/command_line.html#bin-rails-generate)) que ajudam a gerar o código minimo que precisamos para uma determinada tarefa.

Nesse caso vamos utilizar o generator de controller:

Nesse momento, pare o servidor utilizando "ctrl+c" no terminal e rode

```sh
rails g controller market_lists
```

*rails g* é a abreviatura de *rails generate*

Um ponto importante para se perceber é que o nome do controller está no plural. Essa é uma das convensões do rails.

Após executar esse comando, o rails irá criar alguns arquivos para você.

![Arquivos gerados pelo gerador de controller](arquivos_gerados_controller.png)

* O market_lists_controller.rb é onde irá o seu código de controller propriamente dito.
* A pasta views/market_lists é onde deverão ir os arquivos de visualização do seu controller.
* O market_lists_controller_test é onde os testes automatizados do seu controller irão residir
* market_lists_helper os métodos de helper específicos do seu controller
* E por fim o market_lists.scss para caso o seu controller tenha alguma folha de estilo específica

Você pode rodar o comando

```sh
rails generate controller --help
```

Para ter acesso a mais opções caso você queira evitar que alguns desses arquivos seja gerado.

---

1. https://guides.rubyonrails.org/command_line.html#bin-rails-generate

#### 8.1.1. Explicando o conceito do Controller

Conforme já falamos anteriormente, o controller é a cola entre o seu modelo e suas views. É ele quem vai receber as requisições http e decidir quais modelos chamar e quais views apresentar para o usuário.

Ele pode decidir por exemplo apresentar os dados de um controller como um json caso a requisição seja uma chamada de API, renderizar um html caso seja uma chamada direta do browser ou redirecionar por exemplo para a tela de login se o usuário não estiver logado.

Mas cuidado para não colocar lógica de negócio dentro do seu controller. A boa prática é que ele passe as informações necessárias para a camada de modelo, esse com as regras de negócio e baseado no que o modelo retornar, ele tome as decisões.

Chamamos essa prática de ["Fat Model, Skinny Controller"](https://riptutorial.com/ruby-on-rails/example/9609/fat-model--skinny-controller), mas cuidado para seu modelo não ficar ["muito gordo"](https://thoughtbot.com/blog/skinny-controllers-skinny-models).

---

1. https://riptutorial.com/ruby-on-rails/example/9609/fat-model--skinny-controller
2. https://thoughtbot.com/blog/skinny-controllers-skinny-models

### 8.2. Escrevendo teste automatizado do Controller

O próximo passo é escrever o teste automatizado para esse controller, nós queremos que o usuário ao entrar na url da raiz do projeto "/" ou a url "/market_lists" venha escrito "Suas listas de Mercado" e, por enquanto, "Você ainda não possui nenhuma lista".

Abra o arquivo "test/controllers/market_lists_controller_test.rb" que deve estar inicialmente assim:

```rb
require "test_helper"

class MarketListsControllerTest < ActionDispatch::IntegrationTest
  # test "the truth" do
  #   assert true
  # end
end
```

Agora vamos adicionar os (testes)[https://guides.rubyonrails.org/testing.html#functional-tests-for-your-controllers] que descrevem as necessidades apresentadas anteriormente

```rb
require "test_helper"

class MarketListsControllerTest < ActionDispatch::IntegrationTest
  test "Should show Your Market List as title if access root" do
    get root_path
    assert_response :success
    assert_select "h1", text: "Suas listas de Mercado"
  end

  test "Should show Your Market List as title if access specific url" do
    get market_lists_path
    assert_response :success
    assert_select "h1", text: "Suas listas de Mercado"
  end

  test "Should show you don't have any list if don't have any list if access root" do
    get root_path
    assert_response :success
    assert_select "p", text: "Você ainda não possui nenhuma lista"
  end

  test "Should show you don't have any list if don't have any list if access specific url" do
    get market_lists_path
    assert_response :success
    assert_select "p", text: "Você ainda não possui nenhuma lista"
  end
end
```

E rodar os testes

```
 rails test
```

Muito provavelmente nesse momento você vai ter um [erro](https://stackoverflow.com/questions/65479863/rails-6-1-ruby-3-0-0-tests-error-as-they-cannot-load-rexml) dizendo que o Rails não consegue rodar por conta da auxência do 'rexml/document'. Essa é uma gema que foi tirada do padrão do Ruby 3.0.

Abra o arquivo Gemfile e embaixo da linha "ruby '3.0.0'" adicione

```rb
gem 'rexml'
```

E agora rode

```sh
bundle
```

Esse comando irá instalar a gema descrita. E agora podemos rodar novamente:

```sh
rails test
```

Dessa vez os testes vão travar pois não temos o arquivo schema.rb criado. Esse é um arquivo gerado automaticamente pelo rails quando rodamos o comando:

```sh
rails db:migrate
```

Não se preocupe, iremos olhar mais a fundo esses comandos mais a frente.

```sh
rails test
```

Agora os seus testes devem ter rodado, mas, obviamente, sem encontrar os métodos 'root_path' e 'market_lists_path' que usamos nele.

```
Finished in 0.202442s, 19.7587 runs/s, 0.0000 assertions/s.
4 runs, 0 assertions, 0 failures, 4 errors, 0 skips
```

Nesse momento nossos testes estão vermelhos e isso é o esperado.

---

1. https://guides.rubyonrails.org/testing.html#functional-tests-for-your-controllers
2. https://stackoverflow.com/questions/65479863/rails-6-1-ruby-3-0-0-tests-error-as-they-cannot-load-rexml

#### 8.2.1. A importância dos Testes

Apesar do Rails e seu criador ([@DHH](https://twitter.com/dhh)) [não pregarem](https://dhh.dk/2014/tdd-is-dead-long-live-testing.html) exatamente [Test-Driven-Development](https://martinfowler.com/bliki/TestDrivenDevelopment.html), ninguém na comunidade vai descordar da importância de se ter testes.

Seu código tem que ser testado por máquinas e a melhor forma de garantir isso é seguir a prática de "red-green-blue" (vermelho-verde-azul), onde você primeiro escreve o teste, faz ele passar e depois repensa no seu código para ele ser o mais otimizado possível, com a segurança que ele não quebrou nada.

Os testes no longo prazo vão permitir você mudar o comportamento de uma parte do sistema sabendo que não quebrou outra.

Os testes vão servir como uma documentação testável da sua aplicação. Onde um desenvolvedor vai poder entender qual a lógica esperada de uma determinada classe, sem ter que entende-lo.

Repare no código que escrevemos:

```rb
class MarketListsControllerTest < ActionDispatch::IntegrationTest
  test "Should show Your Market List as title if access root" do
    (...)
  end

  test "Should show Your Market List as title if access specific url" do
    (...)
  end

  test "Should show you don't have any list if don't have any list if access root" do
    (...)
  end

  test "Should show you don't have any list if don't have any list if access specific url" do
    (...)
  end
end
```

A idea é que seu código descreva para um humano o comportamento de uma classe.

E vai ser seguindo essa ideia que vamos escrever o restante desse livro.

---

1. https://twitter.com/dhh
2. https://dhh.dk/2014/tdd-is-dead-long-live-testing.html
3. https://martinfowler.com/bliki/TestDrivenDevelopment.html

### 8.3. Roteando a requisição

O caminho dos dados da sua aplicação começa sempre no routes.rb. É ele que o Rails vai olhar para saber para onde enviar a requisição HTTP que chegar no servidor.

O caminho GET /market_lists vai ser apontado para o controller market_lists_controller, já o GET /items vai para o controller items_controller.

O caminho GET / vai também para o market_lists_controller.

É nesse arquivo que vamos razer esse mapeamento de DeXPara.

---

Para isso, edite o seu arquivo routes.rb

e adicione as linhas

```rb
Rails.application.routes.draw do
  # For details on the DSL available within this file, see https://guides.rubyonrails.org/routing.html
  resources :market_lists
  root to: 'market_lists#index'
end
```

E assim o Rails vai criar os mapeamentos necessários para o seu recurso de market_lists, gerando uma API Restful.

Para saber mais sobre as rotas:

---

1. https://guides.rubyonrails.org/routing.html

#### 8.3.1. O que é uma API RESTFUL?

A arquitetura de comunicação REST foi proposta por Roy Fielding em sua tese de [doutorado em 2000](https://www.ics.uci.edu/~fielding/pubs/dissertation/rest_arch_style.htm).

Essa arquitetura, ao invés de determinar como uma API deve ser construída, ela define algumas limitações que a api deve ter.

São elas:

1. Parte de nenhuma limitação

Nenhuma outra limitação prévia é necessária

2. Client-Server

O cliente não pode conhecer previamente nenhuma especificidade do servidor e o servidor não pode conhecer nenhuma especificidade do cliente.

Podendo os dois evoluírem separadamente

3. Stateless

O servidor não pode guardar estado, o que obriga que todas as informações necessárias para se obter a resposta tem que estar contida na mensagem.

Com esse limitação é possível escalar o servidor de maneira simples, dado que cada nó sempre vai ter todas as informações necessárias para processar a requisição.

4. Cache

As respostas do servidor devem poder ser marcadas como “cacheáveis” ou não.

5. Interface uniforme

A interface de comunicação deve ser uniforme entre os componentes da rede. Não existe diferença no formato da mensagem se você está trafegando um vídeo ou um texto.

6. Comunicação em camada

Ser possível adicionar camadas de recebedores entre as partes.

---

Além das restrições impostas pelo REST, ela define alguns atributos que a comunicação deve ter:

1. Recurso

O recurso é o elemento conceitual da requisição: “Listas de mercado”, “Item da Lista”, “Última lista”, etc

2. A url que aponta para esse recurso

/market_lists -> Listas de mercado
/market_list/1/items/2 -> Item com id 2, da lista com id 1
/last_market_list -> Retorna a última lista de mercado do usuário

3. Representação

Como esse recurso vai ser apresentado? Um html, JSON, uma imagem, Excel, um csv, etc.

4. Metadados da Representação

Data que foi alterada pela última vez, tipo da mídia, etc.

5. Metadados do Recurso

Link de url alternativo, variedade, etc

6. Controle do Dado

Se deve ser cacheado, o propósito e o significado da mensagem.

---

Em cima dessas restrições, foi criado o [Richardson Maturity Model](https://martinfowler.com/articles/richardsonMaturityModel.html), que é um modelo para saber a maturidade da sua API em relação ao REST.

Nesse modelo você precisa ter 4 níveis:

1. Level 0

Usar somente o HTTP como mecanismo de transferência.

2. Level 1

A sua API aponta para os recursos usando a URL.

3. Level 2

Usar os verbos do HTTP como diferenciador da requisição. Uma requisição GET busca dados, uma requisição POST envia dados.

4. Level 3

A URL representar o estado da aplicação: "/market_lists?open=true" trazer somente as listas abertas e "/market_lists?open=false" trazer somente as fechadas.

Atingir o 3 nível é o que consideramos o que temos de melhor na internet até hoje (desculpe pessoal do GraphQL).

---

Como esperado, o Rails já vem preparado para ajudar vocês fazer a sua aplicação ser Restful respeitando de maneira simples todas as restrições e utilizando da melhor forma possível os atribútos que o próprio protocolo da WEB já fornece.

---

1. https://www.ics.uci.edu/~fielding/pubs/dissertation/rest_arch_style.htm


2. https://martinfowler.com/articles/richardsonMaturityModel.html


#### 8.3.2. Usando rake routes

Para verificar quais rotas foram geradas pelo Rails na etapa anterior, o mesmo fornece um atalho no terminal

```sh
rails routes
```

No terminal você vai ver que o rails listou tanto as suas rotas, quanto as rotas criadas por ele para o activestorage por exemplo.

Para filtrar somente suas rotas

```sh
rails routes | grep market_list
    market_lists GET    /market_lists(.:format)                                                                           market_lists#index
                    POST   /market_lists(.:format)                                                                           market_lists#create
    new_market_list GET    /market_lists/new(.:format)                                                                       market_lists#new
edit_market_list GET    /market_lists/:id/edit(.:format)                                                                  market_lists#edit
        market_list GET    /market_lists/:id(.:format)                                                                       market_lists#show
                    PATCH  /market_lists/:id(.:format)                                                                       market_lists#update
                    PUT    /market_lists/:id(.:format)                                                                       market_lists#update
                    DELETE /market_lists/:id(.:format)                                                                       market_lists#destroy
            root GET    /                                                                                                 market_lists#index
```

O comando grep filtra o retorno de um outro comando no terminal.

Repare que o rails separa a sua requisição em alguns blocos:

market_lists GET    /market_lists(.:format) market_lists#index

1. market_lists -> É um helper que pode ser chamado na sua aplicação para apontar para a sua rota, é comum usar esses helpers para montar as urls quando necessário. Ele pode ser sufixado com _path onde ele vai por somente o /market_lists ou com _url onde ele vai por toda a url como http://localhost:3000/market_lists

2. GET -> É o método HTTP usado

3. /market_lists(.:format) -> É a url que vai chegar na requisição para ativar essa linha

4. market_lists#index -> É o controller e a #action que vai ser chamado

Agora, se você rodar novamente seus testes

```sh
rails test
```

E você vai ver que agora o erro que vai ser dado é que a action não está definida no seu controller.

### 8.4. Escrevendo a primeira Action

As actions nada mais são do que os métodos dos controllers, elas podem ter qualquer nome, porém é uma boa prática que os controllers possuam no máximo as seguintes actions:

1. index
A action que vamos criar agora é a responsável por listar os recursos necessários

2. show
Essa action é a responsável por mostrar os detalhes de um único recurso selecionado

3. new
Essa action é a responsável por mostrar o formulário de criar um novo recurso

4. create
Essa action é a responsável por salvar os dados do formulário de criação

5. edit
Essa action é a responsável por mostrar o formulário de edição

6. update
Essa action é a responsável por salvar os dados do formulário de edição

7. destroy
Essa action é a responsável por deletar um recurso do banco

Se retringir somente a essas actions e quebrar em mais controllers quando necessário [ajudam a manter o código fácil de entender](http://jeromedalbert.com/how-dhh-organizes-his-rails-controllers/), permitindo que olhando somente para a url da requisição, qualquer desenvolvedor que conheça a estrutura do Rails saiba qual controller/action a requisição está chamando. Quando é necessário algum método além desses 7, normalmente é a hora de criar um novo controller.

```sh
The action 'index' could not be found for MarketListsController
```

Voltando a action index que o nosso teste está pedindo, dentro do nosso controller, vamos criar o método index:

```rb
class MarketListsController < ApplicationController
  def index
  end
end
```

Ao rodar os testes novamente:

```sh
rails test
    (...)
    (...)MarketListsController#index is missing a template for request formats: text/html
    (...)
```

Agora os testes apontam que ele não encontrou o template no formato html para renderizar.

------------

1. http://jeromedalbert.com/how-dhh-organizes-his-rails-controllers/


### 8.5. Escrevendo a primeira View

Aqui entramos novamente em convenção sobre configuração.

A primeira dela é que a rota gerada para o index ('rails routes | grep market_list' caso você queira verificar a informação) diz que você pode passar o formato esperado pelo template.

```sh
market_lists GET /market_lists(.:format) market_lists#index
```

Como não passamos nenhum formato específico, como por exemplo .json, o rails espera renderizar um template html.

A segunda convenção sobre configuração é que as actions por **padrão** renderiza o template que esteja na pasta dentro de views/nome_do_controller/nome_da_action.formato.processador

Nesse nosso caso, views/market_lists/index.html.erb

O [ERB](https://docs.ruby-lang.org/en/2.3.0/ERB.html) é um acrônimo para Embedded Ruby Template, ele permite adicionar código ruby dentro do seu template html.

O ERB já vem imbutido dentro do ruby e é o processador padrão do Rails.

Nesse artigo vamos nos ater a ele, mas, para conhecimento, existem outros processadores como o [slim](http://slim-lang.com/), [haml](https://haml.info/) que são concorrentes diretos do erb e alguns que não são voltados para html, mas sim outros formatos, como o [axlsx](https://github.com/caxlsx/caxlsx_rails) que é voltado para renderizar arquivos em excel.

Pessoalmente acho que a diferença entre o ERB, Slim e Haml é nada mais do que gosto pessoal de quem desenvolveu cada um deles e nesse caso, costumo escolher o que vem por padrão no rails.

Após criar o arquivo index.html.erb dentro de app/market_lists/

Rode o teste novamente:

```sh
rails test
```

Agora nossos testes estão reclamando que nosso arquivo não possui o elemento html h1 e um elemento html p

Vamos arrumar esse problema agora

```html
<h1></h1>
<p></p>
```

Rode o teste novamente:

```sh
rails test
```

O erro agora mudou dizendo que o texto esperado não se encontra dentro dos elementos h1 e p.

Editamos o arquivo agora para:

```html
<h1>Suas listas de Mercado</h1>
<p>Você ainda não possui nenhuma lista</p>
```

Rode o teste novamente:

```sh
rails test
    (...)
    Finished in 0.203206s, 19.6844 runs/s, 39.3688 assertions/s.
    4 runs, 8 assertions, 0 failures, 0 errors, 0 skips
```

Pronto, agora que todos os nossos testes passaram, podemos dar uma olhada no browser.

```sh
rails s
```

Agora se você acessar sua página local, irá ver que a imagem de "You are on Rails" deu lugar a nossa página recem construída.

![Nova Home](home_page.png)

Tembém é possível notar um pequeno número no canto superior esquerdo.

Esse número é o profiler do rails, ele indica quanto tempo a sua página demorou para carregar e clicando nele, é possível ver o porque a sua página demorou aquele tempo.

![Profiler](home_profiler.png)

Agora, também acessando a página /market_lists, também caímos na mesma página.

![Market List](market_list_page.png)

O tempo consideravelmente menor se dá pois o rails verifica na primeira vez que o servidor é requisitado uma série de operações são realizadas, como, por exemplo, se você rodou todas as migrações do seu banco de dados ou está com seus assets disponibilizados corretamente para o servidor.

---

1. https://docs.ruby-lang.org/en/2.3.0/ERB.html
2. http://slim-lang.com/
3. https://haml.info/
4. https://github.com/caxlsx/caxlsx_rails

## 9. Verificando a cobertura de Testes, Sintaxe e Desempenho

Até o momento, fizemos um desenvolvimento guiado pelo teste que escrevemos. Porém em projetos maiores, envolvendo vários desenvolvedores e algumas dezenas de milhares de linhas de código é fácil esquecer de testar algum if, ou mesmo ao refatorar uma parte do código, fazer com que ela deixe de ser coberta.

Outro problema que também encontramos em projetos maiores do que o desse livro, são os desenvolvedores não seguindo um mesmo [estilo de código](https://github.com/rubocop/ruby-style-guide) (tamanho da identação, espaço depois da virgula, número de linhas entre os os métodos e outras boas práticas que parecem bobeira, mas que deixa o código mais legível).

Para resolver esses problemas, o Rails disponibiliza gemas verificar a cobertura do seu código e fazer análise de código para saber se todos estão seguindo o estilo acordado.

----

1. https://github.com/rubocop/ruby-style-guide

### 9.1. O que são Gemas

Conforme já falado anteriormente nesse livro, as gemas são nada mais do que uma forma de você encapsular e distribuir código ruby.

Existem milhares (talvez milhões?) de gemas disponíveis para ajudar o desenvolvedor a atingir o seu objetivo.

O próprio rails é uma gem, que por usa vez tem como dependência outras dezenas de gemas.

A sua utilização varia de coisas complexas como frameworks, até coisas mais simples como, fazer chamadas http, ou fazer conexão com bancos diferentes.

Porém tome cuidado, é comum as pessoas iniciando no mundo do rails buscarem gemas para resolver todos os problemas e possivelmente vão achar uma que realmente resolva.

Mas cada nova dependência no seu projeto é uma possível fonte de problema no futuro para [atualizar o código](https://github.blog/2020-08-25-upgrading-github-to-ruby-2-7/), [compatibilidade de licença](https://dev.to/cseeman/what-s-up-with-mimemagic-breaking-everything-he1) ou possível [falha de segurança](https://stackoverflow.com/questions/56712510/github-warns-security-problem-about-omniauth-gem).

Por isso é sempre importante tentar ficar com o que o rails/ruby já fornecem para você, mas caso tenha algo em específico que você precisa, verificar se a gema ainda é mantida, tem um aval da comunidade são boas práticas para escolher qual dependência adicionar no seu projeto.

———

* https://github.blog/2020-08-25-upgrading-github-to-ruby-2-7/
* https://github.blog/2018-09-28-upgrading-github-from-rails-3-2-to-5-2/
* https://dev.to/cseeman/what-s-up-with-mimemagic-breaking-everything-he1
* https://stackoverflow.com/questions/56712510/github-warns-security-problem-about-omniauth-gem


#### 9.1.1. Fontes que ajudam

https://rubygems.org/gems
https://www.ruby-toolbox.com/

### 9.2. Simplecov

### 9.3. Rubocop

### 9.4. Breakman
