# First steps on new system

Based on
* https://www.snel.com/support/initial-server-setup-with-debian-10/
* https://www.digitalocean.com/community/tutorials/initial-server-setup-with-debian-10
* https://www.natrius.eu/dokuwiki/doku.php?id=digital:server:hardening
* https://medium.com/viithiisys/10-steps-to-secure-linux-server-for-production-environment-a135109a57c5
* https://gist.github.com/vivianspencer/bc86e2765fc4df09795e
* https://www.tecmint.com/manage-etc-with-version-control-using-etckeeper/
* https://ostechnix.com/reptyr-move-running-process-new-terminal/

apt-get update
apt-get install sudo

adduser linux
usermod -aG sudo linux

groups linux # should show group sudo

test new user ssh
test new user sudo

passwd root

# https://www.tecmint.com/manage-etc-with-version-control-using-etckeeper/

sudoedit /etc/ssh/sshd_config
PermitRootLogin no

sudo systemctl restart sshd.service

sudo apt install fail2ban


sudo cp /etc/fail2ban/jail.conf /etc/fail2ban/jail.local

sudoedit /etc/fail2ban/jail.local
[ssh-ddos]
enabled  = true

sudo service fail2ban restart

sudo apt-get install ufw 

sudo ufw allow ssh
sudo ufw enable
sudo ufw status


sudo apt-get -y install sysstat
sudoedit /etc/default/sysstat
set ENABLED=”true”


Open the file /etc/cron.d/sysstat and change cron job to every 2 minutes

# Activity reports every 10 minutes everyday
*/2 * * * * root command -v debian-sa1 > /dev/null && debian-sa1 1 

sudo service sysstat restart



sudo apt-get -y install acct
sudo service acct start

sudo apt-get -y install logwatch
sudo mkdir /var/cache/logwatch
sudo cp /usr/share/logwatch/default.conf/logwatch.conf /etc/logwatch/conf/
sudo cp /usr/share/logwatch/default.conf/logfiles/http.conf /etc/logwatch/conf/logfiles/


sudo apt update && sudo apt upgrade

 sudo apt-get install network-manager
 sudoedit /etc/NetworkManager/NetworkManager.conf
 managed=true
 systemctl restart network-manager
 
 Passthrough of SATA card to VM
 https://passthroughpo.st/gpu-debian/









