---
Demo:
  title: Microsoft Sentinel
  module: 'Module 3 Lesson 3: Describe the capabilities of Microsoft security solutions: Describe security capabilities of Microsoft Sentinel'
ms.openlocfilehash: 242d971510a428170a0d531b1ddcdf422ed4f9c9
ms.sourcegitcommit: 25998048c2e354ea23d6f497205e8a062d34ac80
ms.translationtype: HT
ms.contentlocale: it-IT
ms.lasthandoff: 05/04/2022
ms.locfileid: "144557327"
---
# <a name="demo-microsoft-sentinel"></a>Dimostrazione: Microsoft Sentinel

## <a name="demo-scenario"></a>Scenario demo

Questa demo illustrerÃ  il processo di creazione di un'istanza di Microsoft Sentinel.  Verranno anche configurate le autorizzazioni per garantire l'accesso alle risorse che verranno distribuite per supportare Microsoft Sentinel.  Dopo aver completato questa configurazione di base, verranno illustrati i passaggi per connettere Microsoft Sentinel alle origini dati e creare una cartella di lavoro per monitorare e visualizzare i dati.  Infine, verranno visualizzate alcune altre opzioni disponibili, tra cui l'analisi integrata che consente di ricevere notifiche in merito a qualsiasi attivitÃ  sospetta, la funzionalitÃ  di automazione e altro ancora.

### <a name="pre-demo-setup--create-an-microsoft-sentinel-instance"></a>Configurazione preliminare della demo:  Creare un'istanza di Microsoft Sentinel

1. Aprire la scheda del browser, **Home-Microsoft Azure**.  Se la scheda era stata chiusa in precedenza, aprire una pagina del browser e nella barra degli indirizzi inserire portal.azure.com e accedere di nuovo.

1. Nella casella di ricerca, nella barra blu nella parte superiore della pagina accanto a Microsoft Azure, immettere **Microsoft Sentinel** e quindi selezionare **Microsoft Sentinel** dai risultati della ricerca.

1. Nella pagina di Microsoft Sentinel selezionare **Crea Microsoft Sentinel**.

1. Nella pagina Aggiungi Microsoft Sentinel a un'area di lavoro selezionare **Crea una nuova area di lavoro**.

1. Dalla scheda generale di Crea area di lavoro Log Analytics, inserire quanto segue:
    1. Sottoscrizione:  **Azure Pass - Sponsorship**
    1. Gruppo di risorse: selezionare **Crea nuovo**, quindi inserire il nome **SC900-Sentinel-RG** e selezionare **OK**.
    1. Nome: **SC900-LogAnalytics-workspace**.
    1. Area: **Stati Uniti orientali** (Ã¨ possibile selezionare un'area predefinita diversa in base alla localitÃ )
    1. Al termine, selezionare **Avanti: Tag >**

1. Per i Tag, Ã¨ possibile lasciare questo campo vuoto, quindi selezionare **Verifica + Crea**.

1. Verificare le informazioni inserite e selezionare **Crea**.

1. Potrebbe volerci un minuto o due perchÃ© la nuova area di lavoro compaia nell'elenco; se non compare, selezionare **Aggiorna**, quindi selezionare **Aggiungi**.

1. Dopo aver aggiunto la nuova area di lavoro, verrÃ  visualizzata la pagina Microsoft Sentinel | NovitÃ  e guide.  Osservare i tre passaggi elencati nella pagina Guida introduttiva.

1. Tenere aperta la pagina poichÃ© verrÃ  usata nell'attivitÃ  successiva.

### <a name="demo-part-2"></a>Demo parte 2

Una volta creata l'istanza di Microsoft Sentinel, ci si assicurerÃ  di disporre dell'accesso necessario alle risorse distribuite per il supporto di Microsoft Sentinel.  

1. Nella casella di ricerca, nella barra blu nella parte superiore della pagina accanto a Microsoft Azure, inserire **gruppi di risorse** quindi selezionare **Gruppi di risorse** dai risultati della ricerca. L'assegnazione del ruolo a livello di gruppo di risorse garantirÃ  che il ruolo venga applicato a tutte le risorse distribuite per il supporto di Microsoft Sentinel.

1. Nella pagina Gruppi di risorse selezionare il gruppo di risorse creato con Microsoft Sentinel, **SC900-Sentinel-RG**.

1. Dalla pagina SC900-Sentinel-RG, selezionare **Controllo di accesso (IAM)** dal riquadro di spostamento sinistro.

1. Dalla pagina Controllo di accesso selezionare **Visualizza accesso personale**.  Come amministratore MOD, il ruolo corrente Ã¨ Amministratore del supporto del servizio.  In questo modo verranno concesse le autorizzazioni necessarie. Tuttavia, ai fini della demo, Ã¨ possibile che si voglia visualizzare i ruoli specifici di Sentinel.  Chiudere la finestra delle assegnazioni di Amministratore MOD selezionando la **X** nell'angolo in alto a destra della finestra.

    1. Dalla pagina Controllo di accesso selezionare **+Aggiungi**, quindi selezionare **Add role assignment** (Aggiungi assegnazione di ruolo).

    1. Si apre la finestra Add role assignment (Aggiungi assegnazione di ruolo).  Nella casella di ricerca immettere **Microsoft Sentinel** per visualizzare i 4 ruoli associati a Microsoft Sentinel.
    1. Da uno dei ruoli elencati, selezionare **visualizza** per visualizzarne i dettagli.  Come procedura consigliata si dovrebbe assegnare il privilegio minimo richiesto per il ruolo.  

    1. Chiudere la finestra selezionando la **X** nell'angolo superiore destro della finestra.

1. Nella pagina di controllo dell'accesso chiudere la finestra selezionando la **X** nell'angolo superiore destro della finestra.

### <a name="demo-part-3"></a>Demo parte 3

Questa parte della demo illustrerÃ  il processo di connessione di Microsoft Sentinel all'origine dati per iniziare a raccogliere dati.

1. Nella casella di ricerca, nella barra blu nella parte superiore della pagina accanto a Microsoft Azure, immettere **Microsoft Sentinel** e quindi selezionare **Microsoft Sentinel** dai risultati della ricerca.

1. Nella pagina di Microsoft Sentinel selezionare l'area di lavoro creata con l'istanza di Microsoft Sentinel, **SC900-LogAnalytics-workspace**.

1. Il primo passaggio con Microsoft Sentinel prevede di essere in grado di raccogliere dati. Dal riquadro di spostamento sinistro selezionare **Connettori dati**, elencati sotto la configurazione.

1. Dalla pagina Connettori dati, scorrere verso il basso nella finestra principale per visualizzare l'elenco completo dei connettori disponibili. Nella casella di ricerca della pagina Connettori dati immettere **Office 365** quindi scegliere **Office 365** dall'elenco.

1. VerrÃ  visualizzata la finestra del connettore Office 365.  Selezionare **Apri la pagina del connettore**.

1. Nella pagina del connettore Office 365 esaminare la descrizione sul lato sinistro della finestra.

1. La scheda delle istruzioni nella finestra principale indica i perquisiti per integrare Microsoft Sentinel con Office 365. Questi prerequisiti dovrebbero apparire tutti contrassegnati con un segno di spunta verde.   In Configurazione selezionare **Exchange** e **SharePoint** quindi selezionare Applica modifiche.  Quasi immediatamente verrÃ  visualizzato lo stato connesso sul lato sinistro della finestra.

1. Chiudere la finestra selezionando la **X** nell'angolo superiore destro della finestra per tornare alla pagina dei connettori dati.

1. La parte superiore della pagina dei connettori dati dovrebbe mostrare 1 connesso, per indicare che si Ã¨ ora connessi a Office 365. In caso contrario, selezionare **Aggiorna**. L'aggiornamento della pagina potrebbe richiedere alcuni minuti.

1. Tenere aperta la pagina poichÃ© verrÃ  usata nell'attivitÃ  successiva.

### <a name="demo-part-4"></a>Demo parte 4

In questa parte della demo verrÃ  illustrato il processo di configurazione di una cartella di lavoro per Office 365, per visualizzare e monitorare i dati.

1. Dal riquadro di spostamento sinistro, selezionare **Cartelle di lavoro**.

1. Nella casella di ricerca immettere Office 365 quindi selezionare **Office 365**.

1. Nella finestra che viene visualizzata sul lato destro della schermata esaminare la descrizione, selezionare **Salva** nella parte inferiore della schermata e quindi selezionare **OK** per salvare la cartella di lavoro nel percorso predefinito.  A questo punto selezionare **Visualizza la cartella di lavoro salvata**.

1. VerrÃ  visualizzata la pagina Cartelle di lavoro Office 365.  Selezionare la freccia a discesa accanto a **Operazioni: annulla impostazioni** e quindi selezionare **Tutto**.  Selezionare ora la freccia a discesa accanto a **Utenti: query in sospeso** e selezionare **Tutte**.  Selezionare l'**icona di salvataggio (disco).** Chiudere la finestra selezionando la **X** nell'angolo superiore destro della finestra. La visualizzazione dei dati nella cartella di lavoro puÃ² richiedere alcuni minuti. Si tornerÃ  pertanto alle cartelle di lavoro in un secondo momento.

1. Nell'angolo in alto a sinistra della pagina Cartelle di lavoro, sopra Cartelle di lavoro, selezionare **Microsoft Sentinel**. VerrÃ  visualizzata la pagina di panoramica.

### <a name="demo-part-5"></a>Demo parte 5

In questa parte della demo verranno illustrate alcun opzioni disponibili in Sentinel.

1. Dal riquadro di spostamento sinistro selezionare **Ricerca**.  Nella scheda **Query**, che Ã¨ selezionata (sottolineata), selezionare una query qualsiasi dall'elenco.  Dopo aver selezionato una query, prendere nota delle informazioni fornite su tale query, incluso il codice per la query, nonchÃ© l'opzione per eseguire la query e visualizzare i risultati.  Non selezionare nulla.

1. Dal riquadro di spostamento sinistro, selezionare **MITRE ATT&CK**.  MITRE ATT&CK Ã¨ una knowledge base pubblica di tattiche e tecniche comunemente usate dagli utenti malintenzionati. Con Microsoft Sentinel Ã¨ possibile visualizzare i rilevamenti giÃ  attivi nell'area di lavoro e quelli disponibili per la configurazione, per comprendere la copertura della sicurezza dell'organizzazione, in base alle tattiche e alle tecniche del framework MITRE ATT&CKÂ®.  Selezionare una cella della matrice e prendere nota delle informazioni disponibili sul lato destro della schermata.  

1. Dal riquadro di spostamento sinistro, selezionare **Community**. Gli analisti della sicurezza di Microsoft creano e aggiungono continuamente nuove cartelle di lavoro, playbook, query di ricerca e altro ancora, pubblicandoli nella community perchÃ© ognuno possa usarli nel proprio ambiente. Ã possibile scaricare contenuto di esempio dal repository GitHub privato della community, per creare cartelle di lavoro, query di ricerca, blocchi appunti e playbook personalizzati per Azure Sentinel.  Selezionare **Onboard community content** (Carica contenuti della community).  Viene aperta una nuova scheda del repository GitHub in cui Ã¨ possibile scaricare il contenuto per abilitare gli scenari.  Tornare alla scheda di Azure nel browser.

1. Dal riquadro di spostamento sinistro, selezionare **Analisi**.  Selezionare il primo elemento nell'elenco **Advanced Multistage Attack Detection** (Rilevamento avanzato attacchi multistage).  Prendere nota delle informazioni dettagliate.  Microsoft Sentinel usa Fusion, un motore di correlazione basato su algoritmi di Machine Learning scalabili, per rilevare automaticamente gli attacchi multistage (noti anche come minacce persistenti avanzate) identificando combinazioni di comportamenti anomali e attivitÃ  sospette che vengono osservate in varie fasi della kill chain. Sulla base di queste individuazioni, Microsoft Sentinel genera eventi imprevisti che altrimenti sarebbero difficili da intercettare.

1. Dal riquadro di spostamento sinistro, selezionare **Automazione**.  Qui Ã¨ possibile creare semplicemente regole di automazione, integrare i playbook esistenti o crearne di nuovi.  Selezionare **+ Crea** e quindi selezionare **Regola di automazione**.  Notare la finestra visualizzata sul lato destro della schermata e le opzioni disponibili per creare condizioni e azioni.  Selezionare **Annulla** nella parte inferiore della schermata.

1. Dal riquadro di spostamento sinistro, selezionare **Cartelle di lavoro**. Dalla pagina Cartelle di lavoro, selezionare la scheda **Cartelle di lavoro personali** sopra la casella di ricerca.  La cartella di lavoro appena salvata Ã¨ presente nell'elenco e disponibile per visualizzare e monitorare i dati.  Selezionare quindi **Office 365** dalla finestra che si apre sul lato destro della schermata e selezionare **Visualizza la cartella di lavoro salvata**.  Notare le visualizzazioni correlate ai carichi di lavoro Office 365.  

1. Chiudere la finestra selezionando la **X** nell'angolo superiore destro della finestra.

1. Nell'angolo superiore sinistro della finestra, subito sotto la barra blu, selezionare **Home** per tornare alla home page del portale di Azure.

### <a name="task-6"></a>AttivitÃ  6

Cancellare i dati alla fine del corso. Microsoft Sentinel viene fatturato in base al volume di dati inseriti per l'analisi in Microsoft Sentinel. Sebbene la quantitÃ  di dati inseriti come conseguenza di questa demo sia minima, Ã¨ consigliabile eliminare il gruppo di risorse di Microsoft Sentinel una volta completata l'esplorazione delle funzionalitÃ  di Microsoft Sentinel.

1. Nella pagina di Microsoft Sentinel, nell'angolo in alto a sinistra della pagina, sopra a dove Ã¨ visualizzato Microsoft Sentinel, selezionare **Tutti i servizi**.

2. Nella casella dei servizi del filtro, immettere i gruppi di risorse, quindi dall'elenco fornito selezionare **Gruppi di risorse**.

3. Nella pagina Gruppi di risorse selezionare il gruppo di risorse creato con Microsoft Sentinel, **SC900-ResourceGroup**.

4. Dalla parte centrale in alto della pagina, selezionare **Elimina gruppo di risorse**.  Esaminare l'avviso.  Immettere il nome del gruppo di risorse, **SC900-ResourceGroup**, quindi selezionare **Elimina** dalla parte inferiore della pagina.  L'eliminazione del gruppo di risorse impiegherÃ  diversi minuti.

5. Una volta verificato che il gruppo di risorse Ã¨ stato eliminato, chiudere la pagina del browser.

### <a name="review"></a>Verifica

In questa demo sono stati illustrati i passaggi per la connessione di Microsoft Sentinel alle origini dati, Ã¨ stata impostata una cartella di lavoro e sono state descritte varie opzioni disponibili in Microsoft Sentinel.
