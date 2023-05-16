---
demo:
  title: 'Microsoft Sentinel'
  module: 'Modulo 3: Descrivere le funzionalità di sicurezza di Microsoft Sentinel'
---


# <a name="demo-microsoft-sentinel"></a>Dimostrazione: Microsoft Sentinel

Questa demo corrisponde al contenuto di Learn seguente:

- Percorso di apprendimento: Descrivere le funzionalità delle soluzioni di sicurezza Microsoft
- Modulo: Descrivere le funzionalità di sicurezza di Microsoft Sentinel
- Unità: Descrivere la gestione integrata delle minacce offerta da Microsoft Sentinel

## <a name="demo-scenario"></a>Scenario demo

Questa demo illustrerà il processo di creazione di un'istanza di Microsoft Sentinel.  Verranno anche configurate le autorizzazioni per garantire l'accesso alle risorse che verranno distribuite per supportare Microsoft Sentinel.  Dopo aver completato questa configurazione di base, verranno illustrati i passaggi per connettere Microsoft Sentinel alle origini dati e selezionare una cartella di lavoro per monitorare e visualizzare i dati.  Infine, verranno visualizzate alcune altre opzioni disponibili, tra cui l'analisi integrata che consente di ricevere notifiche in merito a qualsiasi attività sospetta, la funzionalità di automazione e altro ancora.

### <a name="pre-demo-setup--create-a-microsoft-sentinel-instance"></a>Configurazione preliminare della demo: Creare un'istanza di Microsoft Sentinel

1. Aprire la scheda del browser, **Home-Microsoft Azure**.  Se la scheda era stata chiusa in precedenza, aprire una pagina del browser e nella barra degli indirizzi inserire portal.azure.com e accedere di nuovo.

1. Nella casella di ricerca, nella barra blu nella parte superiore della pagina accanto a Microsoft Azure, immettere **Microsoft Sentinel** e quindi selezionare **Microsoft Sentinel** dai risultati della ricerca.

1. Nella pagina di Microsoft Sentinel selezionare **Crea Microsoft Sentinel**.

1. Nella pagina Aggiungi Microsoft Sentinel a un'area di lavoro selezionare **Crea una nuova area di lavoro**.

