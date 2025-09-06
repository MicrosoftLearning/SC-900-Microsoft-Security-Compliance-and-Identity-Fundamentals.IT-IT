---
lab:
  title: Esplorare eDiscovery
  module: Describe the data compliance solutions of Microsoft Purview
---

# Lab: Esplorare eDiscovery

Questo lab corrisponde al contenuto di Learn seguente:

- Percorso di apprendimento: Descrivere le funzionalità di Microsoft Priva e Microsoft Purview
- Modulo: Descrivere le soluzioni di conformità dei dati di Microsoft Purview
- Unità: Descrivere eDiscovery

## Scenario laboratorio

In questo lab verranno illustrati i passaggi necessari per configurare eDiscovery, tra cui la configurazione delle autorizzazioni per i ruoli, la creazione di un caso di eDiscovery, la creazione di un blocco di eDiscovery e la creazione di una query di ricerca.  Nota: le licenze per eDiscovery richiedono la sottoscrizione dell'organizzazione appropriata e le licenze per utente. Se non si è certi delle licenze che supportano eDiscovery, visitare [Introduzione a eDiscovery in Microsoft Purview](https://docs.microsoft.com/microsoft-365/compliance/get-started-core-ediscovery?view=o365-worldwide).

**Tempo** stimato: 45 minuti

### Attività 1

Per accedere a eDiscovery o essere aggiunti come membro di un caso eDiscovery, a un utente devono essere assegnate le autorizzazioni appropriate. In questa attività, l'amministratore globale aggiungerà utenti specifici come membri del Gruppo di ruoli Manager di eDiscovery.

1. Dovrebbe trovarsi nella home page del portale di Microsoft Purview.  Se in precedenza è stata chiusa, aprire una scheda del browser e immettere **https://purivew.microsoft.com**.

1. Nel riquadro di spostamento a sinistra selezionare **Impostazioni, espandere **Ruoli e ambiti**, quindi selezionare **Gruppi di ruoli****.

1. Nel campo di ricerca, in alto a destra della pagina, immettere **eDiscovery** e quindi premere INVIO sulla tastiera.  Selezionare **Manager di eDiscovery**.

1. Seleziona **Modifica** Ai fini di questo lab, l'amministratore mod verrà impostato come amministratore di eDiscovery e amministratore.  In pratica, è necessario designare utenti specifici per ruoli specifici.
    1. La pagina "Gestisci Manager di eDiscovery" consente di aggiungere utenti al ruolo di Manager di eDiscovery.
    1. Selezionare **Scegli utenti**. Cercare e selezionare **Amministratore MOD** , quindi premere **Seleziona** nella parte inferiore della pagina, quindi selezionare **Avanti**.
    1. Nella pagina "Gestisci Amministratore di eDiscovery", selezionare **Scegli utenti**. Cercare e selezionare **Amministratore MOD** , quindi premere **Seleziona** nella parte inferiore della pagina, quindi selezionare **Avanti** e quindi **Salva**.
    1. Nella pagina "Il gruppo di ruoli è stato aggiornato correttamente", selezionare **Fine**.

1. Tornare alla home page di Microsoft Purview selezionando **Home** nel pannello di spostamento a sinistra.

1. Mantenere la scheda del browser aperta perché verrà usata nell'attività successiva.

### Attività 2

In questa attività, come amministratore di eDiscovery (amministratore MOD è un amministratore di eDiscovery), creerà un caso per iniziare a usare eDiscovery.

1. Dovrebbe trovarsi nella home page del portale di Microsoft Purview.

1. Nel pannello di spostamento a sinistra, in Soluzioni espandere **eDiscovery** e quindi selezionare **Casi**.

1. Nella pagina Casi selezionare **Crea caso**.

1. Nella finestra Nuovo caso immettere un nome case, **SC900 Test Case** e quindi selezionare Crea****.

1. Il caso dovrebbe ora apparire nell'elenco.

1. In qualità di autore del caso e grazie ai privilegi di amministratore di eDiscovery, è possibile iniziare a utilizzare il caso.  

1. Lasciare aperta questa scheda del browser, perché verrà usata nell'attività successiva.

### Attività 3

Con un caso creato, è possibile iniziare a lavorare con il caso.  Ciò include la creazione di una query di ricerca per trovare dati e contenuti rilevanti per il caso, l'applicazione di un criterio di blocco, la creazione di un set di revisione e l'esportazione dei dati. In questa attività verranno esaminate alcune di queste opzioni.

1. Aprire la scheda SC900 Caso di test nel browser.

1. Nella pagina TEST CASE SC900 selezionare  **Crea una ricerca**.

1. Nel campo nome immettere **SC900 case search** e quindi selezionare **Crea**.

1. Selezionare **Aggiungi origini**. Prendere nota delle opzioni di filtro e delle impostazioni predefinite. Nella casella di ricerca immettere **Pradeep** e quindi premere INVIO sulla tastiera. Nei risultati della ricerca selezionare Pradeep Gupta, quindi selezionare ****Salva e chiudi**.** Il generatore di condizioni consente di compilare una query di ricerca in base a parole chiave o condizioni specifiche soddisfatte, nella casella della parola chiave immettere **Sales**. Da qui è possibile selezionare **Esegui la query**.  Questa operazione può richiedere alcuni minuti.

1. Con i risultati delle query restituiti sotto forma di statistiche, è possibile esportare i risultati.  Selezionare **Esporta** per impostare le opzioni disponibili e quindi selezionare **Annulla** (le opzioni di esportazione non possono essere selezionate dalla piattaforma lab fornita dall'host del lab autorizzato, ma sono disponibili in un ambiente di produzione e sono considerate parte del flusso di lavoro).

1. È possibile aggiungere a un insieme di revisione per un'ulteriore elaborazione.  Selezionare **Aggiungi per rivedere il set**. Immettere un nome per il nuovo set di revisione, **`SC900-review-set`**, lasciare le impostazioni predefinite e quindi selezionare **Aggiungi per rivedere il set .**  Questa operazione può richiedere alcuni minuti.  È ora possibile esaminare e intervenire dal set di revisione, inclusi gli elementi di assegnazione di tag, l'esecuzione di query sul set di revisione, l'esecuzione di analisi e altro ancora.  Esplorare le varie opzioni.

1. È anche possibile creare criteri di blocco per mantenere il contenuto pertinente al caso. Selezionare **Hold policies (Mantieni criteri**) e quindi **New policy (Nuovo criterio**).  Immettere un nome di criteri, **`SC900-hold`** e selezionare **Crea.**  Come nella ricerca, è necessario aggiungere origini dati per il blocco ed è possibile aggiungere parole chiave e condizioni da usare nei criteri di blocco, quindi è possibile selezionare **Applica blocco**.  Le azioni che è possibile eseguire in un criterio di blocco includono un nuovo tentativo, disattivare un criterio ed eliminare un criterio di blocco.

1. Disconnettersi e chiudere tutte le finestre del browser aperte.

### Revisione

In questo lab sono stati illustrati i passaggi necessari per iniziare a usare eDiscovery, inclusa la configurazione delle autorizzazioni del ruolo per eDiscovery e la creazione di un caso eDiscovery.  Con il caso, sono state esaminate le opzioni disponibili come parte del flusso di lavoro di eDiscovery, tra cui una ricerca eDiscovery, un criterio di blocco, aggiungere i risultati della ricerca a un set di revisione ed esportare i risultati.
