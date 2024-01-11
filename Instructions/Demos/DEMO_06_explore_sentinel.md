<!---
---
Demo: titolo: "Esplorare Microsoft Sentinel" Percorso di apprendimento/Modulo/Titolo: "Percorso di apprendimento: Descrivere le funzionalità delle soluzioni di sicurezza Microsoft; modulo 3: Descrivere le funzionalità di sicurezza di Microsoft Sentinel; unità 3: Descrivere le funzionalità di mitigazione e di rilevamento delle minacce in Microsoft Sentinel"
---
--->

# Demo: Microsoft Sentinel

Questa demo corrisponde al contenuto di Learn seguente:

- Percorso di apprendimento: Descrivere le funzionalità delle soluzioni di sicurezza Microsoft
- Modulo: Descrivere le funzionalità di sicurezza di Microsoft Sentinel
- Unità: Descrivere le funzionalità di mitigazione e rilevamento delle minacce in Microsoft Sentinel

## Scenario dimostrativo

In questa demo verranno illustrate alcune delle opzioni disponibili con Microsoft Sentinel, tra cui l'utilizzo di Hub dei contenuti per trovare pacchetti di soluzioni da distribuire.  Tuttavia, in primo luogo, verrà illustrato il processo di impostazione delle autorizzazioni di controllo degli accessi in base al ruolo per gli utenti che devono accedere alle risorse di Microsoft Sentinel.

### Demo parte 1

Un'istanza di Microsoft Sentinel dovrebbe essere già stata creata come parte della configurazione pre-demo. Verificare che sia stata creata.

1. Aprire la scheda del browser **Home-Microsoft Azure**.  Se la scheda è stata chiusa in precedenza, aprire una pagina del browser e nella barra degli indirizzi digitare **https://portal.azure.com**. Accedere con le credenziali di Azure fornite dal provider di servizi di hosting per il lab autorizzato (ALH).  In questo modo si verrà indirizzati alla home page dei servizi di Azure.

1. Nella casella di ricerca, nella barra blu nella parte superiore della pagina accanto a Microsoft Azure, immettere **Microsoft Sentinel** e quindi selezionare **Microsoft Sentinel** dai risultati della ricerca.  

