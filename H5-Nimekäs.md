# H5 - Nimekäs

a) Nimen vuokraaminen
- Vuokrasin nimen NameCheap sivustolta, sillä käytimme sitä esimerkissä tunnilla ja se vaikutti yksinkertaiselta.
- Päätin ottaa domain nimen kahdeksi vuodeksi kerralla, enkä valinnut mitään muita lisä juttuja, sillä en koe niitä tarpeellisiksi.
<img width="1007" height="706" alt="image" src="https://github.com/user-attachments/assets/ec3faaf6-bb74-43a8-8677-64a5e02411aa" />

- Sitten sivusto kysyy perustietoja kuten osotteen, puhelin numeron yms. Huomasin osoitetta laittaessa, että sivusto ei anna käyttää ääkkösiä joita osoitteessani on. Toivon, että tästä ei koidu harmia myöhemmin.
- Osoitetietojen jälkeen sivusto pyytää pankkikortintietoja.
- Samalla sivulla missä laitettiin pankkikortintiedot oli kohta missä pysty valita automaattisen uusimisen. Laitoin siihen ruksin, jotta ei vahingossakaan jää domain maksamatta ja menetä sitä sen seurauksena.
- Nyt minulla on oma domain nimi
<img width="1477" height="707" alt="image" src="https://github.com/user-attachments/assets/91cf4b7b-f318-4de4-baa1-313b90280669" />

b) Alidomain
- Menin Namecheap sivustilla domain list kohtaan ja painoin minun domainin kohdalla "manage" nappulaa.
- Tämän jälkeen menin Advanced DNS kohtaan.
- Sitten valitsin "ADD NEW RECORD", valitsin tyypiksi A record, host kohtaan minkä haluan nimeksi, ja viimeiseksi sivustoni ip osoite
<img width="1109" height="390" alt="image" src="https://github.com/user-attachments/assets/56f0eaab-8a2d-4ab2-9ad2-3b2dc1ced7a9" />

- Tein alidomaineja kaksi kappaletta "cv" ja "testi". Molemmat menevät vielä tällä hetkellä samalle pääsivustolle.

c) Host ja dig
- Host komento antaa domainin ip osoitteen, myös jonkun mail osoitteen, joka löytyy myös NameCheap sivustolta domainini Advanced DNS asetuksista
<img width="813" height="515" alt="image" src="https://github.com/user-attachments/assets/d5009761-d140-4723-8203-6cf1095e9241" />
<img width="1143" height="267" alt="image" src="https://github.com/user-attachments/assets/37dcab97-824d-4a11-ad84-7e484ebc6196" />

- "dig" komento puolestaan palauttaa paljon yksityiskohtaisemmin tietoa domainista ip osoitteen lisäksi
<img width="760" height="385" alt="image" src="https://github.com/user-attachments/assets/40d1f35f-dda5-409b-ae9e-4694540f8c93" />

- ANSWER SECTION kohdassa näkyy domain nimi minkä laitoin NameCheap palvelussa CNAME Record kohtaan ja palvelimen ip osoite
<img width="1105" height="67" alt="image" src="https://github.com/user-attachments/assets/5d073bb1-ab6d-433d-b373-f533a66884dd" />

- Samassa kohdassa nimen jälkeen on numero jota kutsutaan TTL numeroksi (Time To Live) joka kertoo kuinka monta sekuntia tieto voi olla välimuistissa ennenkuin se on haettava uudestaan.
- IN sanan jälkeen on A kirjain joka kertoo että domainin ip osoite on IPV4 osoite.
- Käytin samaa dig komentoa geeksforgeeks sivustolle ja tuli tällainen vastaus
<img width="798" height="453" alt="image" src="https://github.com/user-attachments/assets/b096a85b-0108-42cd-b49e-7ec273fd8c16" />

- Kuvassa näkyy että niillä on neljä eri IPV4 osoitetta, ja TTL numero on 60
- Jos tein dig haun reddit sivustolle, kuvasta huomaa että niilläkin on 4 eri IPV4 osoitetta ja TTL numero on 154
<img width="796" height="457" alt="image" src="https://github.com/user-attachments/assets/38990ae0-0984-4881-ba66-28512e84b452" />

- Hauissa huomaa kuinka paljon pienemmät TTL numerot sivustoilla on ja kuinka monta eri ip osoitetta on verrattuna minun omaan sivustooni, jotta he voivat tasata sivuston kuormaa eri ip osoitteille ja muuttaa ohjausta nopeasti.

## Lähteet:
- GeeksforGeeks 2025: dig Command in Linux with Examples https://www.geeksforgeeks.org/linux-unix/dig-command-in-linux-with-examples/
- GeeksforGeeks 2019: host command in Linux with examples https://www.geeksforgeeks.org/linux-unix/host-command-in-linux-with-examples/
- Kotitehtävän tehtävänanto: https://terokarvinen.com/linux-palvelimet/#h5-nimekas
