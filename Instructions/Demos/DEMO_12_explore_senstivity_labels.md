<!---
---
Demo: Titolo: "Etichette di riservatezza in Microsoft Purview" Percorso di apprendimento/Modulo/Unità: "Percorso di apprendimento: Descrivere le funzionalità di conformità Microsoft; Module 3: Descrivere la protezione delle informazioni, la gestione del ciclo di vita dei dati e le funzionalità di governance dei dati in Microsoft Purview; Unità 4: Descrivere le etichette di riservatezza"
---
--->

# Demo: etichette di riservatezza in Microsoft Purview

Questa demo corrisponde al contenuto di Learn seguente:

- Percorso di apprendimento: Descrivere le funzionalità di conformità Microsoft
- Modulo: descrivere la protezione delle informazioni, la gestione del ciclo di vita dei dati e le funzionalità di governance dei dati in Microsoft Purview
- Unità: Descrivere le etichette di riservatezza

## Scenario dimostrativo

Questa demo mostra le funzionalità delle etichette di riservatezza.  Verranno esaminate le impostazioni per le etichette di riservatezza esistenti che sono state create e il criterio corrispondente per pubblicare l'etichetta.   Verrà quindi illustrato come applicare un'etichetta e l'impatto della stessa dal punto di vista dell'utente.  **NOTA:** la prima volta che si usa Word online con il tenant di Microsoft 365, la visualizzazione dell'opzione Riservatezza sulla barra multifunzione può richiedere 15 minuti.  I relatori devono eseguire la seconda parte della demo prima della lezione per garantire un tempo sufficiente per la visualizzazione dell'opzione.

### Demo parte 1

Questa demo illustrerà le impostazioni per un'etichetta di riservatezza esistente e il criterio corrispondente per pubblicare l'etichetta.

1. Aprire la scheda del browser sulla Home page di Microsoft Purview.  Se in precedenza è stata chiusa, aprire una scheda del browser e immettere **https://admin.microsoft.com**. Accedere con le credenziali di amministratore per il tenant di Microsoft 365 fornito tramite un provider di servizi di hosting per lab autorizzato (ALH). Dal riquadro di spostamento dell'interfaccia di amministrazione di Microsoft 365, selezionare **Mostra tutto**, quindi selezionare **Conformità**.  Si apre una nuova pagina del browser alla pagina di benvenuto del portale di conformità di Microsoft Purview.  

1. Nel riquadro di spostamento a sinistra, in Soluzioni, espandere **Protezione delle informazioni** e quindi selezionare **Panoramica**.  La pagina di panoramica include informazioni sulle principali etichette di riservatezza applicate al contenuto, sulle attività principali rilevate, sulle posizioni in cui vengono applicate le etichette di riservatezza e altro ancora.  
    1. Nella pagina di panoramica, potrebbe essere visualizzato un riquadro delle informazioni giallo che indica che l'organizzazione non ha attivato la possibilità di elaborare il contenuto dei file online di Office con etichette di riservatezza crittografate applicate e archiviati in OneDrive e SharePoint.  Selezionare **Attiva ora**.  Al termine, potrebbe esserci un ritardo nella propagazione delle impostazioni nel sistema.

1. Dal riquadro di spostamento a sinistra, selezionare **Etichette**.

1. Alcune etichette sono state preconfigurate nel tenant del lab di Microsoft 365, per praticità. Selezionare l'etichetta denominata **Riservato - Finanza**.  Verrà visualizzata una finestra che fornisce informazioni su questa etichetta.  Notare le impostazioni per questa etichetta.  Selezionare l'**icona a forma di matita** nella parte superiore della pagina per visualizzare alcune delle impostazioni di configurazione di base. Se l'icona a forma di matita non viene visualizzata, selezionare i puntini di sospensione.
    1. La configurazione inizia specificando un nome e una descrizione per l'etichetta.  Non modificare nulla.  Nella parte inferiore della pagina, selezionare **Avanti**.
    1. Esaminare l'ambito per questa etichetta. Non modificare nulla.  Nella parte inferiore della pagina, selezionare **Avanti**.
    1. Questa schermata successiva consente di scegliere le impostazioni di protezione per gli elementi etichettati. Questa etichetta è configurata per supportare il contrassegno del contenuto. Non modificare nulla.  Nella parte inferiore della pagina, selezionare **Avanti**.
        1. Nella pagina Contrassegni di contenuto, prendere nota della casella delle informazioni nella parte superiore della pagina.  Non modificare nessuna impostazione.  Nella parte inferiore della pagina, selezionare **Avanti**.
    1. Ora ci si trova nell'etichettatura automatica per la finestra di file e messaggi di posta elettronica.  Leggere la descrizione dell'etichettatura automatica nella parte superiore della pagina e la casella di informazioni sottostante.  Notare anche che questa etichetta è impostata per l'etichettatura automatica secondo condizioni specifiche. Non modificare nessuna impostazione.  Nella parte inferiore della pagina, selezionare **Avanti**.
    1. Questa finestra definisce le impostazioni di protezione per team, gruppi e siti a cui è applicata questa etichetta. Se non è abilitata, selezionare **Avanti** nella parte inferiore della pagina.
    1. Questa finestra costituisce una funzionalità di anteprima per l'etichettatura automatica agli asset di dati schematizzati in Microsoft Purview Data Map (ad esempio SQL, Synapse e altro ancora), che contengono i tipi di informazioni sensibili scelti dall'utente.  Questa funzionalità non è abilitata. Selezionare **Annulla** nella parte inferiore della pagina per uscire dalla procedura guidata per la configurazione dell'etichetta e tornare alla pagina della Protezione delle informazioni.

