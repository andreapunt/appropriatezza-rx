# Appropriatezza RX PWA 1.2.1

## File
- `index.html`: applicazione definitiva.
- `manifest.webmanifest`: dati di installazione PWA.
- `service-worker.js`: cache offline e aggiornamento della shell applicativa.
- `offline.html`: fallback in assenza di cache.
- `icons/`: icone normali e maskable 192/512 px.

## Pubblicazione
Caricare l'intera cartella, senza cambiare la struttura, su un sito servito tramite HTTPS. Non aprire `index.html` con `file://`, perché i service worker richiedono un contesto sicuro. Per i test locali usare `localhost`.

Esempio locale con Python:

```bash
python3 -m http.server 8080
```

Aprire quindi `http://localhost:8080/`.

## Aggiornamenti
Quando si pubblica una nuova versione, modificare `CACHE_NAME` in `service-worker.js`, per esempio `appropriatezza-rx-v1.2.2`, così i client sostituiranno la vecchia cache.

## Verifica
In Chrome o Edge aprire Strumenti per sviluppatori > Application e controllare Manifest e Service Workers. È possibile eseguire anche Lighthouse.
