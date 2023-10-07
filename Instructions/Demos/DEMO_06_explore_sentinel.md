<!---
---
Demo: Title: "Microsoft Sentinel" Learning Path/Module/Title: 'Learning Path: Describe the capabilities of Microsoft security solutions; Modulo 3: Descrivere le funzionalità di sicurezza di Microsoft Sentinel; Unità 3: Descrivere le funzionalità di rilevamento e mitigazione delle minacce in Microsoft Sentinel
---
--->

# Dimostrazione: Microsoft Sentinel

Questa demo corrisponde al contenuto di Learn seguente:

- Percorso di apprendimento: Descrivere le funzionalità delle soluzioni di sicurezza Microsoft
- Modulo: Descrivere le funzionalità di sicurezza di Microsoft Sentinel
- Unità: Descrivere le funzionalità di rilevamento e mitigazione delle minacce in Microsoft Sentinel

## Scenario demo

In questa demo verranno illustrate alcune delle opzioni disponibili con Microsoft Sentinel, tra cui l'uso dell'hub del contenuto per trovare soluzioni in pacchetto che è possibile distribuire.  In primo luogo, tuttavia, si esaminerà il processo di configurazione delle autorizzazioni di controllo degli accessi in base al ruolo per gli utenti che dovranno accedere alle risorse di Microsoft Sentinel.

### Demo parte 1

Un'istanza di Microsoft Sentinel dovrebbe essere già stata creata come parte della configurazione preliminare della demo. Verificare che sia stato creato.

1. Aprire la scheda del browser, **Home-Microsoft Azure**.  Se la scheda è stata chiusa in precedenza, aprire una pagina del browser e nella barra degli indirizzi immettere **https://portal.azure.com**. Accedere con le credenziali di Azure fornite dall'host del lab autorizzato (ALH).  Verrà visualizzata la home page dei servizi di Azure.

1. Nella casella di ricerca, nella barra blu nella parte superiore della pagina accanto a Microsoft Azure, immettere **Microsoft Sentinel** e quindi selezionare **Microsoft Sentinel** dai risultati della ricerca.  

