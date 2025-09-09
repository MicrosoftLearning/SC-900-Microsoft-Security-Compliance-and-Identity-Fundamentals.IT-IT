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

In questo lab verranno esplorate le funzionalità delle etichette di riservatezza.  Verranno esaminate le impostazioni per le etichette di riservatezza esistenti che sono state create e il criterio corrispondente per pubblicare l'etichetta. Verrà quindi illustrato come applicare un'etichetta e l'impatto della stessa dal punto di vista dell'utente.

**Tempo** stimato: 45 minuti

### Attività 1

In questa attività si acquisirà una conoscenza delle operazioni che le etichette di riservatezza possono eseguire eseguendo il processo di creazione di una nuova etichetta e la creazione di un criterio per pubblicare l'etichetta.

1. Aprire la scheda del browser sulla Home page di Microsoft Purview.  Se in precedenza è stata chiusa, aprire una scheda del browser e immettere **`https://admin.microsoft.com`**. Accedere con le credenziali di amministratore per il tenant di Microsoft 365 fornito tramite un provider di servizi di hosting per lab autorizzato (ALH).

1. Nel riquadro di spostamento sinistro del interfaccia di amministrazione di Microsoft 365 selezionare **Mostra tutto** e quindi Selezionare **Microsoft Purview**.  Verrà aperta una nuova pagina del browser nella pagina iniziale del portale di Microsoft Purview.

1. Nel pannello di spostamento sinistro selezionare **Soluzioni** e quindi Selezionare **Protezione delle informazioni**.  Si è nella pagina di panoramica. Scorrere verso il basso per visualizzare le informazioni disponibili.

1. Nel pannello di spostamento a sinistra selezionare Etichette** di riservatezza**.
1. Verrà visualizzato un banner giallo che indica che l'organizzazione non ha attivato la possibilità di elaborare il contenuto nei file online di Office con etichette di riservatezza crittografate applicate e archiviate in OneDrive e SharePoint.  Selezionare **Attiva ora**.

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
    1. Impostazioni predefinite per riunioni ed eventi del calendario: esaminare le opzioni e prendere nota dell'opzione per applicare l'ereditarietà tra riunioni teasm e artefatti. Non modificare nessuna impostazione.  Selezionare **Avanti**.
    1. Impostazioni predefinite per il contenuto di Infrastruttura e Power BI: non modificare alcuna impostazione.  Selezionare **Avanti**.
    1. Assegnare un nome al criterio: poiché si sta modificando il criterio, il campo del nome è disattivato.  Selezionare **Avanti**.
    1. Revisione e fine: dopo che non è stato modificato nulla, selezionare **Annulla**.

