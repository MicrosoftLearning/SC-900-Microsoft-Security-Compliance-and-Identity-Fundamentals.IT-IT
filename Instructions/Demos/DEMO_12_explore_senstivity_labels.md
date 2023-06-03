<a name="---"></a><!---
---
Demo: Titolo: 'Etichette di riservatezza in Microsoft Purview' Percorso di apprendimento/Modulo/Unità: 'Percorso di apprendimento: Descrivere le funzionalità di conformità Microsoft; Module 3: Descrivere la protezione delle informazioni e la gestione del ciclo di vita dei dati in Microsoft Purview; Unità 4: Descrivere le etichette di riservatezza'
---
--->

# <a name="demo-sensitivity-labels-in-microsoft-purview"></a>Dimostrazione: Etichette di riservatezza in Microsoft Purview

Questa demo corrisponde al contenuto di Learn seguente:

- Percorso di apprendimento: Descrivere le funzionalità di conformità Microsoft
- Modulo: Descrivere la protezione delle informazioni e la gestione del ciclo di vita dei dati in Microsoft Purview
- Unità: Descrivere le etichette di riservatezza

## <a name="demo-scenario"></a>Scenario demo

Questa demo mostra le funzionalità delle etichette di riservatezza.  Verranno esaminate le impostazioni per le etichette di riservatezza esistenti che sono state create e il criterio corrispondente per pubblicare l'etichetta.   Verrà quindi illustrato come applicare un'etichetta e l'impatto della stessa dal punto di vista dell'utente.  **NOTA**: la prima volta che si usa Word online con il tenant di Microsoft 365, la visualizzazione dell'opzione Riservatezza sulla barra multifunzione può richiedere 15 minuti.  I relatori devono eseguire la seconda parte della demo prima della lezione per garantire un tempo sufficiente per la visualizzazione dell'opzione.

### <a name="demo-part-1"></a>Demo parte 1

Questa demo illustrerà le impostazioni per un'etichetta di riservatezza esistente e il criterio corrispondente per pubblicare l'etichetta.

1. Aprire Microsoft Edge. Nella barra degli indirizzi immettere **admin.microsoft.com**.

