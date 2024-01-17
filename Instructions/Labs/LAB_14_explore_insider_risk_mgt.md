<!---
---
Lab: Titolo: 'Esplorare la gestione dei rischi Insider in Microsoft Purview' Percorso di apprendimento/Modulo/Unità: 'Percorso di apprendimento: Descrivere le funzionalità di conformità Microsoft; Modulo 4: Descrivere le funzionalità per rischi Insider in Microsoft Purview; Unità 2: Descrivere la gestione dei rischi Insider'
---
--->

# Lab: Esplorare la gestione dei rischi Insider in Microsoft Purview

Questo lab corrisponde al contenuto di Learn seguente:

- Percorso di apprendimento: Descrivere le funzionalità di conformità Microsoft
- Modulo: Descrivere le funzionalità per rischi Insider in Microsoft Purview
- Unità: Descrivere la gestione dei rischi Insider

## Scenario laboratorio

In questo lab, verrà descritto il processo di impostazione di un criterio di rischio Insider, insieme ai prerequisiti di base per configurare e usare i criteri di gestione dei rischi Insider.  Nota: questo lab fornirà soltanto visibilità degli elementi richiesti per impostare la gestione dei rischi Insider e le opzioni associate alla creazione di un criterio.  Questo lab non include un'attività per attivare il criterio, in quanto il numero di eventi necessari per attivare un criterio e il tempo necessario non rientrano nell'ambito di questo esercizio.

**Tempo stimato:** 45-60 minuti

### Attività 1

In questa attività l'utente, in qualità di amministratore globale, abiliterà le autorizzazioni per la Gestione dei rischi Insider.  Nello specifico, verranno aggiunti utenti al gruppo di ruoli Gestione dei rischi Insider per assicurare che gli utenti designati possano accedere e gestire le funzionalità di gestione dei rischi Insider.  Possono essere necessari fino a 30 minuti affinché le autorizzazioni del gruppo di ruoli vengano applicate agli utenti dell'organizzazione.

1. Aprire la scheda del browser sulla Home page di Microsoft Purview.  Se in precedenza è stata chiusa, aprire una scheda del browser e immettere **https://admin.microsoft.com**. Accedere con le credenziali di amministratore per il tenant di Microsoft 365 fornito tramite un provider di servizi di hosting per lab autorizzato (ALH). Dal riquadro di spostamento dell'interfaccia di amministrazione di Microsoft 365, selezionare **Mostra tutto**, quindi selezionare **Conformità**.  Si apre una nuova pagina del browser alla pagina di benvenuto del portale di conformità di Microsoft Purview.  

1. Dal riquadro di spostamento a sinistra, espandere **Ruoli e ambiti** e selezionare **Autorizzazioni**.

1. Sotto le soluzioni Microsoft Purview, selezionare **Ruoli**.

1. Nel campo della ricerca, digitare **Rischio Insider** e premere INVIO sulla tastiera.  Si notino i numerosi ruoli visualizzati.  Ognuno di questi presenta diversi livelli di accesso.  Selezionare **Gestione dei rischi Insider** e rivedere la descrizione.  Scorrere verso il basso fino a Membri e notare che sono elencati l'amministratore MOD e Megan Bowen. Chiudere la finestra selezionando la **X** nella parte superiore a destra della finestra.

1. Dal riquadro di spostamento sinistro selezionare **Home** per tornare alla pagina del portale di conformità di Microsoft Purview.

1. Mantenere questa scheda del browser aperta, perché servirà per un'attività successiva.

### Attività 2 (NOTA: SALTARE l'Attività 2 se è stata eseguita l'attività di configurazione del lab per abilitare il log di controllo.)

La gestione dei rischi Insider utilizza i log di controllo di Microsoft 365 per le informazioni dettagliate sugli utenti e sulle attività identificate nei criteri e nelle informazioni dettagliate analitiche. In questa attività, verrà abilitata la funzione di ricerca nel log di controllo. Nota: è possibile che i risultati della ricerca nel log di controllo richiedano alcune ore dopo l'attivazione della ricerca nel log di controllo.  Sebbene possano essere necessarie diverse ore prima di poter effettuare una ricerca nel log di controllo, ciò non influisce sulla possibilità di completare altre attività di questo lab.

1. Selezionare la scheda del browser con etichetta **Home - Conformità Microsoft 365**.  Se in precedenza è stata chiusa questa scheda del browser, aprire Microsoft Edge e nella barra degli indirizzi immettere **compliance.microsoft.com** e accedere con le credenziali di amministratore.

