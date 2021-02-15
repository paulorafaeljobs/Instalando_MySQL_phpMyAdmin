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

Por padrão a instalação do MySQL permite o acesso de usuários anônimos, utilizados somente para testes e que não são necessários para o ambiente de produção. Pressione Y para removê-los.


<blockquote>
  
  By default, a MySQL installation has an anonymous user,  </br>
allowing anyone to log into MySQL without having to have   </br>
a user account created for them. This is intended only for </br>
testing, and to make the installation go a bit smoother.   </br>
You should remove them before moving into a production     </br>
environment.   </br>
</br>
Remove anonymous users? (Press y|Y for Yes, any other key for No) : Ye

</blockquote>

Para evitar ataques de força bruta, é altamente recomendável desativar o acesso remoto ao usuário "root", permitindo logins para esta conta somente através do localhost. (isto não afeta o phpMyAdmin, que faz login através do localhost). Pressione Y.

<blockquote>
  
Normally, root should only be allowed to connect from  </br>
'localhost'. This ensures that someone cannot guess at </br>
the root password from the network.                    </br>
                                                       </br>
Disallow root login remotely? (Press y|Y for Yes, any other key for No) : Y </br>

</blockquote>  

E por último, a instalação padrão do MySQL vem tabelas de testes que não são necessárias em ambientes de produção, pressione Y para removê-las e Y novamente para aplicar as alterações.

<blockquote>
  <p>
  
  Remove test database and access to it? (Press y|Y for Yes, any other key for No) : Y    </br>
 - Dropping test database...                                                              </br>
Success.                                                                                  </br>
                                                                                          </br>
 - Removing privileges on test database...                                                </br>
Success.                                                                                  </br>
                                                                                          </br>
Reloading the privilege tables will ensure that all changes                               </br>
made so far will take effect immediately.                                                 </br>
                                                                                          </br>
Reload privilege tables now? (Press y|Y for Yes, any other key for No) : Y                </br>
Success.                                                                                  </br>
                                                                                          </br>
All done!                                                                                 </br>
  </p>
</blockquote>

Agora sua instalação do MySQL estará um pouco mais segura, no entanto, ainda estará vulnerável caso utilize softwares inseguros ou mantenha o phpMyAdmin público na internet.



