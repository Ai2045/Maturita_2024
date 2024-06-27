Il **firewall** è una linea di difesa indispensabile contro le intrusioni di rete poiché agisce come sentinella alla porta di collegamento di un computer con una rete esterna come internet.

💡 Il firewall **filtra tutti i pacchetti entranti** e **uscenti**, da e verso una rete o un computer, secondo regole prestabilite (**policy**) che contribuiscono alla sicurezza della rete stessa


Nelle LAN aziendali viene realizzato attraverso una funzionalità logica (software) **inclusa nel router** oppure può essere implementato su un apparato **hardware dedicato**.

Non disporre di un firewall significa essere esposti a numerosi attacchi e tentativi di intrusione.


### Categorie di firewall

I firewall si distinguono in 3 categorie, in base al livello dello stack TCP/IP in cui operano:

1. **Application Level Firewall:** intercetta le trasmissioni a livello Application, cioè valuta il contenuto applicativo dei pacchetti, riconoscendo e bloccando i dati appartenenti, per esempio, a virus o worm noti. A questa categoria appartengono i **proxy**.
    
2. **Packet Filter Firewall:** lavora a livello Network e a livello Transport. Questo tipo di firewall è molto più veloce dell’Application Level Firewall in quanto il controllo viene effettuato **solo** sui pochi byte di **header** (20, escludendo le opzioni) senza preoccuparsi dell’applicazione che ha generato il pacchetto.
    
    I parametri che il Packet Filter Firewall controlla nell’header del pacchetto possono essere:
    
    - IP di origine e destinazione
    - porta di origine e destinazione
    - protocollo di livello superiore usato
3. **Stateful Packet Inspection Firewall:** agisce a livello Transport e permette oltre al controllo dell’header del pacchetto dati, anche di analizzarne il contenuto per catturare più informazioni rispetto ai semplici indirizzi di origine e destinazione.