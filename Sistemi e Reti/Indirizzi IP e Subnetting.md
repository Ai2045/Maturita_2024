

 💡 Gli indirizzi IPv4 sono numeri di 32 bit suddivisi in 4 byte (anche detti **ottetti**). Vengono solitamente espressi nella notazione **decimale puntata** costituita da 4 numeri decimali compresi tra 0 e 255, separati da un punto.

L’indirizzo IPv4 usa 32 bit, quindi il numero massimo, teorico, di indirizzi a disposizione è 2^32.

> Gli indirizzi IP pubblici sono assegnati da ICANN (Internet Corporation for Assigned Names and Numbers), che ha assunto la funzione di IANA (Internet Assigned Numbers Authority).


L’indirizzo IP di un host è **diviso in due parti**:

- **NetID** (o NetworkID): è l’indirizzo della rete in cui si trova l’host.
- **HostID**: è l’indirizzo dell’host all’interno della rete NetID.

 💡 In base al valore dei bit più significativi, gli indirizzi IP sono suddivisi in 5 classi: A, B, C, D, E, ma solo le prime tre: A, B e C, possono essere utilizzate per assegnare indirizzi agli host. Questo sistema di indirizzamento è detto **ClassFull**.



### Indirizzi pubblici/privati e statici/dinamici

Gli indirizzi che si affacciano sulla rete internet sono detti **pubblici** e sono univoci in tutto il pianeta. Poichè il numero di indirizzi IPv4 è limitato, sono stati riservati dei range di indirizzi **privati** per ogni classe.

<aside> 💡 Gli indirizzi privati non possono essere utilizzati per affacciarsi direttamente alla rete pubblica Internet, ma servono per indirizzare gli host di reti private.

</aside>

Gli host con indirizzi privati si connettono a Internet mediante un indirizzo pubblico gestito da un **proxy server** o mediante un router NAT (Network Address Translation). I range di indirizzi pubblici sono definiti in RFC 1918 e valgono:

- per la classe A: **da 10.0.0.0 a 10.255.255.255.**
- per la classe B: **da 172.16.0.0 a 172.31.255.255.**
- per la classe C: **da 192.168.0.0 a 192.168.255.255.**

Un’altra tecnica utilizzata per sopperire allo scarso numero di indirizzi IP a disposizione è quella di assegnare, agli utenti privati, degli **indirizzi dinamici**, cioè degli indirizzi che cambiano ogni volta che ci si collega an internet. In questo modo gli ISP (Internet Service Provider) possono utilizzare uno stesso indirizzo IP pubblico per più utenti in momenti diversi, in quanto è difficile che un utente privato stia collegato 24 ore ad Internet.

### Subnetting: dividere la rete in sottoreti

Per ottimizzare il traffico in una rete risulta particolarmente utile suddividerla in una serie di sottoreti logiche, collegate tra loro da router interni alla rete.

<aside> 💡 Il subnetting si realizza “sacrificando” alcuni dei bit che le classi A, B e C dedicano agli host per definire un indirizzo di sottorete, subnetID.

</aside>

Per segmentare una rete occorre, in fase di progettazione, stabilire quante subnet servono e, di conseguenza, quanti bit servono per indirizzarle univocamente. Nel calcolo è necessario anche valutare **il numero massimo di host previsto per ogni subnet** e in base a ciò calibrare il quantitativo di bit da suddividere rispettivamente tra subnet e host.

> **Piano di indirizzamento**: è il risultato della pianificazione dell’assegnazione degli indirizzi IP agli host. Realizzato dall’amministratore di rete utilizzando gli indirizzi IP di rete a disposizione e applicando, se necessario, il subnetting.

💡 Necessario evitare che nella parte subnet e in quella host vi siano contemporaneamente tutti 0 o tutti 1 perchè diventerebbero indirizzi speciali, riservati rispettivamente alla rete e al broadcast. Questo problema si risolve eliminando dal piano di indirizzamento gli HostID con i bit tutti a = 0 con tutti i bit a 1.


### Subnet mask

Normalmente, per capire qual’è l’indirizzo IP della rete a cui appartiene un host è sufficiente considerare i bit più significativi. Con L‘introduzione del subnetting non è più cosi semplice, infatti lo stesso indirizzo IP potrebbe appartenere alla seconda subnet di una rete che è stata suddivisa in più subnet.

💡 Si è quindi definita una nuova stringa da 32 bit (esattamente come gli indirizzi IP) che prende il nome di **subnet mask** e ha lo scopo di indicare quanti bit dell’indirizzo appartengono alla rete e quanti all’host. Nella subnet mask hanno valore 1 i bit in corrispondenza ai bit di rete e sottorete, mentre hanno valore 0 i bit dell’HostID.


Di norma la subnet mask è la stessa per tutte le subnet della rete. Di default le **subnet mask** sono:

- Classe A: **255.0.0.0** (11111111.00000000.00000000.00000000)
- Classe B: **255.255.0.0** (11111111.11111111.00000000.00000000)
- Classe C: **255.255.255.0** (11111111.11111111.11111111.00000000)


> **Scalabilità**: indica la capacità della rete di aumentare (o diminuire) di scala, in funzione della necessità e delle disponibilità. Si realizza soprattutto con un’opportuna dislocazione degli apparati di rete, ma anche con un’oculata pianificazione degli indirizzi IP.

### Processo di messa in AND

Individuiamo due tecniche di inoltro dei pacchetti nella rete:

- **forwarding diretto**: host mittente e destinatario hanno lo stesso NetID, quindi la comunicazione avviene all’interno della stessa rete senza coinvolgere il router.
- **forwarding indiretto**: host mittente e destinatario hanno diverso NetID, quindi sono su reti differenti, il pacchetto viene inviato al router che lo inoltrerà a un altro router e cosi via fino a destinazione.

💡 Il meccanismo che permette di verificare se due host appartengono alla stessa rete (e sottorete) è detto **processo di messa in AND (ANDing process) bitwise**, cioè bit a bit.


Questo processo consiste nel fare:

1. un’operazione di AND bit a bit tra l’indirizzo IP del **mittente** e la subnet mask del **mittente** ottenendo il NetID e il SubnetID del mittente e azzerando l’HostID;
2. un’operazione di AND bit a bit tra l’indirizzo IP del **destinatario** e la subnet mask del **mittente** ottenendo il NetID e il SubnetID e azzerando l’HostID;
3. il confronto tra i due risultati ottenuti:
    - se sono uguali mittente e destinatario sono nella stessa subnet (comunicazione diretta);
    - se sono diversi mittente e destinatario non sono nella stessa subnet (comunicazione tramite il router).

La funzione di messa in AND ha le seguenti proprietà:

- se i due valori confrontati sono entrambi 1, il risultato è 1.
- se uno dei due valori confrontati è 0, il risultato è 0.

> La messa in AND rappresenta il prodotto logico in cui basta uno 0 per ottenere risultato 0.

💡 Possibile riassumere la coppia indirizzo IP e subnet mask mediante la **slash notion** in cui all’indirizzo IP viene fatto seguire il prefix length, un numero decimale che indica il numero di bit a 1 della maschera. Per esempio **150.169.3.2/24**
