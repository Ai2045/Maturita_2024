**Il server RADIUS (Remote Authentication Dial-In User Service) è un protocollo di rete che fornisce un servizio centralizzato di autenticazione, autorizzazione e registrazione per gli utenti che si connettono e utilizzano una rete. Questo protocollo viene comunemente utilizzato per autenticare gli utenti in reti wireless e in alcune VPN (Virtual Private Network).**


## Storia del protocollo RADIUS:

**Il protocollo RADIUS è stato originariamente sviluppato nel 1991 da Livingston Enterprises per i loro server di networking. Successivamente, è diventato uno standard industriale e nel 1997 è stato pubblicato come RFC (Request for Comments) 2058 e 2059, ora sostituiti dagli aggiornamenti RFC 2865 e 2866.**

**Col tempo, la popolarità di RADIUS è cresciuta grazie alla sua flessibilità e alla capacità di supportare una vasta gamma di tipi di autenticazione e dispositivi di rete. È inoltre noto per la sua scalabilità, in quanto può essere utilizzato in piccole imprese così come in grandi organizzazioni con migliaia di utenti.**

### come funziona in dettaglio:

1. **Quando un client cerca di connettersi a una rete, il server RADIUS riceve una richiesta di autenticazione da quel client.**
2. **Il server RADIUS quindi verifica le credenziali fornite dal client. Queste credenziali possono includere un nome utente e una password, o possono essere più complesse, come certificati digitali o token di sicurezza.**
3. **Se le credenziali del client sono valide, il server RADIUS autorizza il client ad accedere alla rete. A volte, questo può anche includere l'assegnazione di specifici diritti o privilegi di rete al client, a seconda delle impostazioni di sicurezza della rete.**
4. **Se le credenziali non sono valide, il server RADIUS rifiuta la richiesta del client e non gli consente di accedere alla rete.**

## Componenti di un sistema RADIUS:


- **Client RADIUS: Il client RADIUS è un componente della rete che richiede servizi di autenticazione, autorizzazione e contabilità dal server RADIUS. Questi clienti possono essere router, switch, firewall, access point wireless, o qualsiasi altro dispositivo che necessita di controllare l'accesso degli utenti alla rete. Quando un utente cerca di connettersi alla rete, il client RADIUS invia le informazioni relative all'utente (come username e password) al server RADIUS per l'autenticazione.**
- **Server RADIUS: Il server RADIUS è il cuore del sistema RADIUS. Questo server riceve le richieste dal client RADIUS e le processa secondo i suoi criteri configurati. Se l'utente viene autenticato con successo, il server RADIUS comunica al client l'autorizzazione dell'accesso insieme agli eventuali attributi specifici (come un indirizzo IP o le autorizzazioni VLAN) e gestisce la registrazione delle sessioni utente per la contabilità.**
- **Proxy RADIUS: Un proxy RADIUS funziona come intermediario nelle comunicazioni tra client RADIUS e server RADIUS. È utilizzato quando le richieste devono essere inoltrate ad altri server RADIUS, per esempio, in configurazioni più complesse dove le richieste possono essere distribuite tra diversi server, o quando devono essere instradate attraverso diverse reti o domini amministrativi.**

## Metodi di autenticazione supportati:

- **PAP (Password Authentication Protocol): Un metodo semplice che manda la username e la password in chiaro (non criptato), protetto dal campo autenticatore nel pacchetto RADIUS.**
- **CHAP (Challenge-Handshake Authentication Protocol): Più sicuro del PAP, usa un handshake a tre vie e una challenge per verificare l'identità dell'utente senza trasmettere la password in chiaro.**
- **MS-CHAP (Microsoft Challenge-Handshake Authentication Protocol): Una versione di CHAP implementata da Microsoft che offre funzionalità aggiuntive e maggiore supporto per i sistemi operativi Windows.**
- **EAP (Extensible Authentication Protocol): Un framework che permette di utilizzare vari metodi di autenticazione su reti di trasporto come IP. EAP è flessibile e supportato da una vasta gamma di metodi di autenticazione, tra cui smart card, token OTP, certificati digitali, e molto altro. _EAP-OTP (One-Time Password), EAP-GTC (Generic Token Card), EAP-TLS (Transport Layer Security)_**

