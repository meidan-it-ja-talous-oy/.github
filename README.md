# meita-git-rules

Meitan versiohallinan julkiset säännöt. Näillä ohjeilla varmistat ettei työsi mene hukkaa, jos/kun yhtäkkiä kuolet tai koko tiimisi kuolee.
Nämä ohjeet myös auttavat Meitaa jatkamaan operaatioitaan pitkälle tulevaisuuteen. Säännöistä on jätetty pois kaikki ei pakollinen. Noudata
yleisiä versiohallinnan hyviä tapoja muissa asioissa.

## 1. Repositoryn juuressa on oltava README.md suomeksi tekstitiedosto

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
      | Tilaaja              | Alkuperäinen tilaaja yritys, Meita jos ei muuta |
  
  - `## Kuvaus toiminnasta`
    Selkokielinen kuvaus siitä mihin koodia käytetään ja mitä se tekee. Tämän pitää olla tavallisen yhmisen jotenkin ymmärrettävissä
  - `## Käyttöohjeet`
    Lyhyesti käyttöohjeet, esim. komennot tai pää API enpoint
  - `## Vikatilanteessa`
    Lyhyesti mitä tehdä jos ei toimi. Esim. käynnistä kontti uudelleen, boottaa alustapalvelin. Logi löytyy täältä jne.

## 2. Kansio nimellä `documentation`

   `documentation` kansioon kuuluu tallentaa kaikki tarkempi dokumentaatio. Sisällöllä tai tiedostoilla ei ole väliä, mutta suosi
   tekstidokumentteinä yksinkertaista teksti formaattia kuten "Markdown". Älä tallenna Word dokumentteja tai videoita eli isoja
   tiedostoja. Tarkoitus on, että kaiken dokumentaation voi lukea ilman erillisiä ohjelmia esim. ollessasi komentoriviltä
   yhteydessä palvelimeen.

   Täällä saa ja on suositeltavaa kirjoittaa englanniksi.

   Linkitä suoraan juuren README.md tiedostossa relatiivisesti dokumentteihin `documentation` kansiossa.

## 4. Dokumentoi koko repositoryn sisältämä koodi.

   Älä oleta liikoja ihmiseltä, joka avaa repositoryn. Oleta, että repositoryn avaava henkilö on jonkun verran koodausta osaava
   ihminen, jolle ei kuitenkaan ole tarjolla minkäänlaista perehdytystä juuri tähän koodiin.

## 5. Dokumentoi myös asetukset ja komennot

   Kirjoita millä komennoilla ja minkälaisessa ympäristössä koodi käynnistyy ja mitä pitäisi näkyä ja missä jos kaikki on ok.
   Tuotanto ja lokaali kehitys erikseen.
   
## 6. Älä jätä mitään koodiin olennaisesti liittyvään piiloon, mutta piilota salattavat asiat

   Jos/kun käytät .gitignore tiedostoa piilottaaksesi osan versiohallinnasta. Dokumentoi se. Esim. jos käytät
   ympäristömuuttujille, API avaimille ja salasanoille .env tiedostoa lokaalissa ympäristössä, niin dokumentoi mitä ympäristömuuttujia
   koodisi tarvitsee toimiakseen. Muista lisäksi dokumentoida mistä nämä salaiset tiedot saa pyydettyä tarvittaessa.

   Älä kova koodaa mitään, mikä on ympäristöstä riippuvaista. Käytä esim. Kuberneteksen secret:ejä tai ympäristömuuttujia.

   Älä jätä dokumentaatiota pelkästään koodin väliin vaan selitä asiat myös ylemmältä tasolta.

## Linkkejä

  [Markdown ohjeita](https://commonmark.org/help/)

## Ohjeet kirjoitti

Lauri Merisaari

Tämä ei ole ylhäältä määrätty pakollinen käytänto vaan hieman järjestystä kaaokseen. Käytäntöä kuuluu muuttaa, jos se on kohtuullinen 
vaiva ja parantaa järjesystä ja tehokkuutta.

kiitos tästä!