1. Accedere con le credenziali di amministratore.
    1. Nella finestra Accedi immettere **admin@WWLxZZZZZZ.onmicrosoft.com** (dove ZZZZZZ è l'ID tenant univoco fornito dal proprio provider di hosting del lab) e quindi selezionare **Avanti**.
    1. Immettere la password di amministratore, che dovrebbe essere fornita dal proprio provider di hosting del lab. Fare clic su **Accedi**.
    1. Quando compare la domanda se rimanere connessi, selezionare **Sì**. In questo modo si accede alla pagina dell'interfaccia di amministrazione di Microsoft 365.

1. Dal riquadro di spostamento sinistro dell'interfaccia di amministrazione di Microsoft 365, selezionare **Mostra tutto**.

1. In Interfacce di amministrazione selezionare **Conformità**.  Si apre una nuova pagina del browser alla pagina di benvenuto del portale di conformità di Microsoft Purview.  

1. Dal riquadro di spostamento sinistro del portale di conformità di Microsoft Purview selezionare **Mostra tutto**.

1. Dal riquadro di spostamento sinistro, sotto Soluzioni, selezionare **Information Protection**.

1. Nella pagina di panoramica notare il riquadro delle informazioni giallo che indica che l'organizzazione non ha attivato la possibilità di elaborare il contenuto dei file online di Office che hanno etichette di riservatezza crittografate applicate e sono archiviati in OneDrive e SharePoint.  Selezionare **Attiva ora**.  Al termine, potrebbe esserci un ritardo nella propagazione delle impostazioni nel sistema.  Esaminare anche le informazioni disponibili in questa pagina di panoramica.

1. Selezionare la scheda **Etichette** nella parte superiore della pagina.

1. Al centro della pagina sono presenti tre etichette già create.  Selezionare **Riservato - Finanza**.  Si apre una finestra contenente informazioni su questa etichetta.  Questa etichetta è impostata per supportare sia la crittografia che il contrassegno dei contenuti.  Selezionare **Modifica etichetta** nella parte superiore della pagina per visualizzare alcune delle impostazioni di configurazione di base.
    1. La configurazione inizia fornendo un nome e una descrizione per l'etichetta.  Non modificare nulla.  Selezionare **Avanti** nella parte inferiore della pagina.
    1. Osservare l'ambito di questa etichetta.  L'ambito è impostato su File ed e-mail a cui è possibile configurare le impostazioni di crittografia e contrassegno dei contenuti per proteggere le e-mail etichettate e i file di ufficio.  Non modificare nulla.  Selezionare **Avanti** nella parte inferiore della pagina.
    1. Per l'ambito selezionato, File ed e-mail, è possibile configurare la crittografia e/o il contrassegno dei contenuti.  Osservare come è impostata la protezione per file e messaggi di posta elettronica, sia per la crittografia sia per la marcatura dei contenuti dei file.  Esaminare la definizione di ciascuna.  Non modificare nulla.  Selezionare **Avanti** nella parte inferiore della pagina.
    1. La finestra Crittografia mostra la configurazione per le impostazioni di crittografia.  Non modificare nulla.  Esaminare la casella delle informazioni sotto Configura impostazioni di crittografia ed esaminare le impostazioni configurate. Notare che la modalità con cui l'utente accede ai contenuti è impostata per non scadere mai.  È anche possibile assegnare autorizzazioni a specifici utenti e gruppi in modo che solo loro possano interagire con il contenuto a cui è applicata questa etichetta.  Sotto utenti e gruppi, il tenant è definito in modo che tutti gli utenti nel tenant possano vedere il contenuto a cui è applicata questa etichetta.  Nell'elenco è presente il team finanziario che ha autorizzazioni di Co-autore.  Non modificare alcuna impostazione.  Selezionare **Avanti** nella parte inferiore della pagina.
    1. Nella pagina dei contrassegni dei contenuti, prendere nota del riquadro informativo nella parte superiore della pagina.  I contrassegni dei contenuti saranno applicati ai documenti, ma solo le intestazioni e i piè di pagina saranno applicati ai messaggi di posta elettronica. In altre parole, le filigrane non vengono applicate alle e-mail.  Il contrassegno dei contenuti associato a questa etichetta è una filigrana.  Non modificare alcuna impostazione.  Selezionare **Avanti** nella parte inferiore della pagina.
    1. Ora ci si trova nell'etichettatura automatica per la finestra di file e messaggi e-mail.  Leggere la descrizione dell'etichettatura automatica sulla parte alta della pagina e la casella delle informazioni sotto.  Si noti anche che questa etichetta è impostata per l'etichettatura automatica per condizioni specifiche. Non modificare alcuna impostazione.  Selezionare **Avanti** nella parte inferiore della pagina.
    1. La prossima finestra definisce le impostazioni di protezione per i team, i gruppi e i siti a cui è applicata questa etichetta. Questa funzionalità non è abilitata, selezionare **Avanti** nella parte inferiore della pagina.
    1. La prossima finestra è una funzionalità di anteprima per applicare automaticamente questa etichetta alle colonne del database Azure (come SQL, Synapse e altro) che contengono i tipi di informazioni sensibili scelti.  Questa funzionalità non è abilitata. Selezionare **Annulla** in fondo alla pagina per uscire dalla configurazione guidata dell'etichetta e tornare alla pagina Information Protection.

1. Dalla parte superiore della pagina Information Protection, selezionare **Criteri delle etichette**.  È attraverso i criteri delle etichette che le etichette di riservatezza possono essere pubblicate.  

1. In questo caso selezionare **Criterio etichetta di riservatezza globale**.  Si apre una finestra contenente informazioni sul criterio.  Si noti la descrizione, questo è il criterio per le etichette di riservatezza predefinito per tutti gli utenti e i gruppi. Questo criterio serve per pubblicare la maggior parte delle etichette elencate nella scheda delle etichette e viene pubblicato per tutte.  

1. Selezionare il criterio **Modifica** dalla parte superiore della finestra.
    1. Leggere la descrizione sotto "Scegli le etichette di riservatezza da pubblicare".  Osservare l'etichetta inclusa nell'elenco.  Non modificare alcuna impostazione.  Selezionare **Avanti** nella parte inferiore della pagina.
    1. Leggere la descrizione sotto "Pubblica per utenti e gruppi".  Notare che questa etichetta è disponibile per tutti gli utenti.  Non modificare alcuna impostazione.  Selezionare **Avanti** nella parte inferiore della pagina.
    1. Rivedere le impostazioni dei criteri.  Selezionare **Richiedi agli utenti di applicare un'etichetta a messaggi di posta elettronica e documenti**.  Selezionare **Avanti** nella parte inferiore della pagina.
    1. Leggere la descrizione in "Applica un'etichetta predefinita ai documenti".  Si noti che non è presente alcuna etichetta predefinita. Nel campo Etichetta predefinita selezionare la freccia in giù e quindi selezionare **Generale/Tutti i dipendenti (senza restrizioni).**  Selezionare **Avanti** nella parte inferiore della pagina.
    1. Leggere la descrizione in "Applica un'etichetta predefinita ai messaggi di posta elettronica". Non modificare alcuna impostazione.  Selezionare **Avanti** nella parte inferiore della pagina.
    1. Leggere la descrizione in "Applica un'etichetta predefinita al contenuto di Power BI". Non modificare alcuna impostazione.  Selezionare **Avanti** nella parte inferiore della pagina.
    1. L'ultima opzione di configurazione è quella di dare un nome al criterio.  Poiché si sta modificando il criterio, il campo del nome è disattivato. Selezionare **Avanti** nella parte inferiore della pagina.
    1. Esaminare le impostazioni dei criteri e selezionare **Invia**, quindi selezionare **Fine** per tornare alla pagina Information Protection.

1. Dalla pagina Information Protection, selezionare Aggiunta automatica dell'etichetta.  Notare che non è stato configurato alcun criterio di aggiunta automatica dell'etichetta.  Non modificare alcuna impostazione.  Ci si potrebbe chiedere perché non è presente alcun criterio, dato che la configurazione dell'etichetta è impostata sull'aggiunta automatica dell'etichetta per i file e i messaggi di posta elettronica. Tornare ai passaggi di definizione delle impostazioni di configurazione dell'etichetta e riesaminare la descrizione e le caselle informative associate all'aggiunta automatica dell'etichetta per i file e i messaggi di posta elettronica.  Suggerimento:  nella scheda dell'etichettatura automatica per il lab sulla riservatezza, viene mostrato un messaggio simile al seguente:  "Per applicare automaticamente questa etichetta ai file già salvati (in SharePoint e OneDrive) o alle e-mail già elaborate da Exchange, è necessario creare un criterio di aggiunta automatica dell'etichetta".

1. Dal riquadro di spostamento sinistro selezionare Home per tornare alla pagina del portale di conformità di Microsoft Purview.

1. Tenere aperta la pagina perché verrà usata nell'attività successiva.

### <a name="demo-part-2"></a>Demo parte 2

Questo passaggio illustrerà il processo di applicazione di un'etichetta dal punto di vista dell'utente (in questo caso l'utente è l'amministratore).  Allo scopo di visualizzare l'impatto dell'applicazione dell'etichetta, si selezionerà l'etichetta Riservato - Finanza perché questa etichetta applica una filigrana.

1. Nella home page del portale di conformità di Microsoft Purview selezionare l'**icona di avvio dell'app** accanto a Contoso Electronics. Selezionare l'**icona di Word**.  

1. Selezionare **+ Nuovo documento vuoto**, quindi immettere il testo nella pagina.  Nella barra blu nella parte superiore della pagina selezionare la freccia in giù accanto a Documento - Salvato, nella casella Nome file immettere **Etichetta di test** e quindi premere **INVIO**.

1. Nella barra dei menu superiore selezionare **Icona Riservatezza** (icona a destra dell'icona del microfono). Se questa opzione non viene visualizzata immediatamente, aggiornare la pagina. Nell'elenco a discesa selezionare **Riservato - Finanza**.  
1. 
1. Dalla barra dei menu in alto, selezionare **Visualizzazione**, poi selezionare **Visualizzazione di lettura**.

1. Osservare in che modo il documento include la filigrana.  

1. Chiudere le schede di Microsoft Word aperte sul browser per uscire da Word.

### <a name="demo-part-3-optional"></a>Demo parte 3 (facoltativa)

Si ricordi dalla prima parte della demo che l'etichetta Riservato - Finanza è configurata per la crittografia. In base alle autorizzazioni configurate con questa etichetta, gli utenti nel tenant Contoso sono autorizzati a visualizzare qualsiasi documento o messaggio di posta elettronica con l'etichetta applicata.  In questa sezione si invierà un documento creato in precedenza, che include l'etichetta Riservato - Finanza, a un indirizzo di posta elettronica a cui si ha accesso (ad esempio, un indirizzo di posta elettronica personale o il proprio indirizzo di posta elettronica Microsoft) e che NON fa parte del dominio WWLxZZZZ.OnMicrosoft.com.  

1. Nella home page del portale di conformità di Microsoft Purview selezionare l'**icona di avvio dell'app** accanto a Contoso Electronics. Selezionare l'**icona di Outlook**.

1. Selezionare **Nuovo messaggio** dall'angolo in alto a sinistra dello schermo.  Inserire un indirizzo e-mail a cui si ha accesso e che non fa parte del dominio WWLxZZZZ.OnMicrosoft.com e immettere **Test** nell'oggetto.

1. Selezionare **Allega**.

1. Selezionare **Cerca nei percorsi sul cloud**.

1. Dall'elenco che appare, selezionare il documento creato e al quale è stata applicata l'etichetta **Etichetta di test**. Selezionare **Avanti** e selezionare **Allega come copia**.  Fare clic su **Invia**.

1. Controllare l'e-mail a cui è stato inviato il documento.  L'e-mail potrebbe essere finita nella cartella della posta indesiderata.  Il messaggio di posta elettronica viene inviato correttamente, ma quando si tenta di aprire il file di Word allegato, che è stato originariamente etichettato come Riservato - Finanza, verrà visualizzata una notifica per segnalare che non si è autorizzati ad aprire il documento.

1. Chiudere le schede del browser aperte.

### <a name="review"></a>Verifica

In questa demo sono state presentate le etichette di riservatezza.  Sono state esaminate le impostazioni per le etichette di riservatezza esistenti che erano già state create e il criterio corrispondente per pubblicare l'etichetta. Quindi è stato illustrato come applicare un'etichetta e l'impatto della stessa dal punto di vista dell'utente.

