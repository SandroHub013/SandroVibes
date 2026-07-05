# Script di lettura - Video 8

**Titolo:** Buone pratiche, sicurezza e limiti
**Durata target:** 7-8 minuti
**Obiettivo:** chi guarda sa quali azioni richiedono sempre revisione umana e come impostare i permessi in modo sicuro.

**Nota:** questo video non richiede demo tecniche nuove — riprende esempi già mostrati nei video precedenti, quindi puoi riusare clip già registrate al posto (o in aggiunta) delle slide qui sotto.

**Come leggere questo script:** ogni riga che inizia con **→** corrisponde a una pressione della freccia destra (o giù). Premi, aspetta che l'elemento compaia, poi leggi il testo che segue.

## Slide 1 - Titolo (5 pressioni)

→ Abbiamo visto quanto Claude Code possa fare in autonomia: installare i propri strumenti, scrivere codice, lavorare su un obiettivo per più turni, aprire pull request.

→ Questo video è il più importante di tutti, perché riguarda i limiti che dobbiamo darci come team quando usiamo questi strumenti.

→ Non sono regole da imparare a memoria: sono il modo in cui restiamo in controllo di quello che l'agente fa per noi.

→ *(linea decorativa: nessuna nuova battuta, premi e continua)*

→ Le regole d'oro per lavorare con un agente AI.

## Slide 2 - La regola di base (5 pressioni)

→ La regola di base è semplice: più un'azione è difficile da annullare o riguarda altre persone, più serve una conferma umana esplicita prima di eseguirla.

→ Claude Code per default chiede conferma su tutto ciò che non è pura lettura — l'hai visto più volte nel Video 1, quando ogni comando di installazione veniva proposto e non eseguito finché non confermavi.

→ È una scelta di sicurezza, non un fastidio da disattivare alla leggera.

→ Leggere un file è innocuo e reversibile. Controllare lo stato di git, lo stesso.

→ Cancellare un branch, forzare una modifica su git, pubblicare qualcosa online — questo non lo è.

## Slide 3 - Permessi: cosa automatizzare (5 pressioni)

→ Nel Video 3 abbiamo visto /permissions. Ecco il consiglio pratico.

→ Automatizza il rischio basso, chiedi sempre conferma sul resto: decidi tu dove tracciare il confine.

→ Ci sono azioni ripetitive e a basso rischio che vale la pena automatizzare.

→ Sì, automatizza: leggere file, eseguire test, controllare lo stato di git.

→ No, chiedi sempre: push su branch principali, merge di pull request, cancellazione di file o branch, pubblicazione di build. Tutto quello che tocca lo stato condiviso del progetto.

## Slide 4 - /loop e /goal: attenzione in più (4 pressioni)

→ Proprio perché lavorano più a lungo senza supervisione costante, /loop e /goal, visti nel Video 5, vanno usati su compiti dove sei tranquillo che Claude proceda da solo per un bel po' di tempo.

→ Se il compito include azioni irreversibili, meglio spezzarlo.

→ Lascia che l'agente prepari tutto in autonomia, ma chiedigli di fermarsi prima del passaggio finale che non si può disfare.

→ Spezza il compito prima del passaggio irreversibile: tienilo a mente ogni volta che lanci un /loop o un /goal lungo.

## Slide 5 - Strumenti esterni: cosa condividono (7 pressioni)

→ Anche qui vale quanto detto nel Video 6: quando colleghi uno strumento esterno via MCP, quello strumento riceve dati dal progetto.

→ Prima di collegarlo, capite insieme come team cosa contiene quel vault o quel grafo, e se è opportuno che un agente AI ci acceda.

→ Non è una domanda da farsi una volta sola: vale ogni volta che aggiungi un collegamento nuovo.

→ Claude Code, collegato via MCP a tutto quello che gli avete dato accesso.

→ Obsidian — cosa condivide?

→ Graphiti — cosa condivide?

→ E qualunque altro strumento colleghiate in futuro — stessa domanda, ogni volta.

## Slide 6 - Chiusura del corso (10 pressioni)

→ Con questo chiudiamo il percorso.

→ Ripercorriamolo insieme, un video alla volta.

→ Uno: il setup completo — terminale, Claude Code, Obsidian, Graphiti, Ponytail.

→ Due: i livelli di intelligenza artificiale, dal chatbot ai sistemi agentici.

→ Tre: i comandi base per lavorare dentro una sessione.

→ Quattro: skill e plugin, per estendere Claude Code.

→ Cinque: /loop e /goal, per farlo lavorare nel tempo.

→ Sei: Obsidian e Graphiti, al lavoro ogni giorno.

→ Sette: GitHub e il flusso di lavoro in team.

→ Otto: buone pratiche, sicurezza e limiti — quello che stiamo chiudendo proprio ora.

## Slide 7 - Da qui in avanti (4 pressioni)

→ Da qui in avanti l'unico modo per diventare bravi è usarlo sul progetto vero.

→ Non serve un nono video per impararlo: serve aprire una sessione e cominciare.

→ E se qualcosa non torna, fermatevi e chiedete, invece di forzare un comando di cui non siete sicuri cosa faccia.

→ *(linea decorativa di chiusura: pausa, poi saluta e chiudi la registrazione)*

## Nota di registrazione

Apri `8° Video Buone pratiche e sicurezza.html` direttamente nel browser (nessun server necessario). La navigazione è a frecce: freccia destra/giù fa comparire un elemento alla volta nella slide corrente e, quando non ce ne sono più, passa alla slide successiva; freccia sinistra/su fa il percorso inverso. Segui le righe con **→** nell'ordine: ognuna è esattamente una pressione.

Questo video non ha demo dal vivo nuove: per i punti 2 e 4 dello script di esecuzione originale, valuta di riusare le clip già girate per il Video 1 (conferma prima di un comando di installazione) e per il Video 5 (`/loop` e `/goal` in azione), con un overlay testuale al posto della slide, se preferisci quell'effetto in montaggio. Il riferimento completo è nella sezione "Video 8" di `../CLAUDE.md.md`.
