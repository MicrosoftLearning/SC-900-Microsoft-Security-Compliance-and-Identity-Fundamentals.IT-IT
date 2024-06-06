---
lab:
  title: Esplorare Microsoft Sentinel
  module: Describe the security capabilities of Microsoft Sentinel
---

# Lab: Esplorare Microsoft Sentinel

Questo lab corrisponde al contenuto di Learn seguente:

- Percorso di apprendimento: Descrivere le funzionalità delle soluzioni di sicurezza Microsoft
- Modulo: Descrivere le funzionalità di sicurezza di Microsoft Sentinel
- Unità: Descrivere le funzionalità di mitigazione e rilevamento delle minacce in Microsoft Sentinel

## Scenario laboratorio

Questo lab illustrerà il processo di creazione di un'istanza di Microsoft Sentinel.  Verranno anche configurate le autorizzazioni per garantire l'accesso alle risorse che verranno distribuite per supportare Microsoft Sentinel.  Dopo aver completato questa configurazione di base, verranno illustrati i passaggi per connettere Microsoft Sentinel alle origini dati, per configurare una cartella di lavoro e verranno illustrate brevemente alcune delle funzionalità chiave disponibili in Microsoft Sentinel.

**Tempo stimato:** 45-60 minuti

### Attività 1

Creare un'istanza di Microsoft Sentinel

1. Ci si dovrebbe trovare nella home page per i servizi di Azure.  Se il browser è stato chiuso in precedenza, aprire Microsoft Edge. Nella barra degli indirizzi immettere **portal.azure.com** e accedere con le proprie credenziali di amministratore.

1. Nella casella di ricerca blu nella parte superiore della pagina immettere **Microsoft Sentinel** e quindi selezionare **Microsoft Sentinel** dai risultati della ricerca.

1. Nella pagina di Microsoft Sentinel selezionare **Crea Microsoft Sentinel**.

1. Nella pagina Aggiungi Microsoft Sentinel a un'area di lavoro selezionare **Crea una nuova area di lavoro**.