1. Nel riquadro di spostamento a sinistra, sotto Soluzioni, selezionare **Controllo**.

1. Verificare che la scheda **Nuova ricerca**sia selezionata (sottolineata).

1. Una volta visualizzata la pagina Controllo, attendere 2-3 minuti.  Se il controllo NON è abilitato, verrà visualizzata una barra blu nella parte superiore della pagina con l'indicazione di avviare la registrazione delle attività di utenti e amministratori.  Selezionare **Avvia la registrazione delle attività di utenti e amministratori**.  Una volta abilitato il controllo, la barra blu scompare.  Se la barra blu non è presente, il controllo è già abilitato e non sono richieste ulteriori azioni.

1. Tornare alla home page del portale di conformità di Microsoft Purview selezionando **Home** dal riquadro di spostamento sinistro.

1. Mantenere la scheda del browser aperta perché verrà usata nell'attività successiva.

### Attività 3

In questa attività verranno esaminate le impostazioni associate alla soluzione Gestione dei rischi Insider.  Le impostazioni di gestione dei rischi Insider si applicano a tutti i criteri di gestione dei rischi Insider, indipendentemente dal modello scelto al momento della creazione.

1. Dovrebbe essere ancora aperta la home page del portale di conformità di Microsoft Purview. In caso contrario, aprire la scheda del browser **Home - Conformità di Microsoft 365**.

1. Nel riquadro di spostamento a sinistra, sotto la voce Soluzioni, selezionare **Gestione dei rischi Insider**.

1. Prima di iniziare a configurare un criterio, esistono alcune impostazioni che un amministratore deve conoscere e configurare in base alle esigenze dell'organizzazione. Dalla pagina Gestione dei rischi Insider, selezionare l'**icona a forma di ingranaggio delle impostazioni** nell'angolo in alto a destra della finestra Gestione dei rischi Insider per accedere alle impostazioni per i rischi Insider.  
    1. Verificare di essere nella scheda **Privacy**: per gli utenti che eseguono attività che corrispondono ai criteri di rischio Insider, questa impostazione determinerà se mostrare i nomi effettivi o usare versioni anonime per nascondere le relative identità.  Per gli scopi di questa procedura dettagliata è possibile lasciare l'impostazione predefinita.
    1. Selezionare la scheda **Indicatori di criteri**. Una volta che si verifica un evento che attiva il criterio, le attività che corrispondono agli indicatori selezionati vengono utilizzate per determinare il punteggio di rischio per l'utente. Gli indicatori di criteri qui selezionati sono inclusi nei modelli di criteri di rischio Insider.  Scorrere per visualizzare tutti gli indicatori disponibili e le informazioni associate. In **Indicatori di Office** selezionare **Seleziona tutto** e quindi selezionare **Salva** nella parte inferiore della pagina (sarà necessario scorrere verso il basso).
    1. Selezionare la scheda **Intervalli dei criteri**. Gli intervalli scelti entreranno in vigore per un utente quando sarà attivata una corrispondenza per un criterio di rischio Insider.   La finestra Attivazione determina la durata del rilevamento delle attività degli utenti da parte dei criteri e viene attivata quando un utente esegue la prima attività corrispondente a un criterio. Rilevamento attività passate determina a quando risale un criterio per rilevare l'attività dell'utente e si attiva quando un utente esegue la prima attività che corrisponde a un criterio.  Lasciare invariati i valori predefiniti.
    1. Selezionare la scheda **Rilevamenti intelligenti**, quindi esaminare le opzioni.  Notare le impostazioni dei domini e del relativo rapporto con gli indicatori.
    1. Esplorare gli altri elementi elencati nelle impostazioni. Si noti che molti sono in anteprima.

1. Per tornare alla panoramica della gestione dei rischi Insider, selezionare **Gestione dei rischi Insider** nell'angolo superiore a sinistra della pagina, sopra la dicitura Impostazioni.

1. Mantenere la scheda del browser aperta perché verrà usata nell'attività successiva.

### Attività 4

In questa attività verranno esaminate le impostazioni per la creazione di un criterio.  L'obiettivo è semplicemente quello di farsi un'idea delle varie opzioni e della flessibilità associate alla creazione di un criterio.