1. Nella pagina Microsoft Sentinel dovrebbe essere visualizzata l'istanza di Sentinel elencata e selezionarla.  Se non è elencato, crearlo ora.
    1. Nella pagina di Microsoft Sentinel selezionare **Crea Microsoft Sentinel**.

    1. Nella pagina Aggiungi Microsoft Sentinel a un'area di lavoro selezionare **Crea una nuova area di lavoro**. Dalla scheda generale di Crea area di lavoro Log Analytics, inserire quanto segue:
        1. Sottoscrizione: lasciare l'impostazione predefinita.
        1. Gruppo di risorse: selezionare **Crea nuovo**, quindi inserire il nome **SC900-Sentinel-RG** e selezionare **OK**.
        1. Nome: **SC900-LogAnalytics-workspace**.
        1. Area: **Stati Uniti orientali** (è possibile selezionare un'area predefinita diversa in base alla località)
        1. Selezionare **Rivedi e crea** (non verranno configurati tag).
        1. Verificare le informazioni inserite e selezionare **Crea**.
        1. Potrebbe volerci un minuto o due perché la nuova area di lavoro compaia nell'elenco; se non compare, selezionare **Aggiorna**, quindi selezionare **Aggiungi**.
        1. Dopo aver aggiunto la nuova area di lavoro, verrà visualizzata la pagina Microsoft Sentinel | Novità e guide che indica che la versione di valutazione gratuita di Microsoft Sentinel è attivata.  Selezionare **OK**.

1. Mantenere aperta questa pagina, perché verrà usata in un'attività successiva.

### Demo parte 2

Come per tutte le risorse di Azure, si vuole assicurarsi che gli utenti dispongano delle autorizzazioni appropriate per accedere alle risorse di Microsoft Sentinel. Qui verranno illustrati i passaggi per assegnare un ruolo e i ruoli disponibili per l'uso con Microsoft Sentinel.  

1. Nella casella di ricerca, nella barra blu nella parte superiore della pagina accanto a Microsoft Azure, inserire **gruppi di risorse** quindi selezionare **Gruppi di risorse** dai risultati della ricerca. L'assegnazione del ruolo a livello di gruppo di risorse garantirà che il ruolo venga applicato a tutte le risorse distribuite per il supporto di Microsoft Sentinel.

1. Nella pagina Gruppi di risorse selezionare il gruppo di risorse creato con Microsoft Sentinel, **SC900-Sentinel-RG**.

1. Dalla pagina SC900-Sentinel-RG, selezionare **Controllo di accesso (IAM)** dal riquadro di spostamento sinistro.

1. Dalla pagina Controllo di accesso selezionare **Visualizza accesso personale**.  Se si usa la sottoscrizione Skillable Cloud Slice, l'assegnazione di ruolo è impostata su Proprietario LOD, ovvero un'assegnazione di ruolo personalizzata configurata per questa sottoscrizione di Cloud Slice e consentirà di concedere le autorizzazioni necessarie. A scopo dimostrativo, tuttavia, è consigliabile visualizzare i ruoli specifici di Sentinel.  Chiudere la finestra delle assegnazioni selezionando la **X** nell'angolo in alto a destra della finestra.

    1. Dalla pagina Controllo di accesso selezionare **+Aggiungi**, quindi selezionare **Add role assignment** (Aggiungi assegnazione di ruolo).

    1. Si apre la finestra Add role assignment (Aggiungi assegnazione di ruolo).  Nella casella di ricerca immettere **Microsoft Sentinel** per visualizzare i ruoli associati a Microsoft Sentinel.
    1. Da uno dei ruoli elencati, selezionare **visualizza** per visualizzarne i dettagli.  Come procedura consigliata si dovrebbe assegnare il privilegio minimo richiesto per il ruolo.  

    1. Chiudere la finestra selezionando la **X** nell'angolo in alto a destra della schermata.

1. Nella pagina di controllo dell'accesso chiudere la finestra selezionando la **X** nell'angolo in alto a destra della finestra.

### Demo parte 3

In questa parte della demo verranno illustrati i passaggi per la connessione a un'origine dati. Molti connettori dati vengono distribuiti come parte di una soluzione Microsoft Sentinel insieme a contenuti correlati, ad esempio regole di analisi, cartelle di lavoro e playbook. L'hub del contenuto di Microsoft Sentinel è la posizione centralizzata per individuare e gestire contenuti predefiniti (predefiniti). In questo passaggio si userà l'hub del contenuto per distribuire la soluzione Microsoft Defender for Cloud per Microsoft Sentinel.  Questa soluzione consente di inserire gli avvisi di sicurezza segnalati in Microsoft Defender for Cloud.

1. Aprire la scheda del browser per Microsoft Sentinel.

1. Nel pannello di spostamento a sinistra selezionare **Hub contenuto**.

1. Scorrere verso il basso per visualizzare l'elenco lungo delle soluzioni disponibili e le opzioni per filtrare l'elenco.  Per questa demo, stiamo cercando **Microsoft Defender for Cloud**.  Selezionarlo dall'elenco.  Nella finestra laterale visualizzata leggere la descrizione e quindi selezionare **Installa**.  Questa soluzione include un connettore dati e una regola di analisi. L'installazione potrebbe richiedere alcuni minuti.  Selezionare **Gestisci**.

1. Selezionare la casella accanto a dove viene indicato Microsoft Defender per Cloud.  Viene visualizzata una finestra sul lato destro della pagina.  Selezionare **Apri la pagina del connettore**.

1. Prendere nota delle istruzioni di configurazione.  Selezionare la casella accanto al nome della sottoscrizione e quindi selezionare **Connetti**.  Lo stato passerà alla connessione.  Il connettore è ora abilitato, anche se la visualizzazione del connettore nella pagina dei connettori dati potrebbe richiedere del tempo.  

1. Visualizzare ora le informazioni sulla regola di analisi.  Nella parte superiore della pagina (nel percorso di navigazione) selezionare **Microsoft Defender per Cloud**.  Selezionare la casella accanto alla posizione in cui viene indicato "Rileva attività di eliminazione CoreBackUp da avvisi di sicurezza correlati". Nella finestra visualizzata verranno visualizzate informazioni sulla regola e sulle relative operazioni.  È possibile scegliere di eseguire i passaggi per configurare la regola.  **NOTA**: i dettagli della logica della regola non rientrano nell'ambito dei concetti fondamentali, ma è possibile visualizzare il tipo di informazioni che possono essere configurate come parte della regola.  
    1. Selezionare **Configurazione**.
    1. Selezionare la regola Rileva attività di **eliminazione CoreBackUp dagli avvisi di sicurezza correlati**.
    1. Nella finestra visualizzata sul lato destro della pagina selezionare **Crea regola**.
    1. Passare attraverso ognuna delle pagine di configurazione, molto brevemente e di alto livello, quindi selezionare **Rivedi e crea**, quindi selezionare **Salva**.

1. Tornare alla pagina sentinel selezionando **Microsoft Sentinel | Hub del contenuto** dal riquadro di spostamento nella parte superiore della pagina, sopra dove sono indicate le regole di Analisi.

1. Chiamare questa funzionalità usando l'hub del contenuto, una soluzione può essere distribuita in modo semplice e rapido.

1. Tenere aperta la pagina perché verrà usata nell'attività successiva.

### Demo parte 4

In questa parte della demo verranno illustrate alcune delle opzioni disponibili in Sentinel.

1. Dal riquadro di spostamento sinistro selezionare **Ricerca**.  Nella parte superiore della pagina selezionare la scheda **Query** . Leggere la descrizione di una query di ricerca. Le query di ricerca possono essere aggiunte tramite l'hub contenuto. Tutte le query installate in precedenza verranno elencate qui. Selezionare **Vai all'hub del contenuto**.  L'hub del contenuto elenca il contenuto che include le query come parte di una soluzione o come query autonoma.  Scorrere verso il basso per visualizzare le opzioni disponibili.

1. Dal riquadro di spostamento sinistro, selezionare **MITRE ATT&CK**.  MITRE ATT&CK è una knowledge base pubblica di tattiche e tecniche comunemente usate dagli utenti malintenzionati. Con Microsoft Sentinel è possibile visualizzare i rilevamenti già attivi nell'area di lavoro e quelli disponibili per la configurazione, per comprendere la copertura della sicurezza dell'organizzazione, in base alle tattiche e alle tecniche del framework MITRE ATT&CK®.  Selezionare una cella della matrice e prendere nota delle informazioni disponibili sul lato destro della schermata.  

1. Dal riquadro di spostamento sinistro, selezionare **Community**. Gli analisti della sicurezza di Microsoft creano e aggiungono continuamente nuove cartelle di lavoro, playbook, query di ricerca e altro ancora, pubblicandoli nella community perché ognuno possa usarli nel proprio ambiente. È possibile scaricare contenuto di esempio dal repository GitHub privato della community, per creare cartelle di lavoro, query di ricerca, blocchi appunti e playbook personalizzati per Azure Sentinel.  Selezionare **Onboard community content** (Carica contenuti della community).  Viene aperta una nuova scheda del repository GitHub in cui è possibile scaricare il contenuto per abilitare gli scenari.  Tornare alla scheda di Azure nel browser.

1. Dal riquadro di spostamento sinistro, selezionare **Analisi**.  Esistono due regole attive, una disponibile per impostazione predefinita e la regola creata nell'attività precedente. Selezionare la regola predefinita **Rilevamento attacchi multistage** avanzati.  Prendere nota delle informazioni dettagliate.  Microsoft Sentinel usa Fusion, un motore di correlazione basato su algoritmi di Machine Learning scalabili, per rilevare automaticamente gli attacchi multistage (noti anche come minacce persistenti avanzate) identificando combinazioni di comportamenti anomali e attività sospette che vengono osservate in varie fasi della kill chain. Sulla base di queste individuazioni, Microsoft Sentinel genera eventi imprevisti che altrimenti sarebbero difficili da intercettare.

1. Dal riquadro di spostamento sinistro, selezionare **Automazione**.  Qui è possibile creare semplici regole di automazione, integrare i playbook esistenti o crearne di nuovi.  Selezionare **+ Crea** e quindi selezionare **Regola di automazione**.  Notare la finestra visualizzata sul lato destro della schermata e le opzioni disponibili per creare condizioni e azioni.  Selezionare **Annulla** nella parte inferiore della schermata.

1. Dal riquadro di spostamento sinistro, selezionare **Cartelle di lavoro**. Leggere la descrizione di una cartella di lavoro di Microsoft Sentinel.  Le cartelle di lavoro possono essere aggiunte tramite l'hub contenuto. Tutte le cartelle di lavoro installate in precedenza verranno elencate qui. Selezionare **Vai all'hub contenuto**.  L'hub di contenuto elenca il contenuto che include cartelle di lavoro come parte di una soluzione o come cartella di lavoro autonoma. Scorrere verso il basso per visualizzare le opzioni disponibili.

1. Chiudere la finestra selezionando la **X** nell'angolo in alto a destra della schermata.

1. Nell'angolo superiore sinistro della finestra, subito sotto la barra blu, selezionare **Home** per tornare alla home page del portale di Azure.  

### Verifica

In questa demo sono stati illustrati i passaggi per la connessione di Microsoft Sentinel alle origini dati, è stata impostata una cartella di lavoro e sono state presentate varie opzioni disponibili in Microsoft Sentinel.