1. Nella pagina di Microsoft Sentinel, dovrebbe essere elencata e selezionata l'istanza di Sentinel in uso.  Se non è presente nell'elenco, crearla ora.
    1. Nella pagina di Microsoft Sentinel selezionare **Crea Microsoft Sentinel**.

    1. Nella pagina Aggiungi Microsoft Sentinel a un'area di lavoro selezionare **Crea una nuova area di lavoro**. Nella scheda Informazioni di base dell'area di lavoro Crea Log Analytics, immettere quanto segue:
        1. Sottoscrizione: lasciare l'impostazione predefinita.
        1. Gruppo di risorse: selezionare **Crea nuovo**, quindi inserire il nome **SC900-Sentinel-RG** e selezionare **OK**.
        1. Nome: **Area di lavoro Log Analytics SC900**.
        1. Area geografica: **Stati Uniti orientali** (è possibile selezionare un'area geografica predefinita diversa in base alla posizione)
        1. Selezionare **Rivedi e crea** (non verranno configurati tag).
        1. Verificare le informazioni immesse in precedenza e quindi selezionare **Crea**.
        1. Elencare le aree di lavoro potrebbe richiedere qualche minuto. Se l'elenco non viene ancora visualizzato, selezionare **Aggiorna**, quindi selezionare **Aggiungi**.
        1. Dopo aver aggiunto la nuova area di lavoro, verrà visualizzata la pagina Microsoft Sentinel | Novità e guide che indica che la versione di valutazione gratuita di Microsoft Sentinel è attivata.  Seleziona **OK**.

1. Tenere aperta questa pagina, perché verrà usata in un'attività successiva.

### Demo parte 2

Come per tutte le risorse di Azure, è necessario assicurarsi che gli utenti abbiano le autorizzazioni appropriate per accedere alle risorse di Microsoft Sentinel. Qui vengono illustrati i passaggi per assegnare un ruolo e i ruoli disponibili per l'uso con Microsoft Sentinel.  

1. Nella casella di ricerca, nella barra di colore blu nella parte superiore della pagina accanto alla dicitura Microsoft Azure, digitare **gruppi di risorse** e selezionare **Gruppi di risorse** dai risultati di ricerca. L'assegnazione del ruolo a livello di gruppo di risorse garantirà che il ruolo venga applicato a tutte le risorse distribuite per il supporto di Microsoft Sentinel.

1. Nella pagina Gruppi di risorse selezionare il gruppo di risorse creato con Microsoft Sentinel, **SC900-Sentinel-RG**.

1. Nella pagina SC900-Sentinel-RG selezionare **Controllo di accesso (IAM)** dal riquadro di spostamento a sinistra.

1. Nella pagina Controllo di accesso, selezionare **Visualizza Accesso personale**.  Se si usa la sottoscrizione Cloud Slice di Skillable, l'assegnazione del ruolo è impostata su Proprietario LOD, ovvero un'assegnazione di ruolo personalizzata configurata per questa sottoscrizione Cloud Slice, che concede le autorizzazioni necessarie. Ai fini della demo, tuttavia, è opportuno mostrare i ruoli specifici di Sentinel.  Chiudere la finestra delle assegnazioni selezionando la **X** nell'angolo in alto a destra della finestra.

    1. Nella pagina Controllo di accesso, selezionare **+ Aggiungi**, quindi selezionare **Aggiungi assegnazione di ruolo**.

    1. Verrà aperta la pagina Aggiungi assegnazione di ruolo.  Nella casella di ricerca, immettere **Microsoft Sentinel** per visualizzare i ruoli associati a Microsoft Sentinel.
    1. Da uno dei ruoli elencati, selezionare **visualizza** per visualizzarne i dettagli.  Come procedura consigliata, assegnare il privilegio minimo necessario per il ruolo.  

    1. Chiudere la finestra selezionando la **X** nell'angolo in alto a destra della schermata.

1. Nella pagina di controllo dell'accesso chiudere la finestra selezionando la **X** nell'angolo in alto a destra della finestra.

### Demo parte 3

In questa parte della demo verranno illustrati i passaggi per la connessione a un'origine dati. Molti connettori dati vengono distribuiti come parte di una soluzione Microsoft Sentinel insieme a contenuti correlati quali regole di analisi, cartelle di lavoro e playbook. L'Hub contenuti di Microsoft Sentinel è la posizione centralizzata per individuare e gestire contenuto predefinito. In questo passaggio, verrà utilizzato l'Hub contenuti per distribuire la soluzione Microsoft Defender per il cloud per Microsoft Sentinel.  Questa soluzione consente di inserire avvisi di sicurezza segnalati in Microsoft Defender per il cloud.

1. Aprire la scheda del browser per Microsoft Sentinel.

1. Dal riquadro di spostamento a sinistra, selezionare **Hub contenuti**.

1. Scorrere verso il basso per visualizzare il lungo elenco lungo di soluzioni disponibili e le opzioni per filtrare l'elenco.  Per questa demo, deve essere cercato **Microsoft Defender per il cloud**.  Selezionarlo dall'elenco.  Nella finestra laterale visualizzata, leggere la descrizione e quindi selezionare **Installa**.  Questa soluzione include un connettore dati e una regola di analisi. Il caricamento potrebbe richiedere qualche minuto.  Seleziona **Gestisci**.

1. Selezionare la casella accanto a dove è indicato Microsoft Defender per il cloud.  Sul lato destro della pagina verrà visualizzata una finestra.  Selezionare **Apri la pagina del connettore**.

1. Notare le istruzioni di configurazione.  Selezionare la casella accanto al nome della sottoscrizione e quindi selezionare **Connetti**.  Lo stato passerà a Connesso.  Il connettore ora è abilitato, anche se la visualizzazione del connettore nella pagina Connettori dati potrebbe richiedere del tempo.  

1. Visualizzare ora le informazioni relative alla regola di analisi.  Nella parte superiore della pagina (nella barra di navigazione) selezionare **Microsoft Defender per il cloud**.  Selezionare la casella accanto alla posizione in cui è indicato "Rileva attività di rimozione CoreBackUp da avvisi di sicurezza correlati". Nella finestra visualizzata, sarà possibile visualizzare le informazioni relative alla regola e alla sua applicabilità.  È possibile eseguire i passaggi per configurare la regola.  **NOTA**: i dettagli della logica della regola non rientrano nell'ambito dei concetti fondamentali, ma è possibile visualizzare il tipo di informazioni configurabili come parte della regola.  
    1. Seleziona **Configurazione**.
    1. Selezionare la regola **Rileva attività di eliminazione coreBackUp da avvisi di sicurezza correlati**.
    1. Dalla finestra visualizzata sul lato destro della pagina, selezionare **Crea regola**.
    1. Scorrere tutte le pagine della configurazione, molto brevemente e in generale, selezionare **Rivedi e crea**, quindi selezionare **Salva**.

1. Tornare alla pagina Sentinel selezionando **Microsoft Sentinel | Hub contenuti** dalla barra di navigazione nella parte superiore della pagina, al di sopra di Regole di analisi.

1. Richiamarla usando l'Hub contenuti, è possibile distribuire una soluzione in modo semplice e rapido.

1. Tenere aperta la pagina perché verrà usata nell'attività successiva.

### Demo parte 4

In questa parte della demo verranno illustrate alcune delle opzioni disponibili in Sentinel.

1. Dal riquadro di spostamento sinistro, selezionare **Ricerca**.  Dalla parte superiore della pagina, selezionare la scheda **Query**. Leggere la descrizione relativa a cosa è una query di ricerca. È possibile aggiungere query di ricerca tramite l'Hub contenuti. Tutte le query installate in precedenza verranno elencate qui. Selezionare **Passa a Hub contenuti**.  L'Hub contenuti elenca contenuti che includono query come parte di una soluzione o come query autonoma.  Scorrere verso il basso per visualizzare le opzioni disponibili.

1. Dal riquadro di spostamento sinistro, selezionare **MITRE ATT&CK**.  MITRE ATT&CK è una knowledge base pubblica di tattiche e tecniche comunemente usate dagli utenti malintenzionati. Con Microsoft Sentinel è possibile visualizzare i rilevamenti già attivi nell'area di lavoro e quelli disponibili per la configurazione, per comprendere la copertura della sicurezza dell'organizzazione, in base alle tattiche e alle tecniche del framework MITRE ATT&CK®.  Selezionare una cella della matrice e prendere nota delle informazioni disponibili sul lato destro della schermata.  

1. Dal riquadro di spostamento sinistro, selezionare **Community**. Gli analisti della sicurezza di Microsoft creano e aggiungono continuamente nuove cartelle di lavoro, playbook, query di ricerca e altro ancora, pubblicandoli nella community perché ognuno possa usarli nel proprio ambiente. È possibile scaricare contenuto di esempio dal repository GitHub privato della community, per creare cartelle di lavoro, query di ricerca, blocchi appunti e playbook personalizzati per Azure Sentinel.  Selezionare **Onboard community content** (Carica contenuti della community).  Viene aperta una nuova scheda del repository GitHub in cui è possibile scaricare il contenuto per abilitare gli scenari.  Tornare alla scheda di Azure nel browser.

1. Dal riquadro di spostamento a sinistra, selezionare **Analisi**.  Saranno presenti due regole attive, una disponibile per impostazione predefinita e l'altra creata nell'attività precedente. Selezionare la regola predefinita **Rilevamento avanzato attacchi multifase**.  Prendere nota delle informazioni dettagliate.  Microsoft Sentinel usa Fusion, un motore di correlazione basato su algoritmi di Machine Learning scalabili, per rilevare automaticamente gli attacchi multistage (noti anche come minacce persistenti avanzate) identificando combinazioni di comportamenti anomali e attività sospette che vengono osservate in varie fasi della kill chain. Sulla base di queste individuazioni, Microsoft Sentinel genera eventi imprevisti che altrimenti sarebbero difficili da intercettare.

1. Dal riquadro di spostamento a sinistra, selezionare **Automazione**.  Qui è possibile creare semplici regole di automazione, integrare i playbook esistenti o crearne di nuovi.  Selezionare **+ Crea** e quindi selezionare **Regola di automazione**.  Notare la finestra visualizzata sul lato destro della schermata e le opzioni disponibili per creare condizioni e azioni.  Selezionare **Annulla** nella parte inferiore della schermata.

1. Dal riquadro di spostamento a sinistra selezionare **Cartelle di lavoro**. Leggere la descrizione relativa a cosa è una cartella di lavoro Microsoft Sentinel.  Le cartelle di lavoro possono essere aggiunte tramite l'Hub contenuti. Tutte le cartelle di lavoro installate in precedenza verranno elencate qui. Selezionare **Passa a Hub contenuti**.  L'Hub contenuti elenca contenuti che includono cartelle di lavoro come parte di una soluzione o come cartella di lavoro autonoma. Scorrere verso il basso per visualizzare le opzioni disponibili.

1. Chiudere la finestra selezionando la **X** nell'angolo in alto a destra della schermata.

1. Nell'angolo superiore sinistro della finestra, subito sotto la barra blu, selezionare **Home** per tornare alla home page del portale di Azure.  

### Revisione

In questa demo sono stati illustrati i passaggi per la connessione di Microsoft Sentinel alle origini dati, è stata impostata una cartella di lavoro e sono state presentate varie opzioni disponibili in Microsoft Sentinel.
