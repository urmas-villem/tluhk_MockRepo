Tuuma paigaldamine

Tunni sisu

Nأ¼أ¼d kui kogu see igav vأ¤rk on selja taga, rأ¤أ¤gime parem tuuma paigaldamisest ja muutmisest. Sأ¼steemi vأµib paigaldada mitu tuuma. On veel meeles peatأ¼kk alglaadimisest? Alglaaduri GRUB menأ¼أ¼st saab valida, millise tuumaga sأ¼steem kأ¤ivitada. Vaikimisi kأ¤ivitatakse kأµige uuem kui peale tuuma paigaldamist on ka alglaadur uuendatud.


Et tuvastada sأ¼steemi tuuma versioon, kasuta kأ¤sku:

$ uname -r
3.19.0-43-generic
Uname kأ¤sk kuvab sأ¼steemi informatsiooni, -r kuvab tuuma vأ¤ljalaskeversiooni.


Linuxi tuuma vأµib paigaldada mitut moodi. Vأµib laadida alla lأ¤htepaketi ja kompileerida (seda vأ¤ga ei soovita teha) kuid soovitav on seda teha kasutades paketihaldusvahendeid ja paigaldades alati uusimast tuuma versioonist sأµltuvad metapaketid - need uuenevad automaatselt ehk siis kogu sأ¼steemi uuendades (sudo apt update && sudo apt dist-upgrade && sudo apt clean) uueneb ka tuum koos pأ¤istega uusima versiooni peale.


NB! Peale tuuma uuendamist tuleb alati ka kأ¤ivitada alglaaduri uuendamise kأ¤sku sudo update-grub, et teavitada uuema tuuma paigaldamisest - siis teab alglaadur GRUB ka uusimat tuuma kasutusele vأµtta jأ¤rgmise taaskأ¤ivitamise ajal. Kuigi أ¼ldjuhul tarkvara tأ¤ielik uuendamine (dist-upgrade) kأ¤ivitab ka alglaaduri uuendamise siis praktikas on mأ¤rgata endiselt vana tuuma versiooni pealt kأ¤ivitumist - seega ei ole see reegel ja kindluse mأµttes tasub alati peale uue versiooni tuuma paigaldamist uuendada ka alglaadur. Isegi kui alglaadurit uuendada korduvalt siis ei mأµju see kuidagi halvasti sأ¼steemile.


On olemas palju erinevaid tuuma versioone, nأ¤iteks LTS (Long Term Support ehk pikaajalise toega) ja on ka muidugi veel uuemaid ning vingemaid, millest tuleb juttu allpool. Versioonide vahel vأµib olla vأ¤ga palju erinevusi ja vأµib juhtuda, et kasutaja tahab proovida erinevaid tuumasid. أœldiselt vأµib alati ka uusimaid versioone proovida - ka need tأ¶أ¶tavad ja lisavad أ¼ldjuhul uusima riistvara tuge ja parandatud saavad ka turvavead. Eriti just turvalisuse seisukohast lأ¤htuvalt vأµiks sأ¼steemis kasutada alati uusimat tuuma ja peale uusima paigaldatud tuuma pealt tأ¶أ¶tamises veendumist eemaldada vanad tuumad.


Mأµistlik on otsida uusimad LTS-versiooni metapaketid ja paigaldada need - siis sأ¼steemi uuendamise (dist-upgrade) kأ¤igus uuendatakse alati uusima versiooni pikaajalise toega (LTS) tuuma peale:

$ sudo apt search linux-image-generic-lts
$ sudo apt search linux-headers-generic-lts
LTS-versioonid tulevad vأ¤lja 2 aasta tagant aprillikuu lأµpus. Need on rohkem testitud ja sobivad paremini ka missioonikriitilistes kohtades kasutamiseks.


