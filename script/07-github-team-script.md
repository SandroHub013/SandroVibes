# Script di lettura - Video 7

**Titolo:** GitHub e il flusso di lavoro in team
**Durata target:** 8-10 minuti
**Obiettivo:** chi guarda capisce come Claude Code si integra con GitHub e come un collaboratore non tecnico può chiedere modifiche senza aprire un terminale.

**Come leggere questo script:** ogni riga che inizia con **→** corrisponde a una pressione della freccia destra (o giù). Premi, aspetta che l'elemento compaia, poi leggi il testo che segue.

## Slide 1 - Titolo (8 pressioni)

→ Fabioland è un progetto di squadra, e il codice vive su GitHub.

→ In questo video vediamo i modi in cui Claude Code si integra con GitHub — sia per chi lavora da terminale, sia per chi preferisce restare dentro il browser.

→ Quattro strumenti, un solo filo conduttore: la stessa pull request, raggiunta in modi diversi.

→ *(linea decorativa: nessuna nuova battuta, premi e continua)*

→ La gh CLI, per leggere e creare pull request dal terminale.

→ La skill /review, per farsi dare un secondo parere su una PR.

→ /install-github-app, per collegare Claude al repository una volta sola.

→ E @claude, che richiami direttamente in un commento.

## Slide 2 - La gh CLI (7 pressioni)

→ Dentro una sessione di Claude Code, l'agente ha accesso diretto alla gh, la command line ufficiale di GitHub.

→ Questo significa che può leggere una pull request, i suoi commenti, il suo diff, e crearne una nuova — tutto senza che tu debba passare dal browser.

→ Vediamolo in pratica.

→ Proviamolo: mostrami i commenti sulla PR numero 12.

→ Claude usa gh sotto il cofano per leggere quei commenti — lo vedi nei tool call.

→ E può anche crearne una nuova: gh pr create, con titolo e descrizione.

→ PR creata — titolo e descrizione generati da Claude, pronti da rivedere.

## Slide 3 - La skill /review (5 pressioni)

→ Per revisionare una pull request esistente c'è una skill dedicata: /review.

→ Analizza le modifiche cercando bug e problemi, usando lo stesso motore della revisione del codice locale.

→ Un numero di PR, e via: /review 12.

→ Analizza il diff, segnala bug e problemi trovati.

→ Utile prima di un merge, o quando un collaboratore vuole un secondo parere prima di chiedere revisione umana.

## Slide 4 - @claude nei commenti (5 pressioni)

→ La parte più interessante per i collaboratori meno tecnici è questa.

→ Una volta installata la GitHub App di Claude sul repository, puoi taggare @claude direttamente in un commento.

→ L'installazione si fa una volta sola: /install-github-app.

→ Ti guida passo passo nella configurazione — non serve altro.

→ Da questo momento, ogni collaboratore con un account GitHub può usarlo.

## Slide 5 - @claude in azione (4 pressioni)

→ Vediamo cosa succede in pratica, dentro un commento su una issue o una pull request.

→ Qualcuno scrive: @claude correggi il typo in questa riga.

→ Claude legge il contesto della issue o della PR.

→ Propone la modifica e crea un commit — tutto questo senza che nessuno debba aprire un terminale.

## Slide 6 - Perché è utile per tutto il team (5 pressioni)

→ Questo abbassa parecchio la barriera d'ingresso.

→ Un game designer che nota un numero sbagliato in una tabella può chiederne la correzione direttamente nel commento di una issue, senza imparare git o la CLI.

→ Due strade, la stessa destinazione.

→ Solo browser: un commento con @claude, basta un account GitHub.

→ Terminale: gh CLI e /review, per chi lavora sul codice ogni giorno. Resta comunque un passaggio umano di revisione prima che qualsiasi modifica venga unita al progetto — lo vediamo meglio nell'ultimo video.

## Slide 7 - Chiusura (7 pressioni)

→ Con questo abbiamo coperto tutto il flusso, dal terminale al browser.

→ Nell'ultimo video mettiamo insieme le buone pratiche di sicurezza che valgono per tutto quello che abbiamo visto finora.

→ Ricapitoliamo i quattro strumenti di oggi.

→ gh CLI, legge e crea pull request dal terminale.

→ /review, revisiona una pull request.

→ /install-github-app, installa la GitHub App sul repo.

→ @claude, nei commenti, senza aprire un terminale.

## Nota di registrazione

Apri `7° Video GitHub e team.html` direttamente nel browser (nessun server necessario). La navigazione è a frecce: freccia destra/giù fa comparire un elemento alla volta nella slide corrente e, quando non ce ne sono più, passa alla slide successiva; freccia sinistra/su fa il percorso inverso. Segui le righe con **→** nell'ordine: ognuna è esattamente una pressione. Registra la voce con CapCut o un altro screen recorder e premi la freccia un istante prima di leggere il testo che la segue.

Per cosa digitare/mostrare a schermo durante le demo dal vivo (`gh pr view`, `gh pr create`, `/review 12`, commento `@claude` su GitHub), segui lo script di esecuzione nella sezione "Video 7" di `../CLAUDE.md.md`.
