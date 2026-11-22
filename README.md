# 🏠 Spese di casa

App per dividere a metà le spese di casa, pensata per il telefono (iPhone e Android).

**App:** https://infostservice-creator.github.io/spese-domestiche/
**Demo con dati finti:** https://infostservice-creator.github.io/spese-domestiche/?demo=1

## Cosa fa
- **Home:** chi deve a chi (dall'ultimo pareggio), totale speso nel mese, inserimento rapido, pareggio in due step (STEP 1 + "SALDATO").
- **Lista:** storico per anno, schede Lucia / Sergio / Tutte, eliminazione con doppia conferma (eliminazione logica: nel foglio resta traccia).
- **Grafici:** totale della famiglia mese per mese.
- **Ricorrenti:** spese mensili (es. apparecchio dei denti) con avviso in Home e una mail il giorno della scadenza.
- **Soglia 1.000 €:** banner nell'app e mail quando il debito supera la soglia.
- Si installa sulla schermata Home (manifest + icone) e ha la modalità scura automatica.

## Come è fatta
- `index.html`: tutta l'app (HTML, CSS e JavaScript, senza librerie esterne).
- `manifest.webmanifest`, `icon.svg`, `icon-192.png`, `icon-512.png`, `apple-touch-icon.png`: installazione come app.
- Backend: Google Sheet + Apps Script pubblicato come web app; l'app ci parla via JSONP.
  Il codice Apps Script **non** è in questo repository (cartella `apps-script/` esclusa dal `.gitignore`).

## Sicurezza
- Ogni chiamata richiede il **codice di famiglia**, salvato solo nelle Script Properties (`FAMILY_TOKEN`) e, sul telefono, nel `localStorage`.
- Le email stanno nelle Script Properties (`EMAIL_SERGIO`, `EMAIL_LUCIA`), mai nel codice.