1. Nella scheda Informazioni di base dell'area di lavoro Crea Log Analytics, immettere quanto segue:
    1. Sottoscrizione: lasciare l'impostazione predefinita, ovvero la sottoscrizione di Azure fornita dal provider di servizi di hosting per i lab autorizzato.
    1. Gruppo di risorse: selezionare **SC900-Sentinel-RG**. Se questo gruppo di risorse non è elencato, crearlo selezionando **Crea nuovo**, immettere **SC900-Sentinel-RG**, quindi selezionare **OK**.
    1. Nome: **Area di lavoro Log Analytics SC900**.
    1. Area geografica: **Stati Uniti orientali** (è possibile selezionare un'area geografica predefinita diversa in base alla posizione)
    1. Selezionare **Rivedi e crea** (non verranno configurati tag).
    1. Verificare le informazioni immesse in precedenza e quindi selezionare **Crea**.
    1. Elencare le aree di lavoro potrebbe richiedere qualche minuto. Se l'elenco non viene ancora visualizzato, selezionare **Aggiorna**, quindi selezionare **Aggiungi**.

1. Dopo aver aggiunto la nuova area di lavoro, verrà visualizzata la pagina Microsoft Sentinel | Novità e guide che indica che la versione di valutazione gratuita di Microsoft Sentinel è attivata.  Seleziona **OK**.  Notare i tre passaggi elencati nella pagina Attività iniziali.

1. Tenere aperta la pagina perché verrà usata nell'attività successiva.

### Attività 2

Dopo aver creato l'istanza di Microsoft Sentinel, è importante che gli utenti che avranno la responsabilità di supportare Microsoft Sentinel dispongano delle autorizzazioni necessarie.  A tale scopo, è necessario assegnare all'utente designato le autorizzazioni necessarie per il ruolo.  In questa attività verranno visualizzati i ruoli di Microsoft Sentinel predefiniti disponibili.

1. Nella casella di ricerca blu immettere **gruppi di risorse** e quindi selezionare **Gruppi di risorse** dai risultati della ricerca. 

1. Nella pagina Gruppi di risorse selezionare il gruppo di risorse creato con Microsoft Sentinel, **SC900-Sentinel-RG**.  Se si lavora a livello di gruppo di risorse, tutti i ruoli selezionati verranno applicati a tutte le risorse che fanno parte dell'istanza di Microsoft Sentinel creata nell'attività precedente.

1. Nella pagina SC900-Sentinel-RG selezionare **Controllo di accesso (IAM)** dal riquadro di spostamento a sinistra.

1. Nella pagina Controllo di accesso, selezionare **Visualizza Accesso personale**.  Per la sottoscrizione di Azure fornita dal provider di servizi di hosting per i lab autorizzato, è stato definito un ruolo che consentirà l'accesso per gestire tutte le risorse necessarie, come illustrato nella descrizione. È tuttavia importante comprendere i ruoli specifici di Sentinel disponibili.  Chiudere la finestra delle assegnazioni selezionando la **X** nell'angolo in alto a destra della finestra.

1. Nella pagina Controllo di accesso selezionare la scheda **Ruoli** nella parte superiore della pagina.
    1. Nella casella di ricerca immettere **Microsoft Sentinel** per visualizzare i ruoli predefiniti associati a Microsoft Sentinel.
    1. Da uno dei ruoli elencati, selezionare **visualizza** per visualizzarne i dettagli.  Come procedura consigliata, assegnare il privilegio minimo necessario per il ruolo.  
    1. Chiudere la finestra selezionando la **X** nell'angolo in alto a destra della schermata.

1. Nella pagina di controllo dell'accesso chiudere la finestra selezionando la **X** nell'angolo in alto a destra della finestra.

1. Nell'angolo superiore a sinistra della finestra, subito sotto la barra blu, dove compare Microsoft Azure, selezionare **Home** per tornare alla home page dei servizi di Azure.

1. Mantenere aperta la scheda Azure nel browser.

### Attività 3

Lo scopo di questa attività è quello di illustrare i passaggi necessari necessari per la connessione a un'origine dati. Molti connettori dati vengono distribuiti come parte di una soluzione Microsoft Sentinel insieme a contenuti correlati quali regole di analisi, cartelle di lavoro e playbook. L'Hub contenuti di Microsoft Sentinel è la posizione centralizzata per individuare e gestire contenuto predefinito. In questo passaggio, verrà utilizzato l'Hub contenuti per distribuire la soluzione Microsoft Defender per il cloud per Microsoft Sentinel.  Questa soluzione consente di inserire avvisi di sicurezza segnalati in Microsoft Defender per il cloud.

1. Nella home page dei servizi di Azure, selezionare Microsoft Sentinel, quindi selezionare l'istanza creata, **SC900-LogAnalytics-workspace**.

1. Dal riquadro di spostamento a sinistra, selezionare **Hub contenuti**.

1. Scorrere verso il basso per visualizzare il lungo elenco lungo di soluzioni disponibili e le opzioni per filtrare l'elenco.  Per questa attività, la ricerca è **Microsoft Defender per il cloud**.  Selezionarlo dall'elenco.  Nella finestra laterale visualizzata, leggere la descrizione e quindi selezionare **Installa**.  Al termine dell'installazione, nella colonna stato della finestra principale verrà visualizzata installato.

1. Ancora una volta, selezionare **Microsoft Defender per il cloud** nell'elenco. Nella finestra a destra selezionare **Gestisci**.

1. Sul lato destro della pagina Microsoft Defender per il cloud sono presenti la descrizione e le note associate alla soluzione di Hub contenuti e ciò che è incluso in questa soluzione.  Nella finestra principale sono presenti i componenti della soluzione.  In questo caso sono presenti due connettori dati e una regola dati. Il triangolo arancione indica che è necessaria una configurazione. Selezionare la casella accanto a dove è indicato **Microsoft Defender per il cloud basato su sottoscrizione (legacy)**.  Sul lato destro della pagina verrà visualizzata una finestra.  Selezionare **Apri la pagina del connettore**.

1. Notare le istruzioni di configurazione.  Selezionare la casella accanto al nome della sottoscrizione e quindi selezionare **Connetti**.  Potrebbe essere visualizzata una finestra popup a indicare che solo le sottoscrizioni per cui si dispone del ruolo con autorizzazioni di lettura per la sicurezza inizieranno a trasmettere avvisi di Microsoft Defender per il cloud.  Seleziona **OK**.  Lo stato passerà a Connesso.  Il connettore ora è abilitato, anche se la visualizzazione del connettore nella pagina Connettori dati potrebbe richiedere del tempo.  

1. Visualizzare ora le informazioni relative alla regola di analisi.  Nella parte superiore della pagina (nella barra di navigazione) selezionare **Microsoft Defender per il cloud**. Deselezionare la casella accanto alla posizione in cui è indicato Microsoft Defender per il cloud, poiché il connettore è stato già configurato (l'icona di avviso potrebbe richiedere del tempo per scomparire). Selezionare la casella accanto a dove è indicato **Rileva attività di eliminazione coreBackUp da avvisi di sicurezza correlati**.  Verrà visualizzata la pagina Regole di analisi.  Anche in questo caso, selezionare la regola **Rilevare l'attività di eliminazione CoreBackUp dagli avvisi di sicurezza correlati**. Finestra che si apre a destra, che fornisce informazioni sulla regola e sulle operazioni eseguite.  Seleziona **Crea regola**.  
    1. Anche se i dettagli della logica della regola non rientrano nell'ambito dei concetti fondamentali, esaminare ogni scheda della creazione della regola per visualizzare il tipo di informazioni che è possibile configurare
    1. Quando si raggiunge la scheda Rivedi e crea, selezionare **Salva**.

1. Tornare alla pagina Sentinel selezionando **Microsoft Sentinel | Hub contenuti** dalla barra di navigazione nella parte superiore della pagina, al di sopra di Regole di analisi.

1. Tenere aperta la pagina perché verrà usata nell'attività successiva.


### Attività 4

In questa attività verranno illustrate alcune delle opzioni disponibili in Sentinel.

1. Dal riquadro di spostamento sinistro, selezionare **Ricerca**.  Nella parte superiore della pagina, selezionare la scheda **Query**. Leggere la descrizione relativa a cosa è una query di ricerca. È possibile aggiungere query di ricerca tramite l'Hub contenuti. Tutte le query installate in precedenza verranno elencate qui. Selezionare **Passa a Hub contenuti**.  L'Hub contenuti elenca contenuti che includono query come parte di una soluzione o come query autonoma.  Scorrere verso il basso per visualizzare le opzioni disponibili. Chiudere la finestra selezionando la **X** nell'angolo in alto a destra.

1. Dal riquadro di spostamento sinistro, selezionare **MITRE ATT&CK**.  MITRE ATT&CK è una knowledge base pubblica di tattiche e tecniche comunemente usate dagli utenti malintenzionati. Con Microsoft Sentinel è possibile visualizzare i rilevamenti già attivi nell'area di lavoro e quelli disponibili per la configurazione, per comprendere la copertura della sicurezza dell'organizzazione, in base alle tattiche e alle tecniche del framework MITRE ATT&CK®.  Selezionare una cella della matrice e prendere nota delle informazioni disponibili sul lato destro della schermata. **Nota:** potrebbe essere necessario selezionare "**<<**" all'estremità destra della finestra per visualizzare il riquadro delle informazioni.

1. Dal riquadro di spostamento sinistro, selezionare **Community**. La pagina della community include informazioni dettagliate sulla cybersecurity e aggiornamenti di Microsoft Research, un collegamento a un elenco di blog di Microsoft Sentinel, un collegamento ai forum di Microsoft Sentinel, collegamenti alle edizioni più recenti nell'hub di Microsoft Sentinel e altro ancora. Esplorare questi elementi come si vuole.

1. Dal riquadro di spostamento a sinistra, selezionare **Analisi**.  Saranno presenti due regole attive, una disponibile per impostazione predefinita e l'altra creata nell'attività precedente. Selezionare la regola predefinita **Rilevamento avanzato attacchi multifase**.  Prendere nota delle informazioni dettagliate.  Microsoft Sentinel usa Fusion, un motore di correlazione basato su algoritmi di Machine Learning scalabili, per rilevare automaticamente gli attacchi multistage (noti anche come minacce persistenti avanzate) identificando combinazioni di comportamenti anomali e attività sospette che vengono osservate in varie fasi della kill chain. Sulla base di queste individuazioni, Microsoft Sentinel genera eventi imprevisti che altrimenti sarebbero difficili da intercettare. **Nota:** potrebbe essere necessario selezionare "**<<**" all'estremità destra della finestra per visualizzare il riquadro delle informazioni.

1. Dal riquadro di spostamento a sinistra, selezionare **Automazione**.  Qui è possibile creare semplici regole di automazione, integrare i playbook esistenti o crearne di nuovi.  Selezionare **+ Crea** e quindi selezionare **Regola di automazione**.  Notare la finestra visualizzata sul lato destro della schermata e le opzioni disponibili per creare condizioni e azioni.  Selezionare **Annulla** nella parte inferiore della schermata.

1. Dal riquadro di spostamento a sinistra selezionare **Cartelle di lavoro**. Leggere la descrizione della cartella di lavoro di Microsoft Sentinel.  Le cartelle di lavoro possono essere aggiunte tramite l'Hub contenuti. Tutte le cartelle di lavoro installate in precedenza verranno elencate qui. Selezionare **Passa a Hub contenuti**.  L'Hub contenuti elenca contenuti che includono cartelle di lavoro come parte di una soluzione o come cartella di lavoro autonoma. Scorrere verso il basso per visualizzare le opzioni disponibili.

1. Chiudere la finestra selezionando la **X** nell'angolo in alto a destra della schermata.

1. Nell'angolo superiore sinistro della finestra, subito sotto la barra blu, selezionare **Home** per tornare alla home page del portale di Azure.

1. Disconnettersi e chiudere tutte le schede del browser aperte.

### Revisione

In questa demo IV sono stati illustrati i passaggi per la connessione di Microsoft Sentinel alle origini dati, è stata impostata una cartella di lavoro e sono state presentate varie opzioni disponibili in Microsoft Sentinel.
