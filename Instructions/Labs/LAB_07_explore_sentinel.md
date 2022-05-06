---
lab:
  title: Esplorare Microsoft Sentinel
  module: 'Module 3 Lesson 3: Describe the capabilities of Microsoft security solutions: Describe security capabilities of Microsoft Sentinel'
ms.openlocfilehash: 857d7f5ad5e0a9136d298c32cd47063a83e454e7
ms.sourcegitcommit: 25998048c2e354ea23d6f497205e8a062d34ac80
ms.translationtype: HT
ms.contentlocale: it-IT
ms.lasthandoff: 05/04/2022
ms.locfileid: "144557159"
---
# <a name="lab-explore-microsoft-sentinel"></a>Laboratorio: Esplorare Microsoft Sentinel

## <a name="lab-scenario"></a>Scenario del lab

In questo lab verrà illustrato il processo di creazione di un'istanza di Microsoft Sentinel.  Verranno anche configurate le autorizzazioni per garantire l'accesso alle risorse che verranno distribuite per supportare Microsoft Sentinel.  Dopo aver completato questa configurazione di base, verranno illustrati i passaggi per connettere Microsoft Sentinel alle origini dati, per configurare una cartella di lavoro e verranno illustrate brevemente alcune delle funzionalità chiave disponibili in Microsoft Sentinel.  

**Tempo stimato**: 45-60 minuti

### <a name="task-1"></a>Attività 1

Creare un'istanza di Microsoft Sentinel

1. Aprire la scheda del browser, **Home-Microsoft Azure**.  Se la scheda era stata chiusa in precedenza, aprire una pagina del browser e nella barra degli indirizzi inserire portal.azure.com e accedere di nuovo.

1. Nella casella di ricerca, nella barra blu nella parte superiore della pagina accanto a Microsoft Azure, immettere **Microsoft Sentinel** e quindi selezionare **Microsoft Sentinel** dai risultati della ricerca.

1. Nella pagina di Microsoft Sentinel selezionare **Crea Microsoft Sentinel**.

1. Nella pagina Aggiungi Microsoft Sentinel a un'area di lavoro selezionare **Crea una nuova area di lavoro**.

