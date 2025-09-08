<!---
---
Demo: Title: 'Sensitivity labels in Microsoft Purview' Learning Path/Module/Unit: 'Learning Path: Describe the capabilities of the Microsoft Priva and Microsoft Purview; Modulo 2:Descrivere le soluzioni di sicurezza dei dati di Microsoft Purview; Unità 4: Descrivere etichette di riservatezza e criteri in Microsoft Purview Information Protection'
---
--->

# Demo: etichette di riservatezza in Microsoft Purview

Questa demo corrisponde al contenuto di Learn seguente:

- Percorso di apprendimento: Descrivere le funzionalità di Microsoft Priva e Microsoft Purview
- Modulo: Descrivere le soluzioni di sicurezza dei dati di Microsoft Purview
- Unità: Descrivere etichette di riservatezza e criteri in Microsoft Purview Information Protection

## Scenario dimostrativo

In questa demo verranno visualizzate le funzionalità delle etichette di riservatezza.  Verranno esaminate le impostazioni per le etichette di riservatezza esistenti che sono state create e il criterio corrispondente per pubblicare l'etichetta.   Verrà quindi illustrato come applicare un'etichetta e l'impatto della stessa dal punto di vista dell'utente.

**NOTA**: la prima volta che si usa Word online con il tenant di Microsoft 365, la visualizzazione dell'icona Riservatezza sulla barra multifunzione può richiedere fino a 15 minuti. È consigliabile che i relatori aprono Word Online (come illustrato nella parte demo 3) prima di avviare la demo completa per garantire un tempo sufficiente per la visualizzazione dell'opzione.

### Demo part 1 (facoltativo)

Se si tratta della prima istanza in cui si demono le soluzioni Microsoft Purview, è consigliabile dedicare alcuni minuti all'introduzione del portale di Microsoft Purview prima di accedere alle etichette di riservatezza.

1. Aprire Microsoft Edge e nella barra degli indirizzi immettere , accedere **https://purview.microsoft.com**con le credenziali fornite dall'host del lab autorizzato e quindi selezionare **Inizia**.  

1. Prima di accedere alle etichette di riservatezza, dedicare alcuni istanti all'esplorazione del portale di Microsoft Purview.

1. Selezionare il riquadro **Visualizza tutte le soluzioni** per visualizzare il raggruppamento per le soluzioni Microsoft Purview.

1. Nel pannello di spostamento a sinistra verranno visualizzate le opzioni per Soluzioni, Informazioni, Impostazioni e soluzioni selezionate di recente.
    1. **Soluzioni.** Verrà aperto un nuovo pannello con tutte le soluzioni e i portali correlati.
    1. **Informazioni su come** visualizzare i collegamenti a documenti, video e blog.
    1. **Impostazioni**. Esplorare queste opzioni a volontà. Da qui è possibile configurare ruoli e ambiti, connettore dati e tutte le impostazioni della soluzione.

1. Tornare alla home page selezionando **Home** nel pannello di spostamento a sinistra.

### Demo parte 2

Questa demo illustrerà le impostazioni per un'etichetta di riservatezza esistente e il criterio corrispondente per pubblicare l'etichetta.

1. Si dovrebbe essere nella pagina di destinazione del portale di Microsoft Purview.  In caso contrario, aprire una scheda del browser in Microsoft Edge e immettere e accedere **`https://puriview.microsoft.com`** con le credenziali fornite dall'host del lab autorizzato.

1. Nella pagina di destinazione del nuovo portale di Microsoft Purview selezionare il **riquadro Visualizza tutte le soluzioni** e quindi selezionare il **riquadro Information Protection** . In alternativa, selezionare **Soluzioni** nel pannello di spostamento a sinistra, quindi selezionare **Information Protection**.

