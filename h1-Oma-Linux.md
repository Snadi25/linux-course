# Linuxin asentaminen virtuaalikoneeseen

## Tietokoneen tietoja
Käyttöjärjestelmänäni toimii Windows 11 Pro. Tietokoneessani on AMD Ryzen 5 7600 6-Core Processor ja RAM-muistia minulla on 32GB.

## 1. Debian ISO Image
- Ensinmäisenä lähdin asentamaan Debian Live ISO Imagea, käyttäen apunani terokarvinen.com sivuilta löytyvää artikkelia "Install Debian on VirtualBox". Kirjoitin googleen "debian live iso" ja valitsin "Debian --Live install images" sivuston, josta löysin ladattavan tiedoston.
  Lataamisessa meni muutama minuutti.

## 2. VirtualBoxin asentaminen
- Debianin asentamisen jälkeen asensin VirtualBoxin tietokoneelleni edellä mainitusta artikkelista löytyvän linkin kautta.

## 3. Uuden virtuaalikoneen luominen
- Katsoin asentamiseen ohjeita Tero Karvisen artikkelista ja Johannan GitHubista löytyvästä ohjeesta, johon oli linkki Teron artikkelissa.
- Käytin näitä asetuksia
  
  <img width="813" height="407" alt="image" src="https://github.com/user-attachments/assets/06ab02ae-f675-41d3-90c2-c36db5dabaaa" />

## 4. Debianin lataaminen virtuaalikoneelle
- Käynnistin virtuaalikoneen ja valitsin "Live System (amd64)", tähän asti virtuaalikone on toiminut ongelmitta.
-  Seuraavaksi tein muutamia testejä, avasin nettiselaimen ja kokeilin, että netti toimii ja näppäimistö toimii.
-  Kaikki toimi moitteettomasti, mutta näppäimistö oli englanniksi, jonka vuoksi Ä ja Ö ei toiminut. Vaihdoin asetuksista näppäimistön kielen suomeksi.
-  Testien jälkeen aloitin Debianin asentamisen. Työpöydällä oli "Install Debian", joka vei minut Debian GNU/Linux Installeriin.
-  Valitsin kieleksi American English.
-  Sijainti Suomi
-  Tässä vaiheessa huomasin, että installer kysyy näppäimistön kieltä, joten laitoin siihenkin suomen.
-  Sitten valitsin "Erase disk"
-  Nyt installer kysyy käyttäjätietoja, johon kirjoitan omat tietoni.
-  Yleiskatsaus asetuksista, painan "Install"
-  Muutaman minuutin jälkeen asennus oli valmis ja valitsin "Restart now" ja klikkasin "Done"
-  Kirjauduin sisään varmiistaakseni, että käyttäjätunnus ja salasana toimii oikein.
- Asentaminen onnistui ongelmitta.

# Lähteet:
- Karvinen Tero 2021 Install Debian on VirtualBox. https://terokarvinen.com/2021/install-debian-on-virtualbox/
- Heinonen Johanna 2025 How to Install Linux to Virtualbox? https://github.com/johannaheinonen/johanna-test-repo/blob/main/linux-20082025.md
