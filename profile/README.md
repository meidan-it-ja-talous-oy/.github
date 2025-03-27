# Meitalainen! 

[Lue käyttö säännöt täältä](https://github.com/meidan-it-ja-talous-oy/.github/blob/master/README.md)

Vaatii Github tunnukset, johon ohjeet [täältä](https://meitafi.sharepoint.com/:w:/s/Meita-Intra/EVqPVCA8615Lhuim4gh7AsUBQCLEEgnMxM5ejVle7VPLQQ?e=OnuLe7)

## Repository nimeämissäännöt

Nimeä uusi ropository niin, että siitä heti selviää mihin järjeestelmään se liittyy. Esim.

Esimerkkejä:

- Wordpress plugin: wp-plugin-meita-plugininnimi
- Wordpress theme: wp-theme-meita-basetwo
- Microservice: ms-microservisenimi
- Docker image Cloud Runissa: varasivusto-job 

## Pakolliset tietoturva asiat

1. Ei authentikaatio tietoja koodiin. Ei salasanoja ei API avaimia. Käytä esim. ympäristömuuttujia ja secrettejä. Jos esim. salasana vahingossa menne versiohallintaan se pitää sieltä poistaa. Pahimmassa tapauksessa ylikirjoittaa koko historia. Tähän löytyy ohjeet Googlettamalla. Ylläpidä repositoryä, mikä mahdollisesti voidaan muutta joskus Open Sourceksi.
2. Jos privaatista repositorystä tehdään julkinen (Open source), niin suositeltu tapa on luoda kokonaan uusi repository ilman historiaa.

## Dokumentointi

Käytä Markdown formaattia dokumentoinnille. Se kestää aikaa ja on esim. palvelimella tekstimuotoisena luettavaa. Jos tarvitset Word dokumenttia, niin kirjoita ensin Markdownina tallenna se versiohallintaan ja luo siitä sitten Word.
[Markdown Cheact Sheet](https://www.markdownguide.org/cheat-sheet/)

### README.md

Jokaisen repositoryn juuresta pitää löytyä README.md, josta pitäsi selvitä lyhyesti uudelle ihmiselle:

- Mikä on repositoryn käyttötarkoitus, selkokielinen kuvaus.
- Vastuuhenkilöt
- Missä järjestelmässä sitä käytetään
- Riippuvuudet muihin järjestelmiin
- Jos koodissa käytetään ympäristömuutujia tai secrettejä. Dokumentoi mitä nämä ovat, miten niitä hallinnoidaan ja mitä oikeuksia ne vaativat.
- Linkitä liittyviin repositoryihin, palvelukuvauksiin ja Meitan dokumentinhallinnan järjestelmäkuvauksiin sekä Meittarin järjestelmäkortteihin.

Tallenna laajempi dokumentaatio `dokumentation` kansioon repossa. sinne voit dumpata laajempaa kuvausta.

### Kuvat eivät ole hyvää dokumentaatiota

- Käytä kuvia dokumentaatioon ainoastaan, kun muuta vaihtoehtoa ei ole. Esim. Älä ota screenshottia pilvikäyttöliittymästä, vaan kirjoita dokumentaatioon komentorivi työkalun komento. Esim. Googlessa GCloud-CLI komento.
- Kirjoita koodi tekstidokumentaatioon aina käyttäen Markdown koodi muotoilua. [Ohje](https://www.markdownguide.org/basic-syntax/#code)

### Automaattisen dokumentaation tuki

- Jos koodi sisältää rajapintoja, niin dokumentoi ne Open API (Swagger) sääntöjen mukaan, niin että koodista voidaan luoda automaattisesti julkaistava API Dokumentaatio.
- Dokumentoi yleensäkin niin että voidaan käyttää kielikohtaisia automaattisia dokumentointi työkaluja JSDoc, PHPDoc jne.

