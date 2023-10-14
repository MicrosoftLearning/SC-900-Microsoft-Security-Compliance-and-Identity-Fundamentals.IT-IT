<!---
---
Demo: Titolo: 'Microsoft Defender for Cloud Apps' Modulo: 'Percorso di apprendimento: Descrivere le funzionalità delle soluzioni di sicurezza Microsoft; Modulo 4: Descrivere le funzionalità di protezione dalle minacce di Microsoft 365; Unità 5: Descrivere Microsoft Defender for Cloud Apps'
---
--->

# Dimostrazione: Microsoft Defender for Cloud Apps

Questa demo corrisponde al contenuto di Learn seguente:

- Percorso di apprendimento: Descrivere le funzionalità delle soluzioni di sicurezza Microsoft
- Modulo: Descrivere le funzionalità di protezione dalle minacce di Microsoft 365
- Unità: Descrivere Microsoft Defender for Cloud Apps

## Scenario demo

In questa demo verranno presentate le funzionalità di Microsoft Defender for Cloud Apps.  Lo studente verrà guidato attraverso le informazioni disponibili nel dashboard di Cloud Discovery, il catalogo delle app cloud, le funzionalità disponibili per esaminare i risultati con il log attività e i file, nonché i modi a disposizione per controllare l'impatto sull'organizzazione attraverso i criteri.  Nota: un'organizzazione deve avere una licenza per usare Microsoft Defender for Cloud Apps, che è un servizio in abbonamento basato sull'utente.  

### Demo Parte 1: Esplorare Cloud Discovery

1. Nella barra degli indirizzi immettere **admin.microsoft.com**. Accedere con le credenziali di amministratore per il tenant di Microsoft 365 fornito dall'host del lab autorizzato (ALH), per accedere alla interfaccia di amministrazione di Microsoft 365.

1. Dal riquadro di spostamento sinistro dell'interfaccia di amministrazione di Microsoft 365, selezionare **Mostra tutto**.

1. In Interfacce di amministrazione selezionare **Sicurezza**.  Si apre una nuova pagina del browser alla pagina di benvenuto del portale Microsoft 365 Defender.  

1. Se è la prima volta che si visita il portale Microsoft 365 Defender, potrebbe comparire una finestra pop-up per una breve presentazione.

1. Dal riquadro di spostamento sinistro selezionare **App cloud** per espandere l'elenco e quindi selezionare **Cloud Discovery**. Verrà aperta la visualizzazione Dashboard.  Presentare le informazioni disponibili nel dashboard. Nella visualizzazione del dashboard è possibile selezionare schede diverse nella parte superiore della pagina.  Presentare ogni scheda nella parte superiore della pagina.

1. Selezionare **App individuate**. La finestra delle app individuate fornisce una vista più dettagliata delle app individuate, inclusi punteggio di rischio, traffico, numero di utenti e altro.
    1. Da qualsiasi voce dell'elenco, selezionare i **puntini di sospensione** nella colonna delle azioni della tabella.  Notare le varie opzioni disponibili, inclusa la funzione di contrassegnare un'app come approvata o non approvata.  Selezionare di nuovo i puntini di sospensione per chiudere la casella delle azioni.
    1. Selezionando una voce specifica si apre una pagina di dettagli per l'applicazione specifica.  Selezionare una voce dall'elenco.  Per l'elemento selezionato, selezionare la scheda **Utilizzo dell'app cloud** per visualizzare informazioni più dettagliate, tra cui **Utilizzo**, **Utenti**, **Indirizzi IP** e **Avvisi**. Al termine dell'esplorazione della pagina dei dettagli, tornare alla pagina delle app individuate selezionando **Cloud Discovery** nel percorso di navigazione nella parte superiore della pagina.  Se si seleziona Cloud Discovery nel riquadro di spostamento sinistro, si tornerà alla visualizzazione del dashboard.
    1. Nella parte superiore della pagina selezionare la scheda **Indirizzi IP**. In questa scheda sono disponibili dati, tra cui il numero di transazioni, la quantità di traffico e di caricamenti, in base all'indirizzo IP.  È anche possibile filtrare per indirizzo IP specifico o esportare i dati per ulteriori analisi.
    1. Nella parte superiore della pagina selezionare **Utenti**.  Questo è lo stesso tipo di informazioni fornite quando si selezionano gli indirizzi IP, ma sono elencate per i singoli utenti.  Anche qui, è possibile filtrare per utente specifico ed esportare i dati per ulteriori analisi.

1. Un aspetto importante da sottolineare è che le informazioni nella pagina Cloud Discovery e nelle schede correlate si basano su report snapshot dai log del traffico caricati manualmente da firewall e proxy o da report continui che analizzano tutti i log che vengono inoltrati dalla rete usando Cloud App Security.  Per vedere dove si configurano questi report, selezionare **Azioni** nell'angolo in alto a destra della pagina.
    1. Selezionare la prima opzione, **Crea report snapshot di Cloud Discovery** e quindi selezionare **Avanti**. Qui si compilano i dettagli richiesti e si caricano i registri del traffico per generare e caricare un report.  Selezionare **Esci** e, se richiesto di confermare, selezionare di nuovo **Esci**.  I dati visualizzati per il tenant del lab provengono da un report snapshot. Queste informazioni sono riportate in alto nella finestra di Cloud Discovery.
    1. Per vedere l'opzione per i report continui, selezionare **Azioni** nell'angolo in alto a destra della pagina e dal menu a discesa selezionare **Configurare il caricamento automatico**.  Non ci sono origini dati collegate, ma è qui che si può aggiungere un'origine dati. Selezionare **Aggiungi origine dati**, quindi selezionare la freccia a discesa nel campo **Selezionare l'appliance** per visualizzare i tipi di appliance che è possibile connettere come origine dati.  Selezionare **Annulla** per uscire.
    1. Dal riquadro di spostamento sinistro selezionare **Cloud Discovery** per tornare alla pagina di Cloud Discovery.

1. Con Microsoft 365 Defender for Cloud Apps è possibile connettersi alle app direttamente configurando connettori delle app che offriranno una maggiore visibilità e controllo per le app cloud. Nell'angolo in alto a destra della schermata selezionare **Azioni** e quindi **Impostazioni di Cloud Discovery**.  Prendere nota delle impostazioni disponibili.
    1. Nel pannello di spostamento a sinistra della finestra Impostazioni app cloud selezionare **Connettori** app (potrebbe essere necessario scorrere verso il basso).
    1. La pagina Connettori app è la posizione in cui verranno visualizzati tutti i connettori app già configurati e dove è possibile aggiungere un connettore app.
    1. Verrà visualizzato Microsoft 365 elencato. Se viene visualizzato un errore di connessione, passare ai puntini di sospensione verticali sul lato destro dell'elemento della riga e selezionare **Modifica impostazioni**.  Per riconnettersi, selezionare **Connetti Office 365** nella parte inferiore della pagina. La pagina dovrebbe ora indicare che Office 365 è connesso. Selezionare **Fine**.  Lo stato verrà ora visualizzato con un segnale di avviso giallo, che indica che non è presente alcuno stato recente.  L'aggiornamento dello stato richiederà tempo, perché il periodo di tempo per l'analisi retroattiva differisce per ogni app e i tenant del lab potrebbero riscontrare ritardi più lunghi rispetto al normale.
    1. Per configurare un nuovo connettore app.  Selezionare **+Connetti un'app**.  L'elenco a discesa mostra un elenco da scegliere.  È anche possibile chiamare che l'elenco include l'opzione **Suggerisci altre app**.  
    1. Facoltativamente, è possibile aggiungere il connettore di Microsoft Azure. Nell'elenco a discesa selezionare **Microsoft Azure**.  Nella finestra popup di Microsoft Azure selezionare **Connetti Microsoft Azure** e quindi selezionare **Fine**.  Verranno visualizzati lo stato connesso (se non viene visualizzato, aggiornare il browser) e informazioni sull'analisi di utenti, dati e attività.  

1. Mentre nella pagina Delle impostazioni delle app cloud, vale la pena spendere alcuni minuti anche esplorando alcune delle altre impostazioni di Cloud Discovery.  
    1. Selezionare App **di controllo app per l'accesso condizionale** e prendere nota della descrizione: "Il controllo app di accesso condizionale aggiunge funzionalità di monitoraggio e controllo in tempo reale per le app".
    1. Selezionare Microsoft Information Protection, parlare con le impostazioni disponibili.
    1. Esplorare altri utenti. Chiamare il livello di integrazione e flessibilità.

1. Tornare al dashboard di Cloud Discovery selezionando **Cloud Discovery** nel riquadro di spostamento più a sinistra.

1. Tenere aperta la pagina perché verrà usata nella parte successiva.

### Demo parte 2 - Esplorare il catalogo delle app cloud

In questa parte della demo verranno illustrate le funzionalità del catalogo delle app cloud. Cloud Discovery consente di analizzare i log del traffico in base al catalogo delle app cloud di Microsoft Defender for Cloud Apps, che include oltre 31.000 app cloud. Le app cloud, classificate e con punteggi assegnati in base a più di 80 fattori di rischio, offrono visibilità continua sull'uso di cloud, shadow IT e sul rischio di shadow IT per l'organizzazione.  

1. Dal riquadro di spostamento sinistro selezionare **Catalogo delle app cloud**.

1. Il catalogo delle app cloud consente di scegliere le app che soddisfano i requisiti di sicurezza dell'organizzazione. Gli amministratori possono applicare filtri semplici alle app, come illustrato nella parte superiore della pagina, specificando le app con approvazione, senza approvazione o senza tag, il punteggio di rischio, il fattore di rischio della conformità e il fattore di rischio della sicurezza.  Ad esempio, filtrare l'elenco in base al fattore di rischio della conformità consente di cercare standard, certificazioni e conformità specifici per l'app, ad esempio HIPAA, ISO 27001, SOC 2 e PCI-DSS. Selezionare **Fattore di rischio della conformità** per visualizzare le opzioni disponibili.  È possibile filtrare ulteriormente le app in base al punteggio di rischio spostando i dispositivi di scorrimento per il punteggio di rischio nella parte superiore della pagina. Se si sposta il dispositivo di scorrimento, assicurarsi di impostarlo in modo che l'intervallo sia compreso tra 0 e 10.

1. Gli amministratori possono anche cercare le app in base alla categoria.  Ad esempio, nel campo Cercare una categoria immettere **Social network** e quindi selezionare **Social network**.  Selezionare qualsiasi elemento dall'elenco per una visualizzazione dettagliata.  Passando il puntatore del mouse su qualsiasi argomento per una determinata categoria, verrà visualizzata un'icona di informazioni che è possibile selezionare per ottenere altre informazioni su tale argomento.

1. Tenere aperta la pagina perché verrà usata nell'attività successiva.

### Demo parte 3 - Esplorare il log attività e i file

Esplorare i modi in cui è possibile analizzare le attività registrate con il log attività e i file.

1. Dal riquadro di spostamento sinistro selezionare **Log attività**. Qui è possibile visualizzare tutte le attività delle app connesse. È possibile che non vengano visualizzati dati perché possono essere necessarie diverse ore per eseguire analisi retroattive dopo l'abilitazione del controllo e i tenant del lab potrebbero riscontrare ritardi più lunghi del normale. Notare le opzioni di filtro disponibili e l'opzione per creare un nuovo criterio dalla ricerca.

1. Per fornire la protezione dei dati, Microsoft Defender for Cloud Apps offre visibilità su tutti i file delle app connesse, ad esempio tutti i file archiviati in SharePoint e Salesforce. Nel riquadro di spostamento a sinistra selezionare ed esplorare l'opzione **File** .
    1. La possibilità di analizzare i file deve essere abilitata come parte delle impostazioni di Protezione delle informazioni delle app Cloud di Microsoft 365.  Selezionare **Abilita monitoraggio file** e selezionare la casella accanto alla posizione in cui si dice **Abilita monitoraggio file** e quindi selezionare **Salva**.  
    1. Tornare ai file selezionando **File**, elencati in app cloud, nel pannello di spostamento a sinistra. È possibile che non venga visualizzato alcun elemento elencato perché può richiedere diversi giorni prima di poter visualizzare i file, ma la sua pena chiamare che dopo che i file sono elencati è possibile filtrare i dati in base all'app, al proprietario, al livello di accesso, al tipo di file e ai criteri corrispondenti. Inoltre, si crea un nuovo criterio dalla ricerca e dall'esportazione dei dati.

1. Tenere aperta la pagina perché verrà usata nell'attività successiva.

### Demo parte 4 - Esplorare i criteri

In questa parte verranno visualizzate le opzioni disponibili per i criteri in Microsoft Defender for Cloud Apps.

1. Nel pannello di spostamento a sinistra selezionare **Criteri**.
    1. Selezionare **Gestione criteri**.  I criteri elencati offrono informazioni sul numero di avvisi generati dai criteri, la gravità e così via. Selezionando qualsiasi elemento vengono visualizzate informazioni più dettagliate sul criterio. Selezionare un elemento dall'elenco per visualizzare informazioni dettagliate sui criteri.  Parlare con alcune delle opzioni e quindi selezionare **Annulla**.
    2. Si noti che è anche possibile creare un criterio. Selezionare **+ Crea criteri** per visualizzare i tipi di criteri che è possibile creare.  Selezionare **Criteri attività** per visualizzare le diverse opzioni disponibili per la creazione del criterio.  Selezionare **Annulla** per uscire dalla finestra di configurazione.
    3. Si noti che è anche disponibile un'opzione per esportare le informazioni sui criteri.

1. Dal riquadro di spostamento sinistro selezionare **Modelli del criterio**. Per creare un criterio da uno dei modelli disponibili, selezionare il **+** lato destro dell'elemento della riga del modello.  Visualizzare le diverse opzioni di configurazione per i criteri.  Selezionare **Annulla** per uscire dalla pagina.

1. Nel pannello di spostamento a sinistra selezionare **Home** per tornare alla home page per Microsoft 365 Defender.

1. Mantenere aperta la scheda del browser se si prevede di continuare con la demo successiva.

### Verifica

In questa demo sono state presentate le funzionalità di Microsoft Defender for Cloud Apps.  Sono state presentate le informazioni disponibili nel dashboard di Cloud Discovery, il catalogo delle app cloud, le funzionalità disponibili per esaminare i risultati con il log attività e i file, nonché i modi a disposizione per controllare l'impatto sull'organizzazione attraverso i criteri.
