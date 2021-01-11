# Information Security Project: Ho. Mobile
> Federico Torrielli

![Consegna di progetto](https://i.imgur.com/aHBKo5g.png)

## 4.1 Comprendere l'organizzazione e il suo contesto

### Ho. Mobile
Azienda di telefonia mobile, si tratta di un servizio offerto da VEI (Vodafone Enabler Italia): in tutto e per tutto un operatore virtuale italiano low-cost.
L'azienda è nata nel *23 gennaio 2017*, durante il periodo dell'ascesa dell'operatore Iliad in Italia, per dare la possibilità a VEI di occupare anche
la fascia più bassa del mercato della telefonia mobile, arricchendo la concorrenza.
L'operatore si appoggia alla già esistente rete Vodafone, limitandone (da offerta ad offerta) la velocità effettiva di utilizzo a 30Mbps oppure 60Mbps.
Essendo un operatore secondario VEI, quando una cella diventa satura, viene privilegiato l'operatore premium (Vodafone).
L'azienda si configura come 'newcomer' sul mercato degli operatori italiani, effettivamente stravolgendo le offerte presenti e rendendosi competitiva
agli occhi del vecchio mercato italiano.

### Scopo dell'organizzazione
Fornitura di un servizio di telefonia low-cost ad alta disponibilità sul territorio italiano, senza effettivamente mettere in ombra l'azienda principale
e allo stesso tempo contrastare la concorrenza creatasi da un'azienda esterna.

## 4.2 Comprendere le necessità e le aspettative delle parti interessate

I principali player che vengono in atto quando si parla di gestione di un operatore virtuale affidato sono generalmente i seguenti:

- La società **stakeholder** principale. In questo caso, la VEI.
- L'**utenza mobile** interessata da ricoprire: persone interessate a pagare poco ma ad avere un servizio di buona qualità.
- Il servizio principale che si occupa del servizio, anch'esso diviso in:
    - *Programmatori web* della piattaforma
    - *Programmatori DB* per la gestione dei dati
    - Servizio di **management e controllo** delle operazioni
    - Servizio di **erogazione delle offerte** alla clientela
- Servizi secondari, che fanno la differenza tra un'operatore reale e virtuale, come:
    - L'assistenza clienti telefonica, affidata ad aziende esterne, spesso estere
    - L'assistenza clienti online, tramite forum, per ingaggiare una community a trovare risposte da soli tra loro, senza dover spendere troppo sull'assistenza
- Servizi essenziali al corretto svolgimento del servizio principale, quali:
    - Società di erogazione servizi online: noleggio/vendita di DB e spazio online che *NON* sono parte di VEI ma che vengono gestiti e sono effettivamente parte di Ho.
    - Lo stato italiano e l'unione europea, verso cui si hanno obblighi quali il rispetto del GDPR e il pagamento delle tasse per il servizio offerto
    - Il servizio bancario di gestione dell'income dell'azienda
- Interessi esterni negativi (ma effettivamente presenti) per l'azienda:
    - Persone interessate ad *impossessarsi dei dati* degli utenti per finalità di social engineering (od ancora peggiori)
    - **Competitors** interessati a negare lo status quo aziendale per prevalere sulla competizione

Risulta dunque necessario ora poter dividere questi "player principali" in due categorie, successivamente utili:

    - High power players
    - Low power players

Così facendo, riusciamo ad identificare i player su cui focalizzarci e mettere da parte quelli meno essenziali per la gestione della nostra information security.

### High power players
Includiamo:

- Servizi interni che tengono vivo il servizio: programmatori e staff interno, gestione del denaro, il servizio online (DB e offerte online) e la sua sicurezza.
- Persone esterne interessate ai dati degli utenti e al denaro come hackers
- Servizi essenziali al corretto svolgimento del servizio principale

### Low power players
Includiamo:

- Servizi secondari, che possono accedere solo *in parte* alle informazioni aziendali oppure semplicemente alle informazioni che Ho. decide di mettere loro a disposizione.

## 4.3 Determinare il campo di applicazione del sistema di gestione per la sicurezza delle informazioni
Il campo di applicazione si suddivide fra la protezione dei dati e delle operazioni di:
- Ho-mobile
- Clienti
- Dipendenti

### Dati sensibili
- Protezione dei dati sensibili: è necessario ridurre la possibilità che vengano diffusi dati sensibili avendo come 
  effetto collaterale la violazione della privacy, le attività illecite e la compromissione del normale funzionamento 
  della compagnia e dei suoi servizi
- Storage e utilizzo dati: i sistemi di memorizzazione di dati, e i mezzi per raggiungerli, devono essere protetti per 
  evitare l'intrusione di malintenzionati e devono essere periodicamente soggetti a backup necessari in caso di perdita 
  di dati per mano di utenti aventi i permessi, malintenzionati e motivi di forza maggiore. La protezione si deve 
  estendere dai dati interni all'azienda fino a quelli in possesso di altre compagnie ma comunque di proprietà di VEI 
  (ad esempio il noleggio di server di terzi)
- Direttive UE: devono essere garantiti i dati dell'azienda, delle compagnie con cui Ho Mobile interagisce, dei 
  dipendenti e degli utenti nel rispetto della normativa europea (GDPR)

### Operazioni
- Permessi: le operazioni eseguibili dagli utenti all'interno, e all'esterno dell'azienda, devono essere vincolate 
  dalla gestione dei permessi stabiliti in funzione del tipo di operazione e del ruolo dell'utente, viene quindi 
  concessa l'esecuzione delle operazioni sensibili in base a chi risulta essere moralmente e giuridicamente 
  responsabile

- Pagamenti: i metodi di pagamento offerti sul sito e sull'applicazione mobile devono essere protetti garantendo lo 
  scambio di dati crittografati, devono permettere l'autenticazione in più fattori richiesta dalle banche (e altri) ed 
  è essenziale garantire la non diffusione di dati di pagamento per mano di malintenzionati (interni ed esterni 
  all'azienda). I dati bancari da proteggere sono sia quelli dell'azienda che quelli dipendenti, clienti e altre 
  compagnie con cui Ho Mobile interagisce

- Erogazione e gestione delle sim: deve essere concesso un metodo veloce per la disattivazione delle sim, in caso di 
  necessità e rischio, fornito mediante servizio clienti e applicazione web/mobile. Le nuove sim devono essere vendute 
  assicurandosi delle generalità del richiedente e il "cambio operatore" deve avvenire nel rispetto delle volontà 
  dell'utente certificato e dei limiti contrattuali del vecchio operatore (ad esempio lo spostamento del credito 
  residuo). Devono essere quindi ridotte al minimo le possibilità di sim-swapping garantendo la sicurezza degli utenti

- Servizi e applicazioni: i servizi di Ho Mobile (come il servizio clienti, il sito web e l'applicazione mobile) devono 
  essere protetti in modo da contrastare le intrusioni e le attività illecite che tentano di violare la sicurezza dei 
  dati o di manomettere i servizi dell'azienda

## 4.4 Sistema di gestione per la sicurezza delle informazioni

Avendo analizzato dunque in generale i processi fondamentali per il corretto funzionamento dell'azienda possiamo dunque
ora andare a trattare e discutere il sistema di gestione per la sicurezza delle informazioni.
Partendo dal sistema di registrazione dell'utente, fino all'immissione dei suoi dati in un ambiente protetto, è necessario
che l'intero processo garantisca la riservatezza delle sue informazioni. Quest'ultimo processo si può dividere in
un numero limitato di fasi, ovvero:

- Registrazione su sito sicuro (ad es. HTTPS con connessione TCP)
- Le credenziali e i dati personali devono poi salvate su *storage sicuro*, crittografate e non indirizzate sul web
- L'accesso al suddetto storage deve essere riservato solamente alle componenti critiche del personale, non a tutti
- I sistemi automatici che fanno accesso allo storage devono essere altrettanto sicuri
- Se è stato inserito un metodo di pagamento, esso **non** deve essere salvato insieme alle informazioni personali

Oltre a questo processo esemplificativo, un argomento sicuramente altrettanto importante è la corretta divisione
del meccanismo di "granting" (ovvero, a chi il sistema debba dare i privilegi, e a quali documenti l'utente può accedere).
Ad esempio, un tecnico che ripara un server non potrà certamente accedere ai dati conservati sullo stesso, così come un
operatore di call center deve avere solamente *le giuste informazioni* a disposizione per poter aiutare l'utente,
senza però invadere la sua privacy.

Sistemi di backup e ripristini sono necessari in caso di malfunzionamenti o attacchi esterni. In questi casi, e durante 
la manutenzione programmata, deve essere presente una "modalità manutenzione" che permette l'accesso al sistema solo 
dagli addetti alla manutenzione fino al termine delle operazioni richieste.

## 6.1 Criteri di valutazione del rischio

### Legenda / Matrice di calcolo del rischio

I valori della sezione successiva verranno calcolati tenendo conto della seguente tabella:

![Matrice di calcolo del rischio](https://i.imgur.com/v9iQ5vN.png)

#### Criterio di valutazione delle probabilità

.           |      Raro     | Improbabile | Probabile | Quasi certo
------------|---------------|-------------|-----------|------------
Livello     |       1       |      2      |     3     |     4
Probabilità |  ogni 10 anni | ogni 5 anni | ogni mese | ogni settimana

#### Criterio di valutazione degli impatti

.           |     Basso     | Medio-Basso | Medio-Alto|    Alto
------------|---------------|-------------|-----------|------------
Livello     |       1       |      2      |     3     |     4
Impatto     |   Fino a 50k  |   50k-100k  | 100k-500k | più di 1mln

### Analisi dei rischi relativi alla sicurezza delle informazioni

Rischio                                       | Owner
----------------------------------------------|-------
Accesso non autorizzato                       |
Manipolazione di privilegi di sistema         |
Manipolazione software (webapp, app mobile)   |
Erogazione non autorizzata delle SIM          |
Distribuzione di informazioni non autorizzate |
Data breach (social engineering oppure sw)    |

### Tabella dei rischi relativi alla sicurezza delle informazioni

.                                             | Probabilità | Impatti | Rischio residuo
----------------------------------------------|-------------|---------|-----------------
Accesso non autorizzato                       | Improbabile |  Alto   |        8
Manipolazione di privilegi di sistema         |    Raro     |  Alto   |        4
Manipolazione software (webapp, app mobile)   |  Probabile  |  Basso  |        4
Erogazione non autorizzata delle SIM          |  Probabile  |  Basso  |        4
Distribuzione di informazioni non autorizzate | Improbabile | Med-Alto|        6
Data breach (social engineering oppure sw)    |    Raro     |  Alto   |        4

### Qualche nota a lato dei punteggi

Come si può notare, nessun punteggio tra quelli evidenziati, nonostante la severità
di molti, supera il grado 8. Questo può essere dato da due fattori:

- L'impatto dell'accaduto è altissimo (nell'ordine dei milioni di euro), ma la probabilità che accada è Rara.
- L'impatto è basso ma la probabilità è alta, il che è ancora meno grave della precedente

Sicuramente, tenendo conto di quanto è successo qualche giorno fa alla società Ho. Mobile,
riguardante il data breach che ha coinvolto parecchie informazioni personali della clientela
e informazioni tecniche riguardanti le SIM erogate dalla società che avrebbero potuto compromettere
l'integrità del cliente e causare parecchi problemi (non solo in ambito privacy), c'è da considerare
che il punteggio della sezione "Data Breach", così come di "Accesso non autorizzato" possano
essere riconsiderate nella prospettiva dell'evolversi del ciclo Plan-Do-Check-Act che prevede
una costante evoluzione e messa a punto dei parametri di sicurezza della società, che sicuramente
dovranno essere rivisti alla luce degli ultimi fatti.

## Controlli Annex A

### Procedure secondarie Annex A

Individuiamo ora i controlli sugli asset che sono considerati fondamentali nel ciclo di vita
della informazioni della società Ho. Mobile.
Saranno messi in lista solamente i controlli Annex A che sono risultati da un primo generale esame
centrali per la politica e la guida attuativa della sicurezza delle informazioni aziendali.

- Politiche per la sicurezza delle informazioni e conseguente riesame (A.5.1.1/A.5.1.2)
- Politiche per l'organizzazione interna (A.6.1 intero) --> Essendo Ho un'azienda di una grandezza non trascurabile
  possiamo immaginare che abbia bisogno dell'intera *suite* di controlli sulla sua organizzazione interna.
- Politiche per il telelavoro (A.6.2.2) --> bisogna ribadire che in un momento come il presente
  l'importanza di garantire la sicurezza anche in modalità telematica sia una dei temi forti oggigiorno
- Consapevolezza, istruzione, formazione e addestramento sulla sicurezza delle informazioni (A.7.2.2)
- Processo disciplinare (A.7.2.3)
- Cessazione o variazione delle responsabilità durante il rapporto di lavoro (A.7.3.1)
- Responsabilità degli asset (A.8.1) --> Essendo una società informatica di grandi dimensioni, bisogna
  garantire che tutti gli asset su cui sono presenti delle informazioni riservate nei limiti aziendali
  restino nei suddetti confini, per evitare possibili fughe d'informazioni.
- Classificazione delle informazioni (A.8.2) --> Vale il discorso di cui sopra
- Trattamento dei supporti (A.8.3) --> Vale il discorso di cui sopra
- Utilizzo delle informazioni segrete di autenticazione (A.9.3.1) --> come già detto nei paragrafi
  precedenti, l'accesso alle informazioni riservate deve essere esclusivo a chi ne ha il grado
  e la competenza di visionarli, nei limiti della gerarchia d'utenza nella società
- Politica di controllo accessi (A.9.1.1)
- Accesso alle reti e ai servizi di rete (A.9.1.2)
- Controllo degli accessi ai sistemi e alle applicazioni (A.9.4) --> Forse uno dei controlli più importanti
  della lista: la necessità di avere log degli accessi è fondamentale per una società che potrebbe essere
  costantemente target di attacchi da vettori esterni ed interni per impossessarsi di informazioni riservate
- Crittografia (A.10)
- Controlli di accesso fisico ai locali (A.11.1.2)
- Sicurezza e manutenzione delle macchine e dei cablaggi (A.11.2.3 A.11.2.4)
- Trasferimento degli asset, se necessario (A.11.2.5)
- Dimissione sicura delle apparecchiature, soprattutto supporti di memoria (A.11.2.7)

### Procedure fondamentali Annex A di priorità assoluta

Si è deciso di separare la seguente sezione dalla precedente per dare risalto ai controlli Annex A
che non solo bisogna rispettare, ma vengono raccomandati con estrema attenzione

- Procedure operative e responsabilità (A.12.1)
- Protezione da malware, backup e raccolta di log e monitoraggio (A.12.2, A.12.3 e A.12.4)
- Controllo del software di produzione (A.12.5)
- Gestione delle vulnerabilità tecniche (A.12.6)
- Considerazioni sull'audit dei sistemi informativi (12.7.1)
- Sicurezza dell'informazione e sicurezza di trasferimento di esse (A.13 intera), tra cui, ricordiamo:
    - Controlli di rete
    - Sicurezza dei servizi di rete
    - Segregazione nelle reti
    - Politiche del trasferimento delle informazioni e susseguenti accordi
    - Messaggistica elettronica inter-dipartimentale
    - Accordi di riservatezza e non divulgazione
- Acquisizione, sviluppo e manutenzione dei sistemi (A.14 intera) --> altrettanto fondamentale è
  è tutto ciò che riguarda i sistemi, propri o a noleggio, che sono parte degli asset e lo sviluppo,
  la loro manutenzione e il controllo dei cambiamenti che riguarda la loro gestione. Escludiamo, dai controlli
  lo sviluppo affidato all'esterno, in quanto tutto il codice e controlli sono proprietari
    - Protezione delle transazioni dei sistemi applicativi
    - Politica per lo sviluppo sicuro: nessun codice deve uscire dal dominio aziendale
    - Limitazioni ai cambiamenti dei pacchetti software
    - Ambiente di sviluppo sicuro
    - Test di sicurezza dei sistemi
    - Testi di accettazione dei sistemi

> Includiamo la parte più critica ed ultima in questo ciclo di procedure fondamentali di priorità assoluta,
> ovvero la gestione degli incidenti relativi alla sicurezza delle informazioni (A.16), che, nella speranza
> venga applicata anche durante il periodo corrente, a seguito del recente data breach avvenuto qualche giorno fa.

- Procedure e responsabilità ben definite
- Segnalazione IMMEDIATA degli eventi relativi alla sicurezza di informazioni (entro 48h dall'accaduto per norma GDPR)
- Segnalazione dei punti di debolezza relativi alla sicurezza delle informazioni
- Valutazione e decisione sugli eventi relativi alla sicurezza delle informazioni
- Risposta agli incidenti
- Apprendimento dagli incidenti
- Raccolta di evidenze

## Piano di trattamento del rischio

Nella parte corrente, verrà predisposto un piano di trattamento del rischio atto a mitigare alcuni
dei rischi identificati nella seconda sezione del testo.

Abbiamo evidenziato che i punti focali su cui si andrà a poggiare la maggior responsabilità
sono quelli che presentano criticità o il cui punteggio di rischio possibile è più alto.
Affiancheremo ai rischi le risoluzione numerate ed andremo a trattarle una ad una in modo chiaro ed
espicito, formalizzando anche quali potrebbero essere i vettori di attacco e le possibili difese 
a disposizione.

Verranno mostrati, di seguito, quelli che sono i tre problemi principali a cui una società come Ho. Mobile
potrebbe assistere, indipendentemente dalla gestione aziendale.

Rischio                                      | Possibile risoluzione
---------------------------------------------|-----------------------
Protezione dei dati sensibili della clientela| Risoluzione #1
Protezione dello storage e dati interni      | Risoluzione #2
Alterazione dello stato di servizi e downtime| Risoluzione #3

### Risoluzione #1

Affrontiamo il tema della protezione dei dati sensibili della clientela.
Essendo Ho. un servizio che si basa sull'acquisizione di dati sensibili per erogare un servizio
è una delle parti più fondamentali su cui focalizzarsi.

Dalla registrazione del cliente, fino alla rimozione dei suoi dati dai server, i passaggi
devono assicurare la totale sicurezza e trasparenza nei confronti del cliente stesso.

Di seguito, vengono elencati alcuni passaggi che sono sono solo *basilarmente* quello che un'azienda
come Ho. Mobile dovrebbe adottare per protegge i dati sensibili dei suoi clienti.

- Permettere una registrazione con il minor numero possibile di informazioni da dare all'operatore:
  meno informazioni = meno dati sensibili da esporre a vettori di attacco
- Processi di registrazione e trasporto di dati devono essere fatti su connessione crittografata 
- Processi di mantenimento di dati devono essere intrapresi su server sicuri, senza la possibilità di
  *accesso fisico* da parte di personale, se non per manutenzione straordinaria (che deve però richiedere)
  la cancellazione degli stessi dati *prima* di ogni intervento in ogni caso
- Lo stesso personale non dovrebbe avere accesso a dati in chiaro degli utenti, e se proprio
  dovesse essere una necessità, bisognerebbe rispettare una gerarchia di accesso che include
  le conseguenti responsabilità, tenendo sempre traccia dei log di accesso al sistema.
- Grazie al punto di cui sopra, in caso di data breach, si può risalire alla lista degli accessi
  fatti e si potrà facilmente trovare il punto di vulnerabilità del sistema (umano o tecnologico)
  nel tempo più breve possibile

Questi sono solo alcuni, e a mio parere pochi, passaggi obbligatori che ogni azienda che ha a che fare
con delle informazioni riservate dei clienti debba attuare.

### Risoluzione #2

Passiamo invece all'argomento che logicamente segue alla prima risoluzione: la protezione
dello storage interno e dei dati contenuti.
Ovviamente, un utente, dopo la sua registrazione sicura, ha dei dati che devono permanere
per essere riutilizzati dall'azienda un giorno futuro per assicurare la continuità di servizio,
attribuire i pagamenti, e molto altro.
Ovviamente, tenendo conto che nella maggior parte dei casi i server sono solamente *noleggiati*
dall'azienda che offre il servizio (per ridurre i costi di operatività di servizio, ma anche per
garantire la qualità e l'uptime che un operatore dovrebbe avere per i clienti) e non effettivamente
comprati e fisicamente accessibili dalla società.

Questo fatto è sia positivo che negativo, se si guarda il lato della sicurezza delle informazioni:

**Da un lato**, nessuno della nostra azienda potrà fisicamente accedere ai dati, che saranno probabilmente
sparsi su più datacenter, magari non in Italia, rendendoli *direttamente inaccessibili* ad un vettore
di attacco che vuole effettuare un data breach.

**Dall'altro**, invece, si affida la sicurezza della gestione delle proprie informazioni ad 
una società esterna, aggiungendo quindi un layer aggiuntivo di complessità al nostro sistema di
gestione della sicurezza.

Bisogna quindi, se si sceglie di affidarsi all'esterno, fare una scelta ponderata (e non la più 
economica, come spesso accade) sul provider di riferimento del servizio.

Secondariamente, quando ci si è accertati della sicurezza del provider, bisogna anche accertarsi
che le uniche connessioni a tali server da parte del "nostro" servizio siano automatizzate e sicure.
Teoricamente, nessuno dovrebbe accedere "da terminale" ai dati importanti e riservati della clientela.
Se questo dovesse succedere, anche solo per un gruppo riservato di persone, potrebbe essere un vettore 
importante di attacco e sicuramente molto più difficile da tracciare con log rispetto a eventi 
fatti "da macchine su altre macchine".

### Risoluzione #3

Ultima delle risoluzioni trattate, ma non meno importante, è il fatto che si debba assicurare
un tempo di non-operatività (o downtime) vicino allo zero. Un servizio come quello di un operatore
telefonico conta anche sul fatto che il suo servizio sia *costantemente operativo*.
Anche se molte volte questi downtime possono essere causati da cause esterne alla gestione aziendale
(nodi server non operativi o malfunzionanti, troppo traffico per assicurare una qualità accettabile
del servizio..) molte altre volte sono direttamente causati da malgestione interna o attacchi 
provenienti dall'esterno.

Non è raro sentire che diversi servizi di telefonia non siano operativi a causa di diversi tipi
di attacchi, ed è giusto concentrare i propri sforzi per evitare che questo tipo di attacchi
accadano, anche perchè, nonostante non rappresentino un enorme perdita "in denaro" per la società,
fanno perdere la fiducia del consumatore nei confronti del servizio, che, a mio parere, è ancora peggio.

Bisogna dunque focalizzare i propri sforzi sulle seguenti tematiche:

- Adattamento di servizi di backup e ripristino di dati su una location diversa da quella principale
- Cercare di parallelizzare le connessioni verso il servizio e ridurre il traffico da usare nell'usufruire
  di siti e servizi: ridurre in generale le interazione verso il servizio può servire a mantenerne basso
  il traffico ed alta la qualità, di conseguenza

## Conclusione e pareri personali

Nel mondo contemporaneo l'importanza di adattare una o più policy di Information Security management
è diventata palese. Ciò che è successo ad Ho., può ovviamente ripetersi per ogni azienda, non solo del
settore IT, ma anche qualsiasi esso sia.

La fortuna (e sfortuna) che ho avuto nel poter trattare l'argomento pre-breach e post-breach ha 
illuminato la relazione sotto due diverse luci, dando sicuramente degli spunti interessanti.

Ringrazio *Ivan Spada* per avermi dato degli spunti interessanti sulla situazione post-breach ed
aver contribuito alla scrittura del primo paragrafo.