1. Verrà visualizzata la pagina di panoramica. Nel pannello di spostamento a sinistra selezionare Etichette** di riservatezza**. Se viene visualizzato un banner giallo che indica che l'organizzazione non ha attivato la possibilità di elaborare il contenuto nei file online di Office con etichette di riservatezza crittografate applicate e archiviate in OneDrive e SharePoint.  Selezionare **Attiva ora**

1. Alcune etichette sono state preconfigurate nel tenant del lab di Microsoft 365, per praticità. Espandere l'etichetta denominata **Riservatezza elevata** e quindi selezionare **Tutti i dipendenti**.  Verrà visualizzata una finestra che fornisce informazioni su questa etichetta.  Notare le impostazioni per questa etichetta.  Selezionare **Modifica etichetta** Se questa opzione non viene visualizzata, selezionare i puntini di sospensione.
    1. La configurazione inizia con l'aggiunta di dettagli di base per l'etichetta.  Non modificare nulla.  Nella parte inferiore della pagina, selezionare **Avanti**.
    1. Esaminare l'ambito per questa etichetta. Non modificare nulla.  Nella parte inferiore della pagina, selezionare **Avanti**.
    1. Questa schermata successiva consente di scegliere le impostazioni di protezione per gli elementi etichettati. Questa etichetta controlla chi può accedere e visualizzare gli elementi etichettati e applica anche il contrassegno del contenuto.  Selezionare **Avanti** per visualizzare i dettagli.
        1. Controllo di accesso: esaminare le impostazioni, ma non modificare nulla.  Selezionare **Avanti**.
        1. Contrassegno del contenuto: si noti che l'etichetta applica un piè di pagina.  quindi selezionare **Avanti**.
        1. Etichettatura automatica per file e messaggi di posta elettronica: leggere la descrizione dell'etichettatura automatica nella parte superiore della pagina e la casella di informazioni sottostante.  Tenere inoltre presente che questa etichetta è impostata per l'etichettatura automatica quando vengono rilevati numeri di carta di credito. Non modificare nessuna impostazione.  Nella parte inferiore della pagina, selezionare **Avanti**.
    1. Definire le impostazioni di protezione per gruppi e siti: esaminare le opzioni per le impostazioni di protezione e applicare automaticamente le impostazioni.  Nessun elemento è stato configurato in questa finestra.  Non cambiare nulla. Nella parte inferiore della pagina, selezionare **Avanti**.
    1. Esaminare le impostazioni e completare: esaminare le impostazioni.  Dopo che non è stato modificato alcun elemento, selezionare **Annulla**.

1. Nel riquadro di spostamento sinistro espandere **Criteri** e quindi selezionare **Criteri di pubblicazione** delle etichette.  Si tratta di criteri che consentono la pubblicazione di etichette di riservatezza.  Il tenant di Microsoft 365 è stato configurato con alcuni criteri delle etichette, per praticità. Selezionare Criteri** estremamente **riservati.  Verrà visualizzata una finestra che fornisce informazioni sui criteri. Selezionare **Modifica criterio** nella parte superiore della finestra.  Qui verranno illustrate le impostazioni senza modificare nulla.
    1. Scegliere le etichette di riservatezza da pubblicare: si notino le etichette elencate.  Non modificare nessuna impostazione.  Nella parte inferiore della pagina, selezionare **Avanti**.
    1. Assegnare unità di amministrazione: le unità di amministrazione sono impostate sulla directory completa, non modificare le impostazioni. Selezionare **Avanti**.  
    1. Pubblica in utenti e gruppi: si noti che questa etichetta è disponibile per tutti gli utenti.  Non modificare nessuna impostazione.  Nella parte inferiore della pagina, selezionare **Avanti**.
    1. Impostazioni dei criteri: prendere nota delle opzioni disponibili. Non modificare nessuna impostazione.  Nella parte inferiore della pagina, selezionare **Avanti**.
    1. Impostazioni predefinite per i documenti: non modificare le impostazioni.  Nella parte inferiore della pagina, selezionare **Avanti**.
    1. Impostazioni predefinite per i messaggi di posta elettronica: esaminare le opzioni e notare che i messaggi di posta elettronica possono ereditare un'etichetta da un allegato con priorità più alta, se configurata in questo modo. Selezionare **Avanti**.
    1. Impostazioni predefinite per le riunioni e gli eventi del calendario: esaminare le opzioni e prendere nota dell'opzione per applicare l'ereditarietà tra riunioni e artefatti del team. Non modificare nessuna impostazione.  Selezionare **Avanti**.
    1. Impostazioni predefinite per il contenuto di Infrastruttura e Power BI: non modificare alcuna impostazione.  Selezionare **Avanti**.
    1. Assegnare un nome al criterio: poiché si sta modificando il criterio, il campo del nome è disattivato.  Selezionare **Avanti**.
    1. Revisione e fine: dopo che non è stato modificato nulla, selezionare **Annulla**.

