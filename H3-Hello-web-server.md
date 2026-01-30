# H# Hello web server

## a)
- Teimme tunnilla jo esimerkki webbisivun, joten kun kokeilen että webbipalvelin vastaa HTTP osoitteesta tulee tämä kyseinen esimerkkisivu näkyviin.
 <img width="1279" height="770" alt="image" src="https://github.com/user-attachments/assets/2db962fd-e29f-4b5a-959f-eb6117c263ba" />

## b)
- Pääsin käsiksi lokiin kun tein komennon "sudo tail -f /var/log/apache2/other_vhosts-access.log"
- Sieltä rivit näyttävät tältä: <img width="1209" height="39" alt="image" src="https://github.com/user-attachments/assets/93487069-8bad-4c0d-8742-4730e453acc7" />
- Ensinmäinen kohta "toni.example.com:80" kertoo mitä osoitetta ja porttia selain käytti
- Seuraava kohta "127.0.0.1" on "asiakkaan" ip-osoite, joka teki haun.
- Sitä seuraava kohta on kaksi viikaa "- -", jotka osoittavat identiteettiä ja käyttäjänimeä. Eli jos sivu vaatisi kirjautumisen, tulisi käyttäjänimi jälkimmäiseen viivan kohdalle.
- Seuraavana on päivämäärä milloin asiakas teki haun sivulle. Tässä tapauksessa se tehtiin 30. Tammikuuta 2026 klo 15:36:52. Numerot "+0200" tarkoittaa aikavyöhykettä.
- Sitten tulee kohta "GET / HTTP/1.1", joka näyttää pyynnön mikä tehtiin. "GET" on metodi, jolla pyydetään sisältöä. "/" tarkoittaa kohdetta, ja pelkkä vinoviiva tarkoittaa juurihakemistoa.
  Viimeinen kohta "HTTP/1.1" tarkoittaa käytetyn protokollan versiota.
- Seuraavana on numero "200" joka tarkoittaa statuskoodia. Koodi "200" tarkoittaa, että kaikki on OK
- Statuskoodin jälkeen on numero "302", joka tarkoittaa vastauksen kokoa tavuina.
- Sitten on tyhjä kohta, jossa on pelkkä viiva. Tämä on "refer" kohta, joka kertoisi jos asiakas tulisi jonkun toisen sivuston kautta. Mutta kun kirjoitin osoitteen suoraan hakupalkkiin on tämä kohta tyhjänä.
- Viimeinen kohta kertoo mitä selainta asiakas käytti ja mitä käyttöjärjestelmää.
- Löysin ihan hyvän artikkelin jossa selitettiin nämä asiat. Löydät artikkelin tästä linkistä: https://www.sumologic.com/blog/apache-access-log

## c)
- Tässä kohdassa lähdetään luomaan uusi webbisivu. Käytin apunani Tero Karvisen artikkelia "Name Based Virtual Hosts on Apache – Multiple Websites to Single IP Address", linkki artikkeliin lähteissä.
- Luon ensinmäisenä kansion, jonne tulee nettisivun tiedostot. Koska tehtävässä lukee, että sivua pitää pystyä muokkaamaan normaalina käyttäjänä teen sen kotihakemistoon.
- Loin kansion /home/toni/publicsites hakemistoon komennolla "mkdir hattu", jonka jälkeen loin sinne tiedoston nimeltä index.html komennolla micro "index.html".
- Tiedostoon kirjoitin yksinkertaisesti "Tervetuloa hattu -sivustolleni!"
- Seuraavaksi loin Virtual Host asetustiedoston, komennolla "sudoedit /etc/apache2/sites-available/hattu.example.com.conf
- Kirjoitin kyseiseen tiedostoon seuraavat tiedot: <img width="1220" height="699" alt="image" src="https://github.com/user-attachments/assets/cb7c130b-9e00-44d8-bb85-b9ff8cdffb68" />
- Tämän jälkeen otin pois käytöstä tunnilla tehdyn sivuston komennolla "sudo a2dissite toni.conf" <img width="543" height="77" alt="image" src="https://github.com/user-attachments/assets/f500959b-a4f0-461a-8957-a042b7d7e025" />
- Sitten ajoin komennon jolla sain uuden nettisivun käyttöön, ja myös restarttasin apache2: <img width="735" height="97" alt="image" src="https://github.com/user-attachments/assets/2b289b68-d9dd-43d3-b26c-a21dae7c0202" />
- Menin seuraavaksi selaimeen ja kirjoitin hakuun 2http://localhost", ja sivustoni toimi niinkuin pitääkin. <img width="1278" height="776" alt="image" src="https://github.com/user-attachments/assets/e30c283d-137c-41c5-9e79-b8dceaba7f1f" />