## RADIUS vs AD vs LDAP

1. **Active Directory (AD), che è un servizio di directory di Microsoft per la gestione delle identità.**
    
2. **LDAP (Lightweight Directory Access Protocol), che è un protocollo aperto e standard per accedere a servizi di directory.**
    
    - **Vantaggi di RADIUS**
        - **È specificamente progettato per autenticare l'accesso remoto agli utenti, rendendolo ideale per VPN e altri servizi di accesso a distanza.**
        - **Include il supporto per i processi di Accounting (monitoraggio e registrazione) oltre a Autenticazione e Autorizzazione.**
        - **Offre un livello di astrazione che può fornire un unico punto di autenticazione per diversi tipi di accessi, inclusi wired, wireless e VPN.**
        - **Fornisce una maggiore flessibilità nella definizione delle restrizioni e parametri per l'accesso utente rispetto ad LDAP.**
    - **Svantaggi di RADIUS**
        - **Non è un servizio di directory; quindi, mentre AD e LDAP possono memorizzare e organizzare un ampio range di informazioni sugli utenti, RADIUS è focalizzato principalmente sull'autenticazione e sull'accounting.**
        - **Potrebbe essere meno efficiente nel gestire una grande quantità di informazioni sugli utenti rispetto a LDAP o AD, che sono ottimizzati per le operazioni su directory.**
    - **Vantaggi di AD e LDAP**
        - **Sono sia servizi di directory, e possono gestire informazioni dettagliate sugli utenti, inclusi gruppi, permessi e altre impostazioni di sicurezza.**
        - **LDAP è un protocollo standard e aperto, quindi è ben supportato su diverse piattaforme e da diversi fornitori.**
        - **AD, essendo un prodotto Microsoft, integra strettamente con altri prodotti Microsoft e offre una gestione centralizzata degli utenti in ambienti Windows.**
    - **Svantaggi di AD e LDAP**
        - **Per sicurezza, questi sistemi dipendono dalle corrette configurazioni e governance delle politiche di sicurezza.**
        - **Non offrono nativamente i processi di accounting come RADIUS, sebbene possano essere integrati con altri sistemi che lo fanno.**
    
    ## APPLICAZIONI DEL RADIUS
    
    1. **Autenticazione Wi-Fi (802.1X): RADIUS viene comunemente utilizzato in configurazioni Wi-Fi sicure, in particolare quelle che utilizzano l'autenticazione basata su 802.1X. In questo scenario, il server RADIUS funge da intermediario tra gli utenti che tentano di connettersi alla rete e il database di autenticazione, assicurando che solo gli utenti autorizzati accedano al Wi-Fi.**
    2. **VPN (Virtual Private Networks): Per l'accesso remoto alle risorse di rete aziendali, le VPN spesso si appoggiano su RADIUS per autenticare gli utenti. Quando qualcuno tenta di connettersi alla VPN, le loro credenziali vengono verificate tramite RADIUS, il quale conferma se hanno il diritto di accedere alla rete.**
    3. **Dial-up Access: Anche se meno comune oggi con l'avanzamento della banda larga, il servizio dial-up traffica l'accesso remoto alla rete attraverso una linea telefonica. In questi sistemi, RADIUS può gestire l'autenticazione degli utenti dial-up.**
    4. **Access Control in Reti Aziendali e Università: RADIUS è ampiamente utilizzato per controllare l'accesso a risorse di rete sia in ambienti aziendali che universitari. Attraverso l'implementazione di politiche definite nel server RADIUS, le organizzazioni possono gestire dettagliatamente chi ha accesso a quali servizi di rete e in che misura.**
    5. **Gestione delle Sessioni di Rete: Oltre a consentire o negare l'accesso, RADIUS supporta anche il monitoraggio e la gestione delle sessioni di rete. Ciò permette alle organizzazioni di tenere traccia dell'uso delle risorse, addebitare sui servizi a pagamento basati su utilizzo, e identificare e risolvere i problemi di rete.**
    6. **Enforcement delle Politiche di Sicurezza: Con RADIUS, le aziende e le istituzioni educative possono imporre le loro politiche di sicurezza di rete centralmente. Ciò include la gestione delle credenziali degli utenti, la definizione di diritti e restrizioni di accesso, nonché l'attuazione di varie misure di sicurezza come la multifactor authentication (MFA).**

