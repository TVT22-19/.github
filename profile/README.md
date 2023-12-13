![Banner](https://github.com/TVT22-19/.github/blob/main/tvt22-19.png?raw=true)

# TVT22-19-ryhmä

## Movie App – elokuvaharrastajien web-sovellus

### Projektin sisältö ja tekijät

Tämän projektin tarkoituksena oli toteuttaa fullstack-sovellus, joka tarjoaa käyttäjilleen mahdollisuuksia löytää kiinnostavia elokuvia, lukea elokuva-aiheisia uutisia, jättää elokuva-arvosteluja, kustomoida omaa profiilisivuaan ja luoda yksityisiä ryhmiä, joissa ryhmän jäsenet voivat jakaa uutisia ja keskustella elokuvista. Sovelluksen käyttäjäpuoli toteutettiin React-kirjaston avulla ja palvelin Node.js:llä. Lisäksi projektikurssin sisältöön kuului sovelluksen rajapinnan testaaminen Mocha- ja Chai-kirjastoilla.

Projektin toteutti ryhmä, joka muodostui neljästä Oulun ammattikorkeakoulun tieto- ja viestintätekniikan opiskelijasta. Projekti ajoittui opintojen toisen vuoden syyslukukaudelle.

- Asla Riihimaa – päätehtävänä ryhmäsivut: käyttäjäpuolen ryhmäsivu ja pääosa sen toiminnoista sekä ryhmiin liittyvät palvelinpuolen endpointit. Lisäksi hakusivu ja sekalaisia backend-frontend-integrointitehtäviä.
- Kit Lehto – vastuussa käyttäjäpuolen muiden osioiden toteuttamisesta.
- Tazhidin Magaramov – vastuu tietokannan luomisesta sekä palvelinpuolen endpointit, kuten DELETE/api/delete, POST/api/auth(registration), GET/api/login, Search.
- Topi Törmälä – palvelinpuoli-painotus, vastuu endpointeista kuten:

Sovellus toteutettiin asiakas-palvelinarkkitehtuurilla. Sivusto on tarkasteltavissa osoitteessa [https://tvt22-19.github.io/movie-app-frontend/](https://tvt22-19.github.io/movie-app-frontend/). Sovelluksen toimintaa esitellään myös seuraavalla videolla: [video tähän]

### Käytetyt teknologiat

Sovelluksessa käytettävät teknologiat valittiin suurimmaksi osaksi tehtävänannon perusteella. Lisäksi valittiin Material UI-kirjasto nopeuttamaan käyttöliittymän ulkoasun toteuttamista.

#### Back-end

- ExpressJS pääasiallisena REST-palvelukehyksenä
- Dotenv turvallisille tiedoille, joita ei pitäisi ladata
- BCrypt salasanan hajautusta varten
- PG pääsyä varten tietokantaan
- FastXMLParser XML-tiedostojen jäsentämiseksi JSON-muotoon

#### Front-end

- React pääkäyttöliittymän renderöintikirjastona
- Material UI – UI-kitti
- TanStack Query (React Query) API-pyyntöjen käsittelyyn ja tilanhallintaan
- TypeScript - turvallisempi koodi ja vähemmän bugeja

### Tietokantarakenne

Movie App -tietokanta (kuva 1) on suunniteltu tarjoamaan elokuva- ja sisältökeskeisiä sovellustoimintoja. Tämä tietokanta toteuttaa järjestelmän käyttäjien, ryhmien, ryhmien viestien, ryhmiin liittymispyyntöjen, käyttäjäarvostelujen ja yleisen palautteen hallinnan.

![Er-kaavio](https://github.com/TVT22-19/.github/blob/main/public.png?raw=true)

**Kuva 1. ER-kaavio**

Tärkeimmät tietokannan osat:

1. **Käyttäjät:**
   - Sisältää tietoja rekisteröidyistä käyttäjistä, mukaan lukien yksilölliset tunnisteet, nimet, iän ja muut henkilötiedot.
2. **Ryhmät:**
   - Käyttäjät voivat luoda ryhmiä ja liittyä niihin keskustellakseen ja jakaakseen sisältöä. Sisältää tietoja ryhmän nimestä, kuvauksesta ja muista ominaisuuksista.
3. **Viestit ryhmissä (group_posts):**
   - Tallentaa käyttäjien ryhmissä julkaisemat viestit. Sisältää tiedot julkaisun sisällöstä, kirjoittajasta, julkaisuajasta ja yhteydestä ryhmään.
4. **Käyttäjäryhmien yhdistäminen (user_groups):**
   - Näyttää käyttäjien jäsenyyden tietyissä ryhmissä, mukaan lukien päivämäärä, jolloin he liittyivät.
5. **Ryhmään liittymispyynnöt (join_request):**
   - Sisältää pyyntöjä käyttäjiltä, jotka haluavat liittyä ryhmään, ja jotka osoittavat pyynnön tilan (hyväksytty/hylätty).
6. **Arvostelut:**
   - Sisältää kootut arvostelutiedot, kuten käyttäjän antaman arvion (0-5 tähteä) ja kunkin sisällön arvostelujen kokonaismäärän.
7. **Käyttäjien arvostelut:**
   - Tämä taulukko yhdistää arvostelut ja käyttäjätaulukot, ja sen avulla päästään nopeasti tarvittaviin tietoihin.

### Sovelluksen käyttöönotto

Sovellus voidaan asentaa ja ottaa käyttöön ajamalla seuraavat komennot: 

Frontend:

```
git clone https://github.com/TVT22-19/movie-app-frontend.git 

cd movie-app-fronted/ 

npm install 

npm run build 

node .dist/index.js 

```

Backend (lokaalikopio): 
```
git clone https://github.com/TVT22-19/movie-app-backend.git 

cd movie-app-backend/ 

npm install 

npm start 
```

