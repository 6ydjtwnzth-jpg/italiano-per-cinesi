# 意大利语入门课本 · Primo libro di italiano

Corso di italiano per madrelingua cinesi, da zero ad A2: 23 lezioni, 3 ripassi (l'ultimo con un test A2 in stile CILS), dialoghi da ascoltare e recitare, esercizi corretti in automatico (scelta, dettato, completamento, frasi da ricomporre, parlato), flashcard legate alle lezioni, glossario e coniugatore di 38 verbi.

Il percorso segue la progressione A1.1 → A1.2 → A2 dei sillabi di riferimento e l'ordine di acquisizione dell'italiano L2 (presente → passato prossimo → imperfetto → futuro/condizionale), con attenzione alle difficoltà tipiche degli apprendenti sinofoni (articolo, accordo, morfologia verbale, sonore, r, doppie, nessi consonantici).

## Struttura

Il sito pubblicato è un unico file statico, `index.html`, generato da `build.py` a partire da `src/`:

| Percorso | Contenuto |
|---|---|
| `src/course.json` | ordine, titoli e icone di lezioni, ripassi e appendici |
| `src/content/<id>.html` | testo di ogni sezione (l'intestazione colorata la genera `build.py`) |
| `src/content/<id>.js` | dati della sezione: `DLG.<id>` dialoghi, `EX.<id>` esercizi, `VOC.<id>` parole |
| `src/js/dict.js` | dizionario italiano → cinese per i tooltip |
| `src/js/app.js` | logica: audio, dialoghi, esercizi, flashcard, coniugatore, tema |
| `src/style.css`, `src/extra.css` | stile |
| `audio/` | audio pre-registrati |

Per modificare il corso: cambiare i file in `src/`, poi eseguire `python3 build.py` e pubblicare `index.html`.

## Audio

Il sito usa la sintesi vocale del dispositivo (Web Speech API, prima voce italiana disponibile). La cartella `audio/` contiene registrazioni sperimentali (Kokoro, voce «Sara») che al momento non vengono usate: per riattivarle impostare `USE_DEVICE_VOICE=false` in `src/js/app.js`.

I progressi (punteggi, flashcard, «我能做到») restano nel browser dell'utente.
