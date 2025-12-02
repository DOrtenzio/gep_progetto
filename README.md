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

# **Analisi dei Requisiti**

## **Descrizione dei requisiti**

La piattaforma di lettura condivisa è un servizio online che consente agli utenti di **registrarsi**, accedere tramite **login sicuro** e recuperare la password in caso di smarrimento. Ogni utente autenticato può gestire il proprio **profilo personale** e utilizzare le funzionalità principali del sistema (funzionale).

Gli utenti possono **cercare libri**, consultarne i dettagli, leggere tramite il **lettore digitale integrato** e avere la **sincronizzazione automatica delle letture** su tutti i dispositivi (funzionale). La sincronizzazione viene attivata automaticamente durante l’attività di lettura.
La piattaforma permette inoltre di **creare gruppi di acquisto condiviso**, scegliendo tra **gruppi pubblici** (aperti a tutti) o **gruppi privati** (accesso su invito o approvazione). Ogni utente può anche **partecipare ai gruppi** creati da altri, visualizzando le condizioni e la **quota di partecipazione** (funzionale).

Una volta definita la quota, il sistema attiva la procedura di **checkout dei pagamenti**, integrata con il **Sistema Bancario**, responsabile dell’autorizzazione e validazione delle transazioni (funzionale). Solo dopo il pagamento avvenuto correttamente il libro digitale viene reso disponibile ai partecipanti.

Gli utenti possono inoltre **recensire i libri** letti e **recensire i gruppi** ai quali hanno partecipato, contribuendo al sistema di reputazione interno (funzionale).

Gli amministratori accedono tramite un **login con privilegi elevati**, che consente loro la **gestione del catalogo**, comprendente l’aggiunta, aggiornamento o rimozione dei libri. Ogni operazione sul catalogo richiede la **verifica dei diritti editoriali** e delle licenze tramite l’attore esterno **Editore** (funzionale).

L’interfaccia deve essere **semplice e intuitiva**, pensata per utenti di qualsiasi livello di competenza tecnologica (non funzionale). La piattaforma deve garantire **tempi di risposta rapidi**, disponibilità continua e **compatibilità multipiattaforma** (non funzionale).
Il sistema deve essere **scalabile**, strutturato in modo modulare e facilmente manutenibile (non funzionale), senza contenuti pubblicitari (non funzionale).
Tutti i libri sono soggetti al rispetto dei **diritti d’autore** e delle licenze editoriali formalizzate con gli editori (di dominio). Il modello economico si basa sull’**acquisto condiviso**, con ripartizione automatica dei costi e **pagamenti sicuri** tramite integrazione bancaria (di dominio).
La protezione dei contenuti è garantita tramite **DRM**, **watermark dinamici**, e il pieno rispetto delle norme sulla privacy e degli standard di accessibilità (WCAG) (di dominio).

---

## **Elenco Riassuntivo Requisiti**

### **Funzionali**

* Registrazione, login e recupero password
* Gestione del profilo utente
* Ricerca dei libri nel catalogo
* Lettura tramite lettore digitale e sincronizzazione dei progressi
* Creazione di gruppi di acquisto (pubblici o privati)
* Partecipazione ai gruppi di acquisto
* Gestione delle quote di partecipazione
* Checkout dei pagamenti con integrazione al sistema bancario
* Recensioni su libri e gruppi
* Accesso sicuro per le funzionalità d'amministrazione
* Gestione del catalogo da parte dell’amministratore
* Verifica dei diritti editoriali tramite editore esterno

#### **User Story**

| **Attore (Come...)**      | **Requisito / Azione (Voglio...)**         | **Beneficio (In modo da...)**                         |
| ------------------------- | ------------------------------------------ | ----------------------------------------------------- |
| Utente                    | registrarmi alla piattaforma               | creare un account e accedere ai servizi               |
| Utente                    | effettuare il login                        | accedere al mio profilo e alle funzionalità riservate |
| Utente                    | recuperare la password                     | ripristinare l’accesso in caso di smarrimento         |
| Utente                    | gestire il mio profilo                     | aggiornare i dati personali e le configurazioni       |
| Utente                    | cercare un libro nel catalogo              | trovarlo rapidamente tramite filtri e criteri         |
| Utente                    | leggere un libro tramite lettore integrato | accedere comodamente ai contenuti digitali            |
| Utente                    | sincronizzare i miei progressi di lettura  | mantenerli aggiornati su tutti i dispositivi          |
| Utente                    | creare un gruppo di acquisto               | condividere l’acquisto e la lettura con altri utenti  |
| Utente                    | creare un gruppo pubblico                  | permettere a chiunque di partecipare                  |
| Utente                    | creare un gruppo privato                   | limitare l’accesso agli utenti invitati               |
| Utente                    | partecipare a un gruppo di acquisto        | condividere costi e lettura con altri utenti          |
| Utente                    | visualizzare la quota da pagare            | sapere il costo della mia partecipazione              |
| Utente → Sistema Bancario | effettuare il checkout del pagamento       | completare la transazione in modo sicuro              |
| Utente                    | recensire un libro                         | condividere giudizi e valutazioni                     |
| Utente                    | recensire un gruppo                        | valutare l’esperienza di partecipazione               |
| Amministratore            | effettuare il login con privilegi          | accedere alle funzioni amministrative                 |
| Amministratore            | gestire il catalogo dei libri              | aggiungere, modificare o rimuovere contenuti          |
| Amministratore → Editore  | verificare i diritti dei contenuti         | confermare licenze e autorizzazioni editoriali        |


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

## **Use Case UML**

[![Static Badge]( https://img.shields.io/badge/Clicca_Qui-Per_UML-blue)](https://yuml.me/dortenzio/es1.svg)
<img width="990" height="912" alt="image" src="https://github.com/user-attachments/assets/39e7918c-bea1-42ff-824d-61a6e7186666" />

---

## **Prototipo Basato Sui Requisiti**

[![Static Badge]( https://img.shields.io/badge/Clicca_Qui-Per_Prototipo-blue)](https://librflex.lovable.app/)


