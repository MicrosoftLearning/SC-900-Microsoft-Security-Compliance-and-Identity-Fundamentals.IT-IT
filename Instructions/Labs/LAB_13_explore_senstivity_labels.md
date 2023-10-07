<!---
---
Lab: Titolo: 'Esplorare le etichette di riservatezza in Microsoft Purview' Percorso di apprendimento/Modulo/Unità: 'Percorso di apprendimento: Descrivere le funzionalità di conformità Microsoft; Modulo 3: Descrivere la protezione delle informazioni e la gestione del ciclo di vita dei dati in Microsoft Purview; Unità 4: Descrivere le etichette di riservatezza'
---
--->

# Laboratorio: Esplorazione delle etichette di riservatezza in Microsoft Purview

Questo lab corrisponde al contenuto di Learn seguente:

- Percorso di apprendimento: Descrivere le funzionalità di conformità Microsoft
- Modulo: Descrivere la protezione delle informazioni e la gestione del ciclo di vita dei dati in Microsoft Purview
- Unità: Descrivere le etichette di riservatezza

## Scenario del lab

In questo lab verranno esplorate le funzionalità delle etichette di riservatezza.  Verranno esaminate le impostazioni per le etichette di riservatezza esistenti che sono state create e il criterio corrispondente per pubblicare l'etichetta.   Verrà quindi illustrato come applicare un'etichetta e l'impatto della stessa dal punto di vista dell'utente.

**Tempo stimato**: 20-25 minuti

### Attività 1

In questa attività si comprenderanno le funzioni delle etichette di riservatezza esaminando le impostazioni di un'etichetta di riservatezza esistente che è stata creata e il criterio corrispondente per pubblicare l'etichetta.

1. Aprire la scheda del browser per la home page di Microsoft Purview.  Se è stata chiusa in precedenza, aprire una scheda del browser e immettere **https://admin.microsoft.com**. Accedere con le credenziali di amministratore per il tenant di Microsoft 365 fornito dall'host del lab autorizzato (ALH). Nel riquadro di spostamento sinistro del interfaccia di amministrazione di Microsoft 365 selezionare **Mostra tutto** e quindi Selezionare **Conformità**.  Si apre una nuova pagina del browser alla pagina di benvenuto del portale di conformità di Microsoft Purview.   

1. Nel pannello di spostamento a sinistra, in Soluzioni espandere **Information Protection** e quindi selezionare **Panoramica**. Prendere nota dell'avviso nella parte superiore della pagina e scorrere verso il basso per visualizzare le informazioni disponibili.
   1. Nella pagina Panoramica è possibile che venga visualizzata una casella di informazioni gialla che indica che l'organizzazione non ha attivato la possibilità di elaborare il contenuto nei file online di Office con etichette di riservatezza crittografate applicate e archiviate in OneDrive e SharePoint.  Selezionare **Attiva ora**.  Una volta eseguita questa operazione, può verificarsi un ritardo per la propagazione dell'impostazione nel sistema e sono necessari passaggi aggiuntivi per proteggere Teams, siti di SharePoint e Gruppi di Microsoft 365.

1. Nel pannello di spostamento a sinistra selezionare **Etichette**.
   1. Nella pagina Etichette potrebbe essere visualizzata una casella di informazioni gialla che indica che l'organizzazione non ha attivato la possibilità di elaborare il contenuto nei file online di Office con etichette di riservatezza crittografate applicate e archiviate in OneDrive e SharePoint.  Selezionare **Attiva ora**.  Una volta eseguita questa operazione, può verificarsi un ritardo per la propagazione dell'impostazione nel sistema e sono necessari passaggi aggiuntivi per proteggere Teams, siti di SharePoint e Gruppi di Microsoft 365.
