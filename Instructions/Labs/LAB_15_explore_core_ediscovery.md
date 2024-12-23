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

In questo lab verranno illustrati i passaggi necessari per configurare eDiscovery, tra cui la configurazione delle autorizzazioni per i ruoli, la creazione di un caso di eDiscovery, la creazione di un blocco di eDiscovery e la creazione di una query di ricerca.  Le licenze per eDiscovery (Standard) richiedono un abbonamento dell'organizzazione appropriata e licenze per utente. In caso di dubbi sulle licenze che supportano eDiscovery (Standard), vedere [Attività iniziali con eDiscovery (Standard) in Microsoft Purview](https://docs.microsoft.com/microsoft-365/compliance/get-started-core-ediscovery?view=o365-worldwide).

**Tempo** stimato: 45 minuti

### Attività 1

Per accedere a eDiscovery (Standard) o essere aggiunti come membro di un caso di eDiscovery, a un utente devono essere assegnate le autorizzazioni appropriate. In questa attività, l'amministratore globale aggiungerà utenti specifici come membri del Gruppo di ruoli Manager di eDiscovery.

1. Aprire la scheda del browser sulla Home page di Microsoft Purview.  Se in precedenza è stata chiusa, aprire una scheda del browser e immettere **https://admin.microsoft.com**. Accedere con le credenziali di amministratore per il tenant di Microsoft 365 fornito tramite un provider di servizi di hosting per lab autorizzato (ALH).

1. Dal riquadro di spostamento dell'interfaccia di amministrazione di Microsoft 365, selezionare **Mostra tutto**, quindi selezionare **Conformità**.  Verrà aperta una nuova pagina del browser nella pagina iniziale del portale di Microsoft Purview.  

1. Nel riquadro di spostamento a sinistra selezionare **Impostazioni, espandere **Ruoli e ambiti**, quindi selezionare **Gruppi di ruoli****.

1. Nel campo di ricerca, in alto a destra della pagina, immettere **eDiscovery** e quindi premere INVIO sulla tastiera.  Selezionare **Manager di eDiscovery**.

1. Seleziona **Modifica** Ai fini di questo lab, l'amministratore mod verrà impostato come amministratore di eDiscovery e amministratore.  In pratica, è necessario designare utenti specifici per ruoli specifici.
    1. La pagina "Gestisci Manager di eDiscovery" consente di aggiungere utenti al ruolo di Manager di eDiscovery.
    1. Selezionare **Scegli utenti**. Cercare e selezionare **Amministratore MOD** , quindi premere **Seleziona** nella parte inferiore della pagina, quindi selezionare **Avanti**.
    1. Nella pagina "Gestisci Amministratore di eDiscovery", selezionare **Scegli utenti**. Cercare e selezionare **Amministratore MOD** , quindi premere **Seleziona** nella parte inferiore della pagina, quindi selezionare **Avanti** e quindi **Salva**.
    1. Nella pagina "Il gruppo di ruoli è stato aggiornato correttamente", selezionare **Fine**.

1. Mantenere la scheda del browser aperta perché verrà usata nell'attività successiva.

### Attività 2

