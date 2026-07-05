> **Nota — assunzioni fatte in assenza di risposta:**
> Non ho ricevuto conferma su alcuni dettagli, quindi ho proceduto così (modifica pure prima di registrare):
> - **"Graphify"** → l'ho interpretato come **Graphiti** (libreria/MCP server open source di Zep per la memoria a grafo temporale degli agenti AI). Se intendevi altro (es. un plugin Obsidian per il grafo delle note), correggi il Video 1 e il Video 6.
> - **Livello dei collaboratori** → ho scritto il corso assumendo che sappiano già usare un chatbot AI (ChatGPT/Claude via browser) ma non abbiano mai usato una CLI o degli agenti. Se sono principianti assoluti, allunga il Video 2; se sono già developer, puoi tagliare metà del Video 1 e 3.
> - **Struttura** → percorso medio: **8 video**, di durata variabile. Il Video 1 è deliberatamente più lungo (setup pratico completo, su richiesta).
> - **Graphiti nel Video 1** → è il passaggio tecnicamente più pesante del corso (richiede Docker e un database a grafo). L'ho segnalato esplicitamente nel video: se il team non vuole che ogni collaboratore lo installi in locale, conviene che una persona tecnica prepari un'istanza condivisa una volta sola, e tutti gli altri si limitino al comando di collegamento.
>
> Tutti i comandi e comportamenti di Claude Code citati sono stati verificati sulla documentazione ufficiale (code.claude.com/docs) al momento della stesura (luglio 2026). Ponytail, Obsidian e Graphiti sono strumenti/plugin di terze parti, non ufficiali Anthropic — comandi verificati sulle rispettive repository al momento della stesura.

# Corso video: l'AI per i collaboratori di Fabioland

Percorso in 8 video pensato per portare i collaboratori da "so usare un chatbot" a "uso Claude Code in autonomia sul progetto, collego i miei strumenti e capisco cosa può fare un agente AI oggi".

## Come usare questo file

Ogni video ha una scheda con:

- **Obiettivo** — cosa deve saper fare lo spettatore alla fine.
- **Durata indicativa** — narrazione + demo a schermo.
- **Setup prima di registrare** — cosa deve essere già pronto/installato.
- **Script di lettura** — testo da leggere in voce fuori campo, diviso in blocchi. Adatta il ritmo alla tua voce: i tempi sono indicativi, non cronometrati al secondo.
- **Script di esecuzione** — cosa fare a schermo in parallelo a ogni blocco: comandi da digitare, finestre da aprire, cosa inquadrare. Registra lo schermo *mentre* leggi il blocco corrispondente, poi monta.

Convenzione: nello script di esecuzione, `>` indica un comando da digitare nel terminale.

### Checklist tecnica di registrazione (una volta sola, non per video)

1. Risoluzione schermo 1920×1080, terminale con font grande (16-18pt) e tema ad alto contrasto — deve essere leggibile anche compresso su YouTube/Drive.
2. Microfono esterno se possibile; stanza silenziosa; registra un blocco alla volta, non tutto d'un fiato (più facile rifare un pezzo).
3. Prima di ogni demo dal vivo, esegui il comando una volta offline per controllare che non ci siano prompt di login/permessi imprevisti che rallentano la ripresa.
4. Software consigliato: qualsiasi screen recorder con audio di sistema + microfono separati (es. OBS Studio), così puoi silenziare notifiche in post-produzione senza perdere la voce.
5. Esporta ogni video con lo stesso intro/outro di 5 secondi (titolo + numero lezione) per coerenza con gli altri deck del progetto.
6. Per il Video 1 in particolare: registra da una macchina/utente pulito (o una VM), altrimenti "installare da zero" diventa poco credibile se tutto è già presente.

---

## Indice

1. Setup completo: Windows Terminal, Claude CLI, Obsidian, Graphiti (memoria) e Ponytail
2. Cos'è l'AI oggi: dal chatbot ai sistemi agentici
3. Le basi: come si lavora dentro una sessione
4. Skill e Plugin: estendere Claude Code
5. `/loop` e `/goal`: far lavorare l'AI nel tempo
6. MCP nella pratica quotidiana: Obsidian e Graphiti al lavoro
7. GitHub e il flusso di lavoro in team
8. Buone pratiche, sicurezza e limiti

---

## Video 1 — Setup completo: Windows Terminal, Claude CLI, Obsidian, Graphiti e Ponytail