1. Alcune etichette sono state preconfigurate nel tenant del lab di Microsoft 365, per praticità. Espandere l'etichetta **denominata Highly Confidential** selezionando , **>** quindi selezionare **Tutti i dipendenti**.  Si apre una finestra contenente informazioni su questa etichetta.  Questa etichetta è impostata per supportare sia la crittografia che il contrassegno dei contenuti.  Selezionare **l'icona a forma di matita** nella parte superiore della pagina per visualizzare alcune delle impostazioni di configurazione di base. Se l'icona a forma di matita non viene visualizzata, selezionare i puntini di sospensione.
    1. La configurazione inizia fornendo un nome e una descrizione per l'etichetta.  Non modificare nulla.  Selezionare **Avanti** nella parte inferiore della pagina.
    1. Osservare l'ambito di questa etichetta.  L'ambito è impostato su File & Messaggi di posta elettronica.  Non modificare nulla.  Selezionare **Avanti** nella parte inferiore della pagina.
    1. Questa schermata successiva consente di scegliere le impostazioni di protezione per gli elementi etichettati. Si noti che questa etichetta è configurata per supportare la crittografia e il contrassegno del contenuto. Non modificare nulla.  Selezionare **Avanti** nella parte inferiore della pagina.
        1. La finestra Crittografia mostra la configurazione per le impostazioni di crittografia. Esaminare le impostazioni correnti, ma non modificare nulla. Si noti che l'accesso utente al contenuto è impostato su non scadere mai e consentire sempre l'accesso offline.  È anche possibile assegnare autorizzazioni a specifici utenti e gruppi in modo che solo loro possano interagire con il contenuto a cui è applicata questa etichetta.  Sotto utenti e gruppi, il tenant è definito in modo che tutti gli utenti nel tenant possano vedere il contenuto a cui è applicata questa etichetta.  Non modificare alcuna impostazione.  Selezionare **Avanti** nella parte inferiore della pagina.
        1. Nella pagina dei contrassegni dei contenuti, prendere nota del riquadro informativo nella parte superiore della pagina.  I contrassegni dei contenuti saranno applicati ai documenti, ma solo le intestazioni e i piè di pagina saranno applicati ai messaggi di posta elettronica. In altre parole, le filigrane non vengono applicate alle e-mail.  Il contrassegno del contenuto associato a questa etichetta è un piè di pagina.  Non modificare alcuna impostazione.  Selezionare **Avanti** nella parte inferiore della pagina.
    1. Ora ci si trova nell'etichettatura automatica per la finestra di file e messaggi e-mail.  Leggere la descrizione dell'etichettatura automatica sulla parte alta della pagina e la casella delle informazioni sotto.  Si noti anche che questa etichetta è impostata per l'etichettatura automatica per condizioni specifiche. Non modificare alcuna impostazione.  Selezionare **Avanti** nella parte inferiore della pagina.
    1. La prossima finestra definisce le impostazioni di protezione per i team, i gruppi e i siti a cui è applicata questa etichetta. Questa funzionalità non è abilitata, selezionare **Avanti** nella parte inferiore della pagina.
    1. Questa finestra successiva è una funzionalità di anteprima per applicare automaticamente questa etichetta agli asset di dati strutturati in Microsoft Purview Data Map (ad esempio SQL, Synapse e altro) che contengono i tipi di informazioni sensibili scelti.  Questa funzionalità non è abilitata. Selezionare **Annulla** in fondo alla pagina per uscire dalla configurazione guidata dell'etichetta e tornare alla pagina Information Protection.

1. Nel pannello di spostamento a sinistra selezionare **Criteri etichetta**.  È attraverso i criteri delle etichette che le etichette di riservatezza possono essere pubblicate.  Il tenant di Microsoft 365 è stato configurato con alcuni criteri di etichetta, per praticità.

1. In questo caso selezionare **Criterio etichetta di riservatezza globale**.  Si apre una finestra contenente informazioni sul criterio.  Si noti la descrizione, questo criterio di etichetta è stato configurato per fungere da criterio di etichetta di riservatezza predefinito per tutti gli utenti e i gruppi. Questo criterio serve per pubblicare la maggior parte delle etichette preconfigurate per questo tenant del lab Microsoft 365 ed elencate nella scheda delle etichette.  

