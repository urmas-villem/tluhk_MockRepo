Ajastatud toimingud
https://help.ubuntu.com/community/CronHowto
turvalisuse kaalutlustel keelame ajastatud toimingud kasutajatele
sudo nano /etc/cron.deny
sudo nano /etc/at.deny
iga kasutaja uuelt realt

~/.config/autostart/
kaitsta kataloog
nt
sudo chown -R root:root ~/.config/autostart/
sudo chmod -R o+r ~/.config/autostart/

OpenSSH
chmod 700 ~/.ssh
chmod 600 ~/.ssh/*

OpenSSH serveri, kliendi, turvapakettide paigaldus:
sudo apt update && sudo apt install ssh openssh-blacklist* && sudo apt-get clean

Veel sأ¤tteid
------------
/etc/default/apport
enabled=0
service apport restart

Veebiserveri rأ¼ndamine
www.nimi.ee/../../../../../../../../etc/shadow

Vaese mehe VPN
--------------
Sihtkohas OpenSSH serveriga masin vأ¤lisvأµrgus.
Vأµimaldab suunata kogu andmeliikluse ja DNS-pأ¤ringud SSH tunnelisse.

sshuttle https://wiki.itcollege.ee/index.php/Sshuttle

paigaldamine
sudo apt update && sudo apt install sshuttle && sudo apt-get clean

seadistamine
kiireks kأ¤ivitamiseks loome kestprogrammi lأ¼hikأ¤su (aliase):
nano ~/.bash_aliases
alias vpn='sudo sshuttle --dns -Nvr kasutajanimi@sshserver 0.0.0.0/0'
source ~/.bash_aliases

lubame kأµikidel kasutajatel kأ¤ivitada:
/etc/sudoers.d/vpn
Cmnd_Alias VPN=/usr/bin/sshuttle
ALL ALL=(ALL) NOPASSWD:VPN

https://help.ubuntu.com/community/Sudoers
