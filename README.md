# Meita GitHub Säännöt

Meitan versiohallinan julkiset säännöt. Näillä ohjeilla varmistat ettei työsi mene hukkaa, jos/kun yhtäkkiä kuolet tai koko tiimisi kuolee. Nämä ohjeet myös auttavat Meitaa jatkamaan operaatioitaan pitkälle tulevaisuuteen. Säännöistä on jätetty pois kaikki ei pakollinen. Noudata yleisiä versiohallinnan hyviä tapoja muissa asioissa.

## 1. Repository nimeämissäännöt

Nimeä uusi ropository niin, että siitä heti selviää mihin järjeestelmään se liittyy. Esim.

Esimerkkejä:

- Wordpress plugin: wp-plugin-meita-plugininnimi
- Wordpress theme: wp-theme-meita-basetwo
- Microservice: ms-microservisenimi
- Docker image Cloud Runissa: julkkari-varasivusto-cloud-run-job

## 2. Pakolliset tietoturva asiat

1. Ei authentikaatio tietoja koodiin. Ei salasanoja ei API avaimia. Käytä esim. ympäristömuuttujia ja secrettejä. Jos esim. salasana vahingossa menne versiohallintaan se pitää sieltä poistaa. Pahimmassa tapauksessa ylikirjoittaa koko historia. Tähän löytyy ohjeet Googlettamalla. Ylläpidä repositoryä, mikä mahdollisesti voidaan muutta joskus Open Sourceksi.
2. Jos privaatista repositorystä tehdään julkinen (Open source), niin suositeltu tapa on luoda kokonaan uusi repository ilman historiaa.

## 3. Dokumentointi

### 3.1. Markdown formaatti