1. Selezionare **Modifica criterio** nella parte superiore della finestra.
    1. Esaminare la descrizione per "Scegliere le etichette di riservatezza da pubblicare".  Si notino le etichette elencate.  Non modificare alcuna impostazione.  Selezionare **Avanti** nella parte inferiore della pagina.
    1. Esaminare la descrizione per "Assegnare le unità di amministrazione". Le unità di Amministrazione sono impostate sulla directory completa e non modificano le impostazioni. Selezionare **Avanti**.  
    1. Esaminare la descrizione per "Pubblica in utenti e gruppi".  Notare che questa etichetta è disponibile per tutti gli utenti.  Non modificare alcuna impostazione.  Selezionare **Avanti** nella parte inferiore della pagina.
    1. Rivedere le impostazioni dei criteri. Selezionare **Richiedi agli utenti di applicare un'etichetta ai propri messaggi di posta elettronica e documenti** ed esaminare la descrizione fornita. Selezionare **Avanti** nella parte inferiore della pagina.
    1. Esaminare la descrizione per "Applicare un'etichetta predefinita ai documenti". Non modificare alcuna impostazione.  Selezionare **Avanti** nella parte inferiore della pagina.
    1. Esaminare la descrizione per "Applicare un'etichetta predefinita ai messaggi di posta elettronica" e "Ereditare l'etichetta dagli allegati". Non modificare alcuna impostazione.  Selezionare **Avanti** nella parte inferiore della pagina.
    1. Esaminare la descrizione per "Applicare un'etichetta predefinita alle riunioni e agli eventi del calendario". Non modificare alcuna impostazione.  Selezionare **Avanti** nella parte inferiore della pagina.
    1. Esaminare la descrizione per "Applicare un'etichetta predefinita al contenuto di Power BI". Non modificare alcuna impostazione.  Selezionare **Avanti** nella parte inferiore della pagina.
    1. L'ultima opzione di configurazione è quella di dare un nome al criterio.  Poiché si sta modificando il criterio, il campo del nome è disattivato. Selezionare **Avanti** nella parte inferiore della pagina.
    1. Rivedere le impostazioni dei criteri. Selezionare **Annulla** per eliminare le modifiche e tornare alla pagina Criteri etichetta.

1. Dalla pagina Information Protection, selezionare Aggiunta automatica dell'etichetta. Esaminare la descrizione. Si noti che si creano criteri di etichettatura automatica per applicare automaticamente etichette di riservatezza ai messaggi di posta elettronica o ai file di OneDrive e SharePoint che contengono informazioni sensibili. Non sono stati preconfigurati criteri di etichetta automatica nel tenant. Per creare un nuovo criterio di etichetta automatica, selezionare Crea criteri di **etichetta automatica**.  Di seguito verranno illustrati i passaggi per creare un nuovo criterio.
    1. Per iniziare, scegliere le informazioni a cui si vuole applicare questa etichetta.  Prendere nota delle opzioni disponibili.  Selezionare **Medico e integrità** e quindi selezionare uno dei modelli disponibili.  Selezionare **Avanti**.
    1. È possibile assegnare un nome al criterio di etichetta automatica o usare il nome predefinito.  Selezionare **Avanti**.
    1. È possibile assegnare le unità di amministrazione a cui si applica questo criterio.  Lasciare il set predefinito su directory completa e selezionare **Avanti**.
    1. Prendere nota delle posizioni disponibili in cui si vuole applicare l'etichetta.  Lasciare i valori predefiniti e selezionare **Avanti**.
    1. È possibile configurare regole comuni o avanzate che definiscono il contenuto a cui viene applicata l'etichetta.  Lasciare il set predefinito su Regole comuni e selezionare **Avanti**.
    1. È possibile definire regole per il contenuto in tutte le posizioni.  L'etichetta verrà applicata al contenuto che corrisponde alle regole definite in questa pagina.  Per il modello selezionato, verrà visualizzato un elemento della riga. Espanderla per visualizzare le condizioni che si applicano.  Lasciare tutte le impostazioni predefinite e selezionare **Avanti**.
    1. Scegliere un'etichetta da applicare automaticamente selezionando **Scegli un'etichetta**.  Scegliere un'etichetta e quindi **selezionare Aggiungi**. Selezionare **Avanti**.
    1. È possibile configurare impostazioni aggiuntive per la posta elettronica. Lasciare i valori predefiniti e selezionare **Avanti**.
    1. È possibile decidere di testare i criteri ora o versioni successive.  Selezionare **Lascia i criteri disattivati** e quindi selezionare **Avanti**.
    1. Esaminare le impostazioni e selezionare **Crea criteri** e quindi selezionare **Fine**.

1. Nel pannello di spostamento a sinistra selezionare **Home** per tornare alla Portale di conformità di Microsoft Purview.

1. Tenere aperta la pagina perché verrà usata nell'attività successiva.

### Attività 2

