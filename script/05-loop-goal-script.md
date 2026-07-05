# Script di lettura - Video 5

**Titolo:** /loop e /goal: far lavorare l'AI nel tempo
**Durata target:** 9 minuti
**Obiettivo:** chi guarda sa quando usare /loop e quando usare /goal, e li vede in azione su un esempio reale.

**Come leggere questo script:** ogni riga che inizia con **→** corrisponde a una pressione della freccia destra (o giù) sulla tastiera. Premi, aspetta che l'elemento compaia sullo schermo, poi leggi il testo che segue quella riga. Le righe senza testo dopo la freccia sono passaggi puramente visivi (una linea decorativa, un connettore): premi e prosegui con la frase successiva senza fermarti a leggere nulla di nuovo.

## Slide 1 - Titolo (6 pressioni)

→ Nel Video 2 abbiamo detto che il livello più avanzato di sistema AI è quello che continua a lavorare su un obiettivo nel tempo, senza che tu debba guidarlo passo passo.

→ /loop e /goal sono i due comandi con cui Claude Code porta questa idea nella pratica.

→ Sono simili da descrivere, ma rispondono a domande diverse — tra poco vediamo quali.

→ *(linea decorativa: nessuna nuova battuta, premi e continua)*

→ Da un lato /loop, che ripete un compito nel tempo.

→ Dall'altro /goal, che lavora finché non è soddisfatto.

## Slide 2 - /loop, cos'è (5 pressioni)

→ /loop fa una cosa semplice da descrivere: ripete un prompt più volte, mentre la sessione resta aperta.

→ Puoi dargli un intervallo fisso — ad esempio ogni 10 minuti.

→ È lo strumento giusto per compiti di monitoraggio: "controlla se la build è finita", "controlla se sono comparsi errori nel log".

→ Eccolo in pratica: /loop 10 minuti, controlla se ci sono nuovi errori in error.log.

→ Claude conferma l'avvio e programma la prossima esecuzione.

## Slide 3 - /loop, tre varianti (5 pressioni)

→ Non sei obbligato a specificare sempre un intervallo. Ci sono tre modi di dire a Claude quando ripetere.

→ Vediamoli uno per uno.

→ Il primo: intervallo fisso, deciso da te — come abbiamo appena visto.

→ Il secondo: senza intervallo, lasci che sia Claude stesso a decidere quando ripetere, valutando quanto ci vuole realisticamente perché la situazione cambi.

→ Il terzo: se non specifichi nemmeno il prompt, e nel progetto esiste un file .claude/loop.md, Claude usa quello come prompt di default.

## Slide 4 - /goal, cos'è (7 pressioni)

→ /goal invece non ripete un compito a intervalli: imposta una condizione, e Claude continua a lavorare finché quella condizione non è soddisfatta.

→ Anche su più turni di conversazione, senza che tu debba rilanciare la richiesta ogni volta.

→ Non ti importa quanti tentativi servano, purché il risultato finale sia quello.

→ Un esempio concreto: non è un'azione singola. /goal, porta la copertura dei test al 90 per cento.

→ Claude scrive i test che mancano.

→ Li esegue e misura la copertura reale.

→ Se non basta ancora, ripete da solo, senza aspettare un nuovo messaggio da parte tua.

## Slide 5 - Controllare e fermare un obiettivo (6 pressioni)

→ In ogni momento puoi controllare a che punto è.

→ Con /goal senza argomenti vedi l'obiettivo attivo, o l'ultimo raggiunto.

→ Ecco cosa risponde: obiettivo attivo, copertura test al 90 per cento, attuale 74 per cento.

→ E se vuoi fermarti prima che l'obiettivo sia raggiunto?

→ /goal clear rimuove l'obiettivo attivo.

→ Confermato: obiettivo rimosso.

## Slide 6 - Quale usare (4 pressioni)

→ La differenza in breve, per non confonderli mai più.

→ Usa /loop quando vuoi che qualcosa venga controllato ripetutamente nel tempo — un monitoraggio.

→ /loop, monitoraggio ripetuto.

→ Usa /goal quando vuoi che qualcosa venga raggiunto, e non ti importa quanti tentativi o turni servano, purché il risultato finale sia quello.

## Slide 7 - Un avvertimento (4 pressioni)

→ Proprio perché lavorano in autonomia più a lungo, questi due comandi vanno usati su compiti dove sei d'accordo che Claude proceda senza chiederti conferma a ogni passo.

→ Per tutto quello che è rischioso o irreversibile, vale una regola che vediamo meglio nell'ultimo video.

→ Pubblicare, cancellare, forzare modifiche: sono azioni che non si disfano facilmente.

→ Azioni irreversibili, conferma umana sempre. Tienilo a mente: ci torniamo nel Video 8.

## Slide 8 - Chiusura (6 pressioni)

→ Con /loop e /goal chiudiamo la parte sui comandi base di ogni sessione.

→ Nel prossimo video torniamo su Obsidian e Graphiti, che abbiamo collegato nel Video 1, per vedere come si usano davvero nel lavoro di tutti i giorni.

→ Ricapitoliamo i tre comandi visti oggi.

→ /loop, con intervallo o prompt opzionali, ripete nel tempo.

→ /goal, con una condizione, lavora finché non è soddisfatto.

→ /goal clear rimuove l'obiettivo attivo.

## Nota di registrazione

Apri `5° Video loop e goal.html` direttamente nel browser (nessun server necessario). La navigazione è a frecce: freccia destra/giù fa comparire un elemento alla volta nella slide corrente e, quando non ce ne sono più, passa alla slide successiva; freccia sinistra/su fa il percorso inverso. Segui le righe con **→** qui sopra nell'ordine: ognuna è esattamente una pressione. Registra la voce con CapCut o un altro screen recorder e premi la freccia un istante prima di leggere il testo che la segue. Lascia 1-2 secondi di silenzio dopo ogni comparsa: rende più facile tagliare e allineare la voce in montaggio.

Per cosa digitare/mostrare a schermo durante le demo dal vivo (`/loop`, `/goal`), segui lo script di esecuzione nella sezione "Video 5" di `../CLAUDE.md.md`.
