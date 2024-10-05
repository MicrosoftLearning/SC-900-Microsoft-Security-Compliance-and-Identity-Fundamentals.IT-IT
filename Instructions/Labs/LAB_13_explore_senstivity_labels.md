---
lab:
  title: Esplorare le etichette di riservatezza in Microsoft Purview
  module: Describe the data security solutions of Microsoft Purview
---

# Lab: esplorare le etichette di riservatezza in Microsoft Purview

Questo lab corrisponde al contenuto di Learn seguente:

- Percorso di apprendimento: Descrivere le funzionalità di Microsoft Priva e Microsoft Purview
- Modulo: Descrivere le soluzioni di sicurezza dei dati di Microsoft Purview
- Unità: Descrivere etichette di riservatezza e criteri in Microsoft Purview Information Protection

## Scenario laboratorio

In questo lab verranno esplorate le funzionalità delle etichette di riservatezza.  Verranno esaminate le impostazioni per le etichette di riservatezza esistenti che sono state create e il criterio corrispondente per pubblicare l'etichetta.   Verrà quindi illustrato come applicare un'etichetta e l'impatto della stessa dal punto di vista dell'utente.

**Tempo** stimato: 45 minuti

### Attività 1

In questa attività si acquisirà una conoscenza delle operazioni che le etichette di riservatezza possono eseguire eseguendo il processo di creazione di una nuova etichetta e la creazione di un criterio per pubblicare l'etichetta.

1. Aprire la scheda del browser sulla Home page di Microsoft Purview.  Se in precedenza è stata chiusa, aprire una scheda del browser e immettere **https://admin.microsoft.com**. Accedere con le credenziali di amministratore per il tenant di Microsoft 365 fornito tramite un provider di servizi di hosting per lab autorizzato (ALH). Se in precedenza è stato eseguito l'accesso come amministratore, verrà richiesto di completare un'autenticazione secondaria, come parte di MFA. Se in precedenza non è stato eseguito l'accesso come amministratore, verrà richiesto di completare il processo di registrazione dell'autenticazione a più fattori. Seguire le istruzioni visualizzate sullo schermo per configurare l'autenticazione a più fattori.

1. Dal riquadro di spostamento dell'interfaccia di amministrazione di Microsoft 365, selezionare **Mostra tutto**, quindi selezionare **Conformità**.  Verrà aperta una nuova pagina del browser nella pagina iniziale del portale di Microsoft Purview.

1. Nel pannello di spostamento sinistro selezionare **Soluzioni** e quindi Selezionare **Protezione delle informazioni**.  Si è nella pagina di panoramica. Scorrere verso il basso per visualizzare le informazioni disponibili.

1. Nel pannello di spostamento a sinistra selezionare Etichette** di riservatezza**.

1. Alcune etichette sono state preconfigurate nel tenant del lab di Microsoft 365, per praticità. Selezionare l'etichetta denominata **Riservato - Finanza**.  Verrà visualizzata una finestra che fornisce informazioni su questa etichetta.  Notare le impostazioni per questa etichetta.  Selezionare **Modifica etichetta** Se questa opzione non viene visualizzata, selezionare i puntini di sospensione.
    1. La configurazione inizia con l'aggiunta di dettagli di base per l'etichetta.  Non modificare nulla.  Nella parte inferiore della pagina, selezionare **Avanti**.
    1. Esaminare l'ambito per questa etichetta. Non modificare nulla.  Nella parte inferiore della pagina, selezionare **Avanti**.
    1. Questa schermata successiva consente di scegliere le impostazioni di protezione per gli elementi etichettati. Questa etichetta è configurata per supportare il contrassegno del contenuto. Non modificare nulla.  Nella parte inferiore della pagina, selezionare **Avanti**.
        1. Nella pagina Contrassegni di contenuto, prendere nota della casella delle informazioni nella parte superiore della pagina.  Non modificare nessuna impostazione.  Nella parte inferiore della pagina, selezionare **Avanti**.
    1. Ora ci si trova nell'etichettatura automatica per la finestra di file e messaggi di posta elettronica.  Leggere la descrizione dell'etichettatura automatica nella parte superiore della pagina e la casella di informazioni sottostante.  Notare anche che questa etichetta è impostata per l'etichettatura automatica secondo condizioni specifiche. Non modificare nessuna impostazione.  Nella parte inferiore della pagina, selezionare **Avanti**.
    1. Questa finestra definisce le impostazioni di protezione per gruppi e siti a cui è applicata questa etichetta. Se non è abilitata, selezionare **Avanti** nella parte inferiore della pagina.
    1. Questa finestra costituisce una funzionalità di anteprima per l'etichettatura automatica agli asset di dati schematizzati in Microsoft Purview Data Map (ad esempio SQL, Synapse e altro ancora), che contengono i tipi di informazioni sensibili scelti dall'utente.  Questa funzionalità non è abilitata. Selezionare **Annulla** nella parte inferiore della pagina per uscire dalla procedura guidata per la configurazione dell'etichetta e tornare alla pagina della Protezione delle informazioni.