In questa attività si esaminerà il processo di applicazione di un'etichetta di riservatezza a un documento di microsoft Word e quindi visualizzare il contrassegno del contenuto (filigrana) generato dall'etichetta. NOTA: quando si usa Microsoft Word online, è possibile che si verifichi un ritardo prima che l'opzione per selezionare Etichette di riservatezza venga visualizzata nella barra multifunzione superiore.  È consigliabile completare tutti i lab rimanenti e quindi tornare a questa attività.

1. Nella home page del portale di conformità di Microsoft Purview selezionare l'**icona di avvio dell'app** accanto a Contoso Electronics. Selezionare l'**icona di Word**.  

1. In Crea nuovo selezionare **Documento vuoto**, quindi immettere un testo nella pagina.  Nella parte superiore della pagina selezionare la freccia in giù accanto a Documento - Salvato, nella casella Nome file immettere **Etichetta di test** e quindi premere **INVIO**.

1. Nella barra dei menu superiore selezionare **Icona Riservatezza, l'icona** a destra dell'icona del microfono (a seconda delle dimensioni dello schermo, potrebbe essere necessario selezionare i puntini di sospensione e quindi selezionare la riservatezza). Nell'elenco a discesa selezionare **Altamente riservato** e quindi **Tutti i dipendenti**.  NOTA: quando si usa Microsoft Word online, è possibile che si verifichi un ritardo prima che l'opzione per selezionare Etichette di riservatezza venga visualizzata nella barra multifunzione superiore.  È consigliabile completare tutti i lab rimanenti e quindi tornare a questa attività.

1. Dalla barra dei menu in alto, selezionare **Visualizzazione**, poi selezionare **Visualizzazione di lettura**.

1. Si noti come il documento include il piè di pagina "Classificato come altamente riservato".  

1. Chiudere le schede di Microsoft Word aperte sul browser per uscire da Word.

### Attività 3 (facoltativa)

Ricordare dalla prima parte della demo che l'etichetta Alta riservatezza - Tutti i dipendenti è configurata per la crittografia. In base alle autorizzazioni configurate con questa etichetta, gli utenti nel tenant Contoso sono autorizzati a visualizzare qualsiasi documento o messaggio di posta elettronica con l'etichetta applicata.  In questa sezione si invierà il documento creato in precedenza, che include l'etichetta Altamente riservata - Tutti i dipendenti, a un indirizzo di posta elettronica a cui si ha accesso (indirizzo di posta elettronica personale o posta elettronica Microsoft) e che non fa parte del dominio WWLxZZZZ.OnMicrosoft.com.  

1. Nella home page del portale di conformità di Microsoft Purview selezionare l'**icona di avvio dell'app** accanto a Contoso Electronics. Selezionare l'**icona di Outlook**.

1. Selezionare **Nuova posta** nell'angolo superiore sinistro della schermata.  Inserire un indirizzo e-mail a cui si ha accesso e che non fa parte del dominio WWLxZZZZ.OnMicrosoft.com e immettere **Test** nell'oggetto.

1. Selezionare **Associa** (icona del foglio).

1. Selezionare **OneDrive**.

1. Assicurarsi che sia selezionata la scheda **Recenti** nel pannello di spostamento a sinistra.  Nell'elenco visualizzato selezionare il documento **Test-label.docx** creato e a cui è stata applicata l'etichetta Alta riservatezza - Tutti i dipendenti. Selezionare la freccia a discesa **Condividi collegamento** e selezionare **Collega**.  Fare clic su **Invia**.

1. Controllare l'e-mail a cui è stato inviato il documento.  Nota: il messaggio di posta elettronica può essere indirizzato alla cartella della posta indesiderata.  Il messaggio di posta elettronica viene inviato correttamente, ma quando si tenta di aprire il file di word collegato, che è stato originariamente etichettato come altamente riservato - Tutti i dipendenti, verrà visualizzata una notifica che non si dispone dell'autorizzazione per aprire il documento.

1. Chiudere Outlook, ma mantenere aperta la scheda del browser nella home page di Microsoft Purview.

### Verifica

In questo lab verranno esplorate le funzionalità delle etichette di riservatezza.  Verranno visualizzate le impostazioni per le etichette di riservatezza esistenti già create e i criteri corrispondenti per pubblicare l'etichetta.   Verrà quindi illustrato come applicare un'etichetta e l'impatto della stessa dal punto di vista dell'utente.
