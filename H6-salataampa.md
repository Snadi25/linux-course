# H6 - Nimekäs

## x) Tiivistys salauksesta
### Let's Encrypt: How it works
- ACME protokollan tavoitteena on automatisoida HTTPS-sertifikaattien hankinta, asennus ja uusiminen ilman ihmisen interferenssiä käyttämällä ACME asiakasohjelmaa, esimerkiksi CertBot.
- Enne sertifikaatin myöntämistä palvelimen on todistettava hallitsevansa kyseistä verkkotunnusta. Tämän voi tehdä luomalla tietty tiedosto verkkopalvelimelle tai lisäämällä DNS-tietue.
- Hallinnan todentamisen jälkeen asiakasohjelma lähettää allekirjoituspyynnön. Let's Encrypt myöntää lyhytaikaisen sertifikaatin.

### Apache HTTP Server: SSL/TLS Strong Encryption: How-To
- SSL salauksen käyttöönotto vaatii vähintään "SSLEngine on" asetuksen sekä polut sertifikaatti- ja avaintiedostoihin.
- HTTPS liikenne ohjataan tyypillisesti porttiin 443.
- Apache palvelimen salausominaisuudet perustuvat "mod_ssl" moduuliin, joka on ladattava käyttöön, jotta SSL direktiivit toimivat.
- Palvelin tarvitsee julkisen sertifikaatin ja siihen liittyvän yksityisen avaimen. Certbot hoitaa näiden hakemisen ja asetusten lisäämisen automaattisesti, mutta peruskonfiguraatiossa ne osoitetaan manuaalisesti.
---

### a) TLS-sertifikaatin hankkiminen
- Kävin eka katsomassa, että sivustoni toimivat ja näkyvät kaikilla domain nimillä ja toimihan ne
<img width="875" height="324" alt="image" src="https://github.com/user-attachments/assets/a2890da5-eed3-4b1b-b6af-b9071f21cb5e" />

- Sen jälkeen tein komennon sudo apt-get update ja avasin palomuurin portit HTTPS yhteyttä varten
<img width="918" height="478" alt="image" src="https://github.com/user-attachments/assets/0c453d8a-85ec-49c7-80d1-04486229c785" />

- Sitten asensin Certbotin komennolla "sudo apt-get install certbot python3-certbot-apache"
- Hain Certbotin avulla sertifikaatit sivuilleni komennolla "sudo certbot --apache --domains toniparhiala.com,www.toniparhiala.com
- Laitoin sähköpostini ja vastasin kyllä kaikkiin kysymyksiin.
<img width="1471" height="721" alt="image" src="https://github.com/user-attachments/assets/a6fe3ef0-ed6d-41f1-af4b-8ca05412f017" />

- Sitten käynnistin apachen uudelleen "sudo systemctl restart apache2", jonka jälkeen kävin testaamassa toimiko encryptaus
<img width="407" height="196" alt="image" src="https://github.com/user-attachments/assets/df6e654d-b9c5-4394-9189-9f07f8d243da" />   <img width="400" height="215" alt="image" src="https://github.com/user-attachments/assets/8007e61b-bbdc-4d91-9f89-9fb64a2bd631" />

- Kuvissa näkyy että toimii.
- Varmistin vielä että automaattinen uusiminen on päällä kuvan komennolla.
<img width="953" height="274" alt="image" src="https://github.com/user-attachments/assets/9fb342fa-a26b-47bd-94f0-d233fe949312" />

# Lähteet
- The Apache Software Foundation: https://httpd.apache.org/docs/2.4/ssl/ssl_howto.html#configexample
- Let's Encrypt: How it works: https://letsencrypt.org/how-it-works/
- Täälä vielä vähän infoa miten katsoa onko auto renew päällä vai ei: https://community.letsencrypt.org/t/is-auto-renew-on/175547
