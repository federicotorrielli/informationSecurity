# Information Security Project
> Federico Torrielli ed Ivan Spada

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

- La società stakeholder principale. In questo caso, la VEI.
- L'utenza mobile interessata da ricoprire: persone interessate a pagare poco ma ad avere un servizio di buona qualità.
- Il servizio principale che si occupa del servizio, anch'esso diviso in:
    - Programmatori web della piattaforma
    - Programmatori DB per la gestione dei dati
    - Servizio di management e controllo delle operazioni
    - Servizio di erogazione delle offerte alla clientela
- Servizi secondari, che fanno la differenza tra un'operatore reale e virtuale, come:
    - L'assistenza clienti telefonica, affidata ad aziende esterne, spesso estere
    - L'assistenza clienti online, tramite forum, per ingaggiare una community a trovare risposte da soli tra loro, senza dover spendere troppo sull'assistenza
- Servizi essenziali al corretto svolgimento del servizio principale, quali:
    - Società di erogazione servizi online: noleggio/vendita di DB e spazio online che *NON* sono parte di VEI ma che vengono gestiti e sono effettivamente parte di Ho.
    - Lo stato italiano e l'unione europea, verso cui si hanno obblighi quali il rispetto del GDPR e il pagamento delle tasse per il servizio offerto
    - Il servizio bancario di gestione dell'income dell'azienda
- Interessi esterni negativi (ma effettivamente presenti) per l'azienda:
    - Persone interessate ad impossessarsi dei dati degli utenti per finalità di social engineering (od ancora peggiori)
    - Competitors interessati a negare lo status quo aziendale per prevalere sulla competizione

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

