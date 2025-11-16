# **librFlex**

**Autore:** Diego D'Ortenzio

**Descrizione:**
Una piattaforma digitale dove i lettori possono **acquistare insieme i libri**, dividendo la spesa in modo semplice e trasparente. Ogni utente può poi **leggere il libro a turno**, lasciando recensioni non solo sull’opera, ma anche sugli altri lettori con cui ha condiviso l’acquisto.
Un modo innovativo, collaborativo e sostenibile di accedere alla lettura: **meno costi, più condivisione, più scoperta**.

> ✨ *Niente abbonamenti, niente vincoli: solo libri, persone e storie che si incontrano.*

---

## **Problema**

> L’eccessivo costo dell’acquisto di libri, sia in versione online che in versione fisica.

---

## **Target**

Lettori appassionati che vogliono leggere **ovunque**, senza pesi e a un prezzo conveniente.

---

## **Competitors**

*(vedi tabella “Competitors” per dettagli)*

* Kobo Plus
* Kindle Unlimited
* Bookelot
* Anobii

| 🧩 **Caratteristica** | ⭐ **Importanza** | 📚 **LibrFlex (P.)** | 📘 **Kobo Plus** | 📗 **Kindle Unlimited** | 📙 **Bookelot** | 💬 **Anobii** |
|------------------------|------------------|----------------------|------------------|--------------------------|----------------|---------------|
| **Acquisto condiviso** | 🔥 High | 🟢 **Disponibile**<br/>Gruppi di conoscenti o sconosciuti con recensioni tra co-lettori | 🔴 Non disponibile | 🔴 Non disponibile | 🔴 Non disponibile | 🔴 Solo catalogazione (nessun accesso diretto) |
| **Accesso illimitato a migliaia di libri** | 🔥 High | 🟢 Tutti i libri acquistati in gruppo, lettura a turno | 🟢 Ampio catalogo selezionato | 🟠 Solo parte del catalogo incluso | 🔴 Pochi libri a catalogo | 🔴 Solo catalogazione |
| **Prezzo basso e accessibile** | 🔥 High | 🟢 Costo condiviso (molto ridotto) | 🟢 €9.99/mese | 🟠 €13.99/mese | 🔴 Prezzo variabile e crescente | 🟢 Gratis (funzionalità social) |
| **Aggiornamento mensile del catalogo** | 🔥 High | 🟢 Nuovi titoli mensili (classici + novità) | 🟢 Aggiornato frequentemente | 🟢 Aggiornamenti regolari | 🔴 Catalogo statico | 🟠 Dipende dagli utenti |
| **Suggerimenti in base ai propri gusti** | 🔥 High | 🟢 Basati su recensioni e interazioni | 🔴 Limitato | 🟠 Non sempre accurato | 🔴 Assente | 🟢 Social e partecipativo |
| **Nessuna pubblicità** | 🔥 High | 🟢 Nessuna pubblicità | 🟢 Nessuna | 🟢 Nessuna | 🟢 Nessuna | 🟢 Nessuna |
| **Disponibilità multipiattaforma**<br/>(web, mobile, tablet, e-reader) | 🔥 High | 🟢 Tutti i dispositivi | 🟢 Ottimizzato per eReader Kobo | 🟢 App mobile e Kindle | 🔴 Limitato | 🟢 Web e mobile |
| **Possibilità di download offline** | 🟡 Moderate | 🟢 Lettura temporanea protetta | 🟢 Disponibile | 🟢 Disponibile | 🔴 Non previsto | 🔴 Non prevista |
| **Collaborazioni con editori indipendenti o minori** | 🟢 Low | 🟢 Ampio spazio agli indipendenti | 🔴 Pochi | 🔴 Limitati | 🔴 Assenti | 🟢 Supporta piccoli editori |
| **Funzionalità social**<br/>(recensioni, interazioni tra utenti) | 🔥 High | 🟢 Recensioni su libri e co-acquirenti | 🟠 Limitate | 🟠 Solo recensioni libri | 🔴 Nessuna | 🟢 Core del servizio (social reading) |


---

## **Tagline**

> “Una storia letta da molti, vissuta da ciascuno. Ridefinisci il modo di leggere, Insieme.”

---

## **Tecnologie**

* **Frontend:** Next.js (React) + Tailwind CSS → interfaccia moderna, veloce e responsiva
* **Backend:** Node.js con NestJS o Express → API REST e logica applicativa
* **Database:** PostgreSQL (principale) + Redis (cache e sessioni)
* **Autenticazione:** OAuth 2.0 / JWT con Auth0 o Firebase Auth
* **Pagamenti:** Stripe (Stripe Connect per gestione quote e split payment)
* **Storage e distribuzione:** Amazon S3 + Cloudflare CDN
* **Antipirataggio:** DRM (Adobe / Google Widevine) + watermark dinamico + accesso via streaming protetto
* **Hosting e cloud:** AWS o Google Cloud (scalabilità e affidabilità)
* **Sicurezza:** HTTPS, crittografia AES, bcrypt per password, 2FA opzionale
* **Monitoraggio e analytics:** Sentry (errori) + Google Analytics o Mixpanel (uso e engagement)
* **CI/CD e versioning:** GitHub + GitHub Actions per deployment automatici