1. Nel riquadro di spostamento a sinistra espandere **Criteri** e quindi selezionare  **Criteri di pubblicazione**.  Si tratta di criteri che consentono la pubblicazione di etichette di riservatezza.  Il tenant di Microsoft 365 è stato configurato con alcuni criteri delle etichette, per praticità.

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

1. Nel riquadro di spostamento a sinistra, in Protezione delle informazioni, selezionare Etichettatura automatica. Esaminare la descrizione. Tenere presente la creazione di criteri di etichettatura automatica per applicare automaticamente etichette di riservatezza ai messaggi di posta elettronica o ai file di OneDrive e SharePoint, che contengono informazioni riservate. Nessun criterio di etichettatura automatica è stato preconfigurato nel tenant. Per creare un nuovo criterio di etichettatura automatica, selezionare **Crea criterio di etichettatura automatica**.  In questa sezione vengono illustrati i passaggi per la creazione di un nuovo criterio.
    1. Per iniziare, scegliere le informazioni a cui applicare l'etichetta.  Notare le le opzioni disponibili.  Selezionare **Medici e integrità**, quindi selezionare uno dei modelli disponibili.  Selezionare **Avanti**.
    1. È possibile assegnare un nome al criterio di etichettatura automatica o usare il nome predefinito.  Selezionare **Avanti**.
    1. È possibile assegnare le unità di amministrazione a cui si applica questo criterio.  Mantenere le impostazioni predefinite sull'elenco completo, quindi selezionare **Avanti**.
    1. Notare le posizioni disponibili in cui si desidera applicare l'etichetta.  Mantenere le impostazioni predefinite e selezionare **Avanti**.
    1. È possibile configurare regole comuni o avanzate che definiscono il contenuto a cui viene applicata l'etichetta.  Mantenere le impostazioni sulle Regole comuni quindi selezionare **Avanti**.
    1. È possibile definire regole per contenuti in tutte le posizioni.  L'etichetta verrà applicata al contenuto che corrisponde alle regole definite in questa pagina.  Per il modello selezionato, verrà visualizzata una voce. Espanderlo per visualizzare le condizioni che si applicano.  Mantenere le impostazioni predefinite e selezionare **Avanti**.
    1. Scegliere un'etichetta da applicare automaticamente, selezionando **Scegli etichetta**.  Scegliere un'etichetta e quindi selezionare **Aggiungi**. Selezionare **Avanti**.
    1. È possibile configurare impostazioni aggiuntive per i messaggi di posta elettronica. Mantenere le impostazioni predefinite e selezionare **Avanti**.
    1. È possibile testare il criterio ora o in un secondo momento.  Selezionare **Mantieni criterio disattivato** e quindi selezionare **Avanti**.
    1. Rivedere le impostazioni e selezionare **Crea criterio**, quindi selezionare **Fine**.

1. Dal riquadro di spostamento a sinistra, selezionare **Home** per tornare al portale di conformità Microsoft Purview.

1. Tenere aperta la pagina perché verrà usata nell'attività successiva.

### Attività 2

In questa attività, verrà eseguito il processo di applicazione di un'etichetta di riservatezza a un documento di Microsoft Word e quindi visualizzato il contrassegno del contenuto (filigrana) generato dall'etichetta. NOTA: quando si utilizza Microsoft Word online, è possibile che si verifichi un ritardo prima che l'opzione di selezione delle etichette di riservatezza venga visualizzata sulla barra multifunzione superiore.  È consigliabile completare tutti i lab rimanenti e quindi tornare a questa attività.

1. Nella home page del portale di conformità di Microsoft Purview selezionare l'**icona di avvio dell'app** accanto a Contoso Electronics. Selezionare l'**icona di Word**.  

1. In Crea nuovo, selezionare **Documento vuoto**, quindi immettere del testo nella pagina.  Nella parte superiore della pagina selezionare la freccia in giù accanto a Documento - Salvato, nella casella Nome file immettere **Etichetta di test** e quindi premere **INVIO**.

1. All'estrema destra della barra del menu superiore (detta anche barra multifunzione) è presente una freccia verso il basso, selezionarla, quindi selezionare **Barra multifunzione classica**.  In questo modo sarà più semplice identificare l'icona di riservatezza. Selezionare **Riservatezza**, accanto all'icona del microfono. Nel menu a discesa selezionare **Riservato-Finanza**.  

1. Nella barra dei menu superiore, selezionare **Visualizza**, quindi selezionare **Visualizzazione di lettura**.

1. Notare che il documento include la filigrana Riservato DATI FINANZIARI.  

1. Chiudere le schede di Microsoft Word aperte nel browser per uscire da Word, ma mantenere aperta la scheda del browser alla home page di Microsoft Purview.

### Revisione

In questo lab verranno esplorate le funzionalità delle etichette di riservatezza.  Verranno esaminate le impostazioni per le etichette di riservatezza esistenti già create e il criterio corrispondente per la pubblicazione dell'etichetta.   Verrà quindi esaminato come applicare un'etichetta.
