# Log History Timeline v14

Tämä versio visualisoi logaritmisen aikajanan suurimmista kosmisista ja kulttuurisista tapahtumista. Visualisointi on toteutettu D3.js-kirjastolla.

## 🆕 Uutta v14:ssa

- ✅ Tapahtumista lähtee viivat akselille osoittamaan tarkkaa aikaa
- ✅ Viivat renderöidään keskikohdalta ja päivittyvät zoomauksen mukana
- ✅ Viivojen pituus sidottu vasempaan akseliin (logaritminen aikaskaala)
- ✅ Kortteja voi klikata, jolloin ne tulevat näkyväksi (blur pois päältä)
- ✅ Alustava valinta: `ihmiskunta` on valittu aktiiviseksi oletuksena
- ✅ Otsikko ja akseliteksti lisätty DOM-elementteinä (`<h1>` ja `<div>`)
- 🔧 Valmius lisätä `clipPath`, jotta kortit eivät piirry akselin yli

## Rakenne

- Jokainen `card` on D3:n `g`-elementti, jonka sisällä:
  - `rect`: värillinen taustakortti (`.card`), leveys suhteessa viewportiin
  - `text.card-label`: kategorian nimi kortin yläosassa
  - `text.event-label`: yksittäiset tapahtumat (label + vuosi)
  - `line.event-line`: viiva joka osoittaa logaritmiselle aikajanalle

- Aikajana on logaritminen skaala (`scaleLog`): 1 sekunti – 1e20 sekuntia
- Tapahtumien pystysijainti lasketaan `currentY(Math.pow(10, log))`

## Akseli

- Vasemmalle piirretään D3:n `axisLeft`, automaattisilla tickeillä
- Akselin yksikkö merkitty tekstinä: `time from present [s]`
- Akselin paikka on kiinteä (vasemmassa reunassa, `margin.left`)

## Zoom

- D3 `zoomBehavior` skaalan ja translataation hallintaan
- `transform.rescaleY(yBase)` palauttaa logaritmisen skaala-arvon
- Kaikki `y`-arvot päivitetään zoomauksen yhteydessä
- `zoomWindow`-osoitin vasemmalla kertoo käyttäjälle zoom-alueen

## Graafiset detaljit

- Korttien ulkonäkö määritetty CSS:ssä:
  - `fill-opacity: 0.35`
  - `stroke`: hento reunaviiva, suodatettu varjolla (`feDropShadow`)
  - `filter: blur(2px)` käytössä ei-aktiivisilla korteilla
- Värit kategorioittain (vaaleat pastellit), määritetty `categoryColors`-objektissa
- Viivojen sijoitus: `x1` lasketaan akselin mukaan `transform`-attribuutista

## Suunniteltua

- [ ] `clipPath` estämään kortteja piirtymästä akselin päälle
- [ ] Tooltip tai hover-kohdistin akselille
- [ ] Kategoriavalinnat (`checkbox`) suodatukseen
- [ ] Elementtien animointi (hover, transition)

---

🧠 Tämä versio on visuaalisesti ja teknisesti valmis pohja jatkokehitykselle.