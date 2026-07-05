# Script di lettura - Video 6

**Titolo:** MCP nella pratica quotidiana: Obsidian e Graphiti al lavoro
**Durata target:** 9-10 minuti
**Obiettivo:** chi guarda capisce cos'è un MCP server e come sfruttare, nel lavoro di ogni giorno, i collegamenti a Obsidian e Graphiti già fatti nel Video 1.

**Come leggere questo script:** ogni riga che inizia con **→** corrisponde a una pressione della freccia destra (o giù). Premi, aspetta che l'elemento compaia, poi leggi il testo che segue.

## Slide 1 - Titolo (7 pressioni)

→ Nel Video 1 abbiamo collegato Claude Code a Obsidian e a Graphiti chiedendolo direttamente all'agente.

→ In questo video vediamo cosa succede davvero dietro quel collegamento, e soprattutto come usarlo bene ogni giorno.

→ MCP è il protocollo standard con cui Claude Code si collega a strumenti esterni.

→ *(linea decorativa: nessuna nuova battuta, premi e continua)*

→ Al centro c'è sempre Claude Code, collegato via MCP.

→ Da un lato Obsidian, il nostro archivio di note.

→ Dall'altro Graphiti, la memoria a grafo.

## Slide 2 - Cos'è un MCP server (6 pressioni)

→ Un "MCP server" espone a Claude delle funzioni per interagire con uno strumento specifico — che sia un archivio di note o un database.

→ Non è un dettaglio tecnico da ignorare: è quello che rende possibile tutto il resto del video.

→ Vediamolo dal vivo: il comando /mcp.

→ Elenca i server collegati.

→ Obsidian, connesso.

→ Graphiti, connesso.

## Slide 3 - Obsidian nel lavoro quotidiano (5 pressioni)

→ Con Obsidian collegato, quando chiedi a Claude di implementare una feature può andare a controllare da solo se esiste già una nota di design che la descrive.

→ Il beneficio si vede soprattutto quando il vault cresce: più note ci sono, più senso ha lasciare che sia Claude a cercarci dentro invece che farlo a mano.

→ Un esempio concreto: cerca nel vault le note sul sistema di combattimento.

→ Trovate tre note collegate.

→ La risposta arriva davvero dal vault, non da quello che avresti dovuto copiare e incollare in chat.

## Slide 4 - Graphiti, memoria a grafo (5 pressioni)

→ Graphiti è uno strumento diverso da un semplice archivio di note: è un sistema di memoria a grafo temporale, pensato apposta per agenti AI.

→ La differenza è che tiene traccia di come cambiano i fatti nel tempo — non solo il valore di oggi.

→ Prendiamo un esempio: i punti vita di un boss finale.

→ Il 12 marzo erano 500.

→ Il 2 aprile sono diventati 650, dopo un bilanciamento seguito al playtest — e Graphiti ricorda entrambi i valori, con la data del cambiamento.

## Slide 5 - Graphiti in azione (4 pressioni)

→ È utile quando vuoi che l'agente ricordi decisioni prese in sessioni passate, e ne capisca l'evoluzione — non solo lo stato attuale.

→ Chiediamolo direttamente: cosa ricordi sulle decisioni prese sul sistema di combattimento?

→ Claude risponde basandosi su Graphiti.

→ Con date e motivazioni dei cambiamenti — non solo il numero finale.

## Slide 6 - Perché per Fabioland ha senso (5 pressioni)

→ Su un progetto che si sviluppa in tante sessioni diverse, con collaboratori diversi, il rischio è che ogni conversazione con l'AI riparta da zero.

→ Senza contesto su cosa è già stato deciso, o perché una certa scelta di design è stata scartata.

→ Mettiamo le due situazioni a confronto.

→ Senza memoria esterna: ogni conversazione riparte da zero, devi rispiegare tutto.

→ Con memoria esterna: il contesto resta, anche cambiando collaboratore o sessione.

## Slide 7 - Attenzione (4 pressioni)

→ Una nota importante, già anticipata nel Video 1.

→ A differenza dei comandi integrati in Claude Code, Obsidian e Graphiti sono strumenti di terze parti che si collegano via MCP.

→ Prima di collegarli a dati sensibili del progetto, vale la pena capire bene cosa condividono e con chi — soprattutto per Graphiti, che spesso gira su un servizio condiviso dal team.

→ Strumenti di terze parti, verifica sempre cosa condividono e con chi.

## Slide 8 - Chiusura (6 pressioni)

→ Con questo chiudiamo la parte sugli strumenti collegati.

→ Negli ultimi due video vediamo come tutto questo si inserisce nel flusso di lavoro in team su GitHub, e quali sono le buone pratiche da rispettare sempre.

→ Ricapitoliamo cosa abbiamo visto oggi.

→ /mcp elenca i server MCP collegati.

→ Obsidian, le note del progetto, cercabili direttamente da Claude.

→ Graphiti, la memoria a grafo che ricorda l'evoluzione delle decisioni.

## Nota di registrazione

Apri `6° Video MCP Obsidian Graphiti.html` direttamente nel browser (nessun server necessario). La navigazione è a frecce: freccia destra/giù fa comparire un elemento alla volta nella slide corrente e, quando non ce ne sono più, passa alla slide successiva; freccia sinistra/su fa il percorso inverso. Segui le righe con **→** nell'ordine: ognuna è esattamente una pressione. Registra la voce con CapCut o un altro screen recorder e premi la freccia un istante prima di leggere il testo che la segue.

Per cosa digitare/mostrare a schermo durante le demo dal vivo (`/mcp`, ricerca nel vault, domanda a Graphiti), segui lo script di esecuzione nella sezione "Video 6" di `../CLAUDE.md.md`.