In questa attività, lo studente, in qualità di Amministratore di eDiscovery (l'amministratore MOD è un amministratore di eDiscovery), creerà un caso per iniziare a utilizzare eDiscovery (Standard).

1. Dovrebbe essere ancora visualizzata la pagina Ruoli del portale di conformità. Se la scheda del browser è stata chiusa dall'attività precedente, aprire una nuova scheda del browser e immettere **compliance.microsoft.com** per accedere al portale di Microsoft Purview.

1. Nel pannello di spostamento a sinistra, in Soluzioni espandere **eDiscovery** e quindi selezionare **Casi** standard.

1. Nella parte superiore della pagina eDiscovery (Standard), selezionare **+ Crea un caso**.

1. Nella finestra Nuovo caso, immettere il nome del caso, **SC900 Caso di test** e selezionare **Salva** in fondo alla pagina.

1. Il caso dovrebbe ora apparire nell'elenco.

1. In qualità di autore del caso e grazie ai privilegi di amministratore di eDiscovery, è possibile iniziare a utilizzare il caso.  

1. Lasciare aperta questa scheda del browser, perché verrà usata nell'attività successiva.

### Attività 3

Ora che è stato creato un caso di eDiscovery (Standard), si può iniziare a lavorare su di esso.  In questa attività, lo studente creerà un blocco di eDiscovery per il caso creato.  Nello specifico, si dovrà creare un blocco per la cassetta postale di Exchange che appartiene ad Adele Vance.

1. Aprire la scheda eDiscovery (Standard) nel browser.

1. Dalla pagina eDiscovery (Standard), selezionare il caso creato nella scheda precedente, **SC900 Caso di test**.

1. Dalla pagina iniziale del caso, selezionare la scheda **Sospensione**, quindi selezionare **+Crea**.

1. Nel campo del nome immettere **Blocco di test** e quindi selezionare **Avanti**.

1. Nella pagina Scegli posizioni, selezionare l'interruttore accanto a **Cassette postali Exchange** per impostare lo stato su **Attivata**.  

1. Selezionare ora **Scegli utenti, gruppi o team**.  Nella casella di ricerca, immettere **Adele**, quindi premere INVIO sulla tastiera. Nei risultati della ricerca selezionare **Adele Vance** e quindi selezionare **Fatto**.

1. Nella pagina Scegli posizioni, selezionare **Avanti**.  Per motivi di praticità con il lab, non saranno incluse altre posizioni in questo blocco.

1. La pagina Condizioni query consente di creare un blocco per gli elementi in base a una query che è possibile creare.  È possibile scegliere di usare il generatore di query per creare una query o per utenti più avanzati, è possibile usare l'editor KQL. Per questo esercizio, si vuole che il blocco mantenga tutto il contenuto nel percorso specificato per l'utente specificato, quindi non verrà creata una query.

1. Esaminare le impostazioni e selezionare **Invia**; potrebbe essere necessario qualche minuto, quindi selezionare **Fine**.  Il blocco della prova dovrebbe apparire nell'elenco.  Se non viene visualizzato immediatamente, selezionare **Aggiorna**.

1. Lasciare aperta questa scheda del browser, perché verrà usata nell'attività successiva.

### Attività 4

Una volta creato il blocco, occorre creare una query di ricerca.  Al termine della ricerca, eDiscovery supporta azioni, ad esempio l'esportazione e il download dei risultati per indagini successive.   Nota: le ricerche associate a un caso eDiscovery (Standard) non sono elencate nella pagina Ricerca contenuto nel portale di Microsoft Purview. Queste ricerche sono elencate solo nella pagina Ricerche del caso di eDiscovery (Standard) associato.

1. Aprire la scheda SC900 Caso di test nel browser.

1. Nella pagina SC900 Caso di test selezionare **Ricerche**.

1. Dalla pagina Ricerca, selezionare **+ Nuova ricerca**.

1. Nel campo Nome, immettere **Blocco test – Ricerca vendite** e quindi selezionare **Avanti** nella parte inferiore della pagina.

1. Nella pagina Scegli posizioni selezionare **Posizioni con blocco** e deselezionare **Aggiungi il contenuto delle app per gli utenti locali**, perché l'ambiente lab non ha utenti locali, quindi selezionare **Avanti**.

1. La pagina Condizioni query consente di creare una ricerca, in base a parole chiave o condizioni specifiche soddisfatte. Nel campo parola chiave immettere **Vendite** e selezionare **Avanti**.

1. Esaminare le impostazioni e selezionare **Invia**; potrebbe essere necessario qualche minuto, quindi selezionare **Fine**.  La ricerca dovrebbe essere visualizzata nell'elenco.  Se non viene visualizzato immediatamente, selezionare **Aggiorna**.

1. Nella finestra Ricerche selezionare la ricerca appena creata, **Blocco di test - Ricerca vendite**.  Finestra visualizzata con la scheda Riepilogo selezionata.  Una volta eseguita la ricerca, lo stato ne indica il completamento.  Verrà visualizzata la scheda Statistiche ricerca (se la scheda Statistiche ricerca non compare, significa che la ricerca è in corso e richiede ancora qualche minuto per essere completata).  Selezionare la scheda **Statistiche della ricerca** e selezionare l'elenco a discesa accanto a Cerca contenuto.  È possibile visualizzare anche altre informazioni relative al report Condizione e alle posizioni principali.  

1. Nella parte inferiore della pagina, selezionare **Azioni**.  Si notino le opzioni disponibili che includono le opzioni di esportazione (le opzioni di esportazione non possono essere selezionate dall'interno della piattaforma lab fornita dal provider di servizi di hosting per i lab autorizzato, ma sono disponibili in un ambiente di produzione e sono considerate parte del flusso di lavoro standard). Selezionare **Chiudi**.

1. Disconnettersi e chiudere tutte le finestre del browser aperte.

### Revisione

In questo lab sono stati eseguiti i passaggi necessari per iniziare a usare eDiscovery (Standard), incluse l'impostazione delle autorizzazioni per i ruoli di eDiscovery e la creazione di un caso di eDiscovery.  Dopo aver creato il caso sono stati presentati gli elementi del flusso di lavoro di eDiscovery (Standard), creando un blocco di eDiscovery e una query di ricerca.
