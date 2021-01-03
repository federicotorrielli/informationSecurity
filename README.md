# Information Security Project
> Federico Torrielli ed Ivan Spada

![Consegna di progetto](https://i.imgur.com/aHBKo5g.png)

## 4.1 Comprendere l'organizzazione e il suo contesto

### Ho. Mobile

Azienda di telefonia mobile, si tratta di un servizio offerto da VEI (Vodafone Enabler Italia): in tutto e per tutto un operatore virtuale italiano low-cost.
L'azienda è nata nel 23 gennaio 2017, durante il periodo dell'ascesa dell'operatore Iliad in Italia, per dare la possibilità a VEI di occupare anche
la fascia più bassa del mercato della telefonia mobile, arricchendo la concorrenza.
L'operatore si appoggia alla già esistente rete Vodafone, limitandone (da offerta ad offerta) la velocità effettiva di utilizzo a 30Mbps oppure 60Mbps.
Essendo un operatore secondario VEI, quando una cella diventa satura, viene privilegiato l'operatore premium (Vodafone).

### Scopo dell'organizzazione

Fornitura di un servizio di telefonia low-cost ad alta disponibilità sul territorio italiano, senza effettivamente mettere in ombra l'azienda principale
e allo stesso tempo contrastare la concorrenza creatasi da un'azienda esterna.

## 4.2 Comprendere le necessità e le aspettative delle parti interessate



## 4.3 Determinare il campo di applicazione del sistema di gestione per la sicurezza delle informazioni

Il campo di applicazione si suddivide fra la protezione dei dati e delle operazioni di:
-   Ho-mobile;
-   clienti;
-   dipendenti.

È necessario ridurre la possibilità che vengano diffusi dati sensibili avendo come effetto collaterale la violazione
della privacy, le attività illecite e la compromissione del normale funzionamento della compagnia e dei suoi servizi.

Le operazioni eseguibili dagli utenti all'interno, e all'esterno dell'azienda, devono essere vincolate dalla gestione
dei permessi stabiliti in funzione del tipo di operazione e del ruolo dell'utente, viene quindi concessa l'esecuzione 
delle operazioni sensibili in base a chi risulta essere moralmente e giuridicamente responsabile.

I sistemi di memorizzazione di dati, e i mezzi per raggiungerli, devono essere protetti per evitare l'intrusione di 
malintenzionati e devono essere periodicamente soggetti a backup necessari in caso di perdita di dati per mano di
utenti aventi i permessi, malintenzionati e motivi di forza maggiore. La protezione si deve estendere dai dati interni 
all'azienda fino a quelli in possesso di altre compagnie ma comunque di proprietà di VEI (ad esempio il noleggio di 
server di terzi).

I metodi di pagamento offerti sul sito e sull'applicazione mobile devono essere protetti garantendo lo scambio di dati 
crittografati, devono permette l'autenticazione in più fattori richiesta dalle banche (e altri) ed è essenziale 
garantire la non diffusione di dati di pagamento per mano di malintenzionati (interni ed esterni all'azienda). I dati 
bancari da proteggere sono sia quelli dell'azienda che quelli dipendenti, clienti e altre compagnie con cui Ho Mobile 
interagisce.

Deve essere concesso un metodo veloce per la disattivazione delle sim, in caso di necessità e rischio, fornito mediante 
servizio clienti e applicazione web/mobile. Le nuove sim devono essere vendute assicurandosi delle generalità del 
richiedente e il "cambio operatore" deve avvenire nel rispetto delle volontà dell'utente certificato e dei limiti 
contrattuali del vecchio operatore (ad esempio lo spostamento del credito residuo). Devono essere quindi ridotte al
minimo le possibilità di sim-swapping garantendo la sicurezza degli utenti.

I servizi di Ho Mobile (come il servizio clienti, il sito web e l'applicazione mobile) devono essere protetti in modo 
da contrastare gli hackeraggi e le attività illecite che tentano di violare la sicurezza dei dati o di manomettere i
servizi dell'azienda.

Devono essere garatiti i dati dell'azienda, delle compagnie con cui Ho Mobile interagisce, dei dipendenti e degli 
utenti nel rispetto della normativa Europea (GDPR).