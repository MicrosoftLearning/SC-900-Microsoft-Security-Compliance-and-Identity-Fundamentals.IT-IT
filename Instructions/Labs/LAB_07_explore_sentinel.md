<!---
---
Lab: Title: 'Explore Microsoft Sentinel' Learning Path/Module/Title: 'Learning Path: Describe the capabilities of Microsoft security solutions; Modulo 3: Descrivere le funzionalità di sicurezza di Microsoft Sentinel; Unità 3: Descrivere le funzionalità di rilevamento e mitigazione delle minacce in Microsoft Sentinel
---
--->

# Laboratorio: Esplorare Microsoft Sentinel

Questo lab corrisponde al contenuto di Learn seguente:

- Percorso di apprendimento: Descrivere le funzionalità delle soluzioni di sicurezza Microsoft
- Modulo: Descrivere le funzionalità di sicurezza di Microsoft Sentinel
- Unità: Descrivere le funzionalità di rilevamento e mitigazione delle minacce in Microsoft Sentinel

## Scenario del lab

Verrà illustrato il processo di creazione di un'istanza di Microsoft Sentinel.  Verranno anche configurate le autorizzazioni per garantire l'accesso alle risorse che verranno distribuite per supportare Microsoft Sentinel.  Dopo aver completato questa configurazione di base, verranno illustrati i passaggi per connettere Microsoft Sentinel alle origini dati, per configurare una cartella di lavoro e verranno illustrate brevemente alcune delle funzionalità chiave disponibili in Microsoft Sentinel.

**Tempo stimato**: 45-60 minuti

### Attività 1

Creare un'istanza di Microsoft Sentinel

1. Dovrebbe trovarsi nella home page per i servizi di Azure.  Se il browser è stato chiuso in precedenza, aprire Microsoft Edge. Nella barra degli indirizzi immettere **portal.azure.com** e accedere con le credenziali di amministratore.

1. Nella casella di ricerca blu nella parte superiore della pagina immettere **Microsoft Sentinel** e quindi selezionare **Microsoft Sentinel** dai risultati della ricerca.

1. Nella pagina di Microsoft Sentinel selezionare **Crea Microsoft Sentinel**.

1. Nella pagina Aggiungi Microsoft Sentinel a un'area di lavoro selezionare **Crea una nuova area di lavoro**.

