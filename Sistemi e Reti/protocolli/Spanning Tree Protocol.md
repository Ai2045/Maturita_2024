Le moderne reti locali sono suddivise in parti più piccole, dette **segmenti**, tramite **switch** (o bridge) al fine di isolare il traffico tra i segmenti e raggiungere una maggiore ampiezza di banda.

> Il **dominio di collisione** di una rete è un’area in cui può verificarsi una collisione.

Oltre alle LAN segmentate con switch, è possibile creare segmenti di LAN utilizzando i **router**, ma ****questa soluzione rende più lenta la trasmissione rispetto che con gli switch.

Spesso le reti con switch sono progettate con **percorsi fisici ridondanti** al fine di evitare che il guasto di un cavo o di una porta di un apparato possa portare al blocco delle trasmissioni sulla rete.

> Un **broadcast storm** avviene quando ci sono così tanti frame broadcast in un loop da impegnare tutta la banda disponibile.

Per evitare questi loop gli switch usano un protocollo per la gestione dei collegamenti, denominato **STP** (Spanning Tree Protocol).

<aside> 💡 **STP** è un protocollo per realizzare reti LAN complesse **senza loop**. Con STP si crea un **albero gerarchico** che mantiene ancora disponibili i percorsi alternativi da usare in caso di necessità, quindi si lasciano loop fisici ma si eliminano a livello di topologia logica. STP stabilisce **un solo percorso attivo alla volta** tra due dispositivi della rete per evitare i loop, tuttavia stabilisce collegamenti ridondanti come alternative.

</aside>

![Untitled](https://prod-files-secure.s3.us-west-2.amazonaws.com/9d17744a-5448-4680-a196-fbe1ea7a9950/defa9e98-e0f5-457c-a29b-60f12cbd9a07/Untitled.png)

Ogni switch della LAN invia dei messaggi detti **BPDU** (Bridge Protocol Data Unit), su tutte le porte per conoscere l’esistenza di altri switch e per eleggere un **root bridge** nella rete.

I BPDU contengono informazioni per:

- designare **un solo root switch**
- calcolare il percorso più breve da ogni switch alla root
- eleggere il **designated switch**, che per ogni LAN è lo switch più vicino alla root, attraverso cui passano tutte le comunicazioni della LAN
- scegliere per ogni switch la **root port**, cioè l’interfaccia che dà il miglior percorso verso la root

Le porte che fanno parte dello **Spanning Tree** sono le **designated port**, le altre sono bloccate.

![Untitled](https://prod-files-secure.s3.us-west-2.amazonaws.com/9d17744a-5448-4680-a196-fbe1ea7a9950/19f2f55c-f0ee-4f58-8384-9e5cf6710ee2/Untitled.png)

Ogni porta dello switch in STP si può trovare in uno dei seguenti stati:

- **blocking:** può solo ricevere BPDU
- **listening:** sta determinando i percorsi verso il root bridge
- **learning:** costruisce la tabella di bridging, apprende solo indirizzi fisici
- **forwarding:** invia e riceve dati, può svolgere tutte le funzioni possibili
- **disabled:** disabilitata dall’amministratore