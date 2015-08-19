Meteor TODO com Angular Js
==========================

Testando Meteor com Angular JS, utilizando ambiente de desenvolvimento remoto e realizando deploy na heroku.

Você precisará ter uma conta nos seguintes lugares
--------------------------------------------------
* ambiente de desenvolvimento remoto - https://c9.io (cloud9)
* ambiente de produção - https://www.heroku.com
* repositório - https://github.com

Criando nova app meteor no cloud9
---------------------------------
0. crie um novo workspace com template Meteor
0. ***`meteor add urigo:angular`*** - adicione a biblioteca angular ao projeto
0. ***`meteor --port $IP:$PORT`*** - para rodar a aplicação (ip e port são colocados pelo cloud9)
0. ***`git init`*** - se for publicar no git ou criar app na heroku primeiro crie um repositorio local
0. ***`git add .`*** - adicione os arquivos ao repositorio local, "." para pegar todos os arquivos
0. ***`git commit -m "initial repository"`*** - após adcionar, você precisará comitá-los no git local
0. para salvar seus arquivos remotamente no git, primeiro crie o repositorio no git
0. ***`git remote add origin <url server git>`*** - depois adicione o repositorio remoto no ambiente
0. ***`git push origin master`*** - depois de um push dos arquivos para o brunch remoto

Criando / instalando meteor do zero no cloud9
---------------------------------------------
0. ***`curl https://install.meteor.com/ | sh`*** - instale o meteoro no ambiente
0. ***`meteor create <app-name>`*** - crie a aplicação meteor
0. ***`cd <app-name>`*** - para rodar a aplicação você precisará entrar na pasta criada com nome da app
0. ***`meteor --port $IP:$PORT`*** - rode a app

Criando o app no ambiente de produção/deploy heroku no cloud9
-------------------------------------------------------------
0. ***`heroku create <app-name> --stack cedar --buildpack https://github.com/AdmitHub/meteor-buildpack-horse.git`*** - cria o app no heroku utilizando um buildpack para meteor
0. ***`heroku addons:add mongolab --app <app-name>`*** - adciona o addons mongolab na app
0. ***`heroku config:set ROOT_URL=https://<app-name>.herokuapp.com --app <app-name>`*** - configura a variavel de ambiente, necessário para o deploy
0. ***`git push heroku master`*** - realiza o deploy no ambiente da heroku

Configurando o heroku para deploy automático de commits no git
--------------------------------------------------------------
0. acesse o app criado na heroku e na aba deploy escolha a opção github
0. conecte ao projeto do github
0. habilite o deploy automatico

Outros commandos úteis
----------------------
* ***`git remote -v`*** - mostra as conexões remotas criadas no git
* ***`git remote rm <conexao>`*** - remove um conexao git
* ***`heroku logs --app <app-name>`*** - mostrar o log de uma aplicação heroku
* ***`sudo <command>`*** - executar comando como root/admin
* ***`apt-get <command> <app>`*** - installar/atualizar/remover apps
* ***`git status`*** - mostrar status do git (updates/commits)
* ***`git push --set-upstream origin master`*** - caso precise criar o branch master remotamente
