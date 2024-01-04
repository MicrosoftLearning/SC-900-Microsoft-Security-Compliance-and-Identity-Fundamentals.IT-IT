<!---
---
Demo: Titolo: 'Microsoft Defender for Cloud Apps' Modulo: 'Percorso di apprendimento: Descrivere le funzionalità delle soluzioni di sicurezza Microsoft; Modulo 4: Descrivere le funzionalità di protezione dalle minacce di Microsoft 365; Unità 5: Descrivere Microsoft Defender for Cloud Apps'
---
--->

# Demo: Microsoft Defender per app cloud

Questa demo corrisponde al contenuto di Learn seguente:

- Percorso di apprendimento: Descrivere le funzionalità delle soluzioni di sicurezza Microsoft
- Modulo: Descrivere le funzionalità di protezione dalle minacce di Microsoft 365
- Unità: Descrivere Microsoft Defender for Cloud Apps

## Scenario dimostrativo

In questa demo verranno presentate le funzionalità di Microsoft Defender for Cloud Apps.  Lo studente verrà guidato attraverso le informazioni disponibili nel dashboard di Cloud Discovery, il catalogo delle app cloud, le funzionalità disponibili per esaminare i risultati con il log attività e i file, nonché i modi a disposizione per controllare l'impatto sull'organizzazione attraverso i criteri.  Nota: un'organizzazione deve avere una licenza per usare Microsoft Defender for Cloud Apps, che è un servizio in abbonamento basato sull'utente.  

### Demo Parte 1: Esplorare Cloud Discovery

1. Nella barra degli indirizzi immettere **admin.microsoft.com**. Eseguire l'accesso con le credenziali di amministratore per il tenant di Microsoft 365 fornito dal proprio provider di servizi di hosting per lab autorizzato (ALH) per accedere all'interfaccia di amministrazione di Microsoft 365.

1. Dal riquadro di spostamento a sinistra dell'interfaccia di amministrazione di Microsoft 365, selezionare **Mostra tutto**.

1. In Interfacce di amministrazione selezionare **Sicurezza**.  Verrà visualizzata una nuova pagina del browser con la pagina di benvenuto del portale Microsoft 365 Defender.  

1. Se è la prima volta che si visita il portale di Microsoft 365 Defender, è possibile che venga visualizzata una finestra a comparsa per una breve presentazione.

1. Dal riquadro di spostamento sinistro selezionare **App cloud** per espandere l'elenco e quindi selezionare **Cloud Discovery**. Verrà aperta la visualizzazione Dashboard.  Presentare le informazioni disponibili nel dashboard. Nella visualizzazione del dashboard è possibile selezionare schede diverse nella parte superiore della pagina.  Presentare ogni scheda nella parte superiore della pagina.

1. Selezionare **App individuate**. La finestra App individuate offre una visualizzazione più dettagliata delle app individuate, tra cui punteggio di rischio, traffico, numero di utenti e altro ancora.
    1. Da qualsiasi elemento dell'elenco, selezionare i **puntini di sospensione** nella colonna delle azioni della tabella.  Notare le varie opzioni disponibili, inclusa la possibilità di contrassegnare un'app come approvata o non approvata.  Selezionare di nuovo i puntini di sospensione per chiudere la casella delle azioni.
    1. Selezionando una voce specifica, verrà visualizzata una pagina Dettagli per l'app relativa.  Selezionare un'app dall'elenco.  Per l'elemento selezionato, selezionare la scheda **Utilizzo dell'app cloud** per visualizzare informazioni più dettagliate, tra cui **Utilizzo**, **Utenti**, **Indirizzi IP** e **Avvisi**. Al termine dell'esplorazione della pagina dei dettagli, tornare alla pagina delle app individuate selezionando **Cloud Discovery** nel percorso di navigazione nella parte superiore della pagina.  Se si seleziona Cloud Discovery nel riquadro di spostamento sinistro, si tornerà alla visualizzazione del dashboard.
    1. Nella parte superiore della pagina selezionare la scheda **Indirizzi IP**. In questa scheda sono disponibili dati, tra cui il numero di transazioni, la quantità di traffico e di caricamenti, in base all'indirizzo IP.  Tenere presente che è possibile filtrare anche in base a un indirizzo IP specifico o esportare i dati per ulteriori analisi.
    1. Nella parte superiore della pagina selezionare **Utenti**.  Questo è lo stesso tipo di informazioni fornite quando si selezionano gli indirizzi IP, ma sono elencate per i singoli utenti.  Anche in questo caso, è possibile filtrare in base a utenti specifici ed esportare i dati per un'ulteriore analisi.

