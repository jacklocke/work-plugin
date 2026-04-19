# Work Plugin

Plugin per [Obsidian](https://obsidian.md) che aggiunge una finestra di ricerca rapida nel vault, con supporto alla navigazione da tastiera e integrazione con DokuWiki.

---


## Installazione manuale

Da terminale vai nel tuo vault, nella cartella `.obsidian/plugins` e clona questo repository dentro la cartella.

La struttura finale dovrebbe essere:

```.obsidian/
  plugins/
    work-plugin/
      main.js
      manifest.json
      styles.css
      ... (altri file)
```

---

## Funzionalità

### Ricerca rapida nel vault

Apre una finestra modale che permette di cercare note all'interno del vault (o di una sottocartella configurata).

- **Ricerca in tempo reale** — i risultati si aggiornano ad ogni carattere digitato
- **Ricerca per nome file** — controllo rapido sul nome della nota
- **Ricerca nel contenuto** — scansione del testo della nota tramite la cache di Obsidian
- **Ricerca ignorando la formattazione Markdown** — `**grassetto**`, `*corsivo*`, `[[wikilink]]`, ecc. vengono rimossi prima della comparazione, così "un plugin personalizzato" trova anche "un **plugin** _personalizzato_"
- **Badge "contenuto"** — indica visivamente se il match è nel testo (non nel nome del file)

### Navigazione da tastiera

Nella finestra di ricerca è possibile spostarsi tra i risultati senza usare il mouse:

| Tasto | Azione |
|-------|--------|
| `↓` / `↑` | Sposta la selezione tra i risultati |
| `Invio` | Apre il file selezionato |
| `Invio` (senza selezione) | Esegue la ricerca |

### Ricerca su DokuWiki

Se è configurato un URL base DokuWiki nelle impostazioni, nella finestra di ricerca appare un pulsante **🌐 DokuWiki** che apre la stessa query nel browser, usando il formato:

```
https://wiki.esempio.it?do=search&q=parola1+parola2
```

Il pulsante è disabilitato finché la query è vuota e non compare se l'URL non è configurato.

---

## Come aprire la ricerca

- **Icona nella barra laterale sinistra** — clic sull'icona 🔍
- **Comando da palette** — `Apri ricerca nella cartella Wiki`
- **Shortcut da tastiera** — assegnabile da *Impostazioni → Tasti di scelta rapida*, cercando `Apri ricerca nella cartella Wiki`

---

## Impostazioni

Accessibili da *Impostazioni → Plugin di terze parti → Work Plugin*.

| Impostazione | Descrizione | Default |
|---|---|---|
| **Cartella di ricerca** | Sottocartella del vault in cui limitare la ricerca. Lascia vuoto per cercare in tutto il vault. | `wiki` |
| **URL base DokuWiki** | Indirizzo base della DokuWiki (es. `https://wiki.esempio.it`). Lascia vuoto per disabilitare il pulsante. | _(vuoto)_ |

---

## Requisiti

- Obsidian `0.15.0` o superiore
