# Logaritminen Aikajana v12 (Zoom + Akseli)

Tämä versio visualisoi tapahtumia logaritmisella aikajanalla käyttäen D3.js-kirjastoa.

## 🔧 Ominaisuudet

- **Logaritminen y-akseli** (1 sekunti – 10²⁰ sekuntia)
- **Klikattavat kategoriakortit**, jotka nousevat päällimmäiseksi ja poistavat blur-efektin
- **Korttien sisällä tapahtumien aikaleimat oikeassa log10-koordinaatissa**
- **Zoomaus ja pan** hiirellä tai kosketuksella
- **Zoom-indikaattori** vasemmassa laidassa näyttää nykyisen näkyvän aikajanan alueen
- **SVG-filterillä toteutettu varjoefekti**
- **.datum(...) logiikka** estää korttien väärän paikan zoom-päivityksissä

## 🗂 Tiedostot

- `log_aikajana_v12_fixed.html` – koko sovellus yhdessä HTML-tiedostossa (suositeltu versio)

## 📌 Riippuvuudet

- [D3.js v7](https://d3js.org/)

## 📎 Huomioita

- Y-akselin arvoina käytetään logaritmista skaalaa sekunneissa
- Korttien läpinäkyvyys: `fill-opacity: 0.85`
- Kortit siirretty hieman irti akselista (`+30 px` siirtymä)
- Zoomin skaalausvälit: `0.1 – 10×`

## 💡 Kehitysvinkkejä

- Lisää decade-labelit vasemmalle kuten versiossa v8
- Lisää hover-efekti korteille
- Lisää filter-napit kategorioille

