# Script di lettura - Video 3

**Titolo:** Le basi: come si lavora dentro una sessione
**Durata target:** 9-11 minuti
**Obiettivo:** chi guarda sa inizializzare un progetto, gestire i permessi e scegliere modello ed effort.

**Come leggere questo script:** ogni riga che inizia con **→** corrisponde a una pressione della freccia destra (o giù) sulla tastiera: premi, aspetta che l'elemento compaia, poi leggi il testo che segue. Le righe senza testo dopo la freccia sono passaggi puramente visivi: premi e prosegui con la frase successiva senza fermarti.

## Slide 1 - Introduzione (10 pressioni)

→ Con l'ambiente installato nel Video 1 e le idee chiare sui livelli di AI dal Video 2, vediamo ora i comandi che userai praticamente in ogni sessione.

→ Come far conoscere il progetto a Claude, come decidere cosa può fare senza chiedere permesso, e come scegliere quanto ragionamento usare per un compito.

→ Non sono comandi da imparare a memoria uno per uno: sono il modo in cui, ogni volta che apri una sessione su un progetto, imposti le regole del gioco prima di iniziare a lavorare davvero.

→ *(linea decorativa: nessuna nuova battuta, premi e continua)*

→ /init racconta il progetto a Claude.

→ /permissions decide cosa può fare da solo.

→ /model sceglie il modello.

→ /effort regola il ragionamento.

→ /context mostra lo spazio occupato.

→ /plan mostra il piano prima di scrivere.

## Slide 2 - La mappa di una sessione (6 pressioni)

→ Il percorso di questo video segue quattro passaggi.

→ Sono passaggi che si fanno una volta a inizio sessione, tranne l'ultimo, che torna utile ogni volta che il compito cresce.

→ Passo 1: prima diamo a Claude il contesto del progetto.

→ Passo 2: poi decidiamo cosa può fare da solo e cosa deve chiederci.

→ Passo 3: poi scegliamo modello ed effort in base al compito.

→ Passo 4: infine vediamo come gestire il contesto quando la conversazione si allunga, e come vedere un piano prima che Claude scriva codice.

## Slide 3 - /init e CLAUDE.md (8 pressioni)

→ La prima volta che apri Claude Code su un progetto nuovo, conviene lanciare /init.

→ È il primo comando da dare, prima di chiedere qualsiasi modifica concreta.

→ Genera un file CLAUDE.md che descrive il progetto: struttura delle cartelle, comandi principali, convenzioni. Claude lo legge automaticamente a ogni sessione futura, così non devi rispiegare da capo ogni volta com'è fatto il repository.

→ Ecco il comando: /init.

→ *(freccia, nessuna nuova battuta)*

→ Claude esplora cartelle, comandi e convenzioni.

→ *(freccia, nessuna nuova battuta)*

→ E genera CLAUDE.md nella radice del progetto.

## Slide 4 - Permessi (6 pressioni)

→ Ogni volta che Claude vuole fare qualcosa che non è pura lettura — modificare un file, eseguire un comando — per default ti chiede conferma.

→ Con /permissions apri un pannello dove decidi quali azioni autorizzare sempre, quali chiedere ogni volta, quali vietare del tutto.

→ È il modo per bilanciare velocità e controllo: puoi essere permissivo su azioni innocue, e restrittivo su azioni rischiose.

→ Consenti sempre: leggere file, eseguire test, git status.

→ Chiedi conferma: modificare codice, eseguire comandi nuovi, installare strumenti.

→ Vieta sempre: cancellare senza controllo, pubblicare, push su main.

## Slide 5 - Lo hai già visto nel Video 1 (8 pressioni)

→ Questo comportamento non è nuovo: lo abbiamo già visto in azione.

→ Ogni volta che nel Video 1 Claude proponeva un comando, si fermava e aspettava la tua conferma prima di eseguirlo.

→ /permissions è semplicemente il pannello che ti permette di decidere in anticipo quali di quelle conferme vuoi continuare a dare ogni volta, e quali invece autorizzare una volta per tutte.

→ Rivediamo l'esempio: installa la skill Ponytail dal repository ufficiale.

→ *(freccia, nessuna nuova battuta)*

→ Claude propone il comando e chiede conferma.

→ *(freccia, nessuna nuova battuta)*

→ Confermato: comando eseguito e verificato.

## Slide 6 - Modello ed effort (4 pressioni)

→ Con /model scegli quale modello Claude usare.

→ Con /effort scegli quanto "sforzo di ragionamento" applicare.

→ /model sceglie quale modello Claude usare per la sessione corrente.

→ /effort: bassa per compiti semplici e veloci, alta per problemi complessi che meritano più tempo di ragionamento. Più effort significa risposte più ponderate ma anche più lente: per un piccolo aggiustamento di testo non serve il massimo, mentre per un refactor delicato può valerne la pena.

## Slide 7 - Gestire il contesto (5 pressioni)

→ Man mano che la conversazione si allunga, Claude Code riempie una finestra di contesto limitata.

→ Con /context vedi quanto spazio stai occupando, con /compact lo riassumi per liberare spazio senza perdere il filo.

→ /context: quasi pieno dopo una sessione lunga.

→ Lanciamo /compact.

→ Dopo /compact: spazio libero, il filo del discorso resta. È un controllo che vale la pena fare ogni tanto nelle sessioni lunghe, soprattutto prima di un compito nuovo e impegnativo.

## Slide 8 - /plan (8 pressioni)

→ Quando devi affrontare una modifica grande e vuoi vedere il piano prima che Claude parta a scrivere codice, usa /plan.

→ È particolarmente utile per compiti dove il rischio di fraintendimento è alto.

→ Meglio allinearsi sul piano che scoprire a fine lavoro che l'interpretazione era un'altra.

→ Un esempio: /plan aggiungi un pulsante al menu principale.

→ *(freccia, nessuna nuova battuta)*

→ Primo passo: Claude analizza, legge il menu esistente.

→ Secondo passo: propone la struttura del nuovo pulsante.

→ Terzo passo: aspetta conferma prima di scrivere codice.

## Slide 9 - Chiusura (9 pressioni)

→ Con questi comandi hai il controllo base di ogni sessione.

→ Ricapitoliamoli uno per uno.

→ Nel prossimo video vediamo come estendere quello che Claude sa fare con le skill e i plugin, a partire da Ponytail, che abbiamo già installato nel Video 1.

→ /init, contesto del progetto.

→ /permissions, regole di conferma.

→ /model, modello da usare.

→ /effort, livello di ragionamento.

→ /context, spazio occupato.

→ /plan, piano prima di scrivere.

## Nota di registrazione

Apri `3° Video comandi base Claude.html` direttamente nel browser (nessun server necessario). La navigazione è a frecce: freccia destra/giù fa comparire un elemento alla volta nella slide corrente e, quando non ce ne sono più, passa alla slide successiva; freccia sinistra/su fa il percorso inverso. Segui le righe con **→** qui sopra nell'ordine: ognuna è esattamente una pressione. Registra la voce con CapCut o un altro screen recorder e premi la freccia un istante prima di leggere il testo che la segue. Lascia 1-2 secondi di silenzio dopo ogni comparsa: rende più facile tagliare e allineare la voce in montaggio.

Per i blocchi con demo dal vivo (`/init`, `/permissions`, `/model`, `/effort`, `/context`, `/compact`, `/plan`), segui lo script di esecuzione nel file `../CLAUDE.md.md` (sezione Video 3) per sapere cosa digitare e mostrare a schermo in parallelo a ciascuna slide.
