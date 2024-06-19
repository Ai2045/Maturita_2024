💡 Un **proxy** è un programma che si interpone tra un client e un server facendo da tramite. Il client si collega al proxy, invece che al server, e gli invia la richiesta. Il proxy, a sua volta, si collega al server a cui inoltra la richiesta del client. Infine il proxy, ricevuta la risposta, la inoltra al client.


I proxy, nella maggior parte dei casi, lavorano a livello Application. Il loro compito principale è garantire la connettività e il caching ai client a loro collegati ai fini dell’efficienza della rete.

Le configurazioni del Proxy Server permettono di svolgere questi compiti:

- **connettività:** permette a una intera rete privata di accedere a Internet attraverso un unico computer
- **privacy:** maschera il vero IP del client in modo che il server remoto non possa conoscere chi ha effettuato la richiesta
- **caching:** immagazzina per un certo tempo i risultati delle richieste di un client e, se vengono effettuate le stesse richieste, risponde senza dover consultare il server originale
- **monitoraggio:** tiene traccia di tutte le operazioni effettuate, consentendo statistiche e osservazioni dell’utilizzo della rete
- **amministrazione:** applica regole definite dall’amministratore di sistema per determinare quali richieste inoltrare e quali rifiutare, oppure limitare l’ampiezza di banda utilizzata dai client, oppure filtrare le pagine web
- **filtraggio:** svolge funzioni di firewall a livello Application, garantendo un alto grado di protezione a scapito della velocità della rete
- **restrizioni:** crea una zona neutra, non appartenente né alla LAN aziendale né alla WAN, ma dove il traffico LAN e WAN è fortemente limitato e controllato (DMZ - DeMilitarized Zone).

### Tipi di proxy

Si possono individuare tre categorie di utilizzo:

- **Single Proxy Topology:** è la scelta più semplice, utilizza un singolo Proxy Server per servire l’intera rete

- **Multiple Proxy Vertically Topology:** nel caso di reti medio-grandi si configurano più proxy, per esempio uno per ogni subnet, stabilendo un **proxy primario** a cui altri si connettono. I **proxy secondari** agiscono come client del primario; questa tecnica _verticale_ consente a qualsiasi client di avere il filtraggio dei pacchetti personalizzato. Il proxy secondario semplicemente guarda nel suo **repository** per vedere se è i n grado i risolvere il pacchetto in transito; se non lo risolve, inoltra il pacchetto al proxy primario.

- **Multiple Proxy Horizontally Topology:** consente di bilanciare il carico tra i server in base alle richieste dei client. In tale caso, le informazione sul trattamento dei pacchetti personalizzati si distribuiscono ai server di **pari livello**, in modo da garantirne la risoluzione in locale. Lo svantaggio sta nella necessità di sincronizzare il repository di ogni proxy con quello degli altri.