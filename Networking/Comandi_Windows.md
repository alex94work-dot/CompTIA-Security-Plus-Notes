##  Comandi di Rete Essenziali (Windows)

* **`cmd`**
    Apre il Prompt dei comandi, ovvero l'interfaccia a riga di comando (CLI - Command Line Interface) di Windows.

* **`ipconfig /all`**
    Fornisce un output dettagliato della configurazione di rete. Oltre all'indirizzo IP logico, mostra il **MAC address** (indirizzo fisico), il Gateway predefinito e la configurazione DNS di tutte le interfacce di rete collegate alla macchina.

* **`ping`**
    Serve a verificare se due host sono connessi o raggiungibili. 
    - Utilizza il protocollo **ICMP** (host1 invia segnale *echorequest* ad host2 che invia indietro segnale *echoreplay*.
    - Indica la **latenza** (espressa in ms): ovvero quanto tempo impiega il segnale ad andare e tornare.
    - **Security Note:** Una latenza molto alta può indicare che il sistema è sotto attacco o congestionato da malware.