---

## **Analisi dei Requisiti**

### **Descrizione dei requisiti**

La piattaforma di lettura condivisa è un servizio online che consente agli utenti di **acquistare insieme libri digitali**, suddividendo il costo tra più partecipanti, conosciuti o sconosciuti, in modo semplice e trasparente.
L’accesso avviene tramite una **piattaforma web** o **app dedicata**, dove gli utenti possono creare un profilo personale, gestire la propria libreria condivisa e partecipare a gruppi di lettura (funzionale).

Gli utenti possono **registrarsi**, effettuare il **login sicuro** e recuperare la password in caso di smarrimento (funzionale). Ogni utente può **avviare o unirsi a un gruppo di acquisto**, visualizzando la quota di partecipazione e le regole di lettura a turno (funzionale).
Una volta completato l’acquisto condiviso, il libro viene reso disponibile in modalità **a lettura sequenziale o competitiva**, con **sistema di coda** gestito automaticamente dalla piattaforma (funzionale).

Il servizio consente inoltre di **lasciare recensioni e valutazioni** non solo sui libri, ma anche sui **co-acquirenti**, favorendo un sistema di reputazione tra lettori (funzionale).
Gli utenti possono **ricercare libri** per titolo, autore, genere o popolarità, **filtrare per disponibilità o prezzo condiviso**, e accedere a un **lettore digitale integrato** per la lettura sicura dei testi (funzionale).

I contenuti vengono aggiornati regolarmente grazie agli **accordi con editori e autori**, con l’aggiunta di nuovi titoli al catalogo ogni mese (funzionale). I progressi di lettura sono **sincronizzati** su tutti i dispositivi collegati allo stesso account (funzionale).

L’interfaccia deve essere **semplice, chiara e intuitiva**, adatta anche a utenti con scarsa esperienza tecnologica (non funzionale). Il sistema deve garantire **tempi di caricamento rapidi**, **alta disponibilità** e **compatibilità multipiattaforma** (non funzionale).
La piattaforma deve essere **scalabile**, per gestire un numero crescente di utenti, gruppi e libri senza compromettere le prestazioni (non funzionale), e il codice deve essere **modulare e manutenibile** per favorire aggiornamenti futuri (non funzionale). L’esperienza utente deve essere **completamente priva di pubblicità** (non funzionale).

Tutti i libri devono rispettare i **diritti d’autore** e le **licenze editoriali** previste dagli accordi (di dominio).
Il modello economico si basa sull’**acquisto condiviso dei libri**, senza abbonamenti, con pagamento sicuro e ripartizione automatica della spesa (di dominio).
Per proteggere i contenuti, il sistema integra **tecnologie DRM** e **watermark dinamici**, impedendo la copia o distribuzione non autorizzata (di dominio), nel rispetto degli **standard di accessibilità (WCAG)** e delle **normative internazionali sulla privacy** (di dominio).

---

### **Elenco Riassuntivo Requisiti**

#### Funzionali

* Registrazione, login e recupero password
* Creazione e gestione del profilo utente
* Avvio o partecipazione a gruppi di acquisto condiviso
* Gestione delle quote di pagamento
* Lettura a turno o competitiva tramite lettore digitale integrato
* Ricerca e filtro libri per titolo, autore, genere, prezzo o popolarità
* Inserimento automatico di nuovi titoli nel catalogo
* Recensioni e valutazioni su libri e co-acquirenti
* Sincronizzazione progressi di lettura su più dispositivi

#### Non Funzionali

* Interfaccia chiara, accessibile e intuitiva
* Caricamento rapido e tempi di risposta ridotti
* Alta disponibilità e affidabilità del servizio
* Compatibilità multi-piattaforma (web, mobile, tablet, e-reader)
* Scalabilità per gestire un numero crescente di utenti e libri
* Codice modulare e facilmente manutenibile
* Esperienza d’uso priva di pubblicità

#### Di Dominio

* Rispetto di diritti d’autore e licenze digitali
* Accordi continuativi con editori e autori per aggiornare il catalogo
* Modello economico basato sull’acquisto condiviso (no abbonamento)
* Integrazione di DRM e watermarking per protezione antipirateria
* Conformità agli standard WCAG e alle normative sulla privacy (GDPR)

---

#### **Use Case UML**

[![Static Badge]( https://img.shields.io/badge/Clicca_Qui-Per_UML-blue)](https://yuml.me/dortenzio/es1.svg)
<img width="962" height="828" alt="image" src="https://github.com/user-attachments/assets/d8769c35-e8c8-4be3-afb8-98eb14cf4eda" />


