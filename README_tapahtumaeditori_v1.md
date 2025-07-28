# Tapahtumaeditori v1

**Tapahtumaeditori** on selainkäyttöinen HTML-sovellus, jolla voi tarkastella ja muokata historiallisia tapahtumia JSON-muodossa. Sovellus on osa _logaritmista aikajana_ -projektia.

## ✅ Ominaisuudet

- Muokattava taulukko tapahtumista, ryhmiteltyinä teemoihin
- Automaattinen `log`-arvon laskenta kentästä `time_years`
- `time_years` voidaan syöttää **sci-notaatiossa** (esim. `3.8e9`)
- `ref` ja `comments` ovat monirivisiä kenttiä (`<textarea>`)
- JSON-yhteenveto päivittyy reaaliajassa
- JSON-tallennus tieteellisessä muodossa (`1.38000000e+10`)

## 💾 Käyttö

1. Avaa `eventEditor_v12.html` selaimessa
2. Lisää tai muokkaa tapahtumia
3. `time_years`-kenttään voi syöttää:
   - tavallinen desimaaliluku: `3800000000`
   - tieteellinen muoto: `3.8e9`
4. Sovellus laskee `log`-arvon automaattisesti
5. Tallenna JSON-nappi lataa datan tiedostona `eventsDB.json`

## 🧮 Kentät

| Kenttä        | Kuvaus                                       |
|---------------|-----------------------------------------------|
| theme         | Teeman nimi (esim. "kosmos")                  |
| label         | Tapahtuman otsikko                            |
| year          | Ajan esitysmuoto ihmiselle (esim. "13.8 mrd v") |
| time_years    | Aika vuosina (sci- tai desimaalimuoto)        |
| log           | Automaattisesti laskettu log10(aika sekunteina) |
| author        | Kirjoittajan/tekijän nimikirjaimet            |
| ref           | Linkki lähteeseen                             |
| comments      | Vapaamuotoiset lisähuomiot                    |

## 🔧 Kehitysversio v1.4

- Tallennus muotoilee `time_years` aina `toExponential(8)`
- `input`-kenttä ei enää tyhjenny heti kirjoittaessa
- `log` päivittyy vasta kun `time_years` menettää fokuksen

---

🧠 **Tavoite** on yhdistää tämä editori myöhemmin visuaaliseen aikajanaan, joka käyttää logaritmista skaalaa ja väriteemoja.