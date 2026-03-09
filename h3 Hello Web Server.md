# h3 Hello Web Server

## Lue ja tiivistä
-Apache voi palvella useita eri verkkosivuja yhdestä IP-osoitteesta käyttämällä Host-headeria sivuston tunnistamiseen.

-Name-based virtual hostit säästävät IP-osoitteita ja ovat yleisin tapa ajaa useita sivustoja samalla palvelimella.

-Jokaisen domainin DNS tulee osoittaa samaan IP-osoitteeseen, jotta Apache voi erottaa ne Host-headerin perusteella.

-Apache valitsee oikean sivuston VirtualHost-lohkon ServerName- ja ServerAlias-määritysten avulla.

-Uusi sivusto otetaan käyttöön luomalla oma konfiguraatiotiedosto hakemistoon sites-available ja aktivoimalla se komennolla a2ensite.

-Jokaiselle sivustolle määritellään oma DocumentRoot, joka osoittaa sivuston tiedostojen hakemistoon.

-Apache tulee käynnistää uudelleen muutosten jälkeen, jotta uudet sivustot tulevat käyttöön.

## Apache

Aloitin asentamalla apachen sudo apt-get install apache2 komennolla.

Testasin että apache toimii tarkistamalla localhostin selaimessa. Default Apache2 sivu aukeaa.

<img width="980" height="713" alt="image" src="https://github.com/user-attachments/assets/44935b07-0695-4118-a031-4275ad2fe86e" />

Default poistettu ja tilalle laitettu pelkkä Tervetuloa Miikan sivulle

<img width="1029" height="530" alt="image" src="https://github.com/user-attachments/assets/ed915958-f51d-4df3-98ec-cdb3de3811fc" />

Tein ohjeiden mukaan name based virtual hostin ja yksinkertaisen html sivun.

<img width="870" height="706" alt="image" src="https://github.com/user-attachments/assets/15a4485e-36e4-425d-8c64-c511a71bde0e" />

<img width="1185" height="686" alt="image" src="https://github.com/user-attachments/assets/49175a36-420b-45de-a684-14699c553acc" />

en saanut lokeja auki enkä päässyt tästä eteenpäin.

Lähteet:
https://httpd.apache.org/docs/2.4/vhosts/name-based.html
https://terokarvinen.com/2018/04/10/name-based-virtual-hosts-on-apache-multiple-websites-to-single-ip-address/
