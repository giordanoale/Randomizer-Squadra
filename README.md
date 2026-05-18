# Tibia e Perone — Ultimate Team Edition

**Draft Night** è un'app web per sorteggiare casualmente due squadre da 10 giocatori di calcio a 5, con un'esperienza ispirata all'apertura dei pacchetti di FIFA Ultimate Team.

## Demo

Apri `index.html` direttamente nel browser — nessun server o dipendenza richiesti.

## Funzionalità

- **Apertura pacchetto animata** — effetto floating e glow prima di rivelare i giocatori
- **Reveal carta per carta** — flip 3D, esplosione di particelle e flash colorato a ogni rivelazione
- **Distribuzione automatica** — 1 portiere + 4 giocatori di movimento per squadra, sorteggio casuale
- **Rating random** — ogni carta riceve un rating generato al volo (80–92 per i portieri, 72–88 per gli altri)
- **Mini card laterali** — i giocatori già rivelati appaiono nei pannelli Squadra A / Squadra B
- **Risultati finali** — riepilogo completo delle due rose dopo il draft
- **Nuovo Draft** — rimescola e ricomincia senza ricaricare la pagina

## Come funziona

1. Clicca **"Apri il Pacchetto"** sulla pagina principale
2. Tocca il pacchetto animato per avviare il reveal
3. Le carte vengono mostrate una alla volta con animazione — clic per accelerare
4. Al termine clicca **"Vedi Squadre"** per il riepilogo finale
5. Usa **"Nuovo Draft"** per un nuovo sorteggio

## Struttura del progetto

```
.
├── index.html        # App completa (HTML + CSS + JS inline)
└── giocatori.json    # Lista giocatori (reference — i dati sono embedded nell'HTML)
```

## Modificare la lista giocatori

I giocatori sono definiti direttamente nell'`index.html`, nel tag `<script id="giocatori-data">`:

```json
[
  { "nome": "Nome Cognome", "portiere": false },
  { "nome": "Nome Cognome", "portiere": true  }
]
```

- `"portiere": true` — il giocatore può essere sorteggiato come portiere
- Servono **almeno 2 portieri** nella lista per formare le due squadre
- La rosa attuale conta **10 giocatori** (2 portieri + 8 di movimento)

## Tecnologie

- HTML5 / CSS3 / JavaScript vanilla — zero dipendenze esterne
- Font: [Oswald](https://fonts.google.com/specimen/Oswald) e [Rajdhani](https://fonts.google.com/specimen/Rajdhani) via Google Fonts
- Grafica: Canvas API per le particelle di sfondo, CSS animations per tutti gli effetti

## Requisiti

Solo un browser moderno. Nessun build step, nessun package manager.