1. Dovrebbe essere visualizzata la pagina di gestione dei rischi Insider.  Se non è visualizzata, aprire la scheda del browser denominata **Gestione dei rischi Insider - Conformità di Microsoft 365**.

1. Dalla pagina di panoramica di Gestione dei rischi Insider selezionare la scheda **Criteri**, quindi selezionare **+ Crea criterio**.  Configurare ciascuna delle seguenti schede di criteri.

    1. Modello di criterio: nella categoria Perdite di dati selezionare **Perdite di dati**.  Leggere i dettagli associati a questo modello. Nei prerequisiti, i criteri DLP vengono visualizzati con un segno di spunta in un cerchio verde per indicare che il prerequisito è soddisfatto.  È disponibile un criterio di prevenzione della perdita dei dati preconfigurato per questo tenant del lab. Seleziona **Avanti**. 
    1. Nome e descrizione: immettere il nome **SC900-InsiderRiskPolicy**, quindi selezionare **Avanti**.
    1. Utenti e gruppi: esaminare la casella informazioni.  Lasciare l'impostazione predefinita, **Includi tutti gli utenti e i gruppi**.  Seleziona **Avanti**.
    1. Contenuti a cui dare priorità: per ogni descrizione, i punteggi di rischio vengono aumentati per qualsiasi attività contenente contenuto prioritario, che a sua volta aumenta la possibilità di generare un avviso di gravità elevata. Per semplicità, selezionare **Non assegnare priorità al contenuto in questo momento** e quindi selezionare **Avanti**.
    1. Trigger: l'evento di attivazione determina quando un criterio inizierà ad assegnare punteggi di rischio all'attività di un utente.  È possibile scegliere un criterio DLP esistente o se l'utente esegue un'attività di esfiltrazione. Selezionare **Corrispondenza dell'utente con un criterio di prevenzione della perdita dei dati (DLP)** e quindi nell'elenco a discesa selezionare **Dati finanziari USA**. Seleziona **Avanti**.
    1. Indicatori: si noti che tutti gli indicatori di Office selezionati nell'attività precedente sono selezionati (è possibile verificarlo selezionando il tasto freccia in giù accanto agli indicatori di Office), quindi selezionare **Avanti**.
    1. Nella pagina Opzioni di rilevamento lasciare tutte le impostazioni predefinite, ma leggere la descrizione associata alle varie opzioni e passare il puntatore del mouse sull'icona delle informazioni per ottenere informazioni più dettagliate su un'impostazione specifica.  Seleziona **Avanti**.
    1. Nella pagina per decidere se usare le soglie predefinite o le soglie degli indicatori del cliente lasciare l'impostazione predefinita **Soglie predefinite** e quindi selezionare **Avanti**.
    1. Termine: esaminare le impostazioni, selezionare **Invia**.
    1. Esaminare la descrizione di ciò che accade successivamente, quindi selezionare **Fine**.

1. Si è di nuovo nella scheda Criteri della pagina Gestione dei rischi Insider.  Il criterio creato sarà incluso nell'elenco.  Se non è visualizzato, selezionare l'icona **Aggiorna**.

1. Gli amministratori possono iniziare immediatamente ad assegnare punteggi di rischio agli utenti in base all'attività rilevata dai criteri selezionati. In questo modo viene ignorato il requisito che prevede che venga prima rilevato un evento di attivazione, ad esempio una corrispondenza con criteri DLP.  A questo scopo, un amministratore dovrà selezionare il quadratino vuoto accanto al nome del criterio per selezionarlo e quindi selezionare l'opzione **Inizia calcolo punteggio attività per utenti**, disponibile sopra alla tabella dei criteri.  Verrà visualizzata una nuova finestra che richiede all'amministratore di popolare i campi disponibili. Lasciare vuoti i campi perché questa opzione non verrà configurata. Per altre informazioni sul motivo per cui un amministratore potrebbe voler eseguire questa operazione, selezionare **Perché eseguire questa operazione?**.  Chiudere la finestra selezionando la **X** nell'angolo in alto a destra della finestra.

1. Dal riquadro di spostamento a sinistra, selezionare **Home** per tornare alla pagina di destinazione del portale di conformità di Microsoft Purview.

1. Mantenere aperta la scheda del browser.

### Revisione

In questo lab, è stato descritto il processo di impostazione di un criterio di rischio Insider, insieme ai prerequisiti di base per configurare e usare i criteri di gestione dei rischi Insider.