1. Nel pannello di spostamento a sinistra, in Protezione delle informazioni, selezionare **Criteri di etichettatura automatica**. Esaminare la descrizione. Tenere presente la creazione di criteri di etichettatura automatica per applicare automaticamente etichette di riservatezza ai messaggi di posta elettronica o ai file di OneDrive e SharePoint, che contengono informazioni riservate. Nessun criterio di etichettatura automatica è stato preconfigurato nel tenant. Per creare un nuovo criterio di etichettatura automatica, selezionare **Crea criterio di etichettatura automatica**.  In questa sezione verranno illustrati i passaggi necessari per la creazione di un nuovo criterio.
    1. Per iniziare, scegliere le informazioni a cui applicare l'etichetta.  Notare le le opzioni disponibili.  Selezionare Medico e integrità **, quindi selezionare **una delle normative disponibili che fungeranno da modello.  Selezionare **Avanti**.
    1. È possibile assegnare un nome al criterio di etichettatura automatica o usare il nome predefinito.  Selezionare **Avanti**.
    1. Scegliere quindi un'etichetta da applicare automaticamente.  Selezionare **+ Scegliere un'etichetta**.  Selezionare un'etichetta dall'elenco e quindi selezionare **Aggiungi**.
    1. È possibile assegnare le unità di amministrazione a cui si applica questo criterio.  Mantenere le impostazioni predefinite sull'elenco completo, quindi selezionare **Avanti**.
    1. Scegliere le posizioni in cui applicare l'etichetta.  Esaminare le informazioni fornite e le posizioni disponibili che è possibile selezionare. Per questo esercizio, selezionare la casella accanto a **Posta elettronica** di Exchange e quindi selezionare **Avanti**.
    1. È possibile configurare regole comuni o avanzate che definiscono il contenuto a cui viene applicata l'etichetta.  Mantenere le impostazioni sulle Regole comuni quindi selezionare **Avanti**.
    1. È possibile definire regole per contenuti in tutte le posizioni.  L'etichetta verrà applicata al contenuto che corrisponde alle regole definite in questa pagina.  Per il modello selezionato, verrà visualizzata una voce. Espanderlo per visualizzare le condizioni che si applicano.  Mantenere le impostazioni predefinite e selezionare **Avanti**.
    1. È possibile configurare impostazioni aggiuntive per i messaggi di posta elettronica. Mantenere le impostazioni predefinite e selezionare **Avanti**.
    1. È possibile testare il criterio ora o in un secondo momento.  Selezionare **Mantieni criterio disattivato** e quindi selezionare **Avanti**.
    1. Esaminare le impostazioni. Ai fini di questo esercizio, è possibile annullare la creazione dei criteri. Selezionare **Annulla**.

1. Nel pannello di spostamento a sinistra selezionare **Home** per tornare al portale di Microsoft Purview.

1. Tenere aperta la pagina perché verrà usata nell'attività successiva.

### Attività 2

In questa attività si eseguirà il processo di applicazione di un'etichetta di riservatezza a un documento di Microsoft Word e quindi si visualizzerà il contrassegno del contenuto (piè di pagina) generato dall'etichetta. NOTA: quando si utilizza Microsoft Word online, è possibile che si verifichi un ritardo prima che l'opzione di selezione delle etichette di riservatezza venga visualizzata sulla barra multifunzione superiore.  È consigliabile completare tutti i lab rimanenti e quindi tornare a questa attività.

1. Si dovrebbe ancora trovarsi nella home page del portale di Microsoft Purview. 
1. Nel portale di Microsoft Purview selezionare l'icona dell'icona **** di avvio delle app, accanto alla posizione in cui è indicato Microsoft Purview. Selezionare l'**icona di Word**.  

1. In Crea nuovo, selezionare **Documento vuoto**, quindi immettere del testo nella pagina.  Nella parte superiore della pagina, accanto all'icona di Word, selezionare il punto in cui è indicato **Documento** e rinominare il file in **Test-label** e quindi premere **INVIO** sulla tastiera.

1. All'estrema destra della barra del menu superiore (detta anche barra multifunzione) è presente una freccia verso il basso, selezionarla, quindi selezionare **Barra multifunzione classica**.  In questo modo sarà più semplice identificare l'icona di riservatezza. Selezionare **Riservatezza**, accanto all'icona del microfono. Dal menu a discesa selezionare **Riservatezza elevata** e quindi Tutti **i dipendenti**.  

1. Nella barra dei menu superiore, selezionare **Visualizza**, quindi selezionare **Visualizzazione di lettura**.

1. Si noti che il documento include il piè di pagina "Classificato come estremamente riservato".  

1. Chiudere le schede di Microsoft Word aperte nel browser per uscire da Word, ma mantenere aperta la scheda del browser alla home page di Microsoft Purview.

### Revisione

In questo lab sono state esaminate le funzionalità delle etichette di riservatezza.  Sono state esaminate le impostazioni per un'etichetta di riservatezza esistente e i criteri corrispondenti per pubblicare l'etichetta.  L'etichetta è stata applicata e, poiché l'etichetta includeva contrassegni di contenuto, è stato possibile visualizzare il contrassegno nel documento a cui è stata applicata l'etichetta.
