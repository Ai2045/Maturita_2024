
## Cos'è?

Il DNS consente di associare un nome per identificare un computer (nodo) al posto di utilizzare il suo indirizzo IP. Si basa su un database distribuito sui vari Name Server.

### Componenti principali:
- **Domain Name Space**: Specifica la struttura dei nomi di dominio (struttura ad albero) ed è diviso in 3 zone:
  - **Domini radice**
  - **Domini intermedi**
  - **Domini foglia**: Non hanno sottodomini, contengono solo host.
- **Name Server**: Processo con il ruolo di server che contiene informazioni sulle zone del Name Space.
- **Resolver**: Processo client che riceve le informazioni dal Name Server.

> 💡 Il DNS è utilizzato anche nelle LAN private per identificare con nomi comprensibili specifici computer.

### Esempio
- **www.google.com**
  - `.com` rappresenta il TLD (top-level domain → dominio radice).
  - `.google` rappresenta il dominio intermedio.
  - `www` rappresenta il dominio foglia.

## Resource Records (RR)

I Resource Records sono delle strutture nelle quali vengono conservate le informazioni di ogni zona. Sono solitamente usati per recuperare gli indirizzi IP.

- **Name**: Nome del dominio al quale il Resource Record appartiene.
- **Type**: Tipo di informazione contenuta in RData.
- **Class**: Classe delle informazioni nel record (per esempio IN per indicare Internet).
- **TTL**: Timer per la durata del record nella cache del DNS.
- **RDLength**: Lunghezza in ottetti di RData.
- **RData**: Valore restituito dal DNS.

> 💡 Il type più basilare è A, che identifica un indirizzo IPV4 in RData. Per l'IPV6 si utilizza AAAA.

## Come funziona?

Lo spazio dei nomi del DNS è stato suddiviso in zone, ognuna con un Name Server Principale e dei Name Server secondari che fanno affidamento al principale per avere le informazioni.

Il client (resolver) effettua una richiesta al server DNS e se il Resource Record è Authoritative allora il DNS risponde direttamente con l'informazione desiderata dal client, altrimenti effettuerà altre interrogazioni nel namespace. → Risoluzione dei nomi.

### Tipi di query DNS:
- **Iterative**
- **Ricorsive**

> 💡 Esiste anche la possibilità di associare un nome ad un indirizzo IP → Risoluzione Inversa.

## Problemi di Sicurezza

Il DNS presenta vari problemi di sicurezza critici:
- Privo di autenticazione → nessuna garanzia sulla provenienza dell'informazione.
- Lentezza → possibilità di intercettazione con conseguente risposta falsificata (spoofing).
- Integrità delle informazioni assente.

> 💡 Un tipo di attacco molto comune verso i server DNS era il DNS Cache Poisoning, che comprometteva l'integrità dei dati.

### Soluzioni

Per rimediare ad alcuni di questi problemi è stato creato DNSSEC, che ha il compito di garantire all'utente l'autenticità del sito che sta visitando e non una copia.
```