1. Nel riquadro di spostamento a sinistra, in Protezione delle informazioni, selezionare Etichettatura automatica. Esaminare la descrizione. Tenere presente la creazione di criteri di etichettatura automatica per applicare automaticamente etichette di riservatezza ai messaggi di posta elettronica o ai file di OneDrive e SharePoint, che contengono informazioni riservate. Se sono configurati criteri di etichettatura automatica, selezionarne uno e rivedere le informazioni sui criteri nel riquadro Dettagli.  Se non è elencato alcun criterio, è possibile eseguire la procedura dettagliata per crearne uno, se il tempo lo consente.

1. Nel pannello di spostamento a sinistra selezionare Home per tornare al portale di Microsoft Purview.

1. Mantenere aperta la scheda del browser.

### Demo parte 3

In questo passaggio verrà illustrato il processo di applicazione di un'etichetta di riservatezza a un documento di Microsoft Word e quindi di visualizzare il contrassegno del contenuto (piè di pagina) generato dall'etichetta. NOTA: quando si utilizza Microsoft Word online, è possibile che si verifichi un ritardo prima che l'opzione di selezione delle etichette di riservatezza venga visualizzata sulla barra multifunzione superiore.  È consigliabile completare tutti i lab rimanenti e quindi tornare a questa attività.

1. Si dovrebbe ancora trovarsi nella home page del portale di Microsoft Purview. 
1. Nel portale di Microsoft Purview selezionare l'icona dell'icona **** di avvio delle app, accanto alla posizione in cui è indicato Microsoft Purview. Selezionare l'**icona di Word**.  

1. In Crea nuovo, selezionare **Documento vuoto**, quindi immettere del testo nella pagina.  Nella parte superiore della pagina, accanto all'icona di Word, selezionare il punto in cui è indicato **Documento** e rinominare il file in **Test-label** e quindi premere **INVIO** sulla tastiera.

1. All'estrema destra della barra del menu superiore (detta anche barra multifunzione) è presente una freccia verso il basso, selezionarla, quindi selezionare **Barra multifunzione classica**.  In questo modo sarà più semplice identificare l'icona di riservatezza. Selezionare **Riservatezza**, accanto all'icona del microfono. Dal menu a discesa selezionare **Riservatezza elevata** e quindi Tutti **i dipendenti**.  

1. Nella barra dei menu superiore, selezionare **Visualizza**, quindi selezionare **Visualizzazione di lettura**.

1. Si noti che il documento include il piè di pagina "Classificato come estremamente riservato".  

1. Chiudere le schede di Microsoft Word aperte nel browser per uscire da Word, ma mantenere aperta la scheda del browser alla home page di Microsoft Purview.

### Revisione

In questa demo, sono state illustrate le impostazioni che possono essere configurate per le etichette di riservatezza e le impostazioni dei criteri per la pubblicazione delle etichette di riservatezza. È inoltre è stato illustrato come applicare un'etichetta.
