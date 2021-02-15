# Instalando_MySQL_phpMyAdmin

<h1>Instalando o MySQL e o phpMyAdmin no Ubuntu</h1>

Para instalar o MySQL server com o no Ubuntu 18.04 execute os comandos abaixo como superusuário (uma linha por vez):
<blockquote>
<p>
  apt-get update && apt install mysql-server
</p>
</blockquote>

Após o término da instalação, iremos definir uma senha para o root no localhost, digitando os comandos abaixo. Lembre-se de alterar a senha que usamos de exemplo para a sua senha!

No terminal digite:

<blockquote>
<p>
  mysql </br>
ALTER USER 'root'@'localhost' IDENTIFIED WITH mysql_native_password BY 'SUA-SENHA';  </br>
quit
</p>
</blockquote>

Feito isso, você já terá acesso ao usuário "root" em qualquer aplicação que executar no localhost. 
</br></br>
<h1>Instalando o phpMyAdmin </h1>

O phpMyAdmin é uma ferramenta que permite a administração do seu banco através do navegador. Não é recomendável utilizar esta ferramenta em ambientes de produção devido aos riscos de ataques bruteforce e possíveis vulnerabilidades que a aplicação possuir, prefira sempre conexões através de túneis SSH.
</br>
Para instalar o phpMyAdmin, execute o comando abaixo e siga as etapas:
</br>
<blockquote>
<p> apt install phpmyadmin </p>
</blockquote>
<h2>Etapas:</h2>
<ol>
<li> O comando irá lhe perguntar se deseja usar o apache2 ou lighthttp caso você não os tenha instalado anteriormente. Em nosso teste instalamos o apache2. 
</li>
<li>
Selecione "Yes" quando for questionado se deseja que o banco de dados do phpMyAdmin seja configurado usando o dbconfig-common.  
</li>  
<li>
Informe uma senha para o usuário do phpMyAdmin. Esta senha, por razões de segurança, não deve ser a mesma que a informada ao usuário root. Você não precisará desta senha posteriormente.  
</li>  

<li>
Adicione um link simbólico à pasta do phpMyAdmin no diretório de sites do apache2, para isso, utilize o comando abaixo:
</li>
</ol>
<blockquote>
<p> ln -s /usr/share/phpmyadmin /var/www/html </p>
</blockquote>


Agora basta acessar o endereço IP de seu servidor com o diretório "/phpmyadmin", por exemplo.
</br>
<blockquote>
<p> http://167.71.102.227/phpmyadmin </p> </br>
<p> http://localhost/phpmyadmin/ </p>  
</blockquote>

Informe o usuário "root" e sua senha. Esta senha não é a senha do phpMyAdmin.


<h2>Removendo o acesso ao phpMyAdmin</h2>
<p>
Como foi dito anteriormente, deixar o phpMyAdmin acessível em ambientes de produção pode ser muito problemático, portanto para remover seu acesso, basta remover o link simbólico criado anteriormente, usando o comando abaixo:
</p>

<blockquote>
<p>  rm /var/www/html/phpmyadmin </p>
</blockquote>

Após utilizar este comando, o phpMyAdmin não estará mais disponível para ser acessado através de seu navegador.
