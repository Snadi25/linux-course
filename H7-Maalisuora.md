# H7-Maalisuora

### a) Hei maailma kolmella kielellä
- Ekaksi loin joka kielelle oman kansion, jotta pysyn helpommin kärryillä missä on mitäkin. Eli käytin mkdir -kansion nimi-.Valitsin kieliksi Pythonin, C ja Javan.
- Loin kansiot hellurei-c, moi-java ja terve-py
- Siirryin hellurei-c kansioon johon loin tiedoston microlla "hei-maailma.c" ja kirjoitin sinne seuraavat tiedot
<img width="1507" height="716" alt="image" src="https://github.com/user-attachments/assets/a64d191a-9013-420b-ac27-af14ce240b96" />

- Tämän jälkeen tiedosto pitää kääntää. Käytän kääntämiseen gcc:tä. Käytin kuvassa näkyvää komentoa. Eli ekaksi laitetaan kääntäjä eli gcc, sen jälkeen tiedosto jonka haluat kääntää ja sitten -o,
  ja viimeisenä uuden tiedoston nimi, jotta tiedän helpommin minkä tiedoston se loi.
<img width="776" height="16" alt="image" src="https://github.com/user-attachments/assets/0d106fe2-5017-4b9d-9d8f-e95853e1f03c" />

- Nyt näen ls komennolla, että gcc loi uuden tiedoston
<img width="463" height="55" alt="image" src="https://github.com/user-attachments/assets/29da2243-7e8d-4b16-a27a-a22efacb2930" />

- Ajoin sitten uuuden tiedoston
<img width="488" height="63" alt="image" src="https://github.com/user-attachments/assets/7ce20d93-f6a2-43fb-a2df-e3ee82357d8c" />

- Sitten loin microlla uuden tiedoston, jonne kirjoitin pelkästään 'print("Hei maailma")'. Tätä tiedostoa ei tarvitse erikseen kääntää, sillä Python on lähes jokaisessa Linux käyttöliittymässä valmiina.
- Ajoin luomani tiedoston
<img width="548" height="54" alt="image" src="https://github.com/user-attachments/assets/fd6f6c1a-7724-4ab9-8cde-eb1dcf9512a2" />

- Viimeisenä loin microlla tiedoston javaa varten. Tässä pitää olla vähän enemmän tarkkana sillä tiedoston nimi pitää vastata tiedostossa olevaa luokan nimeä.
- Kirjoitin tiedostoon kuvassa näkyvät asiat
<img width="1518" height="720" alt="image" src="https://github.com/user-attachments/assets/36e662a5-db48-454b-b1fd-e167373c2bc7" />

- Tässä vaiheessa tajusin, että minun pitää ladata kääntäjä javaa varten. latasin kääntäjän komennolla "sudo apt install default-jdk"
- Käänsin tiedoston komennolla "javac tiedoston nimi", joka loi uuden tiedoston samalla nimellä mutta lopussa on ".class"
<img width="513" height="82" alt="image" src="https://github.com/user-attachments/assets/7bd9cd19-7f4c-471a-910c-4a6bcbcf9250" />

- Sitten ajoin tiedoston
<img width="449" height="74" alt="image" src="https://github.com/user-attachments/assets/4737d606-35b9-407f-9b05-67ad337ab09a" />

### c) Uusi komento Linuxiin
- Loin uuden tiedoston järjestelmän bin kansioon komennolla "sudo micro /usr/local/bin/huomenta"
- Kirjoitin sinne kuvan mukaiset asiat
<img width="1521" height="724" alt="image" src="https://github.com/user-attachments/assets/08e0c4a7-5f47-463b-a8df-29830e417969" />

-Annoin käyttäjille execute oikeudet ja varmistin vielä että oikeudet meni oikein
<img width="634" height="93" alt="image" src="https://github.com/user-attachments/assets/9904c9e8-6675-4a13-9e2b-4fd44e7f5cbb" />

- Nyt voin ajaa komennon missä vain
<img width="548" height="91" alt="image" src="https://github.com/user-attachments/assets/1ac4eee2-0b0c-4bb1-9d8b-c0806389476a" />

- Testasin vielä että komento toimii muillakin käyttäjillä
<img width="541" height="97" alt="image" src="https://github.com/user-attachments/assets/77580b26-388a-4dac-b643-bb63379e98ca" />

