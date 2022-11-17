Kataloogid on failid
Esialgu on ehk natuke kummaline mأµelda kataloogidest kui erilistest failidest, milles on kirjas seal sisalduvate failide nimed, 
kuid tegelikult vastab see failisأ¼steemi tehnilisele korraldusele.
Niisiis, kataloog on fail, kus on kirjas selles kataloogis sisalduvate failide ja nn alamkataloogide nimed ning viited failide tegelikele asukohtadele.

Õigused:
* r(ead) - lugeda
* w(rite) - kirjutada
* e(x)ecute - kأ¤ivitada

* u(ser) - faili omanik
* g(roup) - faili gruppi kuuluv kasutaja
* o(ther) - mingi muu kasutaja sأ¼steemis, kuulub faili omanikust erinevasse gruppi

bash~$ ls -la
1  2     3     4         5     6
d rwx   r-x   r-x   3   mart users    1 024   12 Mar   1998 ./
d rwx   r-x   r-x   6   mart users    1 024   12 Mar   1998 ../
d rwx   rwx   r-x   2   mart users   23 000   12 Mar   1998 kata
- rw-   r--   r--   1   mart users   30 000   12 Mar   1998 karu
- rwx   r-x   --x   1   mart users   30 000   12 Mar   1998 programm

* (1) kataloogimأ¤rge: esimesed kolm rida on kataloogid, millele viitab mأ¤rge d (ingl. k. directory); 'karu' ja 'programm' on failid.
* (2) faili omaniku õigused faili suhtes
* (3) failiga samasse gruppi kuuluvate kasutajate أµigused faili suhtes
* (4) süsteemi teiste kasutajate أµigused faili suhtes
* (5) faili omanik
* (6) faili grupp

Muutmine tأ¤htedega
      u
      g  +  r
chmod    -  w   fail1 fail2 ...
      o  =  x
      a
kus
u - user; g - group, o - others, a - all,
r - read, w - write ja x -execute

+ lisab أµiguse
- eemaldab أµiguse
= kehtestab vaid mأ¤أ¤ratud أµigused

Muutmine numbriliselt
4 lugemisأµigus
2 kirjutamisأµigus
1 kأ¤ivitamisأµigus

Kataloogi puhul kأ¤ivitamisأµigus tأ¤hendab أµigust sinna siseneda.

----------		0000	ei mingeid õiguseid
---------x		0001	käivitamine
--------w-		0002	kirjutamine
â€“-------wx		0003	kirjutamine ja käivitamine
â€“------r--		0004	lugemine
-------r-x		0005	lugemine ja käivitamine
-------rw-		0006	lugemine ja kirjutamine
-------rwx		0007	lugemine, kirjutamine ja käivitamine
â€“--------t		1000  sticky
â€“-----S---		2000	setgid
â€“--S------		4000	setuid

أµigused    omanik - owner       grupp - group      teised - others
chmod   read write execute    read write execute  read write  execute
0777     4    2      1         4    2      1       4    2       1
0755     4    2      1         4    0      1       4    0       1
0500     4    0      1         0    0      0       0    0       0

0755:
   * 0 - SetUID
   * 7 = 4 + 2 + 1
   * 5 = 4 + 0 + 1
   * 5 = 4 + 0 + 1

Eriأµigused
----------
SetUID
kasutajal peab olema ka käivitusõigus
chmod u+xs fail

chmod u+xs kataloog
midagi ei juhtu

nt:
chmod 4700 fail - ka omanik saab käivitada

SetGID
grupil peab olema ka käivitusõgus
chmod g+xs fail

chmod g+xs kataloog
sellises kataloogis olevad failid on kataloogiga samas grupis

Sticky bit (kleepbitt)
teistel (others) peab olema käivitusõigus
chmod o+xt

* * *

õiguste vaatamine numbriliselt käsureal
stat -c '%A %a %n' *
    %A ligipääsuõigused inimloetavalt
    %a ligipääsuõigused kaheksandsüsteemis
    %n failinimi
vt man stat

umask
-----
Vaikimisi loodavate kataloogide, failide õiguste määramine.
umask määrab, mis õiguseid uuel failil, kataloogil olla ei saa.

hetkel kehtiva vaatamine: umask
ajutiselt määramine: umask 022

umaskâ€™i alusel أµiguste arvutamine

vaikimisi:
kataloogid: 777
failid: 666

umask'i vأ¤أ¤rtus tuleb vaikimisi vأ¤أ¤rtusest lahutada

nأ¤iteks: umask 022
kataloogid: 777 â€“ 022 = 755
failid: 666 â€“ 022 = 644

umask 002 -> 775/664
umask 022 -> 755/644
umask 077 -> 700/600

Kasutamine:
globaalselt:
- /etc/login.defs
- varasemalt /etc/profile
kasutaja: ~/.profile

vajadusel ka faili /etc/pam.d/common-session lisada rida:
session optional pam_umask.so
(libpam-modules peaks olema paigaldatud, vأµib erineda distrote lأµikes)

hard-coded sأ¼steemilaiune sأ¤te
-------------------------------
* faili /etc/pam.d/common-session:
session optional pam_umask.so umask=002
* chfn --other='umask=002' kasutaja (muudab /etc/passwd)
