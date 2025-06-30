# Logaritminen Aikajana – Versio 6

Tämä on D3.js-pohjainen interaktiivinen aikajana, joka esittää historian tapahtumat logaritmisessa aikaskaalassa sekunneista 1e0 aina 1e18 sekuntiin (noin 13,8 miljardia vuotta). Versiossa 6 aikajana on viimeistelty toimivaksi responsiivisena ja zoomattavana.

## Uudet ominaisuudet v6

- **Täysin responsiivinen:** täyttää selainikkunan pystysuunnassa automaattisesti.
- **Kiinteä vasemman reunan skaala:** näyttää aina koko 0–18 logaritmisen alueen.
- **Zoom-indikaattori:** näyttää zoomatun alueen sijainnin kiinteässä janassa.
- **Perinteinen D3:n inertia zoomissa:** smooth zoomaus rullalla ja pinchillä.
- **Suodatus:** tapahtumia voi suodattaa kategorioittain (kosmos, elämä, ihmiskunta, kulttuuri, teknologia).

## Käyttö

1. Avaa `index.html` selaimessa.
2. Vieritä hiirellä tai käytä kosketuslaitteen pinch-zoomia.
3. Suodata tapahtumia valitsemalla kategorioita sivun yläosasta.

## Rakenne

- **HTML/CSS/JS**: ei riippuvuuksia kuin D3.js (cdn).
- **Data**: JSON-tyylinen taulukko JS-koodin alussa (helppo muokata).
- **D3-zoom**: hoitaa skaalaamisen ja inertian automaattisesti.
- **Responsiivisuus**: elementtien koot ja skaala päivittyvät selaimen koon muuttuessa.

## Tunnetut rajoitukset

- Vierityksen inertia toimii vain, kun zoom tapahtuu D3:n kautta (esim. hiiren rulla), ei selainikkunan oman scrollauksen kautta.

## Tiedostot

- `index.html`: sisältää kaiken tarvittavan aikajanan näyttämiseen ja interaktioihin.
- Ei erillisiä CSS- tai JS-tiedostoja.

## Lisenssi

Tämä projekti on vapaa omaksi oppimiskäyttöön ja jatkokehitykseen.
