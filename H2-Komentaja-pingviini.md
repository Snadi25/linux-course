# H2-Komentaja pingviini (24-1-2026)
## Muutama ajatus artikkelista Command Line Basics
- pwd ja ls todella tärkeitä komentoja vaikka ovat tosi "tavanomaisia".
- Hyvä varmistaa, että kirjoittama komento on oikein. Varsinkin silloin kun on poistamassa jotain, ettei poista väärää tiedostoa, sillä Linux ei kysele "poistetaanko varmasti esimerkki.txt".
- Tabulaattori on hyödyllinen apuväline.

# Micro-editorin asennus
- Päivitin ensin olemassa olevat paketit komennolla "sudo apt-get update"
- Asensin Micro-editorin käyttämällä komentoa "sudo apt-get -y install micro"
- Kokeilin vielä, että asennus onnistui ja loin testi-tiedoston komennolla "micro testi.md". Ja toimihan se
  <img width="1156" height="682" alt="image" src="https://github.com/user-attachments/assets/9be8ad38-b4d0-48ba-9ad2-cf02d55f0fea" />

- Poistin vielä testi.md tiedoston komennolla "rm testi.md", sillä en tarvitse sitä.

# Kolme uutta komentoriviohjelmaa
- Etsin eri ohjelmia mitä ladata Redditistä selailemalla paria subreddittiä, kuten r/Linuxquestions, r/commandline.
## NPM
- NPM on hyvä apuväline eri ohjelmien lataamiseen.
- Tämän lataamiseen meni hetki, sillä npm on aika iso.
- Tässä npm help komento jossa näkyy mitä kaikkea npm:llä voi tehdä <img width="1161" height="685" alt="image" src="https://github.com/user-attachments/assets/9ffa8186-2de4-4ffc-9dda-1a1ca3c4a2ae" />
## NCDU (NCurses Disk Usage)
- Ensinmäisenä päätin ladata NCDU-ohjelman, jolla saa näppärästi katsottua tiedostoja ja kuinka paljon tilaa ne vievät. Ohjelmalla saa myös helposti poistettua tiedostoja, painamalla "D" kirjainta näppäimistössä tiedoston kohdalla.
- Kuvankaappaus viikonpäivät kansiosta joka tehtiin tunnilla: <img width="1160" height="688" alt="image" src="https://github.com/user-attachments/assets/66461eba-048b-413e-879f-286ba470c3d9" />
- Tässä vielä kuvankaappaus kun poistaa tiedostoja: <img width="1163" height="686" alt="image" src="https://github.com/user-attachments/assets/e8ca7c02-353e-4fb7-8799-8db633728d07" />
## Cowsay
- Pieni ohjelma, jolla saa lehmän sanomaan haluamiasi asioita
- Tässä muutamia esimerkkejä: <img width="1167" height="686" alt="image" src="https://github.com/user-attachments/assets/4c1e5b13-69b7-4012-bebd-c76378e1cd0d" />
  <img width="1160" height="460" alt="image" src="https://github.com/user-attachments/assets/5d5c6c59-4b72-461b-ac25-d0fd15e21acb" />

- Ohjelmalla saa myös eri hahmoja, esimerkiksi pingviinin
  <img width="1160" height="686" alt="image" src="https://github.com/user-attachments/assets/171f7931-738d-48a5-a0f8-dbfcea26eadb" />
- Täältä löytyy vielä lisää komentoja jos kiinnostuit: https://www.linux.fi/wiki/Cowsay
# FHS
- Ekana on "/", joka on juurihakemisto. Tämän "alta" löydät kaikki virtuaalikoneesi tiedostot <img width="1133" height="625" alt="image" src="https://github.com/user-attachments/assets/e7c8e6e2-5fac-4c6a-85ad-b90d477283fe" />
- Seuraavana on "/home/", jonka alta löytyvät käyttäjät. <img width="1137" height="99" alt="image" src="https://github.com/user-attachments/assets/5a1ef465-2dc2-4d36-8551-546120b9e28f" />
- Sitten on minun oma toni hakemisto, ainoa paikka minne kyseinen käyttäjä, eli minä voi tallettaa tietoa pysyvästi. <img width="1138" height="123" alt="image" src="https://github.com/user-attachments/assets/c0b7c385-2d2d-4b32-834c-12775a7d0c1a" />
- /etc/ sisältää järjestelmän kaikki asetukset. Tässä esimerkkinä joitain tiedostoja <img width="1135" height="606" alt="image" src="https://github.com/user-attachments/assets/639c9c8f-bb82-466a-9d24-f61930f3028b" />
- /meida/. Tänne tulevat kaikki tilapäiset laitteet esimerkiksi muistitikkujen tai CD-levyjen tiedostot. Näät mitä siellä on käyttämällä komentoa "ls /meida". Minulla ei ole siellä mitään niin ei ole kuvankaappausta.
- /var/log/ sisältää lokitiedostoja kaikesta mitä virtuaalikoneellasi tapahtuu, esimerkiksi kirjautumistietoja. /var/log/apt kansiosta löytyy tiedosto "history.log", jossa nähtävästi näkyy mitä olen asentanut virtuaalikoneelle. Kuten tämän Cowsay ohjelman asennus
  
  <img width="370" height="99" alt="image" src="https://github.com/user-attachments/assets/2ed46946-420e-49d5-b879-3a3493f72249" />
# Grep
- Grep on hyvä apuväline tekstin etsimiseen ja suodattamiseen.
- Komennolla sudo grep -r "hostname" /etc/ löydät kaikista tiedostoista rivit joissa on sana "hostname". <img width="1139" height="630" alt="image" src="https://github.com/user-attachments/assets/b39b7637-72e6-47b5-a77c-756bb446ed17" />
- Komennolla "ps aux | grep micro" sain haettua micro-editoriin liittyvät prosessit <img width="793" height="68" alt="image" src="https://github.com/user-attachments/assets/b353965f-020c-4930-a9e8-a8e1ec537b22" />
# Pipes
- Tällä pystyt yhdistämään komentoja, voit esimerkiksi nähdä kansion tiedostojen määrän komennolla "ls -1 | wc -l". <img width="938" height="127" alt="image" src="https://github.com/user-attachments/assets/66b01d0a-9f41-4704-9031-89f772b95142" />
- Pystyn myös putkittamaan "date" komennon Cowasy ohjhelmaan tämän avulla <img width="449" height="218" alt="image" src="https://github.com/user-attachments/assets/bb8983e2-227a-406d-9dec-32c894b500ae" />
# Rauta
- Listaus koneeni raudasta <img width="1139" height="626" alt="image" src="https://github.com/user-attachments/assets/c94277f7-8cad-4fc5-aa85-9bbf8c2ff050" />
- Sain listauksen näkyviin komennolla "sudo lshw -short -sanitize". Jouduin komentoa varten asentamaan lshw:n
- Listauksessa näkyy muunmuassa käyttämäni prosessori, muistin määrä, jonka valitsin itse tehdessäni virtuaalikonetta.

# Lähteet:
Korbin Brown 22 September 2025 Install npm on Linux: https://linuxconfig.org/install-npm-on-linux
Linux Wikipedia: https://www.linux.fi/wiki/Cowsay

Subredditit joista hain ohjelmia:

https://www.reddit.com/r/linuxquestions/

https://www.reddit.com/r/commandline/
