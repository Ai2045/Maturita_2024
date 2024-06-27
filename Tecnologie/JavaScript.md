**JavaScript Sincrono**

  

- **Call Stack:** JavaScript esegue il codice in modo sincrono, ovvero un'istruzione alla volta. La call stack tiene traccia delle funzioni in esecuzione. Ogni volta che una funzione viene chiamata, viene aggiunta alla pila. Quando la funzione termina, viene rimossa dalla pila.
- **Funzioni in JavaScript:** Le funzioni sono blocchi di codice riutilizzabili. In JavaScript, le funzioni sono oggetti di prima classe, il che significa che possono essere passati come argomenti ad altre funzioni, restituiti da altre funzioni e assegnati a variabili.

  

**JavaScript Asincrono**

  

- **Necessità dell'Asincronia:** Operazioni come le richieste di rete o le interazioni con l'utente possono richiedere tempo. Se JavaScript aspettasse il completamento di queste operazioni in modo sincrono, l'intero programma si bloccherebbe.
- **API del Browser e Promise:** Per gestire l'asincronia, JavaScript utilizza:
    - **API del browser (es. setTimeout, XMLHttpRequest, Fetch API):** Forniscono funzionalità asincrone specifiche del browser.
    - **Promise:** Rappresentano il risultato futuro di un'operazione asincrona. Hanno tre stati: _pending_ (in sospeso), _fulfilled_ (completata con successo), _rejected_ (rifiutata).
- **Callback Queue e Job Queue:**
    - **Callback Queue:** Dove vengono inserite le funzioni di callback dopo che un'operazione asincrona è stata completata.
    - **Job Queue (o Microtask Queue):** Ha una priorità superiore alla Callback Queue. Le Promise vengono messe in coda qui per l'esecuzione.
- **Event Loop:** Controlla continuamente la Call Stack e la Callback Queue. Se la Call Stack è vuota, preleverà il primo elemento dalla Callback Queue e lo aggiungerà alla Call Stack per l'esecuzione.

  

**API per l'Asincronia**

  

- **`setTimeout(callback, delay)`:** Esegue la funzione `callback` dopo un ritardo di `delay` millisecondi.
- **`clearTimeout(timeoutID)`:** Annulla l'esecuzione di `setTimeout` identificata da `timeoutID`.
- **`setInterval(callback, delay)`:** Esegue la funzione `callback` ripetutamente ogni `delay` millisecondi.
- **`clearInterval(intervalID)`:** Annulla l'esecuzione di `setInterval` identificata da `intervalID`.

  

**Fetch API**

  

- **Richieste di Rete Moderne:** Fornisce un'interfaccia moderna per effettuare richieste di rete, generalmente più semplice da usare rispetto a `XMLHttpRequest`.
- **Basato su Promise:** Restituisce una Promise che viene risolta con la risposta del server. Questo rende il codice più leggibile e gestibile.

  

**Esempio di Fetch API:**

  

javascript

Copy

```javascript
fetch('https://api.example.com/data')
  .then(response => response.json())
  .then(data => console.log(data))
  .catch(error => console.error('Errore:', error));
```

  

Questo codice effettua una richiesta GET a `https://api.example.com/data`, analizza la risposta come JSON e quindi stampa i dati sulla console. Se si verifica un errore, viene gestito dal blocco `catch`.