Leitud tulemustest tuleks paigaldada viimane ehk siis uusim ja olla nأµus ka sأµltuvustena uusimate tuuma ja selle pأ¤iste versioonide paigaldamisega. Uusima versiooni saab teha kindlaks kasutatava Linuxi koodnime jأ¤rgi, siin toodud nأ¤ide on Ubuntu Linuxi kohta ja see peaks kehtima ka teiste Debiani ja Ubuntu baasil tehtud Linuxite kohta. Ei tohi unustada ka eespool kirjeldatud alglaaduri uuendamist uusima tuuma kasutuselevأµtmiseks. Ei maksa karta, et tuuma ja pأ¤isefailid on mأµeldud uuemale Ubuntu LTS-versioonile - need tأ¶أ¶tavad ka vanemate LTS-versioonidega.


Ubuntu koodnimed on toodud siin tabelis:

https://wiki.ubuntu.com/Releases
https://wiki.ubuntu.com/DevelopmentCodeNames
Oma Ubuntu koodnime vaatamiseks:

lsb_release -cd
Seda nأ¤eb veel ka nأ¤iteks cat /etc/lsb-release abil.

Linuxi tuuma ja pأ¤ise metapakettide paigaldamine, siin nأ¤iteks Ubuntu 16.04 LTS Xenial Xerus:

$ sudo apt install linux-image-generic-lts-xenial linux-headers-generic-lts-xenial linux-image-generic linux-headers-generic && sudo apt clean && sudo update-grub
Seejأ¤rel arvuti taaskأ¤ivitada vأ¤rskelt paigaldatud tuumaga (sudo reboot). On ju lihtne? Tأ¤psustada saab ka versiooninumbrit, metapakettide asemel vأµib paigaldada ka konkreetsed versioonid kuigi see ei ole kأµige parem mأµte kuna sأµltub konkreetsest tuuma ja selle pأ¤ise versioonist, mis ei uuene ja seetأµttu on kavalam on paigaldada eespool kirjeldatud automaatselt uuenevad metapaketid.

Linuxi tuum uueneb pidevalt ja sellega kaasneb parem riistvara tugi, vigade parandused ja seelأ¤bi ka parem turvalisus, kogu sأ¼steemi parem tأ¶أ¶tamine. Seetأµttu on oluline kasutada vأµimalikult uusimat tuuma ja vanad eemaldada.


Kui metapaketid paigaldatud siis edaspidi toimub uusimate tuumade ja pأ¤iste paigaldus automaatselt kogu sأ¼steemi uuendades:

$ sudo apt update && sudo apt dist-upgrade && sudo apt clean
Tuleb vaid ise jأ¤lgida kui uuema LTS-versiooni tuum muutub kأ¤ttesaadavaks ka vanematele versioonidele ja siis on soovitav see kasutusele vأµtta.

Vanade tuumade eemaldamine
Kui uusim LTS-versiooni tuum paigaldatud, alglaadur uuendatud, sأ¼steem taaskأ¤ivitatud ja veendutud uname -r abil, et tأ¶أ¶tatakse uusima tuuma pealt siis tuleks vanad ja kasutuses mitteolevad tuumad turvalisuse kaalutlustel ka eemaldada.


Vaatame esmalt, millised tuumad on paigaldatud:

$ dpkg --get-selections | grep linux-image

$ dpkg --get-selections | grep linux-headers
vأµi ka

$ dpkg -l | grep linux-image

$ dpkg -l | grep linux-headers

Paigaldatud tuumi, pأ¤iseid nأ¤eb ka kui vaadata kataloogi ls -l /boot - tuum on nimega vmlinuz ja teised sama versiooninumbriga failid moodustavadki tuuma komplekti koos pأ¤ise ja kأµige muu juurdekuuluvaga.

RPM-pأµhistes Linuxites nأ¤eb paigaldatud tuumi kأ¤suga rpm -q kernel

Seejأ¤rel veendume, millise tuuma versiooni pealt arvuti hetkel tأ¶أ¶tab: uname -r. Kui tأ¶أ¶tab uusima pealt siis vأµib kohe asuda vanu eemaldama, vastasel korral tuleb uuendada alglaadurit ja arvuti taaskأ¤ivitada: sudo update-grub && sudo reboot