1. Dalla scheda generale di Crea area di lavoro Log Analytics, inserire quanto segue:
    1. Sottoscrizione: lasciare l'impostazione predefinita, ovvero la sottoscrizione di Azure fornita dal provider di servizi di hosting per i lab autorizzato.
    1. Gruppo di risorse: selezionare **SC900-Sentinel-RG**. Se questo gruppo di risorse non è elencato, crearlo selezionando **Crea nuovo**, immettere **SC900-Sentinel-RG**, quindi selezionare **OK**.
    1. Nome: **SC900-LogAnalytics-workspace**.
    1. Area: **Stati Uniti orientali** (è possibile selezionare un'area predefinita diversa in base alla località)
    1. Selezionare **Rivedi e crea** (non verranno configurati tag).
    1. Verificare le informazioni inserite e selezionare **Crea**.
    1. Potrebbe volerci un minuto o due perché la nuova area di lavoro compaia nell'elenco; se non compare, selezionare **Aggiorna**, quindi selezionare **Aggiungi**.

1. Dopo aver aggiunto la nuova area di lavoro, verrà visualizzata la pagina Microsoft Sentinel | Novità e guide che indica che la versione di valutazione gratuita di Microsoft Sentinel è attivata.  Selezionare **OK**.  Osservare i tre passaggi elencati nella pagina Guida introduttiva.

1. Tenere aperta la pagina perché verrà usata nell'attività successiva.

### Attività 2

Dopo aver creato l'istanza di Microsoft Sentinel, è importante che gli utenti che avranno la responsabilità di supportare Microsoft Sentinel dispongano delle autorizzazioni necessarie.  A tale scopo, è necessario assegnare all'utente designato le autorizzazioni necessarie per il ruolo.  In questa attività verranno visualizzati i ruoli di Microsoft Sentinel predefiniti disponibili.

1. Nella casella di ricerca blu immettere **gruppi di risorse** e quindi selezionare **Gruppi di risorse** dai risultati della ricerca. 

1. Nella pagina Gruppi di risorse selezionare il gruppo di risorse creato con Microsoft Sentinel, **SC900-Sentinel-RG**.  Se si lavora a livello di gruppo di risorse, tutti i ruoli selezionati verranno applicati a tutte le risorse che fanno parte dell'istanza di Microsoft Sentinel creata nell'attività precedente.

1. Dalla pagina SC900-Sentinel-RG, selezionare **Controllo di accesso (IAM)** dal riquadro di spostamento sinistro.

1. Dalla pagina Controllo di accesso selezionare **Visualizza accesso personale**.  Per la sottoscrizione di Azure fornita dal provider di servizi di hosting per i lab autorizzato, è stato definito un ruolo che consentirà l'accesso per gestire tutte le risorse necessarie, come illustrato nella descrizione. È tuttavia importante comprendere i ruoli specifici di Sentinel disponibili.  Chiudere la finestra delle assegnazioni selezionando la **X** nell'angolo in alto a destra della finestra.

1. Nella pagina Controllo di accesso selezionare la scheda **Ruoli** nella parte superiore della pagina.
    1. Nella casella di ricerca immettere **Microsoft Sentinel** per visualizzare i ruoli predefiniti associati a Microsoft Sentinel.
    1. Da uno dei ruoli elencati, selezionare **visualizza** per visualizzarne i dettagli.  Come procedura consigliata si dovrebbe assegnare il privilegio minimo richiesto per il ruolo.  
    1. Chiudere la finestra selezionando la **X** nell'angolo in alto a destra della schermata.

1. Nella pagina di controllo dell'accesso chiudere la finestra selezionando la **X** nell'angolo in alto a destra della finestra.

1. Nell'angolo superiore sinistro della finestra, appena sotto la barra blu in cui è indicato Microsoft Azure, selezionare **Home** per tornare alla home page dei servizi di Azure.

1. Mantenere aperta la scheda Azure nel browser.

### Attività 3

Lo scopo di questa attività consiste nell'esaminare i passaggi necessari per la connessione a un'origine dati. Molti connettori dati vengono distribuiti come parte di una soluzione Microsoft Sentinel insieme a contenuti correlati, ad esempio regole di analisi, cartelle di lavoro e playbook. L'hub del contenuto di Microsoft Sentinel è la posizione centralizzata per individuare e gestire contenuti predefiniti (predefiniti). In questo passaggio si userà l'hub del contenuto per distribuire la soluzione Microsoft Defender for Cloud per Microsoft Sentinel.  Questa soluzione consente di inserire gli avvisi di sicurezza segnalati in Microsoft Defender for Cloud.

1. Nella home page dei servizi di Azure selezionare Microsoft Sentinel, quindi selezionare l'istanza creata, **SC900-LogAnalytics-workspace**.

1. Nel pannello di spostamento a sinistra selezionare **Hub contenuto**.

1. Scorrere verso il basso per visualizzare l'elenco lungo delle soluzioni disponibili e le opzioni per filtrare l'elenco.  Per questa attività, si sta cercando **Microsoft Defender for Cloud**.  Selezionarlo dall'elenco.  Nella finestra laterale visualizzata leggere la descrizione e quindi selezionare **Installa**.  Questa soluzione include un connettore dati e una regola di analisi. L'installazione potrebbe richiedere alcuni minuti.  Selezionare **Gestisci**.

1. Selezionare la casella accanto a dove viene indicato Microsoft Defender per Cloud.  Viene visualizzata una finestra sul lato destro della pagina.  Selezionare **Apri la pagina del connettore**.

1. Prendere nota delle istruzioni di configurazione.  Selezionare la casella accanto al nome della sottoscrizione e quindi selezionare **Connetti**.  Potrebbe essere visualizzata una finestra popup che indica che solo le sottoscrizioni per cui si dispone delle autorizzazioni di lettura per la sicurezza inizieranno a trasmettere Microsoft Defender per gli avvisi cloud.  Selezionare **OK**.  Lo stato passerà alla connessione.  Il connettore è ora abilitato, anche se la visualizzazione del connettore nella pagina dei connettori dati potrebbe richiedere del tempo.  

1. Visualizzare ora le informazioni sulla regola di analisi.  Nella parte superiore della pagina (nel percorso di navigazione) selezionare **Microsoft Defender per Cloud**. Deselezionare la casella accanto alla posizione in cui viene indicato Microsoft Defender per Cloud, perché è già stato configurato il connettore (potrebbe essere necessario del tempo prima che l'icona di avviso scompaia). Selezionare la casella accanto a dove è indicato **Rileva attività di eliminazione CoreBackUp da avvisi di sicurezza correlati**. Nella finestra visualizzata verranno visualizzate informazioni sulla regola e sulle relative operazioni.  
    1. Anche se i dettagli della logica della regola non rientrano nell'ambito dei concetti fondamentali, seguire i passaggi per configurare la regola per visualizzare il tipo di informazioni che possono essere configurate come parte della regola. Selezionare **Configurazione**.
    1. Selezionare la regola Rileva attività di **eliminazione CoreBackUp dagli avvisi di sicurezza correlati**.
    1. Nella finestra visualizzata sul lato destro della pagina selezionare **Crea regola**.
    1. Passare attraverso ognuna delle pagine di configurazione, quindi selezionare **Rivedi e crea**, quindi selezionare **Salva**.

1. Tornare alla pagina sentinel selezionando **Microsoft Sentinel | Hub del contenuto** dalla barra di navigazione nella parte superiore della pagina, sopra dove sono indicate le regole di Analisi.

1. Tenere aperta la pagina perché verrà usata nell'attività successiva.


### Attività 4

In questa attività verranno illustrate alcune delle opzioni disponibili in Sentinel.

1. Dal riquadro di spostamento sinistro selezionare **Ricerca**.  Nella parte superiore della pagina selezionare la scheda **Query** . Leggere la descrizione di una query di ricerca. Le query di ricerca possono essere aggiunte tramite l'hub contenuto. Tutte le query installate in precedenza verranno elencate qui. Selezionare **Vai all'hub del contenuto**.  L'hub del contenuto elenca il contenuto che include le query come parte di una soluzione o come query autonoma.  Scorrere verso il basso per visualizzare le opzioni disponibili. Chiudere l'hub contenuto selezionando la **X** nell'angolo superiore destro della finestra.

1. Dal riquadro di spostamento sinistro, selezionare **MITRE ATT&CK**.  MITRE ATT&CK è una knowledge base pubblica di tattiche e tecniche comunemente usate dagli utenti malintenzionati. Con Microsoft Sentinel è possibile visualizzare i rilevamenti già attivi nell'area di lavoro e quelli disponibili per la configurazione, per comprendere la copertura della sicurezza dell'organizzazione, in base alle tattiche e alle tecniche del framework MITRE ATT&CK®.  Selezionare una cella della matrice e prendere nota delle informazioni disponibili sul lato destro della schermata. **Nota**: potrebbe essere necessario selezionare "**<<**" sul lato destro della finestra per visualizzare il pannello delle informazioni.

1. Dal riquadro di spostamento sinistro, selezionare **Community**. Gli analisti della sicurezza di Microsoft creano e aggiungono continuamente nuove cartelle di lavoro, playbook, query di ricerca e altro ancora, pubblicandoli nella community perché ognuno possa usarli nel proprio ambiente. Sul lato destro della schermata selezionare **Onboarding dei contenuti della community**.  Viene aperta una nuova scheda del repository GitHub in cui è possibile scaricare il contenuto per abilitare gli scenari. Scorrere verso il basso fino alla sezione README.md ed esaminare la descrizione. Tornare alla scheda di Azure nel browser.

1. Dal riquadro di spostamento sinistro, selezionare **Analisi**.  Esistono due regole attive, una disponibile per impostazione predefinita e la regola creata nell'attività precedente. Selezionare la regola predefinita **Rilevamento attacchi multistage** avanzati.  Prendere nota delle informazioni dettagliate.  Microsoft Sentinel usa Fusion, un motore di correlazione basato su algoritmi di Machine Learning scalabili, per rilevare automaticamente gli attacchi multistage (noti anche come minacce persistenti avanzate) identificando combinazioni di comportamenti anomali e attività sospette che vengono osservate in varie fasi della kill chain. Sulla base di queste individuazioni, Microsoft Sentinel genera eventi imprevisti che altrimenti sarebbero difficili da intercettare. **Nota**: potrebbe essere necessario selezionare "**<<**" sul lato destro della finestra per visualizzare il pannello delle informazioni.

1. Dal riquadro di spostamento sinistro, selezionare **Automazione**.  Qui è possibile creare semplici regole di automazione, integrare i playbook esistenti o crearne di nuovi.  Selezionare **+ Crea** e quindi selezionare **Regola di automazione**.  Notare la finestra visualizzata sul lato destro della schermata e le opzioni disponibili per creare condizioni e azioni.  Selezionare **Annulla** nella parte inferiore della schermata.

1. Dal riquadro di spostamento sinistro, selezionare **Cartelle di lavoro**. Leggere la descrizione di una cartella di lavoro di Microsoft Sentinel.  Le cartelle di lavoro possono essere aggiunte tramite l'hub contenuto. Tutte le cartelle di lavoro installate in precedenza verranno elencate qui. Selezionare **Vai all'hub contenuto**.  L'hub di contenuto elenca il contenuto che include cartelle di lavoro come parte di una soluzione o come cartella di lavoro autonoma. Scorrere verso il basso per visualizzare le opzioni disponibili.

1. Chiudere la finestra selezionando la **X** nell'angolo in alto a destra della schermata.

1. Nell'angolo superiore sinistro della finestra, subito sotto la barra blu, selezionare **Home** per tornare alla home page del portale di Azure.

1. Disconnettersi e chiudere tutte le schede del browser aperte.

### Verifica

In questa lV sono stati illustrati i passaggi per la connessione di Microsoft Sentinel alle origini dati, è stata configurata una cartella di lavoro e sono state illustrate diverse opzioni disponibili in Microsoft Sentinel.
