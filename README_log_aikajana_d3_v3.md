# Log Aikajana D3 V3

**Pystysuuntainen logaritminen aikajana**, toteutettu HTML:llä ja D3.js:llä.

## 🔍 Yleiskuvaus

Tämä sivu esittää historiallisen aikajanan **logaritmisella skaalaustavalla** (log10), joka ulottuu ajasta 1 sekunti aina 10^18 sekuntiin (n. 13.8 miljardia vuotta). Aikajana on pystysuuntainen, ja se tukee interaktiivista zoomausta sekä tapahtumien suodattamista aihealueen mukaan.

## 📦 Ominaisuudet

- **D3:n skaala- ja zoom-toiminto**
- **Värikoodatut tapahtumat** viidessä kategoriassa:
  - Kosmos
  - Elämä
  - Ihmiskunta
  - Kulttuuri
  - Teknologia
- **Päätapahtumat** näkyvät vasemmalla vaalealla taustalla
- **Muut tapahtumat** näkyvät parvena oikealla
- **Suodatusvalinnat** kategorioiden mukaan
- **Hiusviivat** yhdistävät tapahtumat aikajanaan

## 🧠 Rakenne

- `index.html`: sisältää kaiken koodin (HTML, CSS ja JS yhdessä tiedostossa)
- SVG-aikajana renderöidään elementtiin `#timeline`
- Zoomaus toimii D3:n `zoom()`-funktion kautta
- Tapahtumat ryhmitellään DOM-elementteinä, ja niiden sijainti lasketaan `log`-arvon avulla

## 📁 Riippuvuudet

- [D3.js v7](https://d3js.org/)

## 🗂️ Datan rakenne

Jokainen tapahtuma on olio, jossa kentät:

```js
{
  label: "Tapahtuman nimi",
  year: "Aikamerkintä",
  log: <log10-arvo sekunteina>,
  main: true/false,
  category: "kosmos" | "elämä" | "ihmiskunta" | "kulttuuri" | "teknologia"
}
```

## 🕹️ Käyttöohjeet

1. Avaa `index.html` selaimessa.
2. Zoomaa hiiren rullalla tai sormieleillä.
3. Ruksaa suodattimia ylhäältä piilottaaksesi/tuodaksesi tiettyjä kategorioita.

## 🛠️ Mahdollisia jatkokehityksiä

- Tooltipit tapahtumien kohdalle
- Ajallisesti lähikuvatut näkymät (esim. viimeiset 1000 vuotta)
- Animaatio tapahtumien ilmestymisestä
- Piste tai symboli aikajanan kohdalle

---

Päivitetty: 2025-06-24
