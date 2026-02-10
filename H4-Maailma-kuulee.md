# h4 - Maailma kuulee

## a) Pilven vuokraaminen
- Vuokrattiin tunnilla jo pilvi valmiiksi, mutta käyn tässä vielä läpi miten se tehdään.
- Vuokrasin pilven UpCloudista, sillä niillä on servereitä suomessa.
- Kun olet kirjautunut UpCloudiin, sivun vasemmalla puolella on sivuvalikko. Sieltä painoin server kohtaa, jonka jälkeen painoin deploy server.
<img width="224" height="306" alt="image" src="https://github.com/user-attachments/assets/1c43199e-fa76-4197-a150-71f3be4ddbdf" />

- Sen jälkeen valitaan lokaatio. Valitsin itse toisen näistä suomen servereistä.
<img width="796" height="681" alt="image" src="https://github.com/user-attachments/assets/a99844fe-fd8f-4f82-8e76-a219c00d1e3a" />

- Seuraava vaihe on "Plan". Tässä kannattaa valita omaan tarpeisiin sopiva määrä muistia, jos et mitään hirveitä laitoksia ole pyörittämässä toi pienin mahdollinen on oikein sopiva.
<img width="821" height="716" alt="image" src="https://github.com/user-attachments/assets/4a11ff66-8e2b-4e09-a54d-fb38ba09ff3b" />

- Plan kohdan jälkeen on "Storage" ja "Automated backups". Näistä en valinnut mitään, sillä en koe niitä tarpeellisiksi
- Näiden jälkeen valitaan minkä käyttöjärjestelmän haluat, valitsin tästä Debian Linuxin.
<img width="827" height="656" alt="image" src="https://github.com/user-attachments/assets/2e0712b5-1f3c-4d5f-9526-7f9dc5f64313" />

- Seuraavista kohdista en muuttanut mitään. Eli jätin vain kuvan mukaiset asetukset.
<img width="820" height="876" alt="image" src="https://github.com/user-attachments/assets/ea01d7c1-377a-453b-bed3-e2a79383adb5" />

- Seuraavana on "Login Method". Loin tätä varten uuden SSH avaimen.
- SSH avaimen saa luotua kun terminaaliin laittaa komennon "ssh-keygen" ja sitten painaa enteriä joka kohtaan kunnes se luo sen avaimen. järjestelmä tallentaa avaimen .ssh hakemistoon
- Mene kyseiseen hakemistoon ja näytä sieltä cat komennolla se jonka perässä on .pub, tämä on PUBLIC avain eli sen saa näyttää. Älä koskaan näytä private avainta
- Kopioi koko rimpsu minkä cat tulostaa. Paina UpCloud sivustolla "Add New" ja lisää kopioimasi avain
<img width="824" height="376" alt="image" src="https://github.com/user-attachments/assets/490a97ae-54c6-47f8-b82c-67f74bf6527d" />

- "Initialization Script" kohtaan ei tarvitse laittaa mitään.
- Viimeisenä "Server Configuration" kohdassa valitset serverillesi nimen. Nimi kannattaa olla jokin mistä ei nää kovin henkilökohtaisia tietoja
<img width="818" height="721" alt="image" src="https://github.com/user-attachments/assets/d344d9ac-261f-4a49-9346-589959d863e0" />

## b) Virtuaalipalvelimen alkutoimet
- Tein "reiän" palomuuriin komennolla "sudo ufw allow 22/tcp", jonka jälkeen tein komennon "sudo ufw enable". Tämän jälkeen käynnistin virtuaalikoneen uudestaan.
- Kirjauduin palvelimelle komennolla "ssh root@palvelimen-ip-osoite".
- Loin uuden käyttäjän, jotta saan root käyttäjän kiinni. Käytin komentoa "sudo adduser käyttäjän-nimi"
- Lisäsin käyttäjälle sudo oikeudet "sudo adduser toni sudo" ja lisäsin sen admin ryhmään "sudo adduser toni admin"
- Oikeuksien lisäyksen jälkeen kirjauduin juuri lisäämälleni käyttäjälle uudessa terminaalissa ja lukitsen root käyttäjän komennolla "sudo usermod --lock root"
- Poistin root käyttäjän log in mahdollisuudet komennolla "sudoedit /etc/ssh/sshd_config" ja etsin tiedostosta kohdan (kuva) ja laitoin "PermitRootLogin" kohtaan "no"
<img width="236" height="103" alt="image" src="https://github.com/user-attachments/assets/c2c95227-d882-4145-905d-2a46b0b8c559" />

- Käynnistin sen uudestaan komennolla "sudo service ssh restart"
- Kokeilin vielä, että onnistuiko se ja onnistuhan se
<img width="526" height="62" alt="image" src="https://github.com/user-attachments/assets/8f6954fd-3848-4a14-b77c-ed8068e83dd9" />

- Sitten päivitin ohjelmat "sudo apt-get update" ja "sudo apt-get upgrade". Tässä meni hetki aikaa.

## c) Weppipalvelimen asentaminen ja sivun luominen
- Asensin virtuaalipalvelimelle Apachen komennolla sudo atp-get install -y apache2"
- Menin hakemistoon /var/www/html ja poistin index.html tiedoston joka sisälsi testisivun
- Loin uuden index.html itedoston
<img width="1016" height="622" alt="image" src="https://github.com/user-attachments/assets/141e34f5-2788-49d5-a777-469dcfcc57ca" />

- Kävin vielä testaamassa, että se toimii.
<img width="1276" height="769" alt="image" src="https://github.com/user-attachments/assets/dc495e18-5690-4bf9-9ea6-2385b9f782a1" />

- Testasin myös kännykällä ja sekin toimi.

#Lähteet
- Tero Karvinen 19.9.2017 First Steps on a New Virtual Private Server – an Example on DigitalOcean and Ubuntu 16.04 LTS: https://terokarvinen.com/2017/first-steps-on-a-new-virtual-private-server-an-example-on-digitalocean/