Vanade tuumade eemaldamiseks on uuematel Ubuntu versioonidel olemas vأµimalus:

$ sudo purge-old-kernels
... see eemaldab kأµik vanad tuumad ja jأ¤tab alles kaks viimast.

Kui soovitakse alles jأ¤tta vaid viimane siis:

$ sudo purge-old-kernels --keep 1 -qy
--keep 1 hoiab alles vaid viimase tuuma versiooni
-q teeb ilma vأ¤ljundit nأ¤itamata (quiet)
-y on vaikimisi nأµus.
Lisainfot leiab man purge-old-kernels

Kuid vaikimisi sellist mugavat vanade tuumade eemaldamise kأ¤sku ei ole - selleks tuleb paigaldada pakett byobu, mis on olemas ka Ubuntu vaikimisi varamutes ent mitte kأµige uuem. Uusima saab kui lisada vastav varamu:

sudo add-apt-repository ppa:byobu/ppa && sudo apt-get update
... ning paigaldada byobu

sudo apt update && sudo apt install byobu && sudo apt clean
Lisaks vanade tuumade eemaldamisele vأµimaldab byobu palju muudki, lisainfot leiab programmi kodulehelt.

Kui ei ole vأµimalik rakenduse byobu'ga kaasatulevat mugavat vأµimalust vanade tuumade kasutamiseks rakendada siis saab ka kأ¤sitsi neid eemaldada.

Paketihaldusest otsime paigaldatud tuumi ja nende pأ¤iseid:
1.variant (paigaldatud pakettide tuvastamine):

dpkg-query -l 'linux-image*' | grep '^ii'
dpkg-query -l 'linux-header*' | grep '^ii'
Graafiliselt tأ¶أ¶jaamas sama otsing:
otsida (CTRL+F) Synaptic'uga pakette:

linux-image
linux-header
.. ja tأ¤ielikult eemaldada (SHIFT+Delete) siis need, mis on vanemad ja millelt masin ei tأ¶أ¶ta. Synaptic'us saab pakette mأ¤rkida CTRL-klahvi all hoides. Tأ¤ielikuks pakettide eemaldamiseks Synaptic'us klahvikombinatsioon SHIFT+Delete vأµi menأ¼أ¼s Paketid->Mأ¤rgi tأ¤ielikuks eemaldamiseks.
Kأ¤sureal eraldada tأ¼hikutega paketid jأ¤rgmiselt (asendada nأ¤ites toodud nimed tegelikega):

sudo apt purge pakk1 pakk2.....pakk n
NB! Enne eemaldamist veenduda uname -r abil, milliselt tuuma versioonilt masin tأ¶أ¶tab.

Vأµib kasutada ka mأµnda teist paketihaldustarkvara, soovi korral saab Synaptic'u ka paigaldada:

sudo apt update && sudo apt-get -y install synaptic && sudo apt clean

2.variant paigaldatud tuumade ja pأ¤iste otsimiseks
sudo dpkg --get-selections | grep linux-image

sudo dpkg --get-selections | grep linux-header
Uusim tuum ja pأ¤ised Ubuntule
On vأµimalik paigaldada ka pأ¤ris uusi versioone kuid neid ei saa automaatselt uuendada ja selle lahenduse valimisel tuleb ka edaspidi kأ¤sitsi uuendada ja ise regulaarselt jأ¤lgida kui uus versioon vأ¤lja tuleb. Kui minna ametlikule Linuxi tuuma kodulehele https://www.kernel.org/ siis nأ¤eb, mis on hetkel uusim tuuma versioon (stable). Sealt nأ¤eb ka teisi tuumade versioone, mida veel toetatakse (longterm) ja mis on uusim arenduses olev versioon (mainline).

Uusimad Ubuntu jaoks pakendatud tuumad ja pأ¤ised leiab aadressilt http://kernel.ubuntu.com/~kernel-ppa/mainline/ - tuleb minna lehekأ¼lje lأµppu (nt klahviga End) ja vأµtta suurima numbriga kataloog. Vأ¤ltida tuleks katalooge, mille nime lأµpus on rc1, rc2 jne - need on veel arendusjأ¤rgus olevad vأ¤ljalaskekandidaadid (rc - release candidate).

