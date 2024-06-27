### RPC (Remote Procedure Call)

  

Consiste nel chiamare una funzione su un server remoto come se fosse locale.

  

**Esempio in Python (usando XML-RPC):**

  

python

Copy

```python
from xmlrpc.client import ServerProxy

# Creazione del proxy per il server RPC
server = ServerProxy('http://localhost:8000/')

# Chiamata al metodo remoto 'somma'
risultato = server.somma(5, 3)

# Stampa del risultato
print(risultato)  # Output: 8
```

  

### Cosa sono i Web Services?

  

Sono sistemi software progettati per l'interazione tra applicazioni su una rete, tipicamente utilizzando protocolli web standard come HTTP. Espongono funzionalità attraverso un'interfaccia ben definita.

  

### API vs. Web Services

  

Tutte le web services espongono un'API (Application Programming Interface), ma non tutte le API sono web services.

  

- **Web Services:** Usano sempre protocolli di rete (come HTTP) per la comunicazione.
- **API:** Possono essere locali (es. API di un sistema operativo) o remote (es. web API).

  

## SOAP (Simple Object Access Protocol)

  

Un protocollo basato su XML per scambiare messaggi strutturati in web services. Più complesso di RPC, ma offre funzionalità avanzate come sicurezza e affidabilità.

  

**Differenze da RPC:**

  

- **Formato Messaggi:** SOAP usa XML, mentre RPC può usare diversi formati.
- **Astrazione:** SOAP offre un'astrazione maggiore rispetto a RPC, nascondendo i dettagli implementativi.
- **Funzionalità:** SOAP supporta funzionalità come WS-Security e WS-ReliableMessaging non presenti in RPC.

  

## RESTful API (Representational State Transfer)

  

Un'architettura per progettare web services leggere e scalabili usando HTTP.

  

**Naming delle Risorse:**

  

- **Nomi:** Usare nomi al plurale per le collezioni e singolari per le risorse individuali (es. `/utenti` per la collezione, `/utenti/123` per un utente specifico).
- **Verbi HTTP:** Utilizzare verbi HTTP appropriati:
    - `GET` (lettura),
    - `POST` (creazione),
    - `PUT` (aggiornamento completo),
    - `PATCH` (aggiornamento parziale),
    - `DELETE` (eliminazione).

  

## Progettazione RESTful API in Node.js (Esempio)

  

javascript

Copy

```python
const express = require('express');
const app = express();

app.get('/utenti', (req, res) => {
  // Logica per ottenere tutti gli utenti
  res.json(utenti);
});

app.post('/utenti', (req, res) => {
  // Logica per creare un nuovo utente
  res.status(201).send('Utente creato');
});

app.listen(3000, () => console.log('Server avviato'));
```

  

## Middleware

  

Un componente software che si interpone tra due applicazioni, gestendo attività come:

  

- **Autenticazione:** Verificare l'identità dell'utente.
- **Autorizzazione:** Controllare le autorizzazioni dell'utente.
- **Logging:** Registrare le richieste e le risposte.
- **Gestione degli errori:** Intercettare e gestire gli errori.

  

**Funzionamento, progettazione e implementazione:** Dipendono dalla specifica tecnologia utilizzata (es. Express.js in Node.js).

  

## Autenticazione e Autorizzazione in RESTful API

  

### JSON Web Token (JWT)

  

Un formato standard aperto per la creazione di token di accesso sicuri. Un JWT è composto da tre parti:

  

1. **Header:** Contiene informazioni sull'algoritmo di firma.
2. **Payload:** Contiene le informazioni dell'utente (claims).
3. **Signature:** Verifica l'autenticità del token.

  

### Protezione JWT

  

- **Shared Secret Key:** Meno sicuro, ma più semplice da implementare.
- **Chiavi Pubblica/Privata (OpenSSL):** Più sicuro, richiede la gestione delle chiavi.