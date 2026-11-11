# Il Gioco del Caffè — PWA

Pacchetto PWA basato sul file HTML originale fornito. Include manifest, service worker
per la cache dell'app shell e icone per Android/iOS.

## Pubblicazione online

1. Carica **tutto il contenuto** di questa cartella su un hosting statico con HTTPS
   (ad esempio GitHub Pages, Netlify o un tuo hosting).
2. Verifica che `index.html`, `manifest.json`, `sw.js` e la cartella `icons/` siano
   raggiungibili dallo stesso percorso.
3. Apri l'indirizzo HTTPS dal telefono.

## Installazione

- **Android / Chrome:** apri il sito e usa "Installa app" o "Aggiungi a schermata Home"
  dal menu del browser.
- **iPhone / Safari:** apri il sito, tocca Condividi e poi "Aggiungi alla schermata Home".

## Funzionamento offline e multiplayer

La schermata e i file principali vengono memorizzati nella cache dopo la prima visita.
La modalità passa-telefono può essere usata offline dopo il caricamento iniziale.
Il multiplayer richiede Internet: PeerJS è caricato da CDN e usa un servizio di signaling
esterno. Il service worker non mette in cache le risorse di altri domini.

## Limiti da verificare prima di distribuirla

- Testare installazione e aggiornamento su dispositivi Android e iPhone reali.
- Il multiplayer attuale usa PeerJS con signaling predefinito: per un uso pubblico stabile
  è consigliabile predisporre un servizio di signaling/relay gestito e testare reti diverse.
- La cache offline copre la shell dell'app; la libreria PeerJS remota e il multiplayer
  non sono garantiti offline.
- Se l'app viene ospitata in una sottocartella, mantenere coerenti percorso e scope.
