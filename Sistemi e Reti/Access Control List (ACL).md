La sintassi della configurazione di un firewall in molti casi è basata su un meccanismo di **lista di controllo degli accessi ACL (Access Control List).** Le ACL possono essere modificabili tramite configurazione esplicita da parte dell’amministratore di sistema o possono variare in base allo stato interno del sistema.

<aside> 💡 Le ACL sono un elenco di istruzioni da applicare alle interfacce di un router allo scopo di gestire il traffico, filtrando i pacchetti in entrata e in uscita.

</aside>

Vantaggi dell’utilizzo delle ACL:

- **fornire un livello di base di sicurezza**: si può, per esempio, restringere gli accessi a una determinata rete o sottorete.
- **limitare il traffico e aumentare le performance della rete**: si può decidere che alcuni pacchetti vengano processati prima di altri.
- **decidere quale tipo di traffico può essere trasmesso**.

Le ACL vengono processate dal router in maniera sequenziale in base all’ordine in cui sono state inserite le varie clausole. Appena un pacchetto soddisfa una delle condizioni, la valutazione si interrompe e il resto delle ACL non viene considerato. Se il pacchetto non soddisfa nessuna delle condizioni viene scartato (si considera che alla fine di una ACL non vuota ci sia l’istruzione **deny all** ovvero **nega tutto**).

> L’ordine in cui vengono scritte le ACL è importante: essendo eseguite in sequenza, è necessario inserire le condizioni più restrittive all’inizio.

💡 Le ACL possono essere standard, **Standard ACL**, oppure estese, **Extended ACL**. **Standard ACL**: specificano delle limitazioni ai pacchetti guardando esclusivamente l’indirizzo della sorgente e vanno posizionate sull’interfaccia del router il più possibile vicino alla destinazione finale. **Extended ACL**: pongono limitazioni ai pacchetti in base a molte specifiche, come il protocollo utilizzato, l’indirizzo di sorgente, l’indirizzo di destinazione e la porta a cui è indirizzato il pacchetto.

