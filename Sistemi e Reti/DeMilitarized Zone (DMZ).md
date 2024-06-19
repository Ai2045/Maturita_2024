- La **zona LAN** è il segmento privato e protetto: comprende tutti gli host e i server i cui servizi sono riservati all'uso interno.
- La **zona WAN** è la parte esterna a cui appartengono gli apparati di routing che sostengono il traffico da e per rete locale, Internet e sedi remote dell'azienda.

In molti casi, però, si rende necessaria la creazione di una terza zona.

<aside> 💡 Questa terza zona è detta **DMZ, DeMilitarized Zone**. Si tratta di un'area in cui sia il traffico WAN sia quello LAN sono fortemente limitati e controllati. Tale configurazione viene normalmente utilizzata per permettere ai server posizionati sulla DMZ di fornire servizi all'esterno senza compromettere la sicurezza della rete aziendale interna.

</aside>

Nel caso più comune si colloca nella DMZ la **posta elettronica**; altro caso tipico sono gli **Application Server.** Generalmente in DMZ si installano i server detti **front-end**, a cui corrispondono i relativi **back-end** in LAN.

### Tipi di DMZ

Una DMZ può essere realizzata in due modi:

- **vicolo cieco:** realizzato mediante un firewall con due porte, una verso la LAN e una verso la DMZ, oltre naturalmente alla porta verso la WAN.
- **zona cuscinetto:** creata aggiungendo un secondo firewall. L’**external firewall** separa la rete pubblica dalla DMZ; l’**internal firewall** separa la DMZ dalla zona LAN vera e propria.