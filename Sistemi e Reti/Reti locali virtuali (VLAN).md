Il **dominio di broadcast** di una rete è un insieme di computer che riceve un messaggio di broadcast trasmesso da uno di essi. La tabella seguente mostra come l’impiego di apparati diversi comporti un diverso rapporto con i domini di collisione e di broadcast.



Per ovviare al problema presente nelle reti che utilizzano gli switch, ovvero il fatto che che questi inoltrino su tutte le porte un messaggio broadcast che può generare molto traffico su reti con centinaia di host, gli switch attuali offrono due diverse tecnologie:

- **Virtual LAN (VLAN)**: si creano delle sottoreti nella rete locale che, in realtà, esistono solo sugli switch. La rete rimane configurata con la stessa topologia fisica, mentre cambia la topologia logica; quando un computer su una data sottorete invia un messaggio broadcast, esso verrà trasmesso solo ai computer appartenenti a quella sottorete.
- **Layer 3 switching**: quando un host su una VLAN deve comunicare con un host su un’altra VLAN, è necessaria la presenza di un router che interconnette le due VLAN, dopo di che intervengono i rispettivi switch. Se invece viene utilizzato uno switch con funzionalità di routing, non è più necessario avere un router, perchè questi switch sono in grado di leggere l’indirizzo di rete e individuare verso quale switch inviare i pacchetti.

### Vantaggi e svantaggi delle VLAN

La segmentazione e l’isolamento del traffico che si realizzano con le VLAN consentono di ridurre il traffico non necessario, migliorando notevolmente le prestazioni di rete.

- Semplice aggiungere, cambiare o spostare gli host sulla rete.
- Si definiscono più domini di broadcast, di dimensioni ridotte, all’interno di una stessa rete locale switched, con miglioramento delle prestazioni.
- Migliora la sicurezza della rete.
- Riduce i costi relativi agli apparati di rete impiegati.

Una **Virtual Local Area Network (VLAN)** è un insieme di computer, stampanti, server o altri device di rete che sono trattati come se fossero collegati una singola rete, mentre, in realtà si trovano su LAN fisiche diverse. La tecnica di realizzazione elle VLAN permette di raggruppare, per esempio, una o più porte di uno switch in modo da considerarle parte di un stessa rete virtuale alla quale possono essere aggiunte porte di altri switch.

<aside> 💡 A ogni host della LAN può essere assegnato un numero identificativo (VLAN ID) per identificare la VLAN di appartenenza; host con lo stesso VLAN ID, si comportano come se si trovassero nella stessa rete fisica.

</aside>

Una VLAN può essere creata in più modi:

- per **gruppi di porte**: si utilizza l’identificativo della porta; è la modalità più comune ed è tipica delle LAN che utilizzano un indirizzamento dinamico a livello network.
- per **utenti**: tramite l’indirizzo fisico (MAC) dell’host; poco diffusa molto difficile da gestire.
- per **protocolli**: al posto di indirizzi fisici, usa indirizzi logici (come l’indirizzo IP).



### VLAN Trunking

Un metodo per permettere la comunicazione tra host collocati in VLAN diverse è di realizzare tra switch e router, oppure tra switch e switch, un canale comune, detto **trunk**, sul quale far transitare le comunicazioni tra VLAN diverse.

Due tipi di collegamenti nelle reti VLAN:

- **access link**: collegamento che fa parte di una sola VLAN; un computer collegato tramite questo tipo di link diventa parte di un dominio di broadcast e può comunicare solo con gli altri computer di questo dominio.
- **trunk link**: collegamento punto-punto sul quale transita il traffico appartenente a VLAN diverse.

