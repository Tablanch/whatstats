# WhatStats

<div style="text-align:left">
  <img src="img.png" alt="WhatStats" width="512" height="512" style="width:100px;height:auto"/>
</div>

**Analisi completa e offline delle tue chat WhatsApp — direttamente nel browser.**

Nessun server, nessun upload, nessuna registrazione. Il file rimane sul tuo dispositivo.

---

## Demo

🔗 **[WhatStats su GitHub Pages](https://tablanch.github.io/whatstats)**

---

## Funzionalità

### Riepilogo
- Messaggi totali, giorni attivi, durata della chat, media giornaliera
- Streak massima di giorni consecutivi (con date di inizio e fine)
- Record giornaliero, ora più attiva, primo e ultimo messaggio
- Messaggi eliminati — ogni riquadro è cliccabile per i dettagli

### Filtro temporale
- Range date personalizzabile
- Preset rapidi: Tutto · Ultimo anno · 6 mesi · 3 mesi · Ultimo mese
- Tutte le sezioni si aggiornano in tempo reale al cambio filtro

### Grafici temporali
- **Trend mensile** — andamento mese per mese
- **Attività giornaliera** — grafico giorno per giorno (raggruppato per settimana su chat molto lunghe)

### Calendario interattivo
- Visualizzazione mese per mese con pallini per i giorni attivi
- **Anniversari**: pallino azzurro negli anni successivi alla data del primo messaggio
- **Anniversari del record**: pallino dorato negli anni successivi al giorno con più messaggi
- Click su ogni giorno per vedere dettagli e anniversari

### Distribuzione oraria e settimanale
- Ore del giorno (24 barre, picco evidenziato in verde)
- Giorni della settimana
- **Heatmap ora × giorno** con tooltip istantaneo al passaggio del mouse e al tap su mobile

### Partecipanti
- Tabella con ranking, percentuale e media caratteri per autore
- Grafico a ciambella (doughnut) con distribuzione messaggi
- **Author cards** individuali con: media caratteri, media/giorno, domande, orari, media inviati, eliminati, monologo massimo

### Comportamenti
Otto card sempre visibili, ognuna cliccabile per mostrare la descrizione:
- Chi inizia più conversazioni
- Risposta più veloce (media)
- Ghosting (silenzio > 4 ore)
- Monologo più lungo
- Chi chiude le conversazioni
- Tasso di domande (% messaggi con `?`)
- Più mattiniero (messaggi 6–12)
- Più nottambulo (messaggi 22–6)

### Chi risponde a chi *(solo chat di gruppo)*
Matrice N×N che mostra quante volte ogni partecipante ha risposto a ciascun altro.

### Distribuzione lunghezza messaggi
Per ogni autore, barre proporzionali che mostrano la distribuzione tra:
1 parola · 2–5 · 6–20 · 21–50 · 50+ parole

### Parole uniche per autore
Le parole più caratteristiche di ciascun autore, calcolate con un TF-IDF semplificato
(parole che quell'autore usa più frequentemente rispetto alla media della chat).

### Parole per anno
Top 10 parole più usate per ogni anno della chat — utile per vedere come cambia il vocabolario nel tempo.

### Messaggi più lunghi
Top 10 messaggi più lunghi con anteprima e modale per leggere il testo completo (inclusi gli a capo).

### Velocità di scrittura stimata
Caratteri al minuto stimati su burst di messaggi consecutivi dello stesso autore entro 3 minuti.

### Media leaderboard
Chi ha inviato più immagini, video, audio, sticker, GIF e documenti.

### Emoji più usate
Grafico orizzontale con le 15 emoji più frequenti — con rendering corretto delle emoji composte (sequenze ZWJ, variation selector FE0F incluso).

### Parole più frequenti
Cloud delle 40 parole più usate in tutta la chat (stop-words italiane filtrate).

### Link condivisi
Top 20 domini più condivisi in chat.

---

## Come esportare la chat da WhatsApp

**Android:**
1. Apri la chat
2. Tocca i tre puntini `⋮` → **Altro** → **Esporta chat**
3. Scegli **Senza media**
4. Salva o condividi il file `.zip`

**iPhone:**
1. Apri la chat
2. Tocca il nome del contatto/gruppo in cima
3. Scorri in fondo → **Esporta chat**
4. Scegli **Senza media**

Carica il file `.zip` direttamente — WhatStats lo legge senza estrarlo.

---

## Come usarlo

WhatStats è un singolo file HTML autocontenuto. Non richiede installazione, server o connessione internet (eccetto il caricamento iniziale dei font da Google Fonts).

```bash
# Clona la repo
git clone https://github.com/Tablanch/whatstats.git

# Apri index.html nel browser — fatto.
```

Oppure visita direttamente la [demo su GitHub Pages](https://tablanch.github.io/whatstats).

Su iPhone, per usarlo come app: apri in Safari → tasto Condividi → **Aggiungi a schermata Home**.

---

## Privacy

Tutti i dati vengono elaborati **interamente nel browser**. Nessun messaggio, nessun file, nessuna statistica viene inviata a server esterni. Il codice è ispezionabile — è un unico file HTML.

---

## Limitazioni note

- **Formato supportato**: export WhatsApp in formato italiano (`[GG/MM/AA, HH:MM]`) e inglese. Anno a 2 o 4 cifre, secondi opzionali.
- **Tempo di risposta e ghosting su gruppi**: sono approssimativi perché non è possibile sapere a chi era indirizzato ogni messaggio.
- **Velocità di scrittura**: stima basata su burst consecutivi dello stesso autore entro 3 minuti — dipende dallo stile di scrittura (chi scrive un messaggio lungo vs chi manda tanti messaggi brevi).

---

## Tech stack

- HTML + CSS + JavaScript vanilla — zero framework
- [Chart.js 4.4](https://www.chartjs.org/) per i grafici
- [JSZip 3.10](https://stuk.github.io/jszip/) per la lettura degli archivi `.zip`
- Font: [Syne](https://fonts.google.com/specimen/Syne) + [DM Mono](https://fonts.google.com/specimen/DM+Mono) via Google Fonts

---

## Contribuire

Pull request benvenute. Le aree più interessanti dove contribuire:

- Supporto formati export in altre lingue (spagnolo, portoghese, francese...)
- Miglioramento stop-words per lingue diverse dall'italiano
- Integrazione AI per riassunto e sentiment (richiederebbe API esterna)
- Test su export di WhatsApp Business

---

## Licenza

MIT — fai quello che vuoi, ma lascia un riferimento se lo usi come base.
