# InstalarProjetoDjango

# No terminal Linux, vamos criar uma pasta para o projeto:

mkdir + nome da pasta

Comando: ls para verificar que a pasta foi criada

comando: cd + nome da pasta para acessar a pasta

Dentro da pasta vai ser criado o projeto Django

Suba o VsCode com o comando no terminal: code .

Em extensão do VsCode, instalar a versão o Phyton.

Abra o terminal do VsCode  para instalação do: Pip

Execute o seguinte comando: sudo apt-get install pip

Instalara o Django em seguida: pip install django

Em seguida vamos verificar tudo que está instalado em nosso sistema

execute o camando: pip freeze > requirements.txt

O requirements.txt é onde aparace os programas que estamos usando e suas versões

Em seguida, vamos criar um projeto no Django

execute o comando: django-admin startproject mysite .  

Após esse comando o Vscode gera o os arquivos
mysite
manege.py

![image](https://github.com/leandroloffeu/InstalarProjetoDjango/assets/112645165/81f97f47-bc28-4d08-bc31-0a1c5590aaa0)

Em seguida, exeture o comando: python3 manage.py runserver

Apos irá aparecer se tudo der certo:

![image](https://github.com/leandroloffeu/InstalarProjetoDjango/assets/112645165/a7c90caf-0484-4812-a277-008b0739509a)


# Configurações básicas no Django quando inicia uma nova applicação.


No seu projeto vá em: settings.py

![image](https://github.com/leandroloffeu/InstalarProjetoDjango/assets/112645165/2aea7285-5bde-4c67-b68c-c5ecdc850785)
Local onde podemos mudar o idioma: 'pt-br'

![image](https://github.com/leandroloffeu/InstalarProjetoDjango/assets/112645165/683315e9-2c86-4f29-a748-68d98a27e83e)
Local onde podemos informar em que horário estamos: 'America/Sao_Paulo'

![image](https://github.com/leandroloffeu/InstalarProjetoDjango/assets/112645165/6f106402-c161-475d-9178-7df8826299b6)
Local onde é informado ao Django onde buscar as imagens: '/static/'

Abaixo realize o seguinte comando: STATIC_ROOT = BASE_DIR / 'satatic'

Irá ficar assim:
![image](https://github.com/leandroloffeu/InstalarProjetoDjango/assets/112645165/bbd826df-e054-4927-991b-5d80c51f0106)

Ele serve para quando iremos colocar o site no ar, o STATIC_ROOT serve para encontrar arquivos estáticos (imagens css ou html)



Configurando:
![image](https://github.com/leandroloffeu/InstalarProjetoDjango/assets/112645165/aec95f66-e3c1-44c4-88fc-4f60a940091b)

Em  ALLOWED_HOSTS = [] é nossa lista onde iremos definir quem poderá acessar o nosso projeto.
A principio irmos configurar assim: ALLOWED_HOSTS = ['127.0.0.1', '.pythonanywhere.com'] (atorizando nossa própia máquina e onde iremos hospedar o nosso site.) 
Caso execute o comoando assim ALLOWED_HOSTS = ['*'] qualquer operação irá acessar o projeto. Portanto é uma segurança a ele.


## Banco de dados no Django

Criando uma APP: Que é uma subpasta que tem a sua finalidade específica de aluma funcionalidade do site

Criando uma APP chamado de blog dando o seguinte comando: python3 manage.py startapp blog

Se tudo der certo, aparecerá uma nova pasta com estrututa (APP) conforme exemplo abaixo:

![image](https://github.com/leandroloffeu/InstalarProjetoDjango/assets/112645165/a85da876-529c-47e6-ac68-7817a5f80617)

Podemos criar quantos APPS quiser. Mas toda vez que se cria um APP necesário registrar esse novo APP.

Seguindo os seguintes passos:

1 - ir em setting.py

2 - ir em Installed_APPS - nele aparecerá uns APPS Deful do própio Django. Nele vamos colocar o nome do APP que criamos conforme imagem abaixo:

![image](https://github.com/leandroloffeu/InstalarProjetoDjango/assets/112645165/ecc712cc-260d-49d0-b724-3efb62e1442d)

Depois para verificar se deu certo, vamos acinar o servidor dando o comando: python3 manage.py runserver

Se aparecer a figura abaixo, é pq deu certo e o foguetinho subiu. kkkk

![image](https://github.com/leandroloffeu/InstalarProjetoDjango/assets/112645165/5143a241-0065-4e57-ac88-c538462ec087)

A mensagem em vermelho, irmeos ver mais a frente... 

Bem, apos o registro da APP iremos criar um modelo. Tipo:

O nosso modelo será de um post de um blog, que contem: (Título - Autor - texto -  data) e essas informações serão coletadas em uma tabela.

Sendo assim iremos criar a tabala dentro do nosso aplicativo que é "blog" em models.py conforme a imagem abaixo:

![image](https://github.com/leandroloffeu/InstalarProjetoDjango/assets/112645165/2476a6d7-e4be-41ac-8f2b-f9c0f9d17d77)

Acessando o tutorial abaixo, podemos usar o modelo de postagem para o blog:

https://tutorial.djangogirls.org/pt/django_models/

![image](https://github.com/leandroloffeu/InstalarProjetoDjango/assets/112645165/68c2ef3f-739d-4e64-8329-ae3232a577ee)

Vamos copiar e colar o modelo em models.py na pasta blog conforme a imagem abaixo:

![image](https://github.com/leandroloffeu/InstalarProjetoDjango/assets/112645165/f424ddaa-2069-4fb4-8d9b-555ee37840a2)

Toda class conforme a a imagem abaixo é um modelo

![image](https://github.com/leandroloffeu/InstalarProjetoDjango/assets/112645165/801d7e36-ef04-4e38-ade1-48e23669f8d9)

Nele terá qual a linha e coluna desse modelo conforme a imagem abaixo:

![image](https://github.com/leandroloffeu/InstalarProjetoDjango/assets/112645165/54bf6a33-1b08-4f80-a287-6488f4d318d6)


Atenção a essa linha:

![image](https://github.com/leandroloffeu/InstalarProjetoDjango/assets/112645165/0c157b66-a78e-41f7-826d-212e78877842)

Essa linha informa que o autor vai ser parte da auto_user_model, quer dizer que o autor vai ser parte da tabela de usuários padrão do Django.
Em on_delete=models.CASCADE quer dizer se algum model for deletado ou se deletar todos os post vão ser deletados em cascata

O metodo abaixo faz atriu a data e hora atual.

![image](https://github.com/leandroloffeu/InstalarProjetoDjango/assets/112645165/d0ddf999-bbb9-4886-8b49-2e4d5a85ce53)

O metodo em seguida vamos ver no Djando ADM mais a  frente...

![image](https://github.com/leandroloffeu/InstalarProjetoDjango/assets/112645165/c79b9e73-2525-4535-99d9-c8f5d3516f38)


Vamos verificar a mensagem em vermelho abaixo:

![image](https://github.com/leandroloffeu/InstalarProjetoDjango/assets/112645165/5143a241-0065-4e57-ac88-c538462ec087)













































