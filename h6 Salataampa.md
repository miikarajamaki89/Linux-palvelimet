# h6 Salataampa

## Lue ja tiivistä

-Tavoitteena on mahdollistaa HTTPS-palvelin, joka saa selainten luottaman sertifikaatin automaattisesti ilman manuaalista työtä. 

-ACME‑asiakas todistaa domainin hallinnan CA:lle ja voi sen jälkeen pyytää, uusia ja perua sertifikaatteja. 

-Ensimmäisellä käyttökerralla asiakas luo tiliavaimen ja rekisteröityy CA:lle. 

-Domainin validointi tapahtuu yleensä HTTP‑ tai DNS‑haasteella, jonka ACME‑asiakas suorittaa automaattisesti. 

-SSL‑tuki edellyttää mod_ssl‑moduulin lataamista ja portin 443 kuuntelua. 

-Vähimmäiskonfiguraatio sisältää VirtualHostin, jossa on:

    SSLEngine on
    SSLCertificateFile (sertifikaatti)
    SSLCertificateKeyFile (yksityinen avain) 
    
-Konfiguraatio määrittää myös ServerName‑arvon ja polut sertifikaattitiedostoihin. 

## Certbot asennus ja TLS-sertifikaatti Let's Encryptiltä

Asensin Certbotin jo luennolla, koska .dev‑päätteinen domain vaatii aina toimivan TLS‑sertifikaatin ennen kuin sivu voidaan avata selaimessa. Määrittelin Certbotille omaksi domainiksi miikarajamaki.dev, ja palvelimellani oli jo valmiiksi luotuna name‑based VirtualHost, joten Certbot pystyi lisäämään HTTPS‑konfiguraation suoraan siihen. Sertifikaatin asennuksen jälkeen testasin sivun latautumisen https://‑etuliitteellä, ja yhteys toimi onnistuneesti, mikä vahvisti että sertifikaatti oli asennettu ja Apache palveli sivua salatun yhteyden kautta.

## Laadunvarmistustesti

https://www.ssllabs.com/ssltest/analyze.html?d=miikarajamaki.dev

<img width="993" height="417" alt="image" src="https://github.com/user-attachments/assets/0fb64917-a2ef-4247-b379-1b0fb1f5cfc3" />

-Palvelin sai A‑arvosanan, mikä tarkoittaa vahvaa ja oikein toteutettua TLS‑konfiguraatiota.

-Sertifikaatti on voimassa, oikein asennettu ja luotetun CA:n (Let’s Encrypt) myöntämä.

-Palvelin tukee nykyaikaisia TLS‑versioita ja turvallisia salausmenetelmiä.

-Ei havaittu tunnettuja haavoittuvuuksia.

-OCSP Stapling ja muut keskeiset turvallisuusominaisuudet toimivat odotetusti.

Lähteet: 

https://letsencrypt.org/how-it-works/

https://httpd.apache.org/docs/2.4/ssl/ssl_howto.html#configexample

https://terokarvinen.com/linux-palvelimet/
