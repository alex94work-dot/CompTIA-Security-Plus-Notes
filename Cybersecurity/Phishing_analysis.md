# 🛡️ Investigazione Phishing: Analisi di un Attacco Reale

Questo progetto documenta un'analisi forense completa effettuata su una email di phishing ricevuta su un account universitario. L'obiettivo è stato ricostruire la catena dell'attacco partendo dalla mail fino al sito finale dell'hacker, utilizzando **Kali Linux**.

---

## 📑 Sintesi dell'Indagine (Step-by-Step)

### 1. Analisi dell'Header (Il "DNA" della mail)
Prima di tutto, ho esaminato le intestazioni tecniche della mail per verificarne l'autenticità.
* **Risultato:** I controlli **SPF e DKIM** erano validi (`PASS`).
* **Conclusione:** La mail non è un falso tecnico, ma proviene da un account reale della Sapienza (Google/Gmail) che è stato compromesso (**Account Takeover**). L'hacker ha rubato l'account a uno studente per sfruttarne la reputazione.

### 2. Verifica dell'Infrastruttura (`whois`)
Ho estratto l'indirizzo IP del mittente e ho interrogato i registri mondiali tramite il terminale di Kali.
* **Comando:** `whois 209.85.128.0`
* **Risultato:** Il server appartiene ufficialmente a **Google LLC**. Questo ha confermato definitivamente che l'attacco partiva da una casella Gmail legittima.

### 3. Analisi Dinamica del Link (Payload)
Ho estratto il link contenuto nel pulsante della mail senza cliccarlo: `pagmentomultasteamw728ae.myclickfunnels.com`.
* **Test 1 (Ricercatore):** Usando il comando `curl` standard, il sito ha risposto con un errore **403 Forbidden**. Sembrava protetto o inattivo.
* **Test 2 (Camuffamento):** Ho ripetuto il comando "travestendomi" da utente normale (cambiando lo *User-Agent* in Chrome/Windows).
* **Risultato:** Il sito ha risposto con **302 Found** (Redirect).

### 4. Scoperta della Destinazione Finale
Grazie al test di camuffamento, ho scoperto che il sito non era affatto chiuso. L'hacker utilizzava una tecnica di **Evasione (Cloaking)**:
* Se il visitatore è un analista (Kali), viene bloccato.
* Se il visitatore è una vittima (Windows/Chrome), viene spedito sul vero sito di phishing: `https://rarivascpa.com/-/Multe/Pago-PA/pa`.

---

## 🏁 Verdetto Finale

L'attacco è classificato come **Phishing Avanzato**. L'attaccante ha utilizzato una strategia a "matrioska":
1. **Account Compromesso:** Per superare i filtri antispam.
2. **Sito Ponte (ClickFunnels):** Per filtrare ed evitare i controlli degli esperti di sicurezza.
3. **Sito Target (Hackerato):** Un dominio reale (`rarivascpa.com`) compromesso per ospitare la finta pagina di pagamento PagoPA e rubare dati finanziari.

**Stato della minaccia:** Mitigata parzialmente (segnalata ai provider), ma l'infrastruttura dell'hacker è ancora parzialmente attiva.

---
*Analisi condotta da Alessandro - Laboratorio Cybersecurity*
