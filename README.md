# 🔄 Flusso Automatico: Generazione Contenuti e Keyword Extraction (Ciclo Chiuso)

Un workflow di **Content Automation Avanzato**, costruito con **n8n**, che dimostra un ciclo di feedback chiuso. Legge le idee di contenuto da Google Sheets, utilizza Gemini per generare il post e, in un passaggio successivo, ri-analizza il contenuto generato per estrarre le **Parole Chiave** pertinenti. Le Keyword vengono poi scritte automaticamente nel foglio Google iniziale, arricchendo il database.

## Caratteristiche & Funzionalità

* **Ciclo di Feedback Chiuso:** 🔁 La caratteristica più avanzata: il flusso non si limita a generare e pubblicare, ma arricchisce la fonte dati iniziale con informazioni derivanti dall'analisi del contenuto appena creato.
* **AI Multi-Tasking:** 🧠 Gemini viene utilizzato in due modi chiave all'interno del flusso:
    1.  **Generazione Contenuti:** Creazione del Titolo e del Contenuto del post (come nel Flusso 7).
    2.  **Analisi Contenuti:** Estrazione delle 5-10 **Parole Chiave** più rilevanti dal testo generato.
* **Aggiornamento Database Automatico:** 📊 Utilizza il nodo **Google Sheets (Append row)** per aggiungere o aggiornare le informazioni (incluse le Parole Chiave appena estratte) nel database di Google Sheets.
* **Pubblicazione Multi-Destinazione:** 🚀 Dopo la generazione e l'analisi, il post viene creato come bozza sul database Notion.

## Struttura del Flusso

Questo flusso dimostra una pipeline dati con biforcazioni complesse:

* **Manual Trigger / Schedule:** Avvio del flusso.
* **Google Sheets Read:** Legge le idee di contenuto.
* **Split In Batches:** Elabora le righe singolarmente per l'AI.
* **AI Agent (Generazione):** 💡 Nodo chiave per la generazione del contenuto in formato JSON.
* **AI Agent (Analisi e Keyword):** 🔎 Ramo separato che riceve l'output del primo AI Agent per l'analisi e l'estrazione delle Keyword.
* **Code Extract Keywords:** 🧹 Pulisce le keyword estratte dall'AI.
* **Append row in sheet:** 💾 Scrive le keyword nella riga iniziale su Google Sheets.
* **Notion Create Page:** Crea la bozza del post con il contenuto generato.

## Video di Spiegazione

Per una spiegazione dettagliata del funzionamento e della logica del ciclo di feedback chiuso e dell'AI Multi-Tasking, guarda il video qui sotto:

[Spiegazione dettagliata del Flusso Keyword Extraction AI su YouTube](https://youtu.be/spKK-pqKWWA)

---

## Requisiti

Per utilizzare questo flusso, è necessario configurare le credenziali per i seguenti servizi:

* **Google Sheets Account**
* **Google Gemini (PaLM) API Account**
* **Notion Account**

---
