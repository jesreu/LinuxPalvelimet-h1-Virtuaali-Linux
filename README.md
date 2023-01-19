# LinuxPalvelimet-h1-Virtuaali-Linux

## Tiivistelmä
Tässä raportissa kerron, kuinka asensin Debianin Oraclen VirtualBox- ohjelmaan. Asennuksessa on käytetty apuna Install-debian-on-virtualbox ohjetta, jonka linkki löytyy lähteistä.
  
## Lähtötilanne
      Virtuaaliohjelmisto:                Oraclen VM VirtualBox Manager
      Debianin Iso tiedosto:              debian-live-11.6.0-amd64-xfce+nonfree.iso.
      Ohjelmiston Käyttöympäristö:        Microsoft Windows 10 Pro
      RAM:                                16gb
      Fyysista muistia:                   1 tera
      Aloitus KLO:                        12.09
## Tapahtumien kulku
Aloitin asennuksen käynnistämällä Oraclen VM VirtualBox Manager ohjelmiston. Klikkaamalla yläpalkin New vaihtoehtoa pääsen uuden virtuaalitietokoneen luonti valikkoon. Valikossa valitsen ensimmäisenä expert vaihtoehdon, jolla saan kaikki tarvittavat tiedot samalle näytölle. Asetan tietokoneen nimeksi DebianJesse, jonka ansiosta ohjelma automaattisesti määrittää type: Linux ja version: Debian (64-bit). Asetan järjestelmälle RAM käyttömuistia 8gb ja valitsen virtuaalisen kovalevyn luomisen. KLO: 12.20
      
Virtuaalisen Kovalevyn luonti avatuu, asetan virtuaalisellekovalevylle käytettäväksi 60gb. En muuta muita ruudun valintoja. Klikkaan Create: nappia, ja virtuaali koneeni tulee näkyviin KLO 12:22
      
Valitsen DebianJesse virtuaalikoneeni, ja painan settings painiketta. Navigoin avautuneessa ikunassa vasemmalla olevan palkin Storage osioon. Valitsen Controller: IDE Empty. Avautuneen Attributes osion alta navigoin Optical Drive: osiion, ja klikkaan ruudun oikeassa reunassa olevaa levyn kuvaketta. Valitsen vaihtoehdon Choose/Create a Virtual Optical Disk. Avautuneessa ikkunassa ei näy vielä debianin ISO kuvaa, mutta painamalla ADD ja etsimällä sen hakemiston jossa ISO on tallennettuna voit lisätä sen ikkunaan. Valitsemalla ISON ikkunasta ja painamalla Choose valitsee järjestelmä debianin ISON käytettäväksi. KLO 12.30
      
Virtualboxin perusnäkymässä tupla klikkaan DebianJesse tietokoneetta boottausta varten. Virtuaali kone aukeaa, ja kysyy minkä boot vaihtoehdon haluan valitsen Live, joka mahdollistaa järjestelmän käytön heti. Virtual boxin Ruutu pimenee mutta noin ~30 sekuntin odottamisen jälkeen debianin työpyötä tulee näkyviin. Testatakseni hieman toiminnallisuutta klikkaan ylä vasemmalla olevaa Applications painiketta, valitsen Web Browserin ja avautuneeseen Firefox selaimeen kirjoitan YLE hakukenttään. Hiiri, näyttö, näppäimistö ja web yhteys OK. KLO 12:39
      
Käyttöjärjestelmän loppuun asentamiseksi siirryn takaisin työpyödälle, sulkemalla selaimen ylä oikealta, ja klikkaan punaista Install Debian painiketta. Asennusohjelma käynnistyy, ja pääsen valitsemaan kielen: American English, joka toimii järjestelmän kielenä jatkossa. Seuraavaksi valitsen sijainnin, ensiksi Region: Europe ja Zone: Helsinki. Näppäimistön asetukset määritetään seuraavaksi, valitsen Keyboard Model: Generic 105-key PC (intl.) Vasemmalla olevassa ruudussa valitsen Finnish, ja oikealla olevaan ruutuun jää Default. Kokeilen näppäimistön toimivuutta alhallaa olevassa kentässä kirjoittamalla äö merkkejä. KLO 12.48
      
Partitions vaiheessa valitsen Erase disk, joka tyjentää kohde levyltä ylimääräisen tiedon pois ( koska kysessä on aikaisemmin luotu virtualkovalevy operaation ei pitäisi tuhota mitään tärkeitä tiedostoja). En valitse Encrypt optiota, koska kyseessä on virtuali kone. En koske Master Boot Record optioon, vaan jätän sen alkuperäiseen tilaan. Täytän User tiedot omalla nimelläni, jätän log-in nimen automaattiseksi, jonka järjestelmä luo syötetyn nimen mukaan. Muokaaan tietokoneen nimen Kissaksi, jotta tietokonetta on vaikeampi yhdistää minuun henkilönä. Asetan turvallisen salasanan ja en rastita ''log in automatically...'' vaihtoehtoa. KLO 12.56
      
Järjestelmä antaa yhteenvedon valinnoissa, ja nyt voimme painaa install ruudun oikeasta alanurkasta (jos install ei näy voit painaa kokonäytön tilan päälle oikealta ylhäällä neliö painikkeela). Järjestelmä aloittaa asennuksen  12:58 -> ja lopettaa asennuksen 13.03. Valitsen Restart now vaitoehdon asennuksen valmistuttua. KLO 13.04

Nyt voimme kirjautua järjestelmään ensimmäisen kerran asennuksessa valitsemillamme käyttäjällä ja salasanalla. Kokeilen järjestelmän toimivuuden taas avaamalla YLEn nettisivut. Asennuksen valmistamiseksi ajan komennot:

    $ sudo apt-get update
    $ sudo apt-get -y dist-upgrade 

Ensimmäinen komento tarkistaa puuttuvat päivitykset. Toinen komento päivitää kaiken mahdollisen. KLO 13.11

Seuraavaksi asennamme palomuurin tietoturvaa varten, joka onnistuu komennoilla:

    $ sudo apt-get -y install ufw
    $ sudo ufw enable
    
Käynnistämme tietokoneen uudelleen komentojen ajamisen jälkeen, ja käyttöjärjestelmä on valmiina käytettäväksi KLO 13.20
    
    
## Lopputulos

Onnistuneesti asennettu ja päivitetty Debian linux.

     Lopetus KLO:                  13.20
     Asennukseen käytetty aika:    1h + 11min
     
     

## Lähteet
    https://terokarvinen.com/2021/install-debian-on-virtualbox/
