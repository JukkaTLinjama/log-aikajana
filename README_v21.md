# Logaritminen Aikajana – Versio 21

Tämä versio pohjautuu v20-versioon ja sisältää useita käyttöliittymäparannuksia sekä visuaalisia tarkennuksia erityisesti tapahtumien selkeyttämiseksi.

---

## 🔧 Uudet ominaisuudet

### 1. Päällekkäisten tapahtumien haalistus
- Jokaisessa kortissa tapahtumatekstit tarkistetaan `y`-koordinaatin perusteella.
- Jos useampi tapahtuma on samalla korkeudella (alle 12px erolla), vain ensimmäinen on täysin näkyvä (`opacity: 1`), muut haalistetaan (`opacity: 0.3`).
- Haalistus toimii kaikilla korteilla, ei vain aktiivisella.

### 2. Klikkaus tuo tapahtuman esiin
- Klikkaamalla himmennettyä tapahtumaa se tulee selkeästi näkyviin ja muut samassa ryhmässä haalistuvat.

### 3. Pitkä klikkaus tai kosketus näyttää kommentin
- Kun käyttäjä painaa tapahtumaa yli 400ms, näytetään kommentti popup-laatikossa (`comments`-kenttä).

### 4. Korttien globaalit tilaerot
- Ainoastaan **aktiivinen kortti** on täysin näkyvä.
- Muut kortit (`.card-group.inactive`) ovat automaattisesti haaleita (`opacity: 0.3`).

---

## ⚙️ Tekniset muutokset

- Lisätty `applyOverlapFading()`-funktio, joka analysoi tapahtumat jokaisessa kortissa erikseen.
- Tapahtumat käsitellään ryhminä, ja niille lisätään klikattavuus + pitkä painallus -tuki.
- `fill-opacity` hallinta tapahtuu suoraan `event-label`-elementtien kautta.
- Kommentti-popup luodaan dynaamisesti kerran sivulle (`#comment-box`).
- Kortin tilamuutos tapahtuu `click`-tapahtumalla, joka aktivoi `card-group`-elementin.

---

## 💾 Tietokantarakenne: `eventsDB.json`

Tiedosto sisältää tapahtumaryhmiä teemoittain:

```json
{
  "events": [
    {
      "theme": "kosmos",
      "events": [
        {
          "label": "Alkuräjähdys",
          "year": "13.8e9",
          "time_years": 1.38e10,
          "log": 17.64,
          "ref": "Wikipedia",
          "comments": "Universumin synty"
        },
        ...
      ]
    },
    {
      "theme": "elämä",
      "events": [
        {
          "label": "Elämän synty",
          "year": "3.8e9",
          "time_years": 3.8e9,
          "log": 17.08,
          "ref": "",
          "comments": ""
        },
        ...
      ]
    }
  ]
}
```

### 🔹 Kentät

| Kenttä         | Kuvaus                                     |
|----------------|---------------------------------------------|
| `theme`        | Tapahtumien teema (esim. kosmos, elämä)     |
| `label`        | Tapahtuman nimi                             |
| `year`         | Tapahtuman ajankohta tekstinä               |
| `time_years`   | Tapahtuman ajankohta numeerisena vuosina    |
| `log`          | Logaritminen aika (log10 sekunteina)        |
| `ref`          | Viite (esim. lähde tai URL)                 |
| `comments`     | Vapaa kommentti                             |

---

## 📁 Tiedostot

- `log_aikajana_v21.html` – sisältää kaiken logiikan ja tyylit
- `eventsDB.json` – sisältää tapahtumat, teemat ja lisätiedot (`comments`, `ref`)

---

**Versio 21** tekee tapahtumista helposti hahmotettavia myös tiheässä näkymässä ja mahdollistaa yksittäisten tapahtumien tarkastelun vaivattomasti.
