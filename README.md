# PodoRehab 🦶

PodoRehab è una web app "Podologo Virtuale" pensata per accompagnare i pazienti durante il loro percorso di guarigione e riabilitazione podologica (es. fascite plantare, spina calcaneare).

L'applicazione tiene traccia dei progressi giornalieri, ricorda le regole fondamentali di prevenzione e aggiorna automaticamente il protocollo riabilitativo col passare delle settimane.

## ✨ Funzionalità principali

**Tracciamento Giornaliero (Oggi)**: Una checklist dinamica delle attività terapeutiche da completare ogni giorno. Le spunte si resettano automaticamente a mezzanotte.

**Progressione Automatica (Fasi)**: L'app calcola da quanto tempo l'utente ha iniziato la terapia. Alla Settimana 3, l'interfaccia passa automaticamente dalla fase acuta (es. ghiaccio e riposo) alla fase di riabilitazione attiva (es. esercizi di stretching ed eccentrici).

**Referto Medico Sempre a Portata**: Una sezione fissa dedicata alle regole d'oro e ai consigli strutturali (es. utilizzo delle tallonette in entrambe le scarpe, divieto di camminare scalzi).

**Sistema di Salvataggio Locale**: I dati (data d'inizio terapia e checklist) vengono salvati nel localStorage del browser, garantendo che l'utente non perda i progressi alla chiusura della pagina web.

**Anteprima "Avanti Veloce"**: Un comodo strumento integrato per testare i cambiamenti del protocollo nel tempo senza dover aspettare settimane reali.

## 🚀 Tecnologie Utilizzate

- **React** - Libreria per l'interfaccia utente
- **Tailwind CSS** - Styling e animazioni fluide
- **Lucide React** - Set di icone vettoriali moderne e leggere

## 💻 Come eseguire il progetto localmente

Clona questa repository:
```bash
git clone https://github.com/GitMax76/PodoRehab.git
```

Entra nella cartella del progetto:
```bash
cd PodoRehab
```

Installa le dipendenze:
```bash
npm install
```

Avvia il server di sviluppo:
```bash
npm run dev
```

## 🌐 Pubblicazione (Deployment)

Essendo un'applicazione frontend-only, il deployment è gratuito e velocissimo. L'app usa `gh-pages` per il deployment.

Per aggiornare la versione online (GitHub Pages) lancia questo comando dal terminale:
```bash
npm run deploy
```

Il comando prenderà il codice modificato, lo compilerà nella cartella `/dist/` e lo inoltrerà al branch `gh-pages` senza farti fare manovre complesse su git.

Progettato e sviluppato per digitalizzare e supportare il percorso verso il benessere del piede.