**Obiettivo:** partendo da un PC Windows senza nulla installato, lo spettatore arriva ad avere Claude Code funzionante, collegato a un vault Obsidian, a una memoria a grafo Graphiti e con la skill Ponytail attiva.
**Durata indicativa:** 16-20 min — è volutamente il video più lungo del corso. Se in montaggio risulta troppo denso, valuta di spezzarlo in due file (1a: terminale + CLI; 1b: Obsidian + Graphiti + Ponytail) mantenendo lo stesso script.
**Setup prima di registrare:**
- Un PC Windows "pulito" o un utente/VM di test (altrimenti l'installazione da zero non si vede davvero).
- Un account Claude attivo (Pro/Max/Team/Enterprise/Console) pronto per il login.
- Docker Desktop scaricabile al volo (serve solo per il blocco Graphiti).
- Se possibile, un'istanza Graphiti già preparata da un collaboratore tecnico, così nel video puoi mostrare *anche* il collegamento rapido oltre alla creazione da zero.

**Principio guida di questo video:** una volta che Claude Code è installato e loggato, tutto il resto — collegare Obsidian, collegare Graphiti, installare Ponytail — lo chiediamo **a Claude stesso, in linguaggio naturale**, invece di andare a cercare comandi nella documentazione. È il primo esempio pratico di "agente che si auto-configura", il concetto che approfondiamo nel Video 2.

### Script di lettura

> **Blocco 1 — Cosa costruiamo in questo video (0:00)**
> In questo video partiamo da un computer Windows senza nulla installato e arriviamo ad avere tutto l'ambiente di lavoro AI del team: un terminale moderno, Claude Code, il collegamento al nostro archivio di note Obsidian, una memoria a grafo che ricorda le decisioni nel tempo, e una skill che tiene il codice semplice. Alla fine di questo video avrai l'intero setup pronto, e negli altri video capiremo *perché* ogni pezzo serve e come si usa davvero.
>
> **Blocco 2 — Windows Terminal (1:30)**
> Il primo passo non è ancora l'AI: è avere un buon terminale. Windows ha già un terminale integrato, ma Windows Terminal — il progetto open source di Microsoft — è più moderno, supporta più schede, temi, e si comporta meglio con gli strumenti da riga di comando che useremo. Si installa dal Microsoft Store cercando "Terminal", oppure, se hai già un terminale aperto, con un comando winget.
>
> **Blocco 3 — Installare Claude CLI (3:30)**
> Con Windows Terminal aperto, installiamo Claude Code, la CLI che useremo per tutto il resto. Un solo comando in PowerShell scarica e lancia lo script ufficiale di installazione. Fatto questo, dentro la cartella del nostro progetto lanciamo `claude`: si apre il browser per il login con l'account Anthropic, e una volta autenticati siamo dentro la nostra prima sessione.
>
> **Blocco 4 — Da qui in poi, lo chiediamo a Claude (5:30)**
> Ecco il punto interessante di questo video: da questo momento in poi, invece di cercare comandi da copiare e incollare, glieli chiediamo direttamente. Claude Code sa leggere la documentazione dei suoi stessi strumenti e sa eseguire comandi nel terminale — quindi possiamo scrivergli, in italiano semplice, cosa vogliamo ottenere, e lasciare che sia lui a proporre ed eseguire i comandi giusti, chiedendoci conferma prima di ogni azione. È un piccolo assaggio di cosa significa lavorare con un agente invece che con un semplice programma da riga di comando.
>
> **Blocco 5 — Obsidian (7:00)**
> Se il team usa Obsidian per tenere le note di progetto, scarichiamo e installiamo l'app da obsidian.md come faremmo con qualunque programma, e apriamo (o creiamo) il vault condiviso del progetto. Poi, dentro Claude Code, chiediamo semplicemente: "collega Claude Code al mio vault Obsidian". Claude propone il collegamento tramite un MCP server dedicato e, con la nostra conferma, lo installa e lo configura. Da questo momento Claude può cercare e leggere le note del vault quando gli servono, senza che tu debba copiarle a mano in chat.
>
> **Blocco 6 — Graphiti: il passaggio più tecnico (9:30)**
> Questo è il pezzo più impegnativo del setup, ed è giusto dirlo chiaramente: Graphiti, lo strumento di memoria a grafo che vedremo meglio nel Video 6, ha bisogno di un piccolo database che gira in background, e per farlo girare serve Docker. Ci sono due strade. Se qualcuno del team ha già preparato un'istanza condivisa, il tuo unico compito è chiedere a Claude di collegarti a quella, dandogli l'indirizzo che ti hanno passato. Se invece stai preparando tu l'istanza da zero, installiamo prima Docker Desktop, poi chiediamo a Claude di guidarci nell'avvio del servizio Graphiti e nel collegamento. In entrambi i casi, il comando finale che Claude userà è lo stesso tipo di comando visto per Obsidian: un collegamento MCP.
>
> **Blocco 7 — Ponytail (12:30)**
> L'ultimo pezzo è una skill, non uno strumento esterno: Ponytail, che tiene il codice scritto dall'AI il più semplice possibile — la vediamo bene nel Video 4. Anche qui, basta chiedere a Claude: "installa la skill Ponytail dal suo repository ufficiale". Claude propone di aggiungere il marketplace del progetto e installare il plugin, tu confermi, e da quel momento Ponytail è disponibile in ogni sessione.
>
> **Blocco 8 — Verifica finale (14:00)**
> Per chiudere, verifichiamo che tutto sia collegato: chiediamo a Claude di elencare gli strumenti MCP attivi e i plugin installati, e facciamo una prova pratica — ad esempio chiediamo di cercare una nota specifica nel vault Obsidian, per vedere la risposta arrivare davvero da lì.
>
> **Blocco 9 — Chiusura (16:00)**
> A questo punto hai l'intero ambiente pronto: terminale, Claude Code, Obsidian, Graphiti e Ponytail. Nei prossimi video non installiamo più nulla — ci concentriamo su cosa significano davvero questi strumenti e come sfruttarli al meglio, a partire dal capire i diversi livelli di intelligenza artificiale che esistono oggi.

### Script di esecuzione

1. **0:00-1:30** — Schermo su un desktop Windows pulito, nessuna finestra aperta. Slide/overlay con la lista delle 5 tappe del video (Terminal → Claude CLI → Obsidian → Graphiti → Ponytail) che spunterai una a una.
2. **1:30-3:30** — Apri il Microsoft Store, cerca "Terminal", mostra l'installazione di **Windows Terminal**. In alternativa/aggiunta, da un terminale già presente su Windows:
   ```
   winget install --id Microsoft.WindowsTerminal -e
   ```
   Apri Windows Terminal appena installato.
3. **3:30-5:30** — Dentro Windows Terminal (PowerShell), digita:
   ```
   irm https://claude.ai/install.ps1 | iex
   ```
   Mostra il download/installazione. Poi:
   ```
   cd percorso-del-progetto
   claude
   ```
   Mostra l'apertura del browser per il login, poi il ritorno al prompt di Claude Code attivo.
4. **5:30-7:00** — Nessun comando nuovo: slide/overlay con il testo "da qui in poi lo chiediamo a Claude" e una piccola icona che passa da "terminale" a "conversazione".
5. **7:00-9:30** — Browser: scarica e installa **Obsidian** da obsidian.md, apri/crea il vault del progetto. Torna al terminale, dentro la sessione Claude Code scrivi in linguaggio naturale:
   ```
   collega Claude Code al mio vault Obsidian in questa cartella
   ```
   Mostra Claude che propone il comando MCP (es. `claude mcp add --transport stdio obsidian -- npx obsidian-claude-code-mcp`) e chiede conferma prima di eseguirlo; conferma ed esegui.
6. **9:30-12:30** — Slide con le due strade (istanza condivisa vs istanza da zero). Se disponibile, mostra il caso "istanza condivisa": chiedi a Claude "collega Claude Code alla nostra istanza Graphiti condivisa, indirizzo `http://<host-del-team>:8000/sse`" e mostra il collegamento riuscito. Se mostri anche il caso "da zero": installazione di Docker Desktop (accelerata in post-produzione), poi chiedi a Claude "avvia il server Graphiti in locale con Docker e collegalo a Claude Code" e mostra i passaggi (`docker compose up` nella cartella del server Graphiti, poi il collegamento MCP verso `http://localhost:8000/sse`).
7. **12:30-14:00** — Dentro la sessione, scrivi:
   ```
   installa la skill Ponytail dal repository ufficiale DietrichGebert/ponytail
   ```
   Mostra Claude che propone ed esegue:
   ```
   /plugin marketplace add DietrichGebert/ponytail
   /plugin install ponytail@ponytail
   ```
8. **14:00-16:00** — Digita `/plugin list` e mostra Ponytail installato; chiedi a Claude "elenca i server MCP collegati" (equivalente a `/mcp`) e mostra Obsidian e Graphiti nell'elenco; poi chiedi "cerca nel vault la nota su [argomento reale del progetto]" e mostra il risultato che arriva dal vault.
9. **16:00-17:00** — Slide di riepilogo finale con i 5 tasselli tutti spuntati: Windows Terminal ✓, Claude CLI ✓, Obsidian ✓, Graphiti ✓, Ponytail ✓.

---

## Video 2 — Cos'è l'AI oggi: dal chatbot ai sistemi agentici

**Obiettivo:** lo spettatore distingue i 4 livelli di sistema AI e capisce dove si colloca uno strumento come Claude Code, quello appena installato nel Video 1.
**Durata indicativa:** 8-10 min.
**Setup prima di registrare:** nessuno strumento nuovo da installare, solo slide/schermo con esempi (va bene anche solo il browser con claude.ai aperto per mostrare un chatbot semplice).

### Script di lettura

> **Blocco 1 — Introduzione (0:00)**
> Nel video precedente abbiamo installato tutto l'ambiente di lavoro. Prima di iniziare a usarlo davvero, però, vale la pena capire una cosa: quando sentiamo parlare di "intelligenza artificiale" oggi, in realtà stiamo parlando di cose molto diverse tra loro, che vengono tutte chiamate con lo stesso nome. In questo video mettiamo ordine: vediamo quattro livelli, dal più semplice al più avanzato, così quando useremo termini come "agente" o "sistema ricorsivo" sappiamo esattamente di cosa parliamo.
>
> **Blocco 2 — Livello 1: il chatbot (1:00)**
> Il livello più semplice è il chatbot conversazionale puro. Gli fai una domanda, lui risponde, punto. Non ha memoria oltre la chat aperta, non può eseguire azioni nel mondo reale, non può aprire un file o cercare online da solo a meno che non sia stato esplicitamente attrezzato per farlo. È lo strumento giusto per scrivere un testo, chiedere una spiegazione, fare brainstorming. Ma si ferma lì: non fa nulla di concreto al posto tuo.
>
> **Blocco 3 — Livello 2: l'assistente con strumenti (2:30)**
> Il secondo livello è l'assistente che sa usare strumenti — in gergo si dice "tool use". Qui il modello non si limita a scrivere testo: può cercare sul web, leggere un documento, eseguire un calcolo, chiamare una funzione. È ancora guidato passo passo da noi — gli chiediamo una cosa, lui la fa, ci risponde, aspetta la prossima domanda — ma dentro quella singola risposta può compiere azioni reali.
>
> **Blocco 4 — Livello 3: l'agente autonomo (4:00)**
> Il terzo livello è l'agente autonomo, ed è qui che si colloca Claude Code, lo strumento che abbiamo installato nel video scorso. Un agente non aspetta che gli diciamo ogni singolo passo: gli diamo un obiettivo — "sistema questo bug", "scrivi questa funzione e verificala" — e lui decide da solo quali strumenti usare, in che ordine, quando controllare il proprio lavoro e quando fermarsi a chiederci conferma. L'abbiamo già visto in azione nel Video 1: quando abbiamo chiesto a Claude di collegare Obsidian, non gli abbiamo dettato il comando esatto — ha capito cosa serviva e l'ha proposto lui.
>
> **Blocco 5 — Livello 4: sistemi multi-agente e ricorsivi (6:00)**
> Il livello più recente, quello su cui si concentra la ricerca oggi, sono i sistemi multi-agente e "ricorsivi". Un agente di questo tipo può lanciare altri agenti per lavorare in parallelo su parti diverse di un problema, può continuare a lavorare su un obiettivo per ore mentre noi facciamo altro, e può verificare da solo se ha davvero raggiunto il risultato prima di dirci che ha finito. Nel Video 5 vedremo due comandi concreti che appartengono a questo livello: `/loop`, che fa ripetere un compito nel tempo, e `/goal`, che fa lavorare Claude su un obiettivo finché non è soddisfatto — anche attraverso più turni di conversazione.
>
> **Blocco 6 — Chiusura (7:30)**
> Da qui in avanti, ogni volta che diciamo "agente" intendiamo un sistema che decide da solo i prossimi passi verso un obiettivo, non solo che risponde a una domanda. Nel prossimo video vediamo i comandi di base per lavorare dentro una sessione: come far conoscere il progetto a Claude e come gestire i permessi.

### Script di esecuzione

1. **0:00-1:00** — Schermo su slide di titolo "Livelli di AI" con i 4 nomi elencati (li rivelerai uno per uno più avanti, oppure mostrali già tutti e sfumati finché non arrivi al blocco corrispondente).
2. **1:00-2:30** — Inquadra claude.ai (o ChatGPT) nel browser, fai una domanda semplice tipo "spiegami cos'è la fotosintesi", mostra la risposta. Evidenzia: nessun pulsante per "esegui", nessun accesso a file.
3. **2:30-4:00** — Mostra un esempio di tool use: es. Claude che cerca sul web o usa un plugin/tool dentro una chat normale per rispondere a "che tempo fa oggi a Milano". Evidenzia che la richiesta parte comunque da te, una alla volta.
4. **4:00-6:00** — Riusa la clip del Video 1 dove chiedevi a Claude Code di collegare Obsidian, con overlay che evidenzia: "obiettivo dato in linguaggio naturale → Claude sceglie da solo il comando".
5. **6:00-7:30** — Mostra a schermo (anche solo testo/slide) i comandi `/loop` e `/goal` scritti nel prompt, senza eseguirli ancora — è solo un'anteprima di quello che vedremo nel Video 5.
6. **7:30-8:30** — Slide di riepilogo con i 4 livelli in verticale e una freccia che indica "siamo qui" sul livello 3, in vista dei prossimi video.

---

## Video 3 — Le basi: come si lavora dentro una sessione

**Obiettivo:** lo spettatore sa inizializzare un progetto, gestire i permessi e scegliere modello/effort.
**Durata indicativa:** 9-11 min.
**Setup prima di registrare:** Claude Code installato (Video 1), una cartella di progetto reale (es. il repo di Fabioland) senza `CLAUDE.md` per mostrare `/init` dal vivo, oppure una copia di test.

### Script di lettura

> **Blocco 1 — Introduzione (0:00)**
> Con l'ambiente installato nel Video 1 e le idee chiare sui livelli di AI dal Video 2, vediamo ora i comandi che userai praticamente in ogni sessione: come far conoscere il progetto a Claude, come decidere cosa può fare senza chiedere permesso, e come scegliere quanto "ragionamento" usare per un compito.
>
> **Blocco 2 — /init e CLAUDE.md (1:00)**
> La prima volta che apri Claude Code su un progetto nuovo, conviene lanciare `/init`. Genera un file `CLAUDE.md` che descrive il progetto — struttura delle cartelle, comandi principali, convenzioni. Claude lo legge automaticamente a ogni sessione futura, così non devi rispiegare da capo ogni volta com'è fatto il repository.
>
> **Blocco 3 — Permessi (3:00)**
> Ogni volta che Claude vuole fare qualcosa che non è pura lettura — modificare un file, eseguire un comando — per default ti chiede conferma. L'hai già visto nel Video 1, ogni volta che Claude proponeva un comando prima di eseguirlo. Con `/permissions` apri un pannello dove decidi quali azioni autorizzare sempre, quali chiedere ogni volta, quali vietare del tutto. È il modo per bilanciare velocità e controllo: puoi essere permissivo su azioni innocue come leggere file o eseguire test, e restrittivo su azioni rischiose come cancellare o pubblicare qualcosa.
>
> **Blocco 4 — Modello ed effort (5:30)**
> Con `/model` scegli quale modello Claude usare, e con `/effort` scegli quanto "sforzo di ragionamento" applicare — bassa per compiti semplici e veloci, alta per problemi complessi dove vuoi che ci pensi di più prima di rispondere. Più effort significa risposte più ponderate ma anche più lente: per un piccolo aggiustamento di testo non serve il massimo.
>
> **Blocco 5 — Contesto e /plan (7:30)**
> Man mano che la conversazione si allunga, Claude Code riempie una finestra di contesto limitata. Con `/context` vedi quanto spazio stai occupando, con `/compact` lo riassumi per liberare spazio senza perdere il filo. E quando devi affrontare una modifica grande e vuoi vedere il piano prima che parta a scrivere codice, usa `/plan`: entri in una modalità dove Claude propone la strategia e tu la approvi prima che tocchi un solo file.
>
> **Blocco 6 — Chiusura (9:00)**
> Con questi comandi hai il controllo base di ogni sessione. Nel prossimo video vediamo come estendere quello che Claude sa fare con le skill e i plugin — a partire da Ponytail, che abbiamo già installato nel Video 1.

### Script di esecuzione

1. **0:00-1:00** — Terminale con sessione Claude Code già aperta nella cartella del progetto.
2. **1:00-3:00** — Digita `/init`, mostra Claude che esplora i file e genera `CLAUDE.md`; apri il file generato in un editor per mostrarne il contenuto.
3. **3:00-5:30** — Digita `/permissions`, mostra il pannello interattivo, scorri le categorie (allow/ask/deny), aggiungi una regola di esempio (es. permetti sempre `git status`).
4. **5:30-7:30** — Digita `/model` e mostra il picker; digita `/effort` e mostra lo slider interattivo, seleziona un livello con le frecce.
5. **7:30-9:00** — Digita `/context` e mostra la barra di utilizzo; digita `/compact`; poi digita `/plan aggiungi un pulsante al menu principale` e mostra il piano proposto prima che Claude tocchi file.
6. **9:00-9:30** — Slide di riepilogo con i 6 comandi visti: `/init`, `/permissions`, `/model`, `/effort`, `/context`, `/plan`.

---

## Video 4 — Skill e Plugin: estendere Claude Code

**Obiettivo:** lo spettatore capisce cos'è una skill, vede Ponytail (già installata nel Video 1) in azione, e sa installare un nuovo plugin da un marketplace.
**Durata indicativa:** 10-12 min.
**Setup prima di registrare:** sessione Claude Code aperta, con Ponytail già installata (Video 1); connessione a un marketplace di plugin per la demo di un'installazione aggiuntiva.

### Script di lettura

> **Blocco 1 — Cos'è una skill (0:00)**
> Una skill è un pacchetto di istruzioni che insegna a Claude come affrontare un compito specifico in un certo modo — non è nuovo codice, è più simile a una procedura scritta che Claude legge e segue. Ogni skill vive in un file `SKILL.md`: può essere personale, cioè disponibile in tutti i tuoi progetti, oppure di progetto, cioè condivisa con tutti quelli che lavorano su quel repository tramite git.
>
> **Blocco 2 — Come si invoca una skill (2:00)**
> Puoi invocare una skill in due modi: scrivendo esplicitamente `/nome-skill` nel prompt, oppure lasciando che sia Claude a riconoscerla da solo quando la tua richiesta corrisponde a quello che la skill descrive di fare. Nel Video 1 abbiamo già installato un esempio concreto: Ponytail.
>
> **Blocco 3 — Ponytail in azione (3:30)**
> Ponytail è pensata per una cosa sola: costringere Claude a scegliere la soluzione più semplice possibile. Quando scrivi codice, è facile finire per costruire cose più complicate del necessario — funzioni generiche per un caso che capiterà una volta sola, dipendenze in più quando bastava una riga di libreria standard. Ponytail interviene proprio lì: prima di scrivere, si chiede se il compito serve davvero, se esiste già una soluzione più corta, se sta aggiungendo flessibilità che nessuno ha chiesto. Ha anche livelli di intensità — lite, full, ultra — per quanto deve essere aggressiva nel tagliare. È un progetto open source di terze parti, non di Anthropic, ma è ormai uno standard molto usato.
>
> **Blocco 4 — Cos'è un plugin (5:30)**
> Un plugin è un pacchetto più grande di una singola skill: può contenere più skill insieme, agenti, automazioni (hook) e connessioni a strumenti esterni (MCP — li abbiamo già usati nel Video 1 per Obsidian e Graphiti, e li approfondiamo nel Video 6). I plugin si distribuiscono tramite dei "marketplace" — repository che elencano plugin installabili — e ogni comando di un plugin viene prefissato col nome del plugin per evitare conflitti tra plugin diversi.
>
> **Blocco 5 — Installare un altro plugin (7:30)**
> Il meccanismo è lo stesso già visto per Ponytail nel Video 1: si aggiunge un marketplace con `/plugin marketplace add` seguito dal nome del repository, poi si installa il plugin specifico con `/plugin install`. Con `/plugin list` vedi cosa hai installato, e puoi disattivare temporaneamente un plugin con `/plugin disable` senza doverlo disinstallare. Te lo mostro con un secondo plugin, diverso da Ponytail, per far vedere che il procedimento è sempre lo stesso.
>
> **Blocco 6 — Chiusura (9:30)**
> Skill e plugin sono il modo in cui personalizziamo Claude Code per il modo di lavorare specifico di Fabioland — e sono anche il modo in cui, col tempo, possiamo condividere tra collaboratori le procedure che funzionano meglio per noi. Nel prossimo video vediamo due comandi che appartengono al livello più avanzato visto nel Video 2: `/loop` e `/goal`.

### Script di esecuzione

1. **0:00-2:00** — Mostra a schermo (editor di testo) la struttura di cartelle `.claude/skills/nome-skill/SKILL.md` con un frontmatter di esempio (`description`, `name`).
2. **2:00-3:30** — Terminale Claude Code, digita `/plugin list` e mostra Ponytail già presente dal Video 1.
3. **3:30-5:30** — Descrivi a voce uno scenario tipo "aggiungi una funzione per calcolare lo sconto" e mostra Claude che applica la skill Ponytail, evidenziando nel diff finale la soluzione minimale scelta.
4. **5:30-7:30** — Slide/diagramma: un riquadro "Plugin" che contiene dentro più riquadri più piccoli "Skill", "Agent", "Hook", "MCP server".
5. **7:30-9:30** — Terminale, esegui in sequenza un secondo esempio di installazione plugin (diverso da Ponytail), es.:
   ```
   /plugin marketplace add anthropics/claude-plugins-official
   /plugin install skill-creator@claude-plugins-official
   /plugin list
   ```
   Mostra l'output di ciascun comando, con entrambi i plugin ora elencati.
6. **9:30-10:30** — Slide di riepilogo comandi: `/plugin marketplace add`, `/plugin install`, `/plugin list`, `/plugin disable`.

---

## Video 5 — `/loop` e `/goal`: far lavorare l'AI nel tempo

**Obiettivo:** lo spettatore sa quando usare `/loop` e quando usare `/goal`, e li vede in azione su un esempio reale.
**Durata indicativa:** 9 min.
**Setup prima di registrare:** una sessione Claude Code su un progetto con qualcosa di verificabile (es. una build, un file di log, dei test) per rendere la demo credibile.

### Script di lettura

> **Blocco 1 — Introduzione (0:00)**
> Nel Video 2 abbiamo detto che il livello più avanzato di sistema AI è quello che continua a lavorare su un obiettivo nel tempo, senza che tu debba guidarlo passo passo. `/loop` e `/goal` sono i due comandi con cui Claude Code porta questa idea nella pratica. Sono simili ma rispondono a domande diverse.
>
> **Blocco 2 — /loop: ripeti un compito nel tempo (1:30)**
> `/loop` fa una cosa semplice da descrivere: ripete un prompt più volte mentre la sessione resta aperta. Puoi dargli un intervallo fisso — ad esempio ogni 10 minuti — oppure lasciare che sia Claude stesso a decidere quando ripetere, valutando quanto ci vuole realisticamente perché la situazione cambi. Se non specifichi nemmeno il prompt, e nel progetto esiste un file `.claude/loop.md`, usa quello. È lo strumento giusto per compiti di monitoraggio: "controlla se la build è finita", "controlla se sono comparsi errori nel log".
>
> **Blocco 3 — /goal: lavora finché non è soddisfatto (3:30)**
> `/goal` invece non ripete un compito a intervalli: imposta una condizione, e Claude continua a lavorare — anche su più turni di conversazione — finché quella condizione non è soddisfatta. Ad esempio, `/goal porta la copertura dei test al 90 per cento` non è un'azione singola: Claude scrive test, li esegue, misura la copertura, e se non basta continua, senza che tu debba rilanciare la richiesta ogni volta. Con `/goal` senza argomenti vedi l'obiettivo attivo o l'ultimo raggiunto, e con `/goal clear` lo rimuovi se vuoi fermarti prima.
>
> **Blocco 4 — Quale usare (5:30)**
> La differenza in breve: usa `/loop` quando vuoi che qualcosa venga *controllato* ripetutamente nel tempo — un monitoraggio. Usa `/goal` quando vuoi che qualcosa venga *raggiunto*, e non ti importa quanti tentativi o turni servano per arrivarci, purché il risultato finale sia quello.
>
> **Blocco 5 — Un avvertimento (7:00)**
> Proprio perché lavorano in autonomia più a lungo, questi due comandi vanno usati su compiti dove sei d'accordo che Claude proceda senza chiederti conferma a ogni passo. Per tutto quello che è rischioso o irreversibile — pubblicare, cancellare, forzare modifiche — vale sempre la regola che vediamo nell'ultimo video: revisione umana prima di qualsiasi azione che non si può disfare facilmente.
>
> **Blocco 6 — Chiusura (8:00)**
> Con `/loop` e `/goal` chiudiamo la parte sui comandi base. Nel prossimo video torniamo su Obsidian e Graphiti, che abbiamo collegato nel Video 1, per vedere come si usano davvero nel lavoro di tutti i giorni.

### Script di esecuzione

1. **0:00-1:30** — Slide con le due parole `/loop` e `/goal` affiancate, punto interrogativo tra le due.
2. **1:30-3:30** — Terminale, digita:
   ```
   /loop 10m controlla se ci sono nuovi errori in error.log
   ```
   Mostra l'output che conferma l'avvio del loop; se possibile, accelera in post-produzione mostrando una seconda esecuzione automatica dopo l'intervallo.
3. **3:30-5:30** — Terminale, digita:
   ```
   /goal porta la copertura dei test al 90%
   ```
   Mostra Claude che lavora su più iterazioni (scrivi test → esegui → misura copertura), poi digita `/goal` da solo per mostrare lo stato corrente.
4. **5:30-7:00** — Slide comparativa a due colonne: "/loop → monitoraggio ripetuto" vs "/goal → risultato da raggiungere".
5. **7:00-8:00** — Slide con un'icona di stop/attenzione e il testo "azioni irreversibili = conferma umana sempre", da riprendere nel Video 8.
6. **8:00-9:00** — Digita `/goal clear` per mostrare come si interrompe un obiettivo attivo.

---

## Video 6 — MCP nella pratica quotidiana: Obsidian e Graphiti al lavoro

**Obiettivo:** lo spettatore capisce cos'è un MCP server e come sfruttare, nel lavoro di ogni giorno, i collegamenti a Obsidian e Graphiti già fatti nel Video 1.
**Durata indicativa:** 9-10 min.
**Setup prima di registrare:** i collegamenti MCP a Obsidian e Graphiti già attivi (fatti nel Video 1).

### Script di lettura

> **Blocco 1 — Cos'è un MCP server, in breve (0:00)**
> Nel Video 1 abbiamo collegato Claude Code a Obsidian e a Graphiti chiedendolo direttamente all'agente. In questo video vediamo cosa succede davvero dietro quel collegamento, e soprattutto come usarlo bene ogni giorno. MCP è il protocollo standard con cui Claude Code si collega a strumenti esterni: un "MCP server" espone a Claude delle funzioni per interagire con uno strumento specifico, che sia un archivio di note o un database.
>
> **Blocco 2 — Obsidian nel lavoro quotidiano (2:00)**
> Con Obsidian collegato, quando chiedi a Claude di implementare una feature può andare a controllare da solo se esiste già una nota di design che la descrive, cercare per tag o per collegamenti tra note, invece che dover aspettare che tu copi e incolli il contesto rilevante in chat. Il beneficio si vede soprattutto quando il vault cresce: più note ci sono, più senso ha lasciare che sia Claude a cercarci dentro invece che farlo a mano.
>
> **Blocco 3 — Graphiti: memoria a grafo per gli agenti (4:00)**
> Graphiti è uno strumento diverso da un semplice archivio di note: è un sistema di memoria a grafo temporale, pensato apposta per agenti AI. La differenza è che tiene traccia di *come cambiano* i fatti nel tempo — non solo "il boss finale ha 500 punti vita", ma anche quando e perché quel numero è cambiato rispetto alla versione precedente. È utile quando vuoi che l'agente ricordi decisioni prese in sessioni passate e capisca la loro evoluzione, non solo lo stato attuale.
>
> **Blocco 4 — Perché per Fabioland ha senso (6:00)**
> Su un progetto che si sviluppa in tante sessioni diverse, con collaboratori diversi, il rischio è che ogni conversazione con l'AI riparta da zero, senza contesto su cosa è già stato deciso o perché una certa scelta di design è stata scartata. Obsidian e Graphiti, insieme, danno all'agente una memoria che sopravvive alla singola sessione, così non dobbiamo continuamente rispiegare le stesse cose.
>
> **Blocco 5 — Attenzione (8:00)**
> Una nota importante, già anticipata nel Video 1: a differenza dei comandi integrati in Claude Code, Obsidian e Graphiti sono strumenti di terze parti che si collegano via MCP. Prima di collegarli a dati sensibili del progetto vale la pena capire bene cosa condividono e con chi — soprattutto per Graphiti, che spesso gira su un servizio condiviso dal team.
>
> **Blocco 6 — Chiusura (8:45)**
> Con questo chiudiamo la parte sugli strumenti collegati. Negli ultimi due video vediamo come tutto questo si inserisce nel flusso di lavoro in team su GitHub, e quali sono le buone pratiche da rispettare sempre.

### Script di esecuzione

1. **0:00-2:00** — Diagramma semplice: riquadro "Claude Code" al centro, frecce verso riquadri esterni "Obsidian", "Graphiti", "altro strumento", con etichetta "MCP" sulle frecce. Digita `/mcp` per mostrare l'elenco dei server collegati dal Video 1.
2. **2:00-4:00** — Dentro una sessione, chiedi a Claude "cerca nel vault le note che parlano del sistema di combattimento" (o un argomento reale del progetto) e mostra il risultato che arriva dal vault.
3. **4:00-6:00** — Slide/diagramma con una timeline che mostra lo stesso "fatto" (es. punti vita di un boss) con due valori diversi in due date diverse, per rendere visiva l'idea di "memoria temporale". Se possibile, chiedi dal vivo a Claude "cosa ricordi sulle decisioni prese sul sistema di combattimento?" e mostra la risposta basata su Graphiti.
4. **6:00-8:00** — Slide con due colonne: "senza memoria esterna" (icona di conversazione che riparte da zero) vs "con memoria esterna" (icona di conversazione collegata a un archivio persistente).
5. **8:00-8:45** — Slide con un'icona di attenzione: "strumenti di terze parti → verifica cosa condividono, specie se l'istanza è condivisa dal team".
6. **8:45-9:30** — Slide di riepilogo con `/mcp` e i due strumenti citati.

---

## Video 7 — GitHub e il flusso di lavoro in team

**Obiettivo:** lo spettatore capisce come Claude Code si integra con GitHub e come un collaboratore non tecnico può chiedere modifiche senza aprire un terminale.
**Durata indicativa:** 8-10 min.
**Setup prima di registrare:** repository GitHub del progetto con `gh` CLI autenticato; se disponibile, la GitHub App di Claude già installata sul repo per mostrare `@claude` in un commento.

### Script di lettura

> **Blocco 1 — Introduzione (0:00)**
> Fabioland è un progetto di squadra, e il codice vive su GitHub. In questo video vediamo i modi in cui Claude Code si integra con GitHub — sia per chi lavora da terminale, sia per chi preferisce restare dentro l'interfaccia web di GitHub.
>
> **Blocco 2 — La gh CLI (1:30)**
> Dentro una sessione di Claude Code, l'agente ha accesso diretto alla `gh`, la command line ufficiale di GitHub. Questo significa che può leggere una pull request, i suoi commenti, il suo diff, e può crearne una nuova con titolo e descrizione già scritti, tutto senza che tu debba passare dal browser.
>
> **Blocco 3 — La skill /review (3:00)**
> Per revisionare una pull request esistente c'è una skill dedicata, `/review`, che analizza le modifiche di un pull request GitHub cercando bug e problemi, usando lo stesso motore della revisione del codice locale. Utile prima di un merge, o quando un collaboratore vuole un secondo parere prima di chiedere revisione umana.
>
> **Blocco 4 — @claude nei commenti (4:30)**
> La parte più interessante per i collaboratori meno tecnici è questa: una volta installata la GitHub App di Claude sul repository — con il comando `/install-github-app`, che ti guida passo passo nella configurazione — puoi taggare `@claude` direttamente in un commento su una issue o una pull request, scrivere cosa vuoi che venga fatto, e Claude legge il contesto, propone o applica la modifica, e crea un commit. Tutto questo senza che nessuno debba aprire un terminale: basta un browser e un account GitHub.
>
> **Blocco 5 — Perché è utile per tutto il team (6:30)**
> Questo abbassa parecchio la barriera d'ingresso: un game designer che nota un numero sbagliato in una tabella, o un collaboratore che vuole proporre una piccola correzione, può chiederlo direttamente nel commento di una issue, senza dover imparare git o la CLI. Resta comunque un passaggio umano di revisione prima che qualsiasi modifica venga unita al progetto — lo vediamo meglio nell'ultimo video.
>
> **Blocco 6 — Chiusura (8:00)**
> Con questo abbiamo coperto tutto il flusso, dal terminale al browser. Nell'ultimo video mettiamo insieme le buone pratiche di sicurezza che valgono per tutto quello che abbiamo visto finora.

### Script di esecuzione

1. **0:00-1:30** — Schermo su un repository GitHub reale del progetto, tab "Pull Requests" aperto.
2. **1:30-3:00** — Terminale, dentro Claude Code: chiedi "mostrami i commenti sulla PR #12" e mostra Claude che usa `gh` sotto il cofano (visibile nei tool call), poi mostra `gh pr create` con titolo/descrizione generati.
3. **3:00-4:30** — Terminale, digita `/review 12` (o il numero di una PR reale) e mostra l'output della revisione.
4. **4:30-6:30** — Browser su GitHub, apri una issue, scrivi un commento con `@claude` seguito da una richiesta semplice (es. "correggi il typo in questa riga"), mostra (anche solo con uno screenshot/registrazione precedente se il flusso richiede tempo) la risposta automatica e il commit creato.
5. **6:30-8:00** — Slide con un'icona "browser only" per il collaboratore non tecnico vs "terminale" per chi lavora sul codice, entrambe convergenti verso la stessa pull request.
6. **8:00-9:00** — Slide di riepilogo: `gh` CLI, `/review`, `/install-github-app`, `@claude` nei commenti.

---

## Video 8 — Buone pratiche, sicurezza e limiti

**Obiettivo:** lo spettatore sa quali azioni richiedono sempre revisione umana e come impostare i permessi in modo sicuro.
**Durata indicativa:** 7-8 min.
**Setup prima di registrare:** nessuna demo tecnica nuova — questo video riprende esempi già mostrati nei video precedenti, quindi puoi riusare clip già registrate.

### Script di lettura

> **Blocco 1 — Introduzione (0:00)**
> Abbiamo visto quanto Claude Code possa fare in autonomia: installare i propri strumenti, scrivere codice, lavorare su un obiettivo per più turni, aprire pull request. Questo video è il più importante di tutti, perché riguarda i limiti che dobbiamo darci come team quando usiamo questi strumenti.
>
> **Blocco 2 — La regola di base (1:00)**
> La regola di base è semplice: più un'azione è difficile da annullare o riguarda altre persone, più serve una conferma umana esplicita prima di eseguirla. Leggere un file è innocuo e reversibile. Cancellare un branch, forzare una modifica su git, pubblicare qualcosa online, non lo sono. Claude Code per default chiede conferma su tutto ciò che non è pura lettura — l'hai visto più volte nel Video 1, quando ogni comando di installazione veniva proposto e non eseguito finché non confermavi. È una scelta di sicurezza, non un fastidio da disattivare alla leggera.
>
> **Blocco 3 — Permessi: cosa automatizzare e cosa no (2:30)**
> Nel Video 3 abbiamo visto `/permissions`. Il consiglio pratico: automatizza pure le azioni ripetitive e a basso rischio — leggere file, eseguire test, controllare lo stato di git. Lascia sempre la richiesta di conferma per tutto quello che tocca lo stato condiviso del progetto: push su branch principali, merge di pull request, cancellazione di file o branch, pubblicazione di build.
>
> **Blocco 4 — /loop e /goal: attenzione in più (4:00)**
> Proprio perché lavorano più a lungo senza supervisione costante, `/loop` e `/goal`, visti nel Video 5, vanno usati su compiti dove sei tranquillo che Claude proceda da solo per un bel po' di tempo. Se il compito include azioni irreversibili, meglio spezzarlo: lascia che l'agente prepari tutto in autonomia, ma chiedigli di fermarsi prima del passaggio finale che non si può disfare.
>
> **Blocco 5 — Strumenti esterni: cosa condividono (5:30)**
> Anche qui vale quanto detto nel Video 6: quando colleghi uno strumento esterno via MCP — Obsidian, Graphiti, o altro — quello strumento riceve dati dal progetto. Prima di collegarlo, capite insieme come team cosa contiene quel vault o quel grafo, e se è opportuno che un agente AI ci acceda.
>
> **Blocco 6 — Chiusura del corso (6:30)**
> Con questo chiudiamo il percorso: dal setup completo dell'ambiente, ai livelli di AI, ai comandi base, alle skill e ai plugin, a `/loop` e `/goal`, a Obsidian e Graphiti, fino a GitHub e alle buone pratiche di sicurezza. Da qui in avanti l'unico modo per diventare bravi è usarlo sul progetto vero — e se qualcosa non torna, fermatevi e chiedete, invece di forzare un comando che non siete sicuri cosa faccia.

### Script di esecuzione

1. **0:00-1:00** — Slide di titolo "Regole d'oro" con un'icona di scudo.
2. **1:00-2:30** — Riusa la clip del Video 1 dove Claude chiede conferma prima di eseguire un comando di installazione, con overlay testuale che evidenzia il momento della conferma.
3. **2:30-4:00** — Slide a due colonne: "Sì, automatizza" (leggere, testare, controllare stato) vs "No, chiedi sempre" (push su main, merge, cancellazione, pubblicazione).
4. **4:00-5:30** — Riusa la clip del Video 5 con `/loop`/`/goal`, aggiungi overlay "spezza il compito prima del passaggio irreversibile".
5. **5:30-6:30** — Riusa il diagramma MCP del Video 6, overlay "cosa condivide questo strumento?".
6. **6:30-7:30** — Slide finale con l'indice degli 8 video e un checkmark su ciascuno, per dare la sensazione di percorso completato.

---

## Appendice — Cheat sheet comandi

| Comando | Cosa fa | Video |
|---|---|---|
| `winget install --id Microsoft.WindowsTerminal -e` | Installa Windows Terminal | 1 |
| `irm https://claude.ai/install.ps1 \| iex` | Installa Claude Code su Windows | 1 |
| `claude` | Avvia una sessione nella cartella corrente | 1 |
| `claude mcp add` | Collega un MCP server esterno (es. Obsidian, Graphiti) | 1, 6 |
| `docker compose up` | Avvia il backend Graphiti (Neo4j + MCP server) in locale | 1 |
| `/plugin marketplace add DietrichGebert/ponytail` | Aggiunge il marketplace di Ponytail | 1, 4 |
| `/plugin install ponytail@ponytail` | Installa la skill Ponytail | 1, 4 |
| `/doctor` | Diagnostica l'installazione | 1 |
| `/init` | Genera/aggiorna `CLAUDE.md` | 3 |
| `/permissions` | Gestisce le regole di permesso | 3, 8 |
| `/model` | Cambia modello | 3 |
| `/effort` | Cambia livello di ragionamento | 3 |
| `/context` | Mostra l'uso del contesto | 3 |
| `/compact` | Riassume la conversazione per liberare contesto | 3 |
| `/plan` | Entra in modalità pianificazione prima di modificare | 3 |
| `/plugin list` / `/plugin disable` | Elenca/disattiva i plugin installati | 4 |
| `/loop [intervallo] [prompt]` | Ripete un prompt nel tempo | 5 |
| `/goal <condizione>` | Lavora finché la condizione non è soddisfatta | 5 |
| `/goal clear` | Rimuove l'obiettivo attivo | 5 |
| `/mcp` | Elenca i server MCP collegati | 6 |
| `/review [PR]` | Revisiona una pull request GitHub | 7 |
| `/install-github-app` | Installa la GitHub App di Claude sul repo | 7 |

## Prossimi passi (fuori dallo scope di questo file)

- Registrare i video seguendo gli script sopra e caricarli dove il team li consulterà (stessa cartella `presentation/` o uno spazio condiviso).
- Se serve, spezzare ogni scheda-video in un file `.md` separato una volta confermata la struttura, per facilitare la revisione da parte di chi registra.
- Decidere, prima di registrare il Video 1, se l'istanza Graphiti sarà condivisa dal team (un solo setup) o individuale (ogni collaboratore la installa in locale) — cambia il blocco 6 dello script.
- Rivedere le assunzioni segnalate in cima al file (in particolare "Graphify") prima di registrare.
