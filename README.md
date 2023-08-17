# como-desinstalar-completamente-o-lamp-do-linux-ubuntu
Como desinstalar completamente o LAMP do Linux Ubuntu

# Isso removerá o Apache.
sudo service apache2 stop
sudo apt-get purge apache2 apache2-utils apache2.2-bin 
sudo apt remove apache2.*
sudo apt-get autoremove
whereis apache2
Repita o comando abaixo para todos que mostrar no comando acima.
sudo rm -rf /etc/apache2 

# Isso removerá a versão do PHP. Digite sua versão do php antes de executar o comando abaixo. Estou usando o php 8.0.x mude para sua versao.

php --version
sudo apt-get purge `dpkg -l | grep php8.0| awk '{print $2}' |tr "\n" " "`
sudo apt-get purge php8.*
sudo apt-get autoremove --purge
whereis php
sudo rm -rf /etc/php
sudo apt update -y
sudo apt upgrade -y
php --version

# Isso removerá o MYSQL
sudo service mysql stop
sudo apt-get remove --purge *mysql\*
sudo apt-get remove --purge mysql-server mysql-client mysql-common -y
sudo rm -rf /etc/mysql
sudo apt-get autoremove
sudo apt-get autoclean

# Isso reiniciar seu servidor
sudo reboot
