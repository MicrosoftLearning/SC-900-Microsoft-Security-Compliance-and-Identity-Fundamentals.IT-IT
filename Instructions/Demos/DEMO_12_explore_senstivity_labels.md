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

Questa demo mostra le funzionalità delle etichette di riservatezza.  Verranno esaminate le impostazioni per le etichette di riservatezza esistenti che sono state create e il criterio corrispondente per pubblicare l'etichetta.   Verrà quindi illustrato come applicare un'etichetta e l'impatto della stessa dal punto di vista dell'utente.  **NOTA:** la prima volta che si usa Word online con il tenant di Microsoft 365, la visualizzazione dell'opzione Riservatezza sulla barra multifunzione può richiedere 15 minuti.  I relatori devono eseguire la seconda parte della demo prima della lezione per garantire un tempo sufficiente per la visualizzazione dell'opzione.

### Demo parte 1

Questa demo illustrerà le impostazioni per un'etichetta di riservatezza esistente e il criterio corrispondente per pubblicare l'etichetta.

1. Aprire una nuova scheda del browser Microsoft Edge. Nella barra degli indirizzi immettere **https://purview.microsoft.com**. Per accedere al nuovo portale di Microsoft Purview, selezionare la casella accanto alla posizione in cui è indicato, **accetto le condizioni per la divulgazione del flusso di dati e le informative** sulla privacy, quindi selezionare **Inizia**.  

1. Nella pagina di destinazione del nuovo portale di Microsoft Purview selezionare il **riquadro Visualizza tutte le soluzioni** e quindi selezionare il **riquadro Information Manager** . In alternativa, selezionare **Soluzioni** nel pannello di spostamento a sinistra, quindi selezionare **Information Protection**.

1. Verrà visualizzata la pagina di panoramica. Nel pannello di spostamento a sinistra selezionare Etichette** di riservatezza**.

1. Alcune etichette sono state preconfigurate nel tenant del lab di Microsoft 365, per praticità. Selezionare l'etichetta denominata **Riservato - Finanza**.  Verrà visualizzata una finestra che fornisce informazioni su questa etichetta.  Notare le impostazioni per questa etichetta.  Selezionare **Modifica etichetta** (può anche essere visualizzata come icona a forma di matita) nella parte superiore della pagina per visualizzare alcune delle impostazioni di configurazione di base. Se questa opzione non viene visualizzata, selezionare i puntini di sospensione.
    1. La configurazione inizia specificando un nome e una descrizione per l'etichetta.  Non modificare nulla.  Nella parte inferiore della pagina, selezionare **Avanti**.
    1. Esaminare l'ambito per questa etichetta. Non modificare nulla.  Nella parte inferiore della pagina, selezionare **Avanti**.
    1. Questa schermata successiva consente di scegliere le impostazioni di protezione per gli elementi etichettati. Questa etichetta è configurata per supportare il contrassegno del contenuto. Non modificare nulla.  Nella parte inferiore della pagina, selezionare **Avanti**.
        1. Nella pagina Contrassegni di contenuto, prendere nota della casella delle informazioni nella parte superiore della pagina.  Non modificare nessuna impostazione.  Nella parte inferiore della pagina, selezionare **Avanti**.
    1. Ora ci si trova nell'etichettatura automatica per la finestra di file e messaggi di posta elettronica.  Leggere la descrizione dell'etichettatura automatica nella parte superiore della pagina e la casella di informazioni sottostante.  Notare anche che questa etichetta è impostata per l'etichettatura automatica secondo condizioni specifiche. Non modificare nessuna impostazione.  Nella parte inferiore della pagina, selezionare **Avanti**.
    1. Questa finestra definisce le impostazioni di protezione per team, gruppi e siti a cui è applicata questa etichetta. Se non è abilitata, selezionare **Avanti** nella parte inferiore della pagina.
    1. Questa finestra costituisce una funzionalità di anteprima per l'etichettatura automatica agli asset di dati schematizzati in Microsoft Purview Data Map (ad esempio SQL, Synapse e altro ancora), che contengono i tipi di informazioni sensibili scelti dall'utente.  Questa funzionalità non è abilitata. Selezionare **Annulla** nella parte inferiore della pagina per uscire dalla procedura guidata per la configurazione dell'etichetta e tornare alla pagina della Protezione delle informazioni.

1. Nel pannello di spostamento a sinistra selezionare **Criteri** e quindi Selezionare **Criteri di pubblicazione**.  Si tratta di criteri che consentono la pubblicazione di etichette di riservatezza.  Il tenant di Microsoft 365 è stato configurato con alcuni criteri delle etichette, per praticità.