1. Dalla scheda generale di Crea area di lavoro Log Analytics, inserire quanto segue:
    1. Sottoscrizione:  **Azure Pass - Sponsorship**
    1. Gruppo di risorse: selezionare **Crea nuovo**, quindi inserire il nome **SC900-Sentinel-RG** e selezionare **OK**.
    1. Nome: **SC900-LogAnalytics-workspace**.
    1. Area: **Stati Uniti orientali** (è possibile selezionare un'area predefinita diversa in base alla località)
    1. Al termine, selezionare **Avanti: Tag >**

1. Per i Tag, è possibile lasciare questo campo vuoto, quindi selezionare **Verifica + Crea**.

1. Verificare le informazioni inserite e selezionare **Crea**.

1. Potrebbe volerci un minuto o due perché la nuova area di lavoro compaia nell'elenco; se non compare, selezionare **Aggiorna**, quindi selezionare **Aggiungi**.

1. Dopo aver aggiunto la nuova area di lavoro, verrà visualizzata la pagina Microsoft Sentinel | Novità e guide.  Osservare i tre passaggi elencati nella pagina Guida introduttiva.

1. Tenere aperta la pagina poiché verrà usata nell'attività successiva.

### <a name="task-2"></a>Attività 2

Una volta creata l'istanza di Microsoft Sentinel, ci si assicurerà di disporre dell'accesso necessario alle risorse distribuite per il supporto di Microsoft Sentinel.

1. Nella casella di ricerca, nella barra blu nella parte superiore della pagina accanto a Microsoft Azure, inserire **gruppi di risorse** quindi selezionare **Gruppi di risorse** dai risultati della ricerca. L'assegnazione del ruolo a livello di gruppo di risorse garantirà che il ruolo venga applicato a tutte le risorse distribuite per il supporto di Microsoft Sentinel.

1. Nella pagina Gruppi di risorse selezionare il gruppo di risorse creato con Microsoft Sentinel, **SC900-Sentinel-RG**.

1. Dalla pagina SC900-Sentinel-RG, selezionare **Controllo di accesso (IAM)** dal riquadro di spostamento sinistro.

1. Dalla pagina Controllo di accesso selezionare **Visualizza accesso personale**.  Come amministratore MOD, il ruolo corrente è Amministratore del supporto del servizio.  In questo modo verranno concesse le autorizzazioni necessarie, ma è importante comprendere i ruoli specifici di Sentinel disponibili.  Chiudere la finestra delle assegnazioni di Amministratore MOD selezionando la **X** nell'angolo in alto a destra della finestra.

    1. Dalla pagina Controllo di accesso selezionare **+Aggiungi**, quindi selezionare **Add role assignment** (Aggiungi assegnazione di ruolo).

    1. Si apre la finestra Add role assignment (Aggiungi assegnazione di ruolo).  Nella casella di ricerca immettere **Microsoft Sentinel** per visualizzare i 4 ruoli associati a Microsoft Sentinel.
    1. Da uno dei ruoli elencati, selezionare **visualizza** per visualizzarne i dettagli.  Come procedura consigliata si dovrebbe assegnare il privilegio minimo richiesto per il ruolo.  

    1. Chiudere la finestra selezionando la **X** nell'angolo superiore destro della finestra.

1. Nella pagina di controllo dell'accesso chiudere la finestra selezionando la **X** nell'angolo superiore destro della finestra.

### <a name="task-3"></a>Attività 3

In questa attività si esaminerà il processo di connessione di Microsoft Sentinel all'origine dati per iniziare a raccogliere dati.

1. Nella casella di ricerca, nella barra blu nella parte superiore della pagina accanto a Microsoft Azure, immettere **Microsoft Sentinel** e quindi selezionare **Microsoft Sentinel** dai risultati della ricerca.

1. Nella pagina di Microsoft Sentinel selezionare l'area di lavoro creata con l'istanza di Microsoft Sentinel, **SC900-LogAnalytics-workspace**.

1. Il primo passaggio con Microsoft Sentinel prevede di essere in grado di raccogliere dati. Dal riquadro di spostamento sinistro selezionare **Connettori dati**, elencati sotto la configurazione.

1. Dalla pagina Connettori dati, scorrere verso il basso nella finestra principale per visualizzare l'elenco completo dei connettori disponibili. Nella casella di ricerca della pagina Connettori dati immettere **Office 365** quindi scegliere **Office 365** dall'elenco.

1. Verrà visualizzata la finestra del connettore Office 365.  Selezionare **Apri la pagina del connettore**.

1. Nella pagina del connettore Office 365 esaminare la descrizione sul lato sinistro della finestra.

1. La scheda delle istruzioni nella finestra principale indica i perquisiti per integrare Microsoft Sentinel con Office 365. Questi prerequisiti dovrebbero apparire tutti contrassegnati con un segno di spunta verde.   In Configurazione selezionare **Exchange** e **SharePoint** quindi selezionare Applica modifiche.  Quasi immediatamente verrà visualizzato lo stato connesso sul lato sinistro della finestra.

1. Chiudere la finestra selezionando la **X** nell'angolo superiore destro della finestra per tornare alla pagina dei connettori dati.

1. La parte superiore della pagina dei connettori dati dovrebbe mostrare 1 connesso, per indicare che si è ora connessi a Office 365. In caso contrario, selezionare **Aggiorna**. L'aggiornamento della pagina potrebbe richiedere alcuni minuti.

1. Tenere aperta la pagina poiché verrà usata nell'attività successiva.

### <a name="task-4"></a>Attività 4

In questa attività verrà illustrato il processo di configurazione di una cartella di lavoro per Office 365, per visualizzare e monitorare i dati.

1. Dal riquadro di spostamento sinistro, selezionare **Cartelle di lavoro**.

1. Nella casella di ricerca immettere Office 365 quindi selezionare **Office 365**.

1. Nella finestra che viene visualizzata sul lato destro della schermata esaminare la descrizione, selezionare **Salva** nella parte inferiore della schermata e quindi selezionare **OK** per salvare la cartella di lavoro nel percorso predefinito.  A questo punto selezionare **Visualizza la cartella di lavoro salvata**.

1. Verrà visualizzata la pagina Cartelle di lavoro Office 365.  Selezionare la freccia a discesa accanto a **Operazioni: annulla impostazioni** e quindi selezionare **Tutto**.  Selezionare ora la freccia a discesa accanto a **Utenti: query in sospeso** e selezionare **Tutte**.  Selezionare l'**icona di salvataggio (disco).** Chiudere la finestra selezionando la **X** nell'angolo superiore destro della finestra. La visualizzazione dei dati nella cartella di lavoro può richiedere alcuni minuti. Si tornerà pertanto alle cartelle di lavoro in un secondo momento.

1. Nell'angolo in alto a sinistra della pagina Cartelle di lavoro, sopra Cartelle di lavoro, selezionare **Microsoft Sentinel**. Verrà visualizzata la pagina di panoramica.

### <a name="task-5"></a>Attività 5

In questa attività verranno illustrate alcune delle opzioni disponibili in Sentinel.

1. Dal riquadro di spostamento sinistro selezionare **Ricerca**.  Nella scheda **Query**, che è selezionata (sottolineata), selezionare una query qualsiasi dall'elenco.  Dopo aver selezionato una query, prendere nota delle informazioni fornite su tale query, incluso il codice per la query, nonché l'opzione per eseguire la query e visualizzare i risultati.  Non selezionare nulla.

1. Dal riquadro di spostamento sinistro, selezionare **MITRE ATT&CK**.  MITRE ATT&CK è una knowledge base pubblica di tattiche e tecniche comunemente usate dagli utenti malintenzionati. Con Microsoft Sentinel è possibile visualizzare i rilevamenti già attivi nell'area di lavoro e quelli disponibili per la configurazione, per comprendere la copertura della sicurezza dell'organizzazione, in base alle tattiche e alle tecniche del framework MITRE ATT&CK®.  Selezionare una cella della matrice e prendere nota delle informazioni disponibili sul lato destro della schermata.  

1. Dal riquadro di spostamento sinistro, selezionare **Community**. Gli analisti della sicurezza di Microsoft creano e aggiungono continuamente nuove cartelle di lavoro, playbook, query di ricerca e altro ancora, pubblicandoli nella community perché ognuno possa usarli nel proprio ambiente. È possibile scaricare contenuto di esempio dal repository GitHub privato della community, per creare cartelle di lavoro, query di ricerca, blocchi appunti e playbook personalizzati per Azure Sentinel.  Selezionare **Onboard community content** (Carica contenuti della community).  Viene aperta una nuova scheda del repository GitHub in cui è possibile scaricare il contenuto per abilitare gli scenari.  Tornare alla scheda di Azure nel browser.

1. Dal riquadro di spostamento sinistro, selezionare **Analisi**.  Selezionare il primo elemento nell'elenco **Advanced Multistage Attack Detection** (Rilevamento avanzato attacchi multistage).  Prendere nota delle informazioni dettagliate.  Microsoft Sentinel usa Fusion, un motore di correlazione basato su algoritmi di Machine Learning scalabili, per rilevare automaticamente gli attacchi multistage (noti anche come minacce persistenti avanzate) identificando combinazioni di comportamenti anomali e attività sospette che vengono osservate in varie fasi della kill chain. Sulla base di queste individuazioni, Microsoft Sentinel genera eventi imprevisti che altrimenti sarebbero difficili da intercettare.

1. Dal riquadro di spostamento sinistro, selezionare **Automazione**.  Qui è possibile creare semplicemente regole di automazione, integrare i playbook esistenti o crearne di nuovi.  Selezionare **+ Crea** e quindi selezionare **Regola di automazione**.  Notare la finestra visualizzata sul lato destro della schermata e le opzioni disponibili per creare condizioni e azioni.  Selezionare **Annulla** nella parte inferiore della schermata.

1. Dal riquadro di spostamento sinistro, selezionare **Cartelle di lavoro**. Dalla pagina Cartelle di lavoro, selezionare la scheda **Cartelle di lavoro personali** sopra la casella di ricerca.  La cartella di lavoro appena salvata è presente nell'elenco e disponibile per visualizzare e monitorare i dati.  Selezionare quindi **Office 365** dalla finestra che si apre sul lato destro della schermata e selezionare **Visualizza la cartella di lavoro salvata**.  Notare le visualizzazioni correlate ai carichi di lavoro Office 365.  

1. Chiudere la finestra selezionando la **X** nell'angolo superiore destro della finestra.

1. Nell'angolo superiore sinistro della finestra, subito sotto la barra blu, selezionare **Home** per tornare alla home page del portale di Azure.

### <a name="task-6"></a>Attività 6

Microsoft Sentinel viene fatturato in base al volume di dati inseriti per l'analisi in Microsoft Sentinel. Sebbene la quantità di dati inseriti come conseguenza di questo lab sia minima, è consigliabile eliminare il gruppo di risorse di Microsoft Sentinel una volta completata l'esplorazione delle funzionalità di Microsoft Sentinel.

1. Nella pagina di Microsoft Sentinel, nell'angolo in alto a sinistra della pagina, sopra a dove è visualizzato Microsoft Sentinel, selezionare **Tutti i servizi**.

2. Nella casella dei servizi del filtro, immettere i gruppi di risorse, quindi dall'elenco fornito selezionare **Gruppi di risorse**.

3. Nella pagina Gruppi di risorse selezionare il gruppo di risorse creato con Microsoft Sentinel, **SC900-ResourceGroup**.

4. Dalla parte centrale in alto della pagina, selezionare **Elimina gruppo di risorse**.  Esaminare l'avviso.  Immettere il nome del gruppo di risorse, **SC900-ResourceGroup**, quindi selezionare **Elimina** dalla parte inferiore della pagina.  L'eliminazione del gruppo di risorse impiegherà diversi minuti.

5. Una volta verificato che il gruppo di risorse è stato eliminato, chiudere la pagina del browser.

### <a name="review"></a>Verifica

In questa demo sono stati illustrati i passaggi per la connessione di Microsoft Sentinel alle origini dati, è stata impostata una cartella di lavoro e sono state descritte varie opzioni disponibili in Microsoft Sentinel.
