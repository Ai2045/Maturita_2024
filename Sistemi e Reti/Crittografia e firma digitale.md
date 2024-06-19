

 💡 La **crittografia** è un insieme di procedure ideate allo scopo di nascondere il significato di un messaggio a tutti tranne al legittimo destinatario

Alla base delle principali tecniche di crittografia c’è un **cifrario:** in un cifrario ogni carattere del testo da cifrare viene trasformato in un altro carattere.


Per cifrare un testo occorrono due cose:

- un **algoritmo di cifratura** (pubblico)
- una **chiave** (segreta)

 💡 Il **testo in chiaro** è il messaggio originale, non modificato e quindi comprensibile da chiunque lo intercetti se trasmesso integro. Il **testo cifrato** è il messaggio che viene trasmesso sulla rete, modificato (ma reversibile) allo scopo di renderlo incomprensibile. La **chiave** è una sequenza di bit di lunghezza finita, generata in modo casuale e impiegata come ingresso di un algoritmo crittografico, avente un’uscita dipendente da essa.



### Classificazione dei sistemi crittografici

I sistemi crittografici possono essere classificati in vario modo, in base al:

1. Tipo di operazioni usate per trasformare il testo in chiaro al testo cifrato: - **a sostituzione:** ogni elemento del testo in chiaro è trasformato in un altro elemento ****- a trasposizione:** gli elementi del testo in chiaro sono riorganizzati
2. Modo in cui il testo in chiaro è elaborato: - **a blocchi:** il testo viene suddiviso in blocchi di N bit (lunghezza fissa) e ogni blocco viene elaborato in modo indipendente dagli altri **- a flusso:** elabora un quantitativo di bit variabile, senza una lunghezza predefinita
3. Numero di chiavi (distinte) utilizzate: - **a chiave simmetrica:** le chiavi del mittente e del destinatario sono identiche, quindi si ha una sola chiave - **a chiave asimmetrica:** le chiavi sono diverse, una pubblica e una privata per ogni soggetto

### Crittografia a chiave simmetrica

La crittografia a chiave simmetrica (o a chiave singola) si basa sull’utilizzo di una sola chiave, usata dal mittente per cifrare e dal destinatario per decifrare.

Un esempio di crittografia a chiave simmetrica, che ha anche un algoritmo perfettamente simmetrico, è il **metodo XOR.**

### Crittografia a chiave asimmetrica

La crittografia a chiave asimmetrica nasce per risolvere il problema della **distribuzione sicura delle chiavi.** Essa utilizza due chiavi per ciascun soggetto, una **privata**, nota solo al soggetto, l’altra **pubblica**, distribuita a tutti i possibili soggetti con cui il primo vuole comunicare in sicurezza.

A seconda di come vengono impiegate queste coppie di chiavi abbiamo 3 diversi possibili utilizzi:

- Assicurare la riservatezza del dialogo: **confidenzialità**
- Garantire l’identità del mittente: **autenticazione**
- Garantire la riservatezza della comunicazione, l’identità del mittente e l’integrità del messaggio: **confidenzialità, autenticazione** e **integrità**


> La caratteristica vincente della crittografia a chiave asimmetrica è il fatto di non dover condividere la stessa chiave (quella privata) con nessuno, di non doverla cosi distribuire.


### La firma digitale e gli enti certificatori

 💡 La firma digitale, equivalente elettronico della tradizionale firma autografa su carta, è associata stabilmente al documento elettronico sulla quale è apposta e ne attesta con certezza l’**integrità**, l’**autenticità** e la **non ripudiabilità.**


La firma digitale è basata su un sistema a chiavi crittografiche asimmetriche, utilizza un certificato digitale rilasciato da un **ente certificatore** con specifiche capacità professionali garantite dallo Stato.

💡 Il file firmato digitalmente deve essere certificato dall’ente certificatore **prima** dell’invio. Attraverso il certificato il destinatario otterrà la chiave pubblica sicura che gli permetterà di verificate l’identità del mittente e l’integrità del documento.


Attualmente il nostro ordinamento prevede l’utilizzo di 3 formati per produrre file firmati digitalmente:

- **pkcs#7:** è il primo formato in uso dal 1999 ed è quello che le Pubbliche Amministrazioni sono obbligate ad accettare
- **PDF**
- **XML:** più diffuso nel settore bancario e sanitario

Generare una firma digitale richiede la disponibilità del **kit di firma digitale,** composto dal dispositivo sicuro (smart card o token USB) e dal software di firma in grado di utilizzare lo specifico dispositivo di cui si è dotati.

 💡 L’algoritmo di _apposizione_ della firma digitale prevede la creazione di un’**impronta** attraverso la **funzione di hash.**


Tecnicamente, la **firma digitale non è altro che l’impronta crittografata** con la chiave privata del mittente validata dall’ente di certificazione.

Oltre alla firma digitale, ci sono altri servizi che si basano sugli enti certificatori:

- la **PEC** (Posta Elettronica Certificata)
- lo **SPID** (Sistema Pubblico di Identità Digitale)
- la **CNS** (Carta Nazionale dei Servizi)

---