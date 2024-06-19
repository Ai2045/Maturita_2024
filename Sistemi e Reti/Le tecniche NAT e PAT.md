<aside> 💡 **NAT (Network Address Translation)** è una tecnica attuata dal router che, nell’intestazione di un pacchetto IP, sostituisce l’indirizzo IP, sorgente o destinazione, con un altro indirizzo.

</aside>

NAT, viene usato per permettere a una rete locale, che usa una classe di indirizzi privata, di accedere a Internet usando un solo indirizzo pubblico fornito dall’**Internet Service Provider (ISP)**. Si tratta dunque, di condividere internet su una LAN usando solo un punto di accesso; dal punto di vista della sicurezza, un NAT offre già buone garanzie proprio perchè nasconde gli host interni e non indirizza loro il traffico proveniente dall’esterno.

> NAT usa una **tabella** contenente la corrispondenza tra le socket interne ed esterne in uso. **Le socket** non sono altro che l’insieme di protocollo, indirizzo IP e porta di comunicazione usati da mittente e destinatario.

Quando un client richiede una pagina web a un server esterno, il suo indirizzo e la sua porta di origine vengono traslati e la corrispondenza viene registrata sulla tabella. Quando arriva la risposta dal server esterno, la tabella permette di capire chi voleva quei dati, quindi il router NAT effettua la traslazione inversa e manda i pacchetti al client richiedenti.

<aside> 💡 Il limite del NAT è che può traslare un solo indirizzo IP per volta, dovendo traslare indirizzo IP e porta abbinati. In questo caso vale la **regola del rapporto 1:1** tra indirizzo IP del server di destinazione e indirizzo IP del client.

</aside>

Diversi vantaggi della tecnica NAT:

- limita il numero di indirizzi pubblici necessari per collegare una LAN a Internet.
- mantiene inalterata la configurazione degli host.
- non modifica il funzionamento dei protocolli e delle applicazioni della rete Intranet.
- offre flessibilità elevata grazie allo spazio molto esteso per gli indirizzi privati.
- riduce i costi di accesso a Internet.
- garantisce maggior sicurezza per i computer della rete locale.

Il NAT presenta 3 funzionalità:

- **Static NAT:** ha a disposizione un solo indirizzo pubblico (IP statico) e a qualunque pacchetto in uscita assegnerà tale indirizzo.
- **Dynamic NAT:** ha a disposizione un insieme di indirizzi pubblici tra cui sceglierne uno da assegnare ai pacchetti in uscita.
- **Port Address Translation (PAT):** traduce in modo dinamico l’indirizzo delle porte, ovvero guarda alla porta di trasmissione e non agli indirizzi IP degli host.

<aside> 💡 **La tecnica PAT (Port Address Translation)** consente al router di utilizzare un singolo indirizzo IP per gestire oltre 64.000 connessioni private contemporaneamente. Questo significa che può traslare più indirizzi IP client per un medesimo indirizzo IP destinazione cambiando solo la porta.

</aside>

> Per il PAT vale la regola del **rapporto 1:N** tra indirizzo IP del server di destinazione e indirizzo IP del client.