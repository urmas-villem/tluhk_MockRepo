# Tähtis kursus 
(terve asi on loodud ainult mock andmetena ja kogu sisu on kopeeritud avalikest allikatest ning kasutatakse ainult mock data eesmärgil)
## Kursuse selgitus:

See tekst siin selgitab kursuse sisu ja on ka väga tähtis osa ning iga üliõpilane peaks seda lugema kindlasti.

## Hinde saad kursusel nii:

* „A” - suurepärane 91-100%
* „B” - väga hea 81- 90%
* „C” - hea 71- 80%
* „D” - rahuldav 61-70%
* „E” - kasin 51- 60%
* „F” - puudulik 0 – 50%

### Esimese loengu teemad:

gedit on Gnome töölaua vaikimisi tekstiredaktor. 
Oma omadustelt on tegu vägagi võimsa tekstiredaktoriga, sest toetab ta täielikult UTF-8 kodeeringut, võimalik on teda kasutada mitmete programmeerimiskeelte kirjutamiseks (C, C++, Java, HTML, XML, Python, PHP, Perl ja paljud teised). 
Lisaks on võimalik GNOME VFS teeke kasutades muuuta ja kirjutada ka teistes masinates olevaid faile. Ka on võimalik tema omadusi täiustada erinevate liideste abil. Hiljuti on loodud ka gediti baasile uus gPHPedit nimeline programm, mis ette nähtud just PHP ja HTML failide haldamiseks.

### Teise loengu teemad:

Nii mõnigi võib vahest avastada, et tema Debian või Ubuntu on mingil põhjusel nii kokku jooksnud, et vana hea CTRL-ALT-BKSPC ei suuda midagi teha. Kui üritate ALT-CTRL-F1 abil saada terminali, et kokku jooksnud protsess tappa, siis ka see ei õnnestu. Kuid on olemas siiski veel kaks võimalust, kuidas oma süsteemi protsesse vajadusel tappa või siis vähemalt süsteemile alglaadimine turvalisemalt teha, kui lihtsalt voolu nuppu vajutades.
Esiteks proovime tappa kõik protsessid aktiivses terminalis. Selleks kasutage järgmist klahvikombinatsiooni: ALT + SysReq + k
SysReq klahv asub üldjuhul PrtSc või Print Screen klahvi juures.Klahv k tähistab siin siis protsesside tapmist.
Nüüd peaksite edasi saama kasutada järgnevaid klahvikombinatsioone, et Teie süsteem teeks alguses natuke kodutööd, enne taaskäivitust.
ALT + SysReq + r
Sellega jääte Raw keyboardi juurde. (keegi võiks lahti seletada, mis see raw keyboard täpsemalt on!)
ALT + SysReq + s
Sellega teete süsteemi ketaste testi
ALT + SysReq + e
Sellega lõpetate kõik protsessid
ALT + SysReq + i
Tapab kõik protsessid, mis ei lõpetanud oma tööd korralikult.
ALT + SysReq + u
Ühendab kõik failisüsteemid read only reziimi.
ALT + SysReq + b

### Kolmanda loengu teemad:

IceWM on lihtne ja robustne töölaud erinevatele UNIX süsteemidele. Tema arendajaks ja loojaks on Marko Maček. Tänu oma lihtsusele, vähesele ressursi nõudmisele on tegu hinnatud töölauaga just nende Linuxi distributsioonide juures, kus on vaja graafilist keskonda luua võimalikult väheste vahenditega. Seega sobib antud töölaud ideaalselt näiteks vanematele arvutitele. IceWM-i on võimalik väga lihtsalt seadistada tavalistest konfiguratsiooni failidest, mis talletatud kõik kasutaja kodukataloogi. Tänu sellele on ka oma seadete ja andmete kopeerimine tehtud väga lihtsaks.

### Neljanda loengu teemad:

Grubi menüü peitmine

Vaikimisi on Ubuntus Grubi menüü peidetud Selleks peab järgnev sektsioon välja nägema nii:
hiddenmenu
Hides the menu by default (press ESC to see the menu)
hiddenmenu
Grubi menüü näitamine

Selleks, et Grubi menüü tuleks alati nähtavale tuleb välja kommenteerida lihtsalt hiddenmenu, lisades sinna ette #.
hiddenmenu
Hides the menu by default (press ESC to see the menu)
#hiddenmenu

### Viienda loengu teemad:

Käsku PING kasutatakse selleks, et kontrollida ühenduvust mingi muu arvutiga. Käsk saadab hostile ICMP-pakettide (Internet Control Message Protocol - Interneti juhtsõnumiprotokoll) voo ning esitab siis seejärel tulemuse.
ping [-c number] [i sek] [-q] host
-c number
Saadab number arvu pakette
-i sek
Ootab paketi vahel arv sekundit
-q
