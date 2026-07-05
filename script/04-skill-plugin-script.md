# Script di lettura - Video 4

**Titolo:** Skill e Plugin: estendere Claude Code
**Durata target:** 10-12 minuti
**Obiettivo:** chi guarda capisce cos'è una skill, vede Ponytail (già installata nel Video 1) in azione, e sa installare un nuovo plugin da un marketplace.

**Come leggere questo script:** ogni riga che inizia con **→** corrisponde a una pressione della freccia destra (o giù) sulla tastiera: premi, aspetta che l'elemento compaia, poi leggi il testo che segue. Le righe senza testo dopo la freccia sono passaggi puramente visivi: premi e prosegui con la frase successiva senza fermarti.

## Slide 1 - Titolo (8 pressioni)

→ Con l'ambiente pronto dal Video 1, i livelli di AI chiari dal Video 2 e i comandi base visti nel Video 3, oggi vediamo come estendere quello che Claude sa fare senza scrivere una riga di codice.

→ Una skill insegna a Claude una procedura. Un plugin la distribuisce, insieme ad altro, a tutto il team.

→ In questo video vediamo entrambe in azione, a partire da un esempio concreto che abbiamo già installato nel Video 1: Ponytail.

→ *(linea decorativa: nessuna nuova battuta, premi e continua)*

→ /plugin marketplace add, aggiunge un marketplace.

→ /plugin install, installa un plugin.

→ /plugin list, mostra cosa hai installato.

→ /plugin disable, disattiva senza disinstallare.

## Slide 2 - Cos'è una skill (5 pressioni)

→ Una skill è un pacchetto di istruzioni che insegna a Claude come affrontare un compito specifico in un certo modo. Non è nuovo codice: è più simile a una procedura scritta che Claude legge e segue.

→ Ogni skill vive in un file SKILL.md, dentro una cartella con il suo nome.

→ In cima al file c'è un frontmatter che ne descrive nome e scopo — la description è quello che Claude legge per capire quando usarla — seguito dalle istruzioni vere e proprie.

→ Ecco la struttura: `.claude/skills/nome-skill/SKILL.md`.

→ E il frontmatter: name, description, e sotto le istruzioni che Claude legge e segue.

## Slide 3 - Personale vs di progetto (4 pressioni)

→ Una skill può vivere in due posti diversi.

→ Sono due modi diversi di renderla disponibile, non due formati diversi.

→ Personale: nella tua cartella utente, disponibile in tutti i progetti su cui lavori, a prescindere dal repository che hai aperto.

→ Oppure di progetto: dentro il repository stesso. In questo caso viaggia con git — chiunque clona il progetto ha automaticamente la stessa skill a disposizione, senza doverla installare a parte.

## Slide 4 - Come si invoca una skill (6 pressioni)

→ Puoi invocare una skill in due modi.

→ Esplicita con /nome-skill, oppure riconosciuta da sola da Claude.

→ Il primo è esplicito: scrivi /nome-skill nel prompt, e Claude la segue subito dall'inizio alla fine.

→ Il secondo è automatico: lasci che sia Claude a riconoscerla da solo, quando la tua richiesta corrisponde a quello che la skill descrive di fare.

→ Nel Video 1 abbiamo già installato un esempio concreto — Ponytail — e infatti se ora chiediamo a Claude l'elenco dei plugin: /plugin list.

→ La vediamo già lì, attiva: ponytail@ponytail, installata nel Video 1.

## Slide 5 - Ponytail in azione (7 pressioni)

→ Ponytail è pensata per una cosa sola: costringere Claude a scegliere la soluzione più semplice possibile.

→ Quando scrivi codice, è facile finire per costruire cose più complicate del necessario — funzioni generiche per un caso che capiterà una volta sola, dipendenze in più quando bastava una riga di libreria standard.

→ Ponytail interviene proprio lì: prima di scrivere, si chiede se il compito serve davvero, se esiste già una soluzione più corta, se sta aggiungendo flessibilità che nessuno ha chiesto.

→ Ha anche livelli di intensità — lite, full, ultra — per quanto deve essere aggressiva nel tagliare. Ed è giusto dirlo chiaramente: è un progetto open source di terze parti, non di Anthropic, ma è ormai uno standard molto usato.

→ Prendiamo un esempio semplice: aggiungi una funzione per calcolare lo sconto.

→ Senza Ponytail rischiamo una funzione generica con parametri opzionali mai usati, e una dipendenza in più per un calcolo semplice.

→ Con Ponytail: una funzione, un parametro, nessuna dipendenza aggiunta — un diff minimo, facile da rivedere.

## Slide 6 - Cos'è un plugin (4 pressioni)

→ Un plugin è un pacchetto più grande di una singola skill.

→ Può contenere più skill insieme, agenti, automazioni — chiamate hook — e connessioni a strumenti esterni via MCP, come Obsidian e Graphiti che abbiamo già collegato nel Video 1.

→ I plugin si distribuiscono tramite dei "marketplace" — repository che elencano plugin installabili — e ogni comando di un plugin viene prefissato col nome del plugin stesso, per evitare conflitti tra plugin diversi.

→ Un plugin, dentro: skill, agenti, hook, server MCP come Obsidian e Graphiti.

## Slide 7 - Installare un secondo plugin (9 pressioni)

→ Il meccanismo per installare un plugin è lo stesso già visto per Ponytail nel Video 1.

→ Stesso meccanismo, ogni volta.

→ Prima si aggiunge un marketplace con /plugin marketplace add seguito dal nome del repository, poi si installa il plugin specifico con /plugin install. Te lo mostro con un secondo plugin, diverso da Ponytail, apposta per far vedere che il procedimento è sempre identico.

→ Primo comando: /plugin marketplace add anthropics/claude-plugins-official.

→ Marketplace aggiunto.

→ Poi: /plugin install skill-creator@claude-plugins-official.

→ Plugin installato.

→ Verifichiamo con /plugin list.

→ Ed eccolo comparso accanto a quello che avevamo già: ponytail@ponytail, skill-creator@claude-plugins-official.

## Slide 8 - Gestire i plugin installati (4 pressioni)

→ Con /plugin list vedi in ogni momento cosa hai installato e in che stato si trova.

→ Ed è utile sapere che non devi disinstallare un plugin solo perché per ora non ti serve: con /plugin disable lo disattivi temporaneamente, e lo riattivi quando torna utile, senza perdere la configurazione.

→ /plugin list: elenca tutti i plugin installati e il loro stato.

→ /plugin disable: disattiva temporaneamente, senza disinstallare.

## Slide 9 - Chiusura (7 pressioni)

→ Skill e plugin sono il modo in cui personalizziamo Claude Code per il modo di lavorare specifico di Fabioland.

→ Sono anche il modo in cui, col tempo, possiamo condividere tra collaboratori le procedure che funzionano meglio per noi.

→ Nel prossimo video vediamo due comandi che appartengono al livello più avanzato di autonomia visto nel Video 2: /loop, che fa ripetere un compito nel tempo, e /goal, che fa lavorare Claude su un obiettivo finché non è soddisfatto.

→ /plugin marketplace add, aggiunge un marketplace.

→ /plugin install, installa un plugin.

→ /plugin list, mostra cosa hai installato.

→ /plugin disable, disattiva senza disinstallare.

## Nota di registrazione

Apri `4° Video Skill e Plugin.html` direttamente nel browser (nessun server necessario). La navigazione è a frecce: freccia destra/giù fa comparire un elemento alla volta nella slide corrente e, quando non ce ne sono più, passa alla slide successiva; freccia sinistra/su fa il percorso inverso. Segui le righe con **→** nell'ordine: ognuna è esattamente una pressione. Registra la voce con CapCut o un altro screen recorder e premi la freccia un istante prima di leggere il testo che la segue. Lascia 1-2 secondi di silenzio dopo ogni comparsa: rende più facile tagliare e allineare la voce in montaggio.

Per cosa digitare/mostrare a schermo durante le demo dal vivo (`/plugin list`, `/plugin marketplace add`, `/plugin install`, `/plugin disable`), segui lo script di esecuzione nella sezione "Video 4" di `../CLAUDE.md.md`.