1. Dal riquadro di spostamento a sinistra, selezionare **Criteri etichette**   Si tratta di criteri che consentono la pubblicazione di etichette di riservatezza.  Il tenant di Microsoft 365 è stato configurato con alcuni criteri delle etichette, per praticità.

1. Selezionare **Riservato - Criterio finanza**.  Verrà visualizzata una finestra che fornisce informazioni sui criteri. 

1. Selezionare **Modifica criterio** nella parte superiore della finestra.  Qui verranno illustrate le impostazioni senza modificare nulla.
    1. Esaminare la descrizione per "Scegliere le etichette di riservatezza da pubblicare".  Notare l'etichetta presente nell'elenco.  Non modificare nessuna impostazione.  Nella parte inferiore della pagina, selezionare **Avanti**.
    1. Esaminare la descrizione per "Assegnare le unità di amministrazione". Le unità di Amministrazione sono impostate sulla directory completa, non modificare le impostazioni. Seleziona **Avanti**.  
    1. Esaminare la descrizione per "Pubblicare in utenti e gruppi".  Notare che questa etichetta è disponibile per tutti gli utenti.  Non modificare nessuna impostazione.  Nella parte inferiore della pagina, selezionare **Avanti**.
    1. Esaminare le impostazioni dei criteri. Non modificare nessuna impostazione.  Nella parte inferiore della pagina, selezionare **Avanti**.
    1. Esaminare la descrizione per "Applicare un'etichetta predefinita ai documenti". Non modificare nessuna impostazione.  Nella parte inferiore della pagina, selezionare **Avanti**.
    1. Esaminare la descrizione "Applicare un'etichetta predefinita ai messaggi di posta elettronica" ed "Ereditare l'etichetta dagli allegati". Non modificare nessuna impostazione.  Nella parte inferiore della pagina, selezionare **Avanti**.
    1. Esaminare la descrizione per "Applicare un'etichetta predefinita alle riunioni e agli eventi del calendario". Non modificare nessuna impostazione.  Nella parte inferiore della pagina, selezionare **Avanti**.
    1. Esaminare la descrizione in "Applicare un'etichetta predefinita al contenuto di Power BI". Non modificare nessuna impostazione.  Nella parte inferiore della pagina, selezionare **Avanti**.
    1. L'ultima opzione di configurazione consiste nell'assegnare un nome al criterio.  Poiché si sta modificando il criterio, il campo del nome è disattivato. Selezionare **Avanti** nella parte inferiore della pagina.
    1. Esaminare le impostazioni dei criteri. Selezionare **Annulla** per rimuovere le modifiche e tornare alla pagina Criteri delle etichette.

1. Nella pagina Protezione delle informazioni, selezionare Etichettatura automatica. Esaminare la descrizione. Tenere presente la creazione di criteri di etichettatura automatica per applicare automaticamente etichette di riservatezza ai messaggi di posta elettronica o ai file di OneDrive e SharePoint, che contengono informazioni riservate. Se sono configurati criteri di etichettatura automatica, selezionarne uno e rivedere le informazioni sui criteri nel riquadro Dettagli.  Se non è elencato alcun criterio, è possibile eseguire la procedura dettagliata per crearne uno, se il tempo lo consente.

1. Dal riquadro di spostamento a sinistra, selezionare Home per tornare al portale di conformità Microsoft Purview.

1. Mantenere aperta la scheda del browser.

### Demo parte 2

Questo passaggio illustrerà il processo di applicazione di un'etichetta dal punto di vista dell'utente (in questo caso l'utente è l'amministratore).  Allo scopo di visualizzare l'impatto dell'applicazione dell'etichetta, si selezionerà l'etichetta Riservato - Finanza perché questa etichetta applica una filigrana.

1. Nella home page del portale di conformità di Microsoft Purview selezionare l'**icona di avvio dell'app** accanto a Contoso Electronics. Selezionare l'**icona di Word**.  

1. Selezionare **Documento vuoto**, quindi immettere il testo nella pagina.  Nella barra blu nella parte superiore della pagina selezionare la freccia in giù accanto a Documento - Salvato, nella casella Nome file immettere **Etichetta di test** e quindi premere **INVIO**.

1. Nella barra dei menu superiore selezionare **Icona Riservatezza** (icona a destra dell'icona del microfono). Se questa opzione non viene visualizzata immediatamente, aggiornare la pagina. Nell'elenco a discesa selezionare **Riservato - Finanza**.   NOTA: se non viene visualizzata immediatamente l'opzione Riservatezza, aggiornare la pagina; tuttavia, poiché si tratta di un ambiente lab tenant, è possibile che si verifichino ritardi più lunghi del normale (10-15 minuti).
1. 
1. Nella barra dei menu superiore, selezionare **Visualizza**, quindi selezionare **Visualizzazione di lettura**.

1. Notare che il documento include la filigrana.  

1. Chiudere le schede di Microsoft Word aperte nel browser per uscire da Word.

1. Tenere aperta la scheda del browser Microsoft Purview per la demo successiva.

### Revisione

In questa demo, sono state illustrate le impostazioni che possono essere configurate per le etichette di riservatezza e le impostazioni dei criteri per la pubblicazione delle etichette di riservatezza. È inoltre è stato illustrato come applicare un'etichetta.
