## Il modello **OSI** 

Modello teorico che descrive la struttura della rete. Esso è strutturato in vari livelli, precisamente 7 e si leggono dall'alto verso il basso.

7- **Application:** connessione tra due applicazioni, HTTPS, DNS, FTP

6- **Presentation:** crittografia e traduzione dati (TLS, SSL)

5- **Session:**   Mantiene aperta la sessione tra due dispositivi

4- **Transport:** Qua avviene il trasporto dei dati e la correzione (protocolli TCP ed UDP)

3- **Network:**  Indirizzamento logico e instradamento (indirizzo IP, Router)

2- **Datalink:** Indirizzamento fisico (indirizzo MAC, Switch)

1- **Physical:**  Trasmissione fisica dei bit 

## Three-Way HandShake ##
Avviene al livello 4-*Transport* è un meccanismo utilizzato da TCP per instaurare una connessione affidabile tra due host. Host1 manda un segnale *SYN* 
e attende da Host2 una risposta *SYN/ACK*. Dopodichè Host1 rimanda un segnale ACK per chiudere il cerchio e stabilire la connessione.
