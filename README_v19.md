# Logaritminen Aikajana v19

Tämä versio visualisoi historian tapahtumia logaritmisella aikajanalla ajassa taaksepäin nykyhetkestä. Käyttöliittymä tukee zoomausta ja eri teemojen korostamista.

## 🔧 Ominaisuudet

- Datan lukeminen ulkoisesta tiedostosta: `eventsDB.json`
- Fallback-tapahtumat sisäänrakennettuna, jos tiedosto ei löydy
- Tukee `theme`-pohjaisia kategorioita (esim. "kosmos", "elämä", "ihmiskunta", ...)
- Tapahtumat visualisoitu värikoodatuissa "korteissa"
- Zoom-indikaattori näyttää nykyisen näkymän sijainnin log-asteikolla

## 📁 Tiedostorakenne

- `log_aikajana_v19.html`: pääsivu, joka lataa datan ja piirtää aikajanan
- `eventsDB.json`: JSON-muotoinen tapahtumatiedosto, jossa on rakenne:

```json
{
  "metadata": { ... },
  "events": [
    {
      "theme": "teema_nimi",
      "events": [
        {
          "label": "Tapahtuman nimi",
          "year": "näytettävä vuosi",
          "time_years": 3.8e9,
          "log": 17.08,
          "author": "",
          "ref": "",
          "comments": ""
        }
      ]
    }
  ]
}
```

## ⚠️ Huomioita

- **JSON-lataus toimii vain localhost-palvelimelta**, esim. `npx http-server` tai `Live Server` VS Codessa. `file://` ei toimi selaimen CORS-politiikan vuoksi.
- Jos `eventsDB.json` ei lataudu, käytetään sisäistä testidataa.
- Sivulla näkyy statusviesti, joka kertoo onko data ladattu onnistuneesti.

## 🛠 Kehitystyökalut

- **Tapahtumaeditori v1**: käytä `nykyhetkesta_editoriformaatti.json`-tiedostoa suoraan muokattavaksi editorissa
- **Valmiit konversiot**: `nykyhetkesta_teemoittain.json` ja `nykyhetkesta_editoriformaatti.json` tuotettu `log_aikajanat3.html`-tiedostosta

## ✅ Versiohistoria

- **v18**: kovakoodatut tapahtumat
- **v19**: ulkoinen JSON-lataus, teemat `theme`-kentässä, editoriyhteensopiva rakenne

---

Päivitetty: 2025-07-29  
Tekijä: Jukka Linjama