# Script di lettura - Video 2

**Titolo:** Cos'e l'AI oggi: dal chatbot ai sistemi agentici  
**Durata target:** 8-10 minuti  
**Obiettivo:** chi guarda deve distinguere i 4 livelli di sistema AI e capire dove si colloca Claude Code.

## Slide 1 - Introduzione

Nel video precedente abbiamo installato tutto l'ambiente di lavoro. Prima di iniziare a usarlo davvero, pero, vale la pena chiarire una cosa: quando oggi diciamo "intelligenza artificiale", spesso stiamo usando la stessa parola per indicare strumenti molto diversi.

In questo video mettiamo ordine. Vediamo quattro livelli: il chatbot, l'assistente con strumenti, l'agente autonomo e i sistemi multi-agente o ricorsivi. L'obiettivo non e imparare una teoria astratta: e capire cosa possiamo aspettarci da ogni strumento, e soprattutto dove si colloca Claude Code.

## Slide 2 - La mappa dei quattro livelli

Il modo piu semplice per leggerli e pensare a una scala. Al primo livello abbiamo una risposta singola dentro una chat. Al secondo livello il modello puo usare strumenti dentro una richiesta. Al terzo livello riceve un obiettivo e decide i passaggi. Al quarto livello piu agenti o piu iterazioni lavorano nel tempo.

Non significa che un livello renda inutili gli altri. Un chatbot resta utilissimo per scrivere, spiegare o fare brainstorming. Ma se dobbiamo modificare un progetto, leggere file, eseguire controlli e verificare il risultato, serve qualcosa di piu vicino a un agente.

## Slide 3 - Livello 1: il chatbot

Il primo livello e il chatbot conversazionale puro. Gli fai una domanda, lui risponde, e la conversazione resta li. Non puo aprire un file del progetto, non puo eseguire un comando, non puo fare una verifica concreta a meno che qualcuno gli abbia dato strumenti specifici.

Questo lo rende semplice e comodo, ma anche limitato. E lo strumento giusto quando vogliamo testo, spiegazioni, idee, riformulazioni. Non e lo strumento giusto se ci aspettiamo che faccia qualcosa al posto nostro dentro il progetto.

## Slide 4 - Livello 2: l'assistente con strumenti

Il secondo livello e l'assistente con strumenti, spesso chiamato "tool use". Qui il modello non si limita a scrivere una risposta: puo cercare sul web, leggere un documento, fare un calcolo, chiamare una funzione o interrogare un servizio collegato.

La differenza e importante: dentro una singola richiesta possono succedere azioni reali. Pero il ritmo resta guidato da noi. Chiediamo una cosa, l'assistente usa uno o piu strumenti, risponde, e poi aspetta la prossima istruzione.

## Slide 5 - Livello 3: l'agente autonomo

Il terzo livello e l'agente autonomo, ed e qui che entra Claude Code. Un agente non aspetta che gli dettiamo ogni singolo passo. Gli diamo un obiettivo, per esempio "sistema questo bug" oppure "collega questo progetto a Obsidian", e lui decide quali strumenti usare, in che ordine, quando verificare e quando fermarsi a chiedere conferma.

Questa e la differenza concreta tra una chat e un agente: non produce solo una risposta, costruisce un piccolo percorso operativo verso un risultato.

## Slide 6 - Il ponte con il Video 1

Nel Video 1 lo abbiamo gia visto senza chiamarlo cosi. Quando abbiamo chiesto a Claude di collegare Obsidian, non abbiamo copiato un comando dalla documentazione e non gli abbiamo spiegato ogni passaggio.

Gli abbiamo dato un obiettivo in linguaggio naturale. Claude ha capito il tipo di collegamento necessario, ha proposto il comando MCP corretto, ha chiesto conferma e poi ha verificato che il collegamento fosse attivo. Questo e comportamento da agente.

## Slide 7 - Livello 4: sistemi multi-agente e ricorsivi

Il quarto livello e quello piu avanzato e piu recente: sistemi multi-agente e ricorsivi. Qui non c'e solo un agente che fa una sequenza di passi. Puo esserci un agente principale che delega parti del lavoro ad altri agenti, oppure un sistema che continua a iterare finche non raggiunge una condizione.

Per noi, nel corso, questo livello diventa concreto nel Video 5. Li vedremo `/loop`, che ripete un controllo nel tempo, e `/goal`, che fa lavorare Claude su un obiettivo finche non e soddisfatto.

## Slide 8 - `/loop` e `/goal`

Anticipiamo gia la distinzione. `/loop` serve quando vogliamo controllare qualcosa piu volte: per esempio se una build e finita, se sono comparsi errori in un log, o se una situazione esterna e cambiata.

`/goal`, invece, serve quando vogliamo raggiungere un risultato: per esempio aumentare la copertura dei test, correggere una serie di problemi o completare una checklist. Non gli stiamo chiedendo solo di controllare: gli stiamo chiedendo di arrivare a una condizione finale.

## Slide 9 - Come useremo la parola "agente"

Da qui in avanti, quando nel corso diciamo "agente", intendiamo un sistema che decide i prossimi passi verso un obiettivo. Non significa che sia infallibile, e non significa che debba avere liberta totale.

Significa che puo scegliere strumenti, leggere contesto, proporre azioni, eseguire controlli e fermarsi quando serve una conferma. Questa definizione ci aiuta a essere precisi: un agente non e solo un chatbot piu potente.

## Slide 10 - Chiusura

Quindi, ricapitolando: il chatbot risponde, l'assistente con strumenti agisce dentro una richiesta, l'agente pianifica e verifica verso un obiettivo, e i sistemi ricorsivi o multi-agente lavorano nel tempo o in parallelo.

Nel prossimo video portiamo questa idea dentro una sessione concreta. Vedremo come far conoscere il progetto a Claude, come gestire i permessi e come scegliere modello ed effort prima di farlo lavorare sul repository.

## Nota di registrazione

Avvia `npm run dev` e registra il player HyperFrames con CapCut. Se vuoi un montaggio piu pulito, registra blocchi brevi e lascia 1-2 secondi di silenzio dopo ogni cambio slide: rende piu facile tagliare e allineare la voce.
