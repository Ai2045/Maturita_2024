 💡 IPsec non è un singolo protocollo ma piuttosto un’architettura di sicurezza a livello Network, composta da vari protocolli e da altri elementi


IPsec rappresenta la scelta adottata più frequentemente dalle aziende in quanto consente la realizzazione di diversi tipi di VPN, come una VPN Site-to-site con topologia a maglia completa, o una VPN Remote-access con topologia a stella.

## Protocolli:

- **Authentication Header (AH):** garantisce l'autenticazione e l'integrità del messaggio ma non offre la confidenzialità
- **Encapsulating Security Payload (ESP):** fornisce autenticazione, confidenzialità e integrità del messaggio
- **Internet Key Exchange (IKE):** implementa lo scambio delle chiavi per realizzare il flusso crittografato

# AH e ESP

questi due protocolli forniscono protezione anche da attacchi replay e possono essere usate in due modalità: tunnel e trasporto

![Untitled](https://prod-files-secure.s3.us-west-2.amazonaws.com/9d17744a-5448-4680-a196-fbe1ea7a9950/60465679-65ff-42dd-bbda-2d754b7e8972/Untitled.png)

![Untitled](https://prod-files-secure.s3.us-west-2.amazonaws.com/9d17744a-5448-4680-a196-fbe1ea7a9950/26664867-ff92-4c62-aa28-8c7bca73795a/Untitled.png)

# Ike

- Gestisce la negoziazione delle chiavi di sicurezza
- Stabilisce le Security Associations
- Utilizza un metodo sicuro per scambiare le chiavi crittografiche

# Modalità di trasporto e tunnel

<aside> 💡 Le due modalità che usa l’architettura IPsec per scambiare i messaggi fra host tramite i protocolli AH e ESP sono la modalità di trasporto e tunnel.

</aside>

## Modalità di trasporto:

- **Applicazione**: Utilizzata principalmente per la comunicazione end-to-end tra due host.
- **Protezione del Payload**: Solo il payload del pacchetto IP (cioè i dati effettivi) è protetto tramite criptazione (con ESP) o autenticazione (con AH o ESP).
- **Header IP Originale**: L'header IP originale rimane invariato, il che significa che la modalità di trasporto non cripta né nasconde l'header IP originale.
- **Efficienza**: Generalmente, la modalità di trasporto è più efficiente rispetto alla modalità tunnel perché ci sono meno overhead e meno elaborazione richiesta.

## Modalità di tunnel:

- **Applicazione**: Utilizzata per la comunicazione tra due gateway di sicurezza (ad esempio, tra due firewall o router VPN) o tra un client e un gateway.
- **Protezione Completa**: Protegge l'intero pacchetto IP, inclusi sia i dati (payload) sia l'header originale. In questa modalità, il pacchetto originale viene incapsulato in un nuovo pacchetto IP con un nuovo header.
- **Nuovo Header IP**: Viene aggiunto un nuovo header IP al pacchetto incapsulato, il che consente il routing attraverso internet mantenendo il pacchetto originale nascosto e protetto.
- **Compatibilità con NAT e Firewall**: Poiché vengono utilizzati nuovi header IP, la modalità tunnel è più compatibile con NAT e firewall, che possono modificare l'header esterno senza influenzare l'integrità del pacchetto originale criptato.
- **Overhead e Prestazioni**: Ha un maggior overhead a causa dell'incapsulamento aggiuntivo, il che può comportare un leggero calo nelle prestazioni a causa dell'elaborazione e della larghezza di banda aggiuntive necessarie.