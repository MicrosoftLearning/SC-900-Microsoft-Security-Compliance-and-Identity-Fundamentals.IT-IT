---
ms.openlocfilehash: ef5c993972dcff57836c8ac045a19903b8c15721
ms.sourcegitcommit: 15658ca1c7bae8a4dbaa33ab6f897070bde521b9
ms.translationtype: HT
ms.contentlocale: it-IT
ms.lasthandoff: 09/12/2022
ms.locfileid: "147892630"
---
<a name="---"></a><!---
---
Lab: Titolo: 'Esplorare Microsoft Defender for Cloud Apps' Modulo: 'Percorso di apprendimento: Descrivere le funzionalità delle soluzioni di sicurezza Microsoft; Modulo 4: Descrivere le funzionalità di protezione dalle minacce di Microsoft 365; Unità 5: Descrivere Microsoft Defender for Cloud Apps'
---
--->

# <a name="lab-explore-microsoft-defender-for-cloud-apps"></a>Laboratorio: Esplorare Microsoft Defender for Cloud Apps

Questo lab corrisponde al contenuto di Learn seguente:

- Percorso di apprendimento: Descrivere le funzionalità delle soluzioni di sicurezza Microsoft
- Modulo: Descrivere le funzionalità di protezione dalle minacce di Microsoft 365
- Unità: Descrivere Microsoft Defender for Cloud Apps

## <a name="lab-scenario"></a>Scenario del lab

In questo lab verranno esplorate le funzionalità di Microsoft Defender for Cloud Apps.  Verranno esaminate le informazioni disponibili sul dashboard Cloud Discovery nonché le funzionalità disponibili per indagare le scoperte e controllare l'impatto sulla propria organizzazione attraverso criteri.  Nota:  un'organizzazione deve avere una licenza per usare Microsoft Defender for Cloud Apps, che è un servizio con sottoscrizione basato sull'utente.

**Tempo stimato**: 15-20 minuti

### <a name="task-1"></a>Attività 1

Esplorare Cloud Discovery.

1. Aprire Microsoft Edge. Nella barra degli indirizzi immettere **admin.microsoft.com**.

1. Accedere con le credenziali di amministratore.
    1. Nella finestra Accedi immettere **admin@WWLxZZZZZZ.onmicrosoft.com** (dove ZZZZZZ è l'ID tenant univoco fornito dal proprio provider di hosting del lab) e quindi selezionare **Avanti**.
    1. Immettere la password di amministratore, che dovrebbe essere fornita dal proprio provider di hosting del lab. Fare clic su **Accedi**.
    1. Quando compare la domanda se rimanere connessi, selezionare **Sì**. In questo modo si accede alla pagina dell'interfaccia di amministrazione di Microsoft 365.

1. Dal riquadro di spostamento sinistro dell'interfaccia di amministrazione di Microsoft 365, selezionare **Mostra tutto**.

1. In Interfacce di amministrazione selezionare **Sicurezza**.  Si apre una nuova pagina del browser alla pagina di benvenuto del portale Microsoft 365 Defender.  

1. Dalla parte inferiore del riquadro di spostamento sinistro della pagina di Microsoft 365 Defender, selezionare **Altre risorse**.

1. Nella scheda **Microsoft Defender for Cloud Apps** selezionare **Apri**.  Si apre una nuova pagina del browser sul dashboard di Cloud App Security.  Osservare le schede di informazioni disponibili.  È possibile che non sia visibile alcuna informazione sulle schede, dato che questo è un ambiente tenant di laboratorio preconfigurato che non è stato utilizzato attivamente.  

1. Dal riquadro di spostamento sinistro, selezionare **Individua**, quindi dal menu a discesa selezionare **Dashboard Cloud Discovery**.  Il dashboard include una panoramica delle app individuate, categorie di app, livelli di rischio e altro.  
    1. Dalla parte superiore della pagina Cloud Discovery, selezionare la scheda **App individuate**.  La finestra delle app individuate fornisce una vista più dettagliata delle app individuate, inclusi punteggio di rischio, traffico, numero di utenti e altro.
        1. Da qualsiasi voce dell'elenco, selezionare i **puntini di sospensione** nella colonna delle azioni della tabella.  Notare le varie opzioni disponibili, inclusa la funzione di contrassegnare un'app come approvata o non approvata.  Selezionare di nuovo i puntini di sospensione per chiudere la casella delle azioni.
        1. Selezionando una voce specifica si apre una pagina di dettagli per l'applicazione specifica.  Selezionare una voce dall'elenco.  Per la voce selezionata, esaminare ogni scheda nella parte superiore della pagina dei dettagli:  **Utilizzo**, **Info, Indirizzi** **IP**, **Utenti** e **Avvisi**. Dopo aver esaminato la pagina dei dettagli, tornare alle app scoperte selezionando **App individuate** dal riquadro di spostamento sinistro.
    1. Dalla parte superiore della pagina, selezionare la scheda **Indirizzi IP** (questa operazione equivale a selezionare gli indirizzi IP dal riquadro di spostamento a sinistra).  Qui sono riportati i dati tra cui il numero di transazioni, la quantità di traffico e le quantità di upload, per indirizzi IP.  È anche possibile filtrare per indirizzo IP specifico o esportare i dati per ulteriori analisi.
    1. Dalla parte superiore della pagina (o dal riquadro di spostamento sinistro) selezionare **Utenti**.  Questo è lo stesso tipo di informazioni fornite quando si selezionano gli indirizzi IP, ma sono elencate per i singoli utenti.  Anche qui, è possibile filtrare per utente specifico ed esportare i dati per ulteriori analisi.

1. Le informazioni fornite in queste schede si basano su report istantanei dai registri del traffico che caricati manualmente dai firewall e proxy o da report continui che analizzano tutti i registri che vengono inoltrati dalla rete utilizzando Cloud App Security.  Per vedere dove si trova questa impostazione, selezionare i **puntini di sospensione** verticali nell'angolo in alto a destra della pagina.
    1. Selezionare la prima opzione, **Create Cloud Discovery snapshot report** (Crea report snapshot di Cloud Discovery). Qui si compilano i dettagli richiesti e si caricano i registri del traffico per generare e caricare un report.  Selezionare **Esci**.  I dati visualizzati per il tenant di laboratorio provengono da un report Snapshot; queste informazioni sono riportate nell'angolo in alto a destra dello schermo.
    1. Per vedere l'opzione per i report continui, selezionare i **puntini di sospensione** nell'angolo in alto a destra della pagina e dal menu a tendina selezionare **Configura il caricamento automatico**.  Non ci sono origini dati collegate, ma è qui che si può aggiungere un'origine dati. Selezionare **Aggiungi origine dati**, quindi nella finestra Aggiungi origine dati selezionare la freccia a discesa nel campo Origine per visualizzare i tipi di appliance che è possibile connettere come origine dati.  Selezionare **Annulla** per uscire.

1. Un altro punto da sottolineare è che è possibile connettersi alle app direttamente impostando i connettori delle app che offriranno una maggiore visibilità e controllo delle app cloud. Dall'angolo in alto a sinistra dello schermo, selezionare l'**icona dell'ingranaggio Impostazioni** e dall'elenco a discesa, selezionare **Connettori app**.  
    1. Nella pagina delle app collegate, dovrebbe essere visibile Office 365 nell'elenco con uno stato collegato.  Se Office 365 mostra un errore di connessione, molto probabilmente è perché Controllo non è attivato.
    1. Selezionare **+Connetti un'app** e dal menu a discesa selezionare **Microsoft Azure**.  Dalla finestra pop-up di Microsoft Azure, selezionare **Connetti Microsoft Azure**.  Verrà visualizzato lo stato connesso e le informazioni sulla scansione di utenti, dati e attività.  Selezionare il **pulsante Chiudi**.

1. Tenere aperta la pagina poiché verrà usata nell'attività successiva.

### <a name="task-2"></a>Attività 2

Esplorare i modi in cui è possibile esaminare le attività registrate.

1. Dal riquadro di spostamento sinistro, sotto Esamina, selezionare **Log attività**.  Qui si ottiene la visibilità in tutte le attività dalle app connesse.   Poiché il connettore di Office 365 è già connesso, dovrebbero essere visibili alcuni dati. Dopo la connessione a un'app tramite il connettore app, Cloud App Security analizza tutte le attività eseguite (il periodo di retroattività dell'analisi varia a seconda dell'app) e quindi viene aggiornato con le nuove attività.  

1. Selezionare la colonna delle attività per qualsiasi elemento per visualizzare informazioni più dettagliate. All'estrema destra dell'elemento selezionato selezionare i **puntini di sospensione** verticali.  Notare le varie opzioni.  Selezionare la colonna delle attività per lo stesso elemento per comprimere la visualizzazione dettagliata.

1. Nella parte superiore della pagina è presente l'opzione per aggiungere un nuovo criterio dalla ricerca o per esportare i dati per ulteriori analisi.  Selezionare **+Nuovo criterio dalla ricerca**.  È possibile creare un criterio basato su un modello, selezionare una gravità e una categoria del criterio, creare filtri per il criterio, creare avvisi e persino inviare gli avvisi a Power Automate.  Selezionare **Annulla** per uscire dalla finestra di creazione dei criteri.

1. Dal riquadro di spostamento sinistro, selezionare ed esplorare l'opzione **File** e notare le opzioni per filtrare i dati, creare un criterio per i file ed esportare i dati.  

1. Nel pannello di spostamento a sinistra selezionare ed esplorare l'opzione **utente e account**.  Notare le opzioni per filtrare ed esportare i dati.

1. Dal riquadro di spostamento sinistro selezionare **Configurazione di sicurezza**. Questa pagina contiene le valutazioni della configurazione di sicurezza per gli account Azure, Amazon Web Services (AWS) e Google Cloud Platform (GCP).

1. Tenere aperta la pagina poiché verrà usata nell'attività successiva.

### <a name="task-3"></a>Attività 3

In questa attività si esploreranno le pagine dei criteri e degli avvisi in Microsoft Defender for Cloud Apps.

1. Nel pannello di spostamento a sinistra selezionare la freccia a discesa accanto a **Controllo** e quindi selezionare **Criteri**.  I criteri elencati offrono informazioni sul numero di avvisi generati dai criteri, la gravità e così via. Quando si seleziona una voce, come **Accesso a rischio**, viene offerta un'opzione per modificare il criterio. Selezionare **Annulla** nella parte inferiore della pagina.

1. Dal riquadro di spostamento sinistro, selezionare **Avvisi**.  Se sono elencati degli avvisi, selezionare una voce dall'elenco degli avvisi. Esaminare le informazioni fornite.  Dal lato superiore destro della finestra, selezionare **Chiudi avviso** per visualizzare le opzioni di chiusura dell'avviso.  

1. Chiudere tutte le schede del browser aperte.

### <a name="review"></a>Verifica

In questo lab sono state esplorate le funzionalità di Microsoft Defender for Cloud Apps.  Sono state esaminate le informazioni disponibili sul dashboard Cloud Discovery nonché le funzionalità disponibili per analizzare le scoperte e controllare l'impatto sulla propria organizzazione attraverso criteri.