Paigaldamiseks tuleb teada ka oma sأ¼steemi arhitektuuri, أ¼ldiselt kas 32-bit vأµi 64-bit: uname -m. Kui vastuseks on i686 (vأµi ka i386) siis 32-bit ja kui x86_64 siis on 64-bit sأ¼steemiga tegemist.

Soovitav on alla laadida eraldi kataloogi, nأ¤iteks tekitame kataloogi mkdir -p /home/kasutaja/Allalaadimised/tuum/.
Enne uue versiooni allalaadimist kustutada vanad versioonid: rm -fr /home/kasutaja/Allalaadimised/tuum/*
Alla saab laadida nأ¤iteks esmalt soovitud kausta sisenedes cd /home/kasutaja/Allalaadimised/tuum/ ja seejأ¤rel wget http://kernel.ubuntu.com/~kernel-ppa/mainline/vx.x/failinimi.deb abil alla laadides.

32-bit sأ¼steemi korral tuleb alla laadida:

linux-headers-VERSIOONINUMBER_VERSIOONINUMBER.LOOMISE-AEG_all.deb
linux-headers-VERSIOONINUMBER-generic_VERSIOONINUMBER.LOOMISE-AEG_i386.deb
linux-image-VERSIOONINUMBER-generic_VERSIOONINUMBER.LOOMISE-AEG_i386.deb
Kui on saadaval siis vأµib vأµtta ka linux-image-extra-VERSIOONINUMBER_i386 vأµi amd64.deb

Tuumad, mille nimes on lowlatency on reaalaja tuumad ja mأµeldud teistsugustele sأ¼steemidele kus vaja vأ¤ga kiiret reageerimist, mida kasutatakse nأ¤iteks helitأ¶أ¶tluses, arvutijuhitavate tأ¶أ¶pinkide juhtimiseks jne. Seal on saadaval veel ka teistele riistvara arhitektuuridele tuumi (arm, ppc jne).

64-bit sأ¼steemi korral tuleb alla laadida:

linux-headers-VERSIOONINUMBER_VERSIOONINUMBER.LOOMISE-AEG_all.deb
linux-headers-VERSIOONINUMBER-generic_VERSIOONINUMBER.LOOMISE-AEG_amd64.deb
linux-image-VERSIOONINUMBER-generic_VERSIOONINUMBER.LOOMISE-AEG_amd64.deb
Enne paigaldamist tuleb ka veenduda, et kataloogis /home/kasutaja/Allalaadimised/tuum/ ei ole muid mittevajalikke .deb faile ega ka vanu, juba paigaldatud tuumade ja pأ¤iste faile - kui on siis need tuleks enne jأ¤rgmise paigalduskأ¤su kأ¤ivitamist sealt kataloogist kustutada.

Allalaaditud tuuma- ja pأ¤isefailide paigaldamiseks, alglaaduri uuendamiseks ja sأ¼steemi taaskأ¤ivitamiseks:

cd /home/kasutaja/Allalaadimised/tuum/ && sudo dpkg -i * && sudo update-grub && sudo reboot
Seejأ¤rel tuleks eemaldada vanad tuumad, millest eespool ka juttu oli. Kui vanade tuumade eemaldamisel sأµltuvusena eemaldatakse ka pakett linux-generic siis selles ei ole midagi halba ja selle vأµib eemaldada, isegi enne eemaldamist mأ¤rkida tأ¤ielikuks eemaldamiseks (kأ¤surealt sudo apt purge linux-generic).

Uudiseid Linuxi tuumaga seoses

* https://www.kernel.org/ * https://lwn.net/Kernel/ * https://lkml.org/ - postiloend * http://www.phoronix.com/scan.php?page=news_topic&q=Linux+Kernel * https://www.reddit.com/r/kernel/ * https://kernelnewbies.org/