## e)
- Tässä vaiheessa huomasin tämän tehtävä kohdan jossa pitää tehdä validi HTML5 sivusto, joten muokkasin olemassa olevaa index.html tiedostoa kuvan näköiseksi
  <img width="1227" height="701" alt="image" src="https://github.com/user-attachments/assets/08d02b9b-8de9-4b49-95c0-f7558c9aef59" />
- Kävin vielä testaamassa että muutokseni näkyivät ja toimivat sivustolla <img width="1277" height="775" alt="image" src="https://github.com/user-attachments/assets/9758c022-be4a-4d31-90b9-efe5da79498d" />
- Sivuston latauduttua ihmettelin miksi ääkköset ei näy kunnolla ja menin tarkistamaan index.html tiedoston ja huomasin että olin kirjoittanut "meta charset="utf=8" " vaikka sen piti olla "meta charset="utf-8" ". Joten muokkasin sen oikeaksi,
  jonka jälkeen teksti näkyi oikein.

## f)
- Komennolla "curl http://localhost/" saan näkyviin kaiken mitä olen kirjoittanut index.html tiedostoon <img width="1210" height="646" alt="image" src="https://github.com/user-attachments/assets/fd3b5287-8e51-4e1b-8b7d-622209188c23" />
- Komento "curl -I http://localhost" pyytää palvelimelta metadata tiedot <img width="1210" height="648" alt="image" src="https://github.com/user-attachments/assets/e27b3672-9aa8-4ae7-8761-def0ee03ebc1" />
- Ensimmäinen otsake kertoo onnistuiko pyyntö, kuvassa näkyy "200 OK" eli kaikki onnistui
- Toisena on Date joka kertoo palvelimen ajan pyyntöhetkellä, joka on nähtävästi 2h omaa kelloani jäljessä.
- Kolmantena on palvelinohjelmiston nimi ja versio.
- Neljäntenä näkyy milloin tiedostoa on viimeksi muokattu, joka on myös 2h kelloani jälessä.
- Jouduin etsimään tietoa tuosta ETag kohdasta sillä en entuudestaan sitä tiennyt. Se on ilmeisesti "Entity tag", joka on tiedoston yksilöllinen tunniste. ETag lasketaan muunmuassa tiedoston koosta ja muokkausajasta, eli jos tiedostosta muutetaan
  vaikkapa yksi kirjain, muuttuu ETag erilaiseksi. Lisää aiheesta täältä: https://developer.mozilla.org/en-US/docs/Web/HTTP/Reference/Headers/ETag
- Accept-Ranges: bytes, on otsake jolla palvelin ilmoittaa tukevansa tiedoston lataamista osissa.
- Content-Length kertoo vastauksen koon.
- Vary: Accep-Encoding tarkoittaa, että palvelin voi lähettää samasta resurrsista eri versioita. Aiheesta lisää täältä: https://developer.mozilla.org/en-US/docs/Web/HTTP/Reference/Headers/Accept-Encoding
- Viimeinen kohta kertoo selaimelle mitä dataa on tulossa, jotta se osaa näyttää sen oikein.

# Lähteet
Tero Karvinen 2018: Name Based Virtual Hosts on Apache – Multiple Websites to Single IP Address https://terokarvinen.com/2018/04/10/name-based-virtual-hosts-on-apache-multiple-websites-to-single-ip-address/

David Girvin 2025: Understanding the Apache access log: how to view, locate, and analyze https://www.sumologic.com/blog/apache-access-log

MDN: https://developer.mozilla.org/en-US/docs/Web/HTTP/Reference/Headers/ETag

MDN: https://developer.mozilla.org/en-US/docs/Web/HTTP/Reference/Headers/Accept-Encoding