Käytä Markdown formaattia dokumentoinnille. Se kestää aikaa ja on esim. palvelimella tekstimuotoisena luettavaa. Jos tarvitset Word dokumenttia, niin kirjoita ensin Markdownina tallenna se versiohallintaan ja luo siitä sitten Word.
[Markdown Cheact Sheet](https://www.markdownguide.org/cheat-sheet/)
[Markdown ohjeita](https://commonmark.org/help/)

### 3.2. Repositoryn juuressa on oltava README.md

  Tiedostossa vähintään seuraavat asiat.
    
  - `# Otsikko` joka kuvaa mahdollisimman hyvin mitä repository kokonaisuutena sisältää
    
    Vakio taulukko joka sisältää aina vähintään seuraavat tiedot selitteet pitää pysyä samana. Rivejä voi lisätä tarvittaessa.

      |Selite|Arvo|
      |-|-|
      | Vastuuhenkilöt       | Kaikkien koodin kehityksessä mukanaolleiden nimet, ensimmäisenä vastuuhenkilö|
      | Muut ympäristöt      | Jos koodi on julkaistu muualla kuin tuotantoympäristössä esim kehitysympäristöt |
      | Tuotantoympäristö    | Tuotantoympäristön tiedot tai osoite |
      | Päivitystapa         | Lyhyesti miten koodi buildtataan, viedään tuotantoon ja päivitetään |
      | Jira-projekti tunnus | Linkki Jira projektiin, jossa on tehtävät |
      | Meittari             | Linkki Meittarin pääsivun johon koodi liittyy |
      | Riippuvuudet         | Pää riippuvuudet ja esim. alusta jolla pyörii |
      | Tilaaja              | Alkuperäinen tilaaja yritys ja yhteyshenkilö, Meita jos ei muuta |
  
  - `## Kuvaus toiminnasta`
    Selkokielinen kuvaus siitä mihin koodia käytetään ja mitä se tekee. Tämän pitää olla tavallisen yhmisen jotenkin ymmärrettävissä. Lisää linkit liittyviin repositoryihin, palvelukuvauksiin ja Meitan dokumentinhallinnan järjestelmäkuvauksiin sekä Meittarin järjestelmäkortteihin.
  - `## Käyttöohjeet`
    Lyhyesti käyttöohjeet, esim. komennot tai pää API enpoint
  - `## Vikatilanteessa`
    Lyhyesti mitä tehdä jos ei toimi. Esim. käynnistä kontti uudelleen, boottaa alustapalvelin. Logi löytyy täältä jne.

### 3.2. Kansio nimellä `documentation`

   `documentation` kansioon kuuluu tallentaa kaikki tarkempi dokumentaatio. Sisällöllä tai tiedostoilla ei ole väliä, mutta suosi tekstidokumentteinä yksinkertaista teksti formaattia kuten "Markdown". Älä tallenna Word dokumentteja tai videoita eli isoja tiedostoja. Tarkoitus on, että kaiken dokumentaation voi lukea ilman erillisiä ohjelmia esim. ollessasi komentoriviltä yhteydessä palvelimeen.

   Täällä saa ja on suositeltavaa kirjoittaa englanniksi.

   Linkitä suoraan juuren README.md tiedostossa relatiivisesti dokumentteihin `documentation` kansiossa.

### 3.3. Dokumentoi koko repositoryn sisältämä koodi.

   Älä oleta liikoja ihmiseltä, joka avaa repositoryn. Oleta, että repositoryn avaava henkilö on jonkun verran koodausta osaava ihminen, jolle ei kuitenkaan ole tarjolla minkäänlaista perehdytystä juuri tähän koodiin.

### 3.4. Dokumentoi myös asetukset ja komennot

   Kirjoita millä komennoilla ja minkälaisessa ympäristössä koodi käynnistyy ja mitä pitäisi näkyä ja missä jos kaikki on ok. Tuotanto ja lokaali kehitys erikseen.

   Jos koodissa käytetään ympäristömuutujia tai secrettejä. Dokumentoi mitä nämä ovat, miten niitä hallinnoidaan ja mitä oikeuksia ne vaativat.
   
### 3.5. Älä jätä mitään koodiin olennaisesti liittyvään piiloon, mutta piilota salattavat asiat

   Jos/kun käytät .gitignore tiedostoa piilottaaksesi osan versiohallinnasta. Dokumentoi se. Esim. jos käytät ympäristömuuttujille, API avaimille ja salasanoille .env tiedostoa lokaalissa ympäristössä, niin dokumentoi mitä ympäristömuuttujia koodisi tarvitsee toimiakseen. Muista lisäksi dokumentoida mistä nämä salaiset tiedot saa pyydettyä tarvittaessa.

   Älä kova koodaa mitään, mikä on ympäristöstä riippuvaista. Käytä esim. Kuberneteksen secret:ejä tai ympäristömuuttujia.

   Älä jätä dokumentaatiota pelkästään koodin väliin vaan selitä asiat myös ylemmältä tasolta selkokielellä.

### Kuvat eivät ole hyvää dokumentaatiota

   Käytä kuvia dokumentaatioon ainoastaan, kun muuta vaihtoehtoa ei ole. Esim. Älä ota screenshottia pilvikäyttöliittymästä, vaan kirjoita dokumentaatioon komentorivi työkalun komento. Esim. Googlessa GCloud-CLI komento.
   
   Kirjoita koodi tekstidokumentaatioon aina käyttäen Markdown koodi muotoilua. [Ohje](https://www.markdownguide.org/basic-syntax/#code)

### Automaattisen dokumentaation tuki

   Jos koodi sisältää rajapintoja, niin dokumentoi ne Open API (Swagger) sääntöjen mukaan, niin että koodista voidaan luoda automaattisesti julkaistava API Dokumentaatio.
   
   Dokumentoi yleensäkin niin että voidaan käyttää kielikohtaisia automaattisia dokumentointi työkaluja JSDoc, PHPDoc jne.

## Ohjeet kirjoitti

Lauri Merisaari

Käytäntöä kuuluu muuttaa, jos se on kohtuullinen  vaiva ja parantaa järjesystä, tietoturvaa tai tehokkuutta.

kiitos tästä!