## LEGISLAZIONE E NORMATIVE

- **GDPR (General Data Protection Regulation) nell'Unione Europea**
    
    **Probabilmente la legislazione sulla privacy dei dati più discussa al mondo, il GDPR impone rigorose regole sul trattamento dei dati personali degli individui all'interno dell'UE.**
    
    > **Per le organizzazioni che utilizzano RADIUS, ciò significa garantire che le informazioni degli utenti siano raccolte, gestite, conservate e distrutte in maniera conforme alle prescrizioni del GDPR. Questo include l'ottenimento del consenso per la raccolta di dati, la fornitura di trasparenza su come vengono utilizzati i dati e l'implementazione di misure di sicurezza appropriate.**
    
    ### **Articolo 5 del GDPR ([https://gdprinfo.eu/it/it-article-5](https://gdprinfo.eu/it/it-article-5)):**
    
    1. **Liceità, correttezza e trasparenza: La gestione dei dati attraverso RADIUS dovrebbe essere conforme alle leggi e alle politiche di privacy. Questo include informare gli utenti sul trattamento dei loro dati personali che può avvenire tramite l'autenticazione RADIUS.**
    2. **Limitazione della finalità: I dati trattati attraverso RADIUS dovrebbero essere raccolti solo per le finalità esplicite di autenticazione, autorizzazione e accounting, e non dovrebbero essere usati per finalità incompatibili con quelle originarie.**
    3. **Minimizzazione dei dati: Con RADIUS, solo le informazioni necessarie per il processo di autenticazione e autorizzazione dovrebbero essere raccolte e memorizzate.**
    4. **Esattezza: Le informazioni personali gestite da RADIUS devono essere mantenute accurate e aggiornate per evitare identificazioni errate e problemi di sicurezza.**
    5. **Limitazione della conservazione: I log e altri dati conservati da RADIUS devono essere mantenuti solo per il periodo necessario per le finalità per cui sono stati raccolti, in linea con i requisiti di conservazione dei dati stabiliti dal GDPR.**
    6. **Integrità e riservatezza: Le misure di sicurezza per proteggere i dati personali gestiti da RADIUS sono cruciali e devono essere adeguate per prevenire accessi non autorizzati o compromissioni dei dati.**
    7. **Responsabilità: Il titolare del trattamento dei dati che utilizza RADIUS deve assicurare e poter dimostrare che tutte le operazioni svolte con il protocollo RADIUS sono conformi ai principi del GDPR.**

## Best Practices per la sicurezza

1. **Controllo di Accesso: Limitare l'accesso al server RADIUS a dispositivi e utenti fidati, utilizzando liste di controllo degli accessi e regole di firewall.**
2. **Sicurezza Fisica del Server: Proteggere fisicamente il server RADIUS da accessi non autorizzati, ponendolo in un ambiente sicuro.**
3. **Gestione delle Password: Impostare politiche per l'utilizzo di password forti e cambiarle regolarmente.**
4. **Backup e Ripristino: Eseguire backup regolari delle configurazioni e dei dati del server RADIUS e garantire la disponibilità di un piano di ripristino in caso di emergenza.**
5. **Aggiornamenti e Patch: Mantenere il software del server RADIUS aggiornato con le ultime patch di sicurezza e aggiornamenti.**