**Evoluzione dei sistemi distribuiti:**

  
I sistemi distribuiti si sono evoluti drasticamente, spinti principalmente dalla necessità di superare i limiti delle macchine standalone e dalle crescenti richieste di elaborazione e condivisione dei dati. Possiamo riassumere l'evoluzione in questo modo:

  

1. **Mainframe:** Inizialmente, l'elaborazione era centralizzata nei mainframe, con terminali stupidi per l'accesso.
2. **Sistemi client-server:** L'avvento del personal computer ha portato ai sistemi client-server, dove i client richiedono risorse e i server le forniscono.
3. **Sistemi distribuiti:** Con l'ascesa di Internet, i sistemi distribuiti si sono evoluti per consentire a più computer di collaborare e condividere risorse su larga scala.
4. **Cloud computing:** Oggi, il cloud computing rappresenta l'apice, offrendo risorse virtualizzate e servizi su richiesta tramite Internet.

  

**Tipologie di sistemi distribuiti:**

  

Esistono diverse tipologie di sistemi distribuiti, ognuna con i suoi punti di forza e di debolezza:

  

- **Sistemi client-server:** Come accennato in precedenza, un modello comune in cui i client richiedono servizi dai server.
- **Sistemi peer-to-peer (P2P):** Tutti i nodi hanno pari responsabilità e capacità, condividendo risorse direttamente tra loro.
- **Sistemi basati sul cloud:** Utilizzo di infrastrutture di terze parti per fornire servizi su richiesta, come l'archiviazione e l'elaborazione.
- **Sistemi cluster:** Gruppi di computer interconnessi che lavorano insieme come un'unica entità per migliorare le prestazioni o l'affidabilità.

  

**Architetture di un'applicazione distribuita:**

  

Le architetture client-server sono ampiamente utilizzate nelle applicazioni distribuite. Vediamo le più comuni:

  

- **Architettura a 2 livelli (Client-Server):** Il client (presentazione) interagisce direttamente con il server (logica e dati), esempio: un'applicazione desktop che accede a un database su un server.
- **Architettura a 3 livelli (Client-Presentazione-Logica-Dati):** Aggiunge un livello intermedio dedicato alla logica applicativa, separando la presentazione, l'elaborazione e i dati. Un esempio è un'applicazione web con un server web (presentazione), un server applicativo (logica) e un server di database.

  

**Il Middleware e il suo ruolo in un'app distribuita:**

  

Il middleware agisce come un tessuto connettivo tra i diversi componenti di un'applicazione distribuita. Facilita la comunicazione, l'interoperabilità e la gestione dei dati tra i vari componenti.

  

- **Funzioni chiave:**
    - **Comunicazione:** Gestisce l'invio e la ricezione di messaggi tra client e server.
    - **Transazioni:** Assicura che le operazioni complesse che coinvolgono più componenti vengano completate in modo affidabile.
    - **Sicurezza:** Fornisce meccanismi di autenticazione, autorizzazione e crittografia per proteggere i dati.