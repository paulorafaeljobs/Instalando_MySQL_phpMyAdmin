<h1>Aumentando a segurança do servidor MySQL</h1>

Para garantir uma maior segurança de seu servidor, é altamente recomendável executar o comando "mysql_secure_installation", que irá remover os usuários anônimos, tabelas de testes e remover o acesso remoto ao usuário root. 

<blockquote>
  /usr/bin/mysql_secure_installation
</blockquote>

Em seguida, várias perguntas serão realizadas pelo script. Primeiramente, informe a senha do usuário root do MySQL

<blockquote>
  Securing the MySQL server deployment. </br>

  Enter password for user root: [digite a senha do usuário root do MySQL]
</blockquote>

O script irá lhe perguntar se deseja ativar o plugin "validate password", que força que os usuários dos banco de dados tenham senhas seguras. Em nosso caso, não ativamos este plugin pois já utilizamos senhas seguras. Selecione "N" e aperte enter.

<blockquote>

VALIDATE PASSWORD PLUGIN can be used to test passwords </br>
and improve security. It checks the strength of password  </br>
and allows the users to set only those passwords which are  </br>
secure enough. Would you like to setup VALIDATE PASSWORD plugin?  </br>
</br>
Press y|Y for Yes, any other key for No: N  </br>

</blockquote>
Em seguida você será questionado se deseja alterar a senha do root do MySQL, selecione não digitando "N".

<blockquote>
Using existing password for root.  </br>
Change the password for root ? ((Press y|Y for Yes, any other key for No) : N  </br>
</blockquote>


