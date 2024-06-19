💡 Una **VPN** (Virtual Private Network) è una rete privata creata all’interno di un’infrastruttura di rete pubblica, per esempio Internet.


Le VPN sono configurabili e riconfigurabili facilmente, sono scalabili e offrono un valido rapporto tra costi e funzionalità. Nel contesto attuale delle reti VPN basate su Internet vengono affrontati impiegando una combinazione di 3 fattori: **autenticazione, cifratura** e **tunneling.**

### Tipi di VPN

Esistono due tipi di VPN in commercio:

- **Remote-access VPN:** porta qualsiasi applicazione dati, voce e video al desktop remoto, emulando il desktop dell’ufficio principale.
- **Site-to-site VPN:** è l’alternativa alle WAN e consente alle azienda di ampliare le risorse di rete alle filiali, agli uffici domestici e alle sedi di partner.

### Remote-access VPN

Una **Remote-access VPN** consente ai singoli utenti di stabilire connessioni sicure con la LAN aziendale remota. Gli utenti possono accedere alle risorse protette dalla rete locale, come se fossero direttamente collegati ai server della rete.

Ci sono due componenti indispensabili per realizzare un accesso remoto VPN:

- Un server di accesso alla rete, ovvero un **NAS (Network Access Server)**. il NAS richiede all’utente di fornire credenziali valide per accedere alla VPN. Il NAS utilizza il proprio processo di autenticazione oppure, si avvale di un server di autenticazione separato, per esempio RADIUS AAA Server.

<aside> 💡 Per ogni connessione VPN, il Server AAA conferma chi sei (**Authentication**), identifica ciò a cui ti è permesso accedere tramite la connessione (**Authorization**) e tiene traccia di ciò che fai mentre sei loggato (**Accounting**).

</aside>

- Un **software VPN Client.**

Inoltre, è necessario un firewall che fornisce una barriera tra la LAN privata e Internet.

<aside> 💡 Una **Remote-access VPN** è adatta per i singoli dipendenti/utenti o per aziende con filiali costituite da piccoli uffici

</aside>

### Site-to-site VPN

Una **site-to-site VPN** permette di stabilire connessioni sicure attraverso una rete pubblica, come Internet, anche ad aziende con tante sedi, ognuna con una sua LAN. Creando collegamenti LAN-to-LAN.

Ci sono due tipi di Site-to-site VPN:

- **Intranet-based:** se una società desidera unire le reti delle sedi remote in un’unica rete privata, può creare una **VPN intranet** per collegare ogni LAN separata in una singola rete WAN
- **Extranet-based:** se una società ha un rapporto stretto con un altra società può costruire una **VPN extranet** che collega le LAN di queste imprese. Permettono alle imprese di lavorare in un ambiente sicuro, condividendo le risorse e senza l’accesso preventivo alla propria intranet.
