
Il DHCP (Dynamic Host Configuration Protocol) è un protocollo di rete utilizzato per assegnare automaticamente gli indirizzi IP e altre informazioni di configurazione ai dispositivi di una rete.

## Funzionamento del DHCP

Il processo di configurazione DHCP si articola in 4 fasi principali:

1. **DISCOVER:** Il client invia un messaggio broadcast sulla rete per identificare i server DHCP disponibili.
2. **OFFER:** I server DHCP che ricevono il messaggio DISCOVER rispondono con un'offerta (OFFER) contenente un indirizzo IP disponibile e altre informazioni di configurazione.
3. **REQUEST:** Il client sceglie l'offerta più vantaggiosa e invia un messaggio di richiesta (REQUEST) al server DHCP selezionato.
4. **ACK:** Il server DHCP conferma l'assegnazione degli indirizzi e delle configurazioni al client con un messaggio di acknowledgement (ACK).

## CONFIGURAZIONE

Un server DHCP può essere configurato per assegnare gli indirizzi IP in base a diverse policy:

* **Policy di assegnazione degli Indirizzi:**  Si possono definire range di indirizzi IP da assegnare dinamicamente, indirizzi statici per dispositivi specifici e la durata del lease degli indirizzi.
* **MAC Addresses:** È possibile assegnare indirizzi IP statici a dispositivi specifici in base al loro indirizzo MAC.
* **Classe Utente (tipo di utenza):** Si possono creare classi di utenti con differenti policy di assegnazione degli indirizzi.
* **Classe Fornitore (marca o al modello dei dispositivi):** Si possono definire policy di assegnazione in base al tipo di dispositivo.

**Altre informazioni fornibili durante la configurazione:**

* Gateway predefinito
* Server DNS

## Vantaggi

* **Gestione semplificata della rete:** L'assegnazione automatica degli indirizzi IP riduce il carico amministrativo.
* **Scalabilità:** Il DHCP semplifica l'aggiunta e la rimozione di dispositivi dalla rete.
* **Sicurezza (centralizzazione assegnazione indirizzi ip e server DNS):** La centralizzazione della gestione degli indirizzi IP e dei server DNS migliora la sicurezza della rete.

## Svantaggi

* **Gestione indirizzi statici:** La gestione degli indirizzi statici può essere più complessa con il DHCP.
* **Conflitti di Indirizzamento:**  Se il server DHCP non è configurato correttamente, potrebbero verificarsi conflitti di indirizzamento IP.

## DHCP Failover

### Definizione

Il failover DHCP è una funzionalità che permette a due server DHCP di supportarsi a vicenda in caso di guasto di uno dei due.

### Modalità di Operazione

* **Modalità di Condivisione del Carico:** I due server DHCP si dividono il carico di lavoro, gestendo entrambi le richieste dei client.
* **Modalità di Standby Attivo (server secondario è in standby):** Il server secondario rimane in standby e subentra solo se il server principale si guasta.