### d) Vanha laboratorioharjoitus
- Päädyin tekemään tämän labraharjoituksen: https://terokarvinen.com/2018/arvioitava-laboratorioharjoitus-linux-palvelimet-ict4tn021-8-maanantai-alkukevat-2018-5-op/?fromSearch=laboratorioharjoitus
- Teen harjoituksesta osiot jotka osaan varmasti ja jotka ollaan käyty kurssin aikana läpi.
- Ekana teen uuden komennon nimeltä "ipos", joka näyttää tietokoneen ip-osoitteen.
- Loin tiedoston komennolla "sudo micro /usr/local/bin/ipos"
- Kirjoitin sinne kuvassa näkyvät asiat
<img width="270" height="115" alt="image" src="https://github.com/user-attachments/assets/44eef515-7d4e-4e6d-a301-550100223876" />

- Annoin käyttäjille execute oikeudet. Testasin vielä, että tiedosto toimii
<img width="465" height="58" alt="image" src="https://github.com/user-attachments/assets/328f355c-302c-4a86-9ac7-33baaec0b5b8" />

- Tämän jälkeen loin uuden käyttäjän nimeltä Jorma, johon teen harjoituksessa olevia tehtäviä.
- Luon Jorman kotihakemistoon seuraavat kolme tiedostoa: hei.py, hei.sh ja hei.js
- Kuvissa näkyy mitä kirjoitin sinne
- Hei.py <img width="227" height="57" alt="image" src="https://github.com/user-attachments/assets/9a337717-aa15-42e3-abcb-7249bf6a92c9" />
- Hei.sh <img width="219" height="42" alt="image" src="https://github.com/user-attachments/assets/8b695265-3f47-4620-8e7e-bf62d6e1997d" />
- Hei.js <img width="282" height="51" alt="image" src="https://github.com/user-attachments/assets/29016beb-d213-4467-9c51-d8f6d0c1dff3" />
- Seuraavassa kohdassa teen Jormalle omat kotisivut
- Loin kansion ja sinne index.html sivuston
<img width="709" height="47" alt="image" src="https://github.com/user-attachments/assets/9e8c7a68-eb56-4957-ae97-32a15342e323" />

- Kirjoitin index.html tiedostoon tämän: <img width="380" height="56" alt="image" src="https://github.com/user-attachments/assets/931d9f8e-56e0-49e3-a9e5-9ebf93614bdd" />
- Tein /etc/apache2/sites_available/ kansioon tiedoston nimeltä jorma.conf
<img width="697" height="272" alt="image" src="https://github.com/user-attachments/assets/e112149f-2cef-44af-914d-1abc859800b3" />

- Laitoin sivuston käyttöön komennolla "sudo a2ensite jorma.conf
- käynnistin apachen uudestaan. Menin kokeilemaan toimiiko sivu ja tuli Forbidden virhe
<img width="778" height="326" alt="image" src="https://github.com/user-attachments/assets/81407539-dae1-4b34-b639-ebb0df9034b3" />

- Käydessäni läpi raportointiani huomasin että jorma.conf tiedostossa on DocumentRoot kohdassa ja directoryssä "/home/jorma/public_html/index.html", eikä siinä saa olla tuota index.html kohtaa joten poistin sen.
  Tiedostossa on myös sana "require" pienellä R-kirjaimella vaikka sen pitäisi olla isolla. Tiedostossa oli myös polun ympärillä lainausmerkit, ja kun otin ne pois nii alkoi toimimaan.
<img width="908" height="243" alt="image" src="https://github.com/user-attachments/assets/fedb4d40-5e7a-4696-9aea-8734a42f16d0" />

- Jätin loput labraharjoituksesta tekemättä, sillä ei olla opeteltu niitä asioita tunnilla.

# Lähteet
- Labraharjoitus: Tero Karvinen 2018: https://terokarvinen.com/2018/arvioitava-laboratorioharjoitus-linux-palvelimet-ict4tn021-8-maanantai-alkukevat-2018-5-op/?fromSearch=laboratorioharjoitus
- Tero Karvinen 2018: https://terokarvinen.com/2018/hello-python3-bash-c-c-go-lua-ruby-java-programming-languages-on-ubuntu-18-04/
- Kotitehtävän tehtävänanto: https://terokarvinen.com/linux-palvelimet/#h7-maalisuora