1. Un aspetto importante da sottolineare è che le informazioni nella pagina Cloud Discovery e nelle schede correlate si basano su report snapshot dai log del traffico caricati manualmente da firewall e proxy o da report continui che analizzano tutti i log che vengono inoltrati dalla rete usando Cloud App Security.  Per vedere dove si configurano questi report, selezionare **Azioni** nell'angolo in alto a destra della pagina.
    1. Selezionare la prima opzione, **Crea report snapshot di Cloud Discovery** e quindi selezionare **Avanti**. Qui si compilano i dettagli richiesti e si caricano i log del traffico per generare e caricare un report.  Selezionare **Esci** e, se richiesto di confermare, selezionare di nuovo **Esci**.  I dati visualizzati per il tenant del lab provengono da un report snapshot. Queste informazioni sono riportate in alto nella finestra di Cloud Discovery.
    1. Per vedere l'opzione per i report continui, selezionare **Azioni** nell'angolo in alto a destra della pagina e dal menu a discesa selezionare **Configurare il caricamento automatico**.  Non sono presenti origini dati connesse, ma è qui che si potrebbe aggiunge un'origine dati. Selezionare **Aggiungi origine dati**, quindi selezionare la freccia a discesa nel campo **Selezionare l'appliance** per visualizzare i tipi di appliance che è possibile connettere come origine dati.  Seleziona **Annulla** per uscire.
    1. Dal riquadro di spostamento sinistro selezionare **Cloud Discovery** per tornare alla pagina di Cloud Discovery.

1. Con Microsoft 365 Defender for Cloud Apps è possibile connettersi alle app direttamente configurando connettori delle app che offriranno una maggiore visibilità e controllo per le app cloud. Nell'angolo in alto a destra della schermata selezionare **Azioni** e quindi **Impostazioni di Cloud Discovery**.  Notare le impostazioni disponibili.
    1. Dal pannello di navigazione a sinistra della finestra delle impostazioni delle app cloud, selezionare **Connettori app** (potrebbe essere necessario scorrere verso il basso).
    1. Nella pagina Connettori app si possono visualizzare i connettori app già impostati e aggiungere un connettore app.
    1. Nell'elenco è possibile visualizzare anche Microsoft 365. Se viene visualizzato un errore di connessione, passare ai puntini di sospensione verticali a destra dell'elemento della riga e selezionare **Modifica impostazioni**.  Per riconnettersi, selezionare **Connetti Office 365** nella parte inferiore della pagina. La pagina dovrebbe ora indicare che Office 365 è connesso. Selezionare **Fine**.  Lo stato verrà ora visualizzato con un segnale di avviso giallo, che indica che non è presente alcuno stato recente.  L'aggiornamento dello stato richiederà tempo, perché il periodo di tempo per l'analisi retroattiva differisce per ogni app e i tenant del lab potrebbero riscontrare ritardi più lunghi rispetto al normale.
    1. Per configurare un nuovo connettore app.  Selezionare **+ Connetti un'app**.  L'elenco a discesa mostra un elenco da cui scegliere.  Si potrebbe anche voler illustrare che l'elenco include l'opzione **Suggerisci più app**.  
    1. Facoltativamente, è possibile aggiungere il connettore di Microsoft Azure. Dall'elenco a discesa, selezionare **Microsoft Azure**.  Nella finestra popup di Microsoft Azure selezionare **Connetti Microsoft Azure** e quindi selezionare **Fine**.  Verranno visualizzati lo stato connesso (se non viene visualizzato, aggiornare il browser) e informazioni sull'analisi di utenti, dati e attività.  

1. Nella pagina delle impostazioni delle applicazioni cloud, è opportuno dedicare qualche minuto anche all'esplorazione di altre impostazioni di Cloud Discovery.  
    1. Selezionare **App di controllo app per l'accesso condizionale** e prendere nota della descrizione "Controllo app per l'accesso condizionale aggiunge funzionalità di monitoraggio e controllo in tempo reale per le applicazioni".
    1. Selezionare Microsoft Information Protection e consultare le impostazioni disponibili.
    1. Esplorare le altre a seconda delle esigenze. Illustrare il livello di integrazione e di flessibilità.

1. Tornare al dashboard di Cloud Discovery selezionando **Cloud Discovery** nel riquadro di spostamento più a sinistra.

1. Tenere aperta la pagina perché verrà usata nella parte successiva.

### Demo parte 2 - Esplorare il catalogo delle app cloud

In questa parte della demo verranno illustrate le funzionalità del catalogo delle app cloud. Cloud Discovery consente di analizzare i log del traffico in base al catalogo delle app cloud di Microsoft Defender for Cloud Apps, che include oltre 31.000 app cloud. Le app cloud, classificate e con punteggi assegnati in base a più di 80 fattori di rischio, offrono visibilità continua sull'uso di cloud, shadow IT e sul rischio di shadow IT per l'organizzazione.  

1. Dal riquadro di spostamento sinistro selezionare **Catalogo delle app cloud**.