1. Selezionare **Riservato - Criterio finanza**.  Verrà visualizzata una finestra che fornisce informazioni sui criteri. Selezionare **Modifica criterio** nella parte superiore della finestra.  Qui verranno illustrate le impostazioni senza modificare nulla.
    1. Esaminare la descrizione per "Scegliere le etichette di riservatezza da pubblicare".  Notare l'etichetta presente nell'elenco.  Non modificare nessuna impostazione.  Nella parte inferiore della pagina, selezionare **Avanti**.
    1. Esaminare la descrizione per "Assegnare le unità di amministrazione". Le unità di Amministrazione sono impostate sulla directory completa, non modificare le impostazioni. Selezionare **Avanti**.  
    1. Esaminare la descrizione per "Pubblicare in utenti e gruppi".  Notare che questa etichetta è disponibile per tutti gli utenti.  Non modificare nessuna impostazione.  Nella parte inferiore della pagina, selezionare **Avanti**.
    1. Esaminare le impostazioni dei criteri. Non modificare nessuna impostazione.  Nella parte inferiore della pagina, selezionare **Avanti**.
    1. Esaminare la descrizione per "Applicare un'etichetta predefinita ai documenti". Non modificare nessuna impostazione.  Nella parte inferiore della pagina, selezionare **Avanti**.
    1. Esaminare la descrizione "Applicare un'etichetta predefinita ai messaggi di posta elettronica" ed "Ereditare l'etichetta dagli allegati". Non modificare nessuna impostazione.  Nella parte inferiore della pagina, selezionare **Avanti**.
    1. Esaminare la descrizione per "Applicare un'etichetta predefinita alle riunioni e agli eventi del calendario". Non modificare nessuna impostazione.  Nella parte inferiore della pagina, selezionare **Avanti**.
    1. Esaminare la descrizione in "Applicare un'etichetta predefinita al contenuto di Power BI". Non modificare nessuna impostazione.  Nella parte inferiore della pagina, selezionare **Avanti**.
    1. L'ultima opzione di configurazione consiste nell'assegnare un nome al criterio.  Poiché si sta modificando il criterio, il campo del nome è disattivato. Selezionare **Avanti** nella parte inferiore della pagina.
    1. Esaminare le impostazioni dei criteri. Selezionare **Annulla** per rimuovere le modifiche e tornare alla pagina Criteri delle etichette.

1. Nel riquadro di spostamento a sinistra, in Protezione delle informazioni, selezionare Etichettatura automatica. Esaminare la descrizione. Tenere presente la creazione di criteri di etichettatura automatica per applicare automaticamente etichette di riservatezza ai messaggi di posta elettronica o ai file di OneDrive e SharePoint, che contengono informazioni riservate. Se sono configurati criteri di etichettatura automatica, selezionarne uno e rivedere le informazioni sui criteri nel riquadro Dettagli.  Se non è elencato alcun criterio, è possibile eseguire la procedura dettagliata per crearne uno, se il tempo lo consente.

1. Nel pannello di spostamento a sinistra selezionare Home per tornare al portale di Microsoft Purview.

1. Mantenere aperta la scheda del browser.

### Demo parte 2

Questo passaggio illustrerà il processo di applicazione di un'etichetta dal punto di vista dell'utente (in questo caso l'utente è l'amministratore).  Allo scopo di visualizzare l'impatto dell'applicazione dell'etichetta, si selezionerà l'etichetta Riservato - Finanza perché questa etichetta applica una filigrana.

1. Nella home page Portale di conformità di Microsoft Purview selezionare l'icona **** di avvio dell'app, accanto a dove è indicato Microsoft Purview (nella parte superiore dell'icona home). Selezionare l'**icona di Word**.  

1. Selezionare **Documento vuoto**, quindi immettere il testo nella pagina.  Nella barra blu nella parte superiore della pagina selezionare la freccia in giù accanto a Documento - Salvato, nella casella Nome file immettere **Etichetta di test** e quindi premere **INVIO**.

1. All'estrema destra della barra del menu superiore (detta anche barra multifunzione) è presente una freccia verso il basso, selezionarla, quindi selezionare **Barra multifunzione classica**.  In questo modo sarà più semplice identificare l'icona di riservatezza. Selezionare **Riservatezza**, accanto all'icona del microfono. Nel menu a discesa selezionare **Riservato-Finanza**.  

1. Nella barra dei menu superiore, selezionare **Visualizza**, quindi selezionare **Visualizzazione di lettura**.

1. Notare che il documento include la filigrana.  

1. Chiudere le schede di Microsoft Word aperte nel browser per uscire da Word.

1. Tenere aperta la scheda del browser Microsoft Purview per la demo successiva.

### Revisione

In questa demo, sono state illustrate le impostazioni che possono essere configurate per le etichette di riservatezza e le impostazioni dei criteri per la pubblicazione delle etichette di riservatezza. È inoltre è stato illustrato come applicare un'etichetta.