1. Dalla scheda generale di Crea area di lavoro Log Analytics, inserire quanto segue:
    1. Sottoscrizione: lasciare l'impostazione predefinita.
    1. Gruppo di risorse: selezionare **Crea nuovo**, quindi inserire il nome **SC900-Sentinel-RG** e selezionare **OK**.
    1. Nome: **SC900-LogAnalytics-workspace**.
    1. Area: **Stati Uniti orientali** (è possibile selezionare un'area predefinita diversa in base alla località)
    1. Selezionare **Rivedi e crea** (non verranno configurati tag).
    1. Verificare le informazioni inserite e selezionare **Crea**.
    1. Potrebbe volerci un minuto o due perché la nuova area di lavoro compaia nell'elenco; se non compare, selezionare **Aggiorna**, quindi selezionare **Aggiungi**.

1. Dopo aver aggiunto la nuova area di lavoro, verrà visualizzata la pagina Microsoft Sentinel | Novità e guide che indica che la versione di valutazione gratuita di Microsoft Sentinel è attivata.  Selezionare **OK**.  Osservare i tre passaggi elencati nella pagina Guida introduttiva.

1. Tenere aperta la pagina perché verrà usata nell'attività successiva.

### <a name="demo-part-2"></a>Demo parte 2

Dopo aver creato l'istanza di Microsoft Sentinel, ci si assicurerà di disporre dell'accesso necessario alle risorse distribuite per il supporto di Microsoft Sentinel.  

1. Nella casella di ricerca, nella barra blu nella parte superiore della pagina accanto a Microsoft Azure, inserire **gruppi di risorse** quindi selezionare **Gruppi di risorse** dai risultati della ricerca. L'assegnazione del ruolo a livello di gruppo di risorse garantirà che il ruolo venga applicato a tutte le risorse distribuite per il supporto di Microsoft Sentinel.

1. Nella pagina Gruppi di risorse selezionare il gruppo di risorse creato con Microsoft Sentinel, **SC900-Sentinel-RG**.

1. Dalla pagina SC900-Sentinel-RG, selezionare **Controllo di accesso (IAM)** dal riquadro di spostamento sinistro.

1. Dalla pagina Controllo di accesso selezionare **Visualizza accesso personale**.  Come amministratore MOD, il ruolo corrente è Amministratore del supporto del servizio.  In questo modo verranno concesse le autorizzazioni necessarie. Tuttavia, ai fini della demo, è possibile che si voglia visualizzare i ruoli specifici di Sentinel.  Chiudere la finestra delle assegnazioni di Amministratore MOD selezionando la **X** nell'angolo in alto a destra della finestra.

    1. Dalla pagina Controllo di accesso selezionare **+Aggiungi**, quindi selezionare **Add role assignment** (Aggiungi assegnazione di ruolo).

    1. Si apre la finestra Add role assignment (Aggiungi assegnazione di ruolo).  Nella casella di ricerca immettere **Microsoft Sentinel** per visualizzare i 4 ruoli associati a Microsoft Sentinel.
    1. Da uno dei ruoli elencati, selezionare **visualizza** per visualizzarne i dettagli.  Come procedura consigliata si dovrebbe assegnare il privilegio minimo richiesto per il ruolo.  

    1. Chiudere la finestra selezionando la **X** nell'angolo in alto a destra della schermata.

1. Nella pagina di controllo dell'accesso chiudere la finestra selezionando la **X** nell'angolo in alto a destra della finestra.

### <a name="demo-part-3"></a>Demo parte 3

In questa parte della demo verranno illustrati i passaggi per la connessione a un'origine dati.  In particolare, ci si connetterà al connettore dati di Microsoft Defender per il cloud.

1. Nella casella di ricerca, nella barra blu nella parte superiore della pagina accanto a Microsoft Azure, immettere **Microsoft Sentinel** e quindi selezionare **Microsoft Sentinel** dai risultati della ricerca.

1. Nella pagina di Microsoft Sentinel selezionare l'area di lavoro creata con l'istanza di Microsoft Sentinel, **SC900-LogAnalytics-workspace**.

1. Il primo passaggio con Microsoft Sentinel prevede di essere in grado di raccogliere dati. Dal riquadro di spostamento sinistro selezionare **Connettori dati**, elencati sotto la configurazione.

1. Dalla pagina Connettori dati, scorrere verso il basso nella finestra principale per visualizzare l'elenco completo dei connettori disponibili. Nella casella di ricerca della pagina Connettori dati immettere **Microsoft Defender per il cloud** e quindi nell'elenco selezionare **Microsoft Defender per il cloud**.

1. Viene visualizzata la finestra del connettore di Microsoft Defender per il cloud. Esaminare la descrizione e quindi selezionare **Aprire la pagina del connettore**.

1. Nella pagina del connettore di Microsoft Defender per il cloud esaminare la descrizione sul lato sinistro della finestra.

1. La scheda delle istruzioni nella finestra principale indica i prerequisiti.  Esaminare le istruzioni e le informazioni di configurazione.
    La scheda delle istruzioni nella finestra principale indica i prerequisiti.  Esaminare le istruzioni e le informazioni di configurazione.
    1. Nella sezione della configurazione selezionare la casella vuota accanto alla sottoscrizione elencata, **MOC Subscription--lodXXXXXXXX** in modo che venga visualizzato un segno di spunta in una casella blu, quindi selezionare **Connetti** (l'opzione Connetti viene visualizzata sopra la casella di ricerca).  Verrà visualizzata una finestra Connetti. Selezionare **OK**.  Nella colonna dello stato, accanto alla sottoscrizione, si noterà che lo stato viene aggiornato a Connesso.  Non preoccuparsi se non viene visualizzato lo stato di connesso nella finestra sul lato sinistro della pagina e NON aggiornare il browser.
    1. Scorrere verso il basso nella pagina e selezionare **Abilita** per creare automaticamente eventi imprevisti da tutti gli avvisi generati nel servizio connesso.
    1. Selezionare ora la scheda **Passaggi successivi** nella parte superiore della pagina per visualizzare le cartelle di lavoro consigliate per questo connettore dati.  Microsoft Sentinel include anche modelli di cartella di lavoro predefiniti per ottenere rapidamente informazioni dettagliate sui dati non appena si connette un'origine dati.
    1. Selezionare **Conformità e protezione del Centro sicurezza di Azure** (Nota: i nomi ASC o Centro sicurezza di Azure sono stati sostituiti con Microsoft Defender per il cloud).  Verrà visualizzata la pagina delle cartelle di lavoro.  Sul lato destro della schermata esaminare la descrizione, selezionare **Salva** nella parte inferiore della schermata e quindi selezionare **OK** per salvare la cartella di lavoro nella posizione predefinita.  A questo punto selezionare **Visualizza la cartella di lavoro salvata**.  
    1. Nel campo dell'area di lavoro selezionare **SC900-LogAnalytics-workspace**.
    1. Nella parte superiore della pagina della cartella di lavoro selezionare **Aggiornamento automatico: Disattivato**, quindi selezionare **5 minuti** e selezionare **Applica**.
    1. Nella parte superiore della pagina della cartella di lavoro selezionare l'**icona Salva**.
    1. Nell'angolo in alto a sinistra della pagina Cartelle di lavoro, sopra Cartelle di lavoro, selezionare **Microsoft Sentinel**. Verrà visualizzata la pagina di panoramica. Nella parte superiore dovrebbe essere ora visualizzato il numero 1 con la dicitura Connesso, per indicare un connettore attivo (potrebbe essere necessario selezionare Aggiorna).

1. Tenere aperta la pagina perché verrà usata nell'attività successiva.

### <a name="demo-part-4"></a>Demo parte 4

In questa parte della demo verranno illustrate alcune delle opzioni disponibili in Sentinel.

1. Dal riquadro di spostamento sinistro selezionare **Ricerca**.  Nella scheda **Query**, che è selezionata (sottolineata), selezionare una query qualsiasi dall'elenco.  Dopo aver selezionato una query, notare le informazioni fornite su tale query, tra cui il codice per la query e l'opzione per eseguire la query e visualizzare i risultati.  Non selezionare nulla.

1. Dal riquadro di spostamento sinistro, selezionare **MITRE ATT&CK**.  MITRE ATT&CK è una knowledge base pubblica di tattiche e tecniche comunemente usate dagli utenti malintenzionati. Con Microsoft Sentinel è possibile visualizzare i rilevamenti già attivi nell'area di lavoro e quelli disponibili per la configurazione, per comprendere la copertura della sicurezza dell'organizzazione, in base alle tattiche e alle tecniche del framework MITRE ATT&CK®.  Selezionare una cella della matrice e prendere nota delle informazioni disponibili sul lato destro della schermata.  

1. Dal riquadro di spostamento sinistro, selezionare **Community**. Gli analisti della sicurezza di Microsoft creano e aggiungono continuamente nuove cartelle di lavoro, playbook, query di ricerca e altro ancora, pubblicandoli nella community perché ognuno possa usarli nel proprio ambiente. È possibile scaricare contenuto di esempio dal repository GitHub privato della community, per creare cartelle di lavoro, query di ricerca, blocchi appunti e playbook personalizzati per Azure Sentinel.  Selezionare **Onboard community content** (Carica contenuti della community).  Viene aperta una nuova scheda del repository GitHub in cui è possibile scaricare il contenuto per abilitare gli scenari.  Tornare alla scheda di Azure nel browser.

1. Dal riquadro di spostamento sinistro, selezionare **Analisi**.  Selezionare il primo elemento nell'elenco **Advanced Multistage Attack Detection** (Rilevamento avanzato attacchi multistage).  Prendere nota delle informazioni dettagliate.  Microsoft Sentinel usa Fusion, un motore di correlazione basato su algoritmi di Machine Learning scalabili, per rilevare automaticamente gli attacchi multistage (noti anche come minacce persistenti avanzate) identificando combinazioni di comportamenti anomali e attività sospette che vengono osservate in varie fasi della kill chain. Sulla base di queste individuazioni, Microsoft Sentinel genera eventi imprevisti che altrimenti sarebbero difficili da intercettare.

1. Dal riquadro di spostamento sinistro, selezionare **Automazione**.  Qui è possibile creare semplicemente regole di automazione, integrare i playbook esistenti o crearne di nuovi.  Selezionare **+ Crea** e quindi selezionare **Regola di automazione**.  Notare la finestra visualizzata sul lato destro della schermata e le opzioni disponibili per creare condizioni e azioni.  Selezionare **Annulla** nella parte inferiore della schermata.

1. Dal riquadro di spostamento sinistro, selezionare **Cartelle di lavoro**. Dalla pagina Cartelle di lavoro, selezionare la scheda **Cartelle di lavoro personali** sopra la casella di ricerca.  La cartella di lavoro appena salvata è presente nell'elenco e disponibile per visualizzare e monitorare i dati.   NOTA: non viene eseguita alcuna attività reale nella sottoscrizione di Azure da riflettere nella cartella di lavoro e le sottoscrizioni per i lab di Azure potrebbero riscontrare ritardi maggiori del normale per la raccolta di dati che possono essere visualizzati nella cartella di lavoro.

1. Chiudere la finestra selezionando la **X** nell'angolo in alto a destra della schermata.

1. Nell'angolo superiore sinistro della finestra, subito sotto la barra blu, selezionare **Home** per tornare alla home page del portale di Azure.  

### <a name="review"></a>Verifica

In questa demo sono stati illustrati i passaggi per la connessione di Microsoft Sentinel alle origini dati, è stata impostata una cartella di lavoro e sono state presentate varie opzioni disponibili in Microsoft Sentinel.