1. Il catalogo delle app cloud consente di scegliere le app che soddisfano i requisiti di sicurezza dell'organizzazione. Gli amministratori possono applicare filtri semplici alle app, come illustrato nella parte superiore della pagina, specificando le app con approvazione, senza approvazione o senza tag, il punteggio di rischio, il fattore di rischio della conformità e il fattore di rischio della sicurezza.  Ad esempio, filtrare l'elenco in base al fattore di rischio della conformità consente di cercare standard, certificazioni e conformità specifici per l'app, ad esempio HIPAA, ISO 27001, SOC 2 e PCI-DSS. Selezionare **Fattore di rischio della conformità** per visualizzare le opzioni disponibili.  È possibile filtrare ulteriormente le app in base al punteggio di rischio spostando i dispositivi di scorrimento per il punteggio di rischio nella parte superiore della pagina. Se si sposta il dispositivo di scorrimento, assicurarsi di impostarlo in modo che l'intervallo sia compreso tra 0 e 10.

1. Gli amministratori possono anche cercare le app in base alla categoria.  Ad esempio, nel campo Cercare una categoria immettere **Social network** e quindi selezionare **Social network**.  Selezionare una voce dall'elenco per una visualizzazione dettagliata.  Passando il puntatore del mouse su qualsiasi argomento per una determinata categoria, verrà visualizzata un'icona di informazioni che è possibile selezionare per ottenere altre informazioni su tale argomento.

1. Tenere aperta la pagina perché verrà usata nell'attività successiva.

### Demo parte 3 - Esplorare il log attività e i file

Esplorare i modi in cui è possibile analizzare le attività registrate con il log attività e i file.

1. Dal riquadro di spostamento sinistro selezionare **Log attività**. Qui si ha visibilità su tutte le attività delle app connesse. È possibile che non vengano visualizzati dati perché possono essere necessarie diverse ore per eseguire analisi retroattive dopo l'abilitazione del controllo e i tenant del lab potrebbero riscontrare ritardi più lunghi del normale. Notare le opzioni di filtro disponibili e l'opzione per creare un nuovo criterio dalla ricerca.

1. Per garantire la protezione dei dati personali, Microsoft Defender for Cloud Apps offre visibilità su tutti i file delle applicazioni connesse, ad esempio tutti i file archiviati in SharePoint e Salesforce. Nel pannello di spostamento a sinistra, selezionare ed esplorare l'opzione **File**.
    1. La possibilità di analizzare i file deve essere abilitata come parte delle impostazioni di Protezione delle informazioni delle app cloud di Microsoft 365.  Selezionare **Abilita monitoraggio file** e selezionare la casella accanto a dove è indicato **Abilita monitoraggio file**, quindi selezionare **Salva**.  
    1. Tornare ai file, elencati in App cloud, selezionando **File**, nel riquadro di spostamento a sinistra. È possibile che non venga visualizzato alcun elemento nell'elenco, questo perché la visualizzazione dei file potrebbe richiedere diversi giorni, ma vale la pena evidenziarli una volta presenti, in modo da poter filtrare i dati in base ad app, proprietario, livello di accesso, tipo di file e criteri corrispondenti. Inoltre, è possibile creare un nuovo criterio dalla funzione ricerca ed esportarne i dati.

1. Tenere aperta la pagina perché verrà usata nell'attività successiva.

### Demo parte 4 - Esplorare i criteri

In questa parte verranno visualizzate le opzioni disponibili per i criteri in Microsoft Defender for Cloud Apps.

1. Dal riquadro di spostamento a sinistra, selezionare **Criteri**.
    1. Selezionare **Gestione Criteri**.  I criteri elencati forniscono informazioni sul numero di avvisi generati dal criterio, relativi a gravità e così via. Se si seleziona una voce, verranno fornite informazioni più dettagliate sul criterio. Selezionare un elemento dall'elenco per visualizzare informazioni dettagliate sui criteri.  Presentare alcune opzioni e quindi selezionare **Annulla**.
    2. Si noti che è anche possibile creare un criterio. Selezionare **+ Crea criteri** per visualizzare i tipi di criteri che è possibile creare.  Selezionare **Criteri attività** per visualizzare le diverse opzioni disponibili per la creazione del criterio.  Selezionare **Annulla** per uscire dalla finestra di configurazione.
    3. Si noti che è anche disponibile un'opzione per esportare le informazioni sui criteri.

1. Dal riquadro di spostamento sinistro selezionare **Modelli del criterio**. Per creare un criterio da uno dei modelli disponibili, selezionare il **+** sul lato a destra delle voci del modello.  Visualizzare le diverse opzioni di configurazione per i criteri.  Selezionare **Annulla** per uscire dalla pagina.

1. Dal riquadro di spostamento a sinistra, selezionare **Home** per tornare alla home page di Microsoft 365 Defender.

1. Se si prevede di continuare con la demo successiva, mantenere aperta la scheda del browser.

### Revisione

In questa demo sono state presentate le funzionalità di Microsoft Defender for Cloud Apps.  Sono state presentate le informazioni disponibili nel dashboard di Cloud Discovery, il catalogo delle app cloud, le funzionalità disponibili per esaminare i risultati con il log attività e i file, nonché i modi a disposizione per controllare l'impatto sull'organizzazione attraverso i criteri.
