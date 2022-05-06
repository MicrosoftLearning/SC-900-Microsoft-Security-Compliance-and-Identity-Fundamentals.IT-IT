---
lab:
  title: Esplorare Microsoft Defender per il cloud
  module: 'Module 3 Lesson 2: Describe the capabilities of Microsoft security solutions: Describe security management capabilities of Azure'
ms.openlocfilehash: 580e84e726a6ba9c7d9109881710e08f059d0818
ms.sourcegitcommit: 25998048c2e354ea23d6f497205e8a062d34ac80
ms.translationtype: HT
ms.contentlocale: it-IT
ms.lasthandoff: 05/04/2022
ms.locfileid: "144557574"
---
# <a name="lab-explore-microsoft-defender-for-cloud"></a>Laboratorio: Esplorare Microsoft Defender per il cloud

## <a name="lab-scenario"></a>Scenario del lab

In questo lab verrà esplorato Microsoft Defender per il cloud e si apprenderà in che modo il punteggio di sicurezza di Azure può essere usato per migliorare la postura di sicurezza dell'organizzazione.

**Tempo stimato**: 30 minuti

### <a name="task-1"></a>Attività 1

Questa attività include una breve presentazione di Microsoft Defender per il cloud.

1. Aprire Microsoft Edge. Nella barra degli indirizzi immettere **portal.azure.com**.

1. Accedere con le credenziali di amministratore.
    1. Nella finestra Accedi immettere **admin@WWLxZZZZZZ.onmicrosoft.com** (dove ZZZZZZ è l'ID tenant univoco fornito dal proprio provider di hosting del lab) e quindi selezionare **Avanti**.
    1. Immettere la password di amministratore, che dovrebbe essere fornita dal proprio provider di hosting del lab. Fare clic su **Accedi**.
    1. Quando compare la domanda se rimanere connessi, selezionare **Sì**.

1. Nell'angolo superiore sinistro della schermata, accanto al punto in cui è indicato Microsoft Azure, selezionare l'icona Mostra menu portale (le tre linee orizzontali note anche come icona hamburger) e quindi nel pannello di spostamento a sinistra, in Preferiti, selezionare **Microsoft Defender per il cloud**.  Se non è elencato nei Preferiti, nella casella di ricerca immettere **Microsoft Defender per il cloud** e quindi nell'elenco dei risultati selezionare **Microsoft Defender per il cloud**.

1. Notare le informazioni disponibili nella pagina Panoramica di Microsoft Defender per il cloud.  

1. potrebbe essere visualizzata una casella di informazioni blu in alto nella pagina la quale indica che la visualizzazione delle informazioni potrebbe essere limitata.  Selezionare **fare clic qui**.
    1. Per assicurarsi di ottenere la visibilità a livello di tenant, assegnarsi il ruolo necessario.  Selezionare **Amministratore sicurezza**, quindi selezionare **Get access** (Ottieni accesso) nella parte inferiore della pagina.
    1. Verrà probabilmente visualizzato un messaggio del tipo "Il gruppo di gestione radice non esiste".  In base alla descrizione, verrà creato dal sistema il gruppo per conto dell'utente.  Per il completamento possono essere richiesti fino a 15 minuti, ma in genere l'operazione è più veloce.  Dopo aver ottenuto l'accesso, selezionare **Microsoft Defender per il cloud** nell'angolo superiore sinistro della pagina, dove compare Ottieni autorizzazioni, quindi aggiornare la pagina di panoramica di Microsoft Defender per il cloud.

1. Le informazioni nella parte superiore della pagina includono il numero di sottoscrizioni Azure, il numero di risorse valutate, il numero di raccomandazioni attive ed eventuali avvisi di sicurezza.  Il corpo principale della pagina contiene schede per Punteggio di sicurezza, Conformità con le normative, Informazioni dettagliate e altro.  

1. Nella parte superiore della pagina selezionare **Assessed resources** (Risorse valutate).  (Si noti che questo equivale ad aver selezionato Inventario dal riquadro di spostamento sinistro della home page di Microsoft Defender per il cloud).
    1. In questo modo si verrà reindirizzati alla pagina **Inventario** che mostra la sottoscrizione di Azure Pass.  Selezionare **Azure Pass – Sponsorizzazione**.
    1. La pagina Integrità risorse offre un elenco di raccomandazioni.  Dall'elenco disponibile, selezionare **There should be more than one owner assigned to your subscription** (È consigliabile assegnare più di un proprietario all'abbonamento).
    1. Selezionare la freccia a discesa accanto a Procedura di correzione. Osservare in che modo sono forniti i passaggi di correzione insieme all'opzione per intraprendere un'azione.  
    1. Selezionare **Microsoft Defender per il cloud** nell'angolo superiore sinistro della schermata per tornare alla pagina Panoramica di Microsoft Defender per il cloud.

1. Dalla parte superiore della pagina selezionare **Raccomandazioni attive**.  (Si noti che questo equivale ad aver selezionato Raccomandazioni dal riquadro di spostamento sinistro della home page di Microsoft Defender per il cloud).
    1. La pagina delle raccomandazioni mostra la Dashboard del punteggio di sicurezza.
    1. Sotto alla Dashboard del punteggio di sicurezza è presente un elenco di controlli. Ciascun controllo di sicurezza rappresenta un rischio di sicurezza che deve essere mitigato e include anche informazioni sul punteggio massimo associato al rispettivo controllo, il punteggio attuale, il potenziale aumento del punteggio e lo stato di integrità della risorsa.  
    1. Selezionare uno dei controlli, ad esempio **Abilita MFA**.  Selezionare una delle voci secondarie **È consigliabile abilitare MFA negli account con autorizzazioni di tipo proprietario per la sottoscrizione**.  Nella pagina che si apre saranno presenti una descrizione, la procedura di correzione e le risorse interessate. Uscire da questa pagina selezionando la **X** nell'angolo in alto a destra dello schermo.
    1. Uscire dalla pagina delle raccomandazioni selezionando la **X** nell'angolo in alto a destra dello schermo per tornare alla pagina della panoramica.

1. Dalla pagina principale, selezionare **Conformità alle normative**. La pagina della conformità alle normative offre un elenco di controlli di conformità.  Sotto ciascun controllo è riportata una serie di valutazioni che sono basate su Azure Security Benchmark che offre raccomandazioni su come proteggere le soluzioni cloud su Azure.
    1. Selezionare **IM. Gestione delle identità** e quindi selezionare **IM.6 Usare controlli di autenticazione avanzata**.  L'elenco mostra azioni di responsabilità che il cliente può intraprendere per migliorare il profilo di conformità.
    1. Selezionare la **X** nell'angolo in alto a destra della schermata per chiudere la pagina e tornare alla pagina Panoramica di Microsoft Defender per il cloud.
    1. Mantenere aperta la pagina Panoramica di Microsoft Defender per il cloud, che verrà usata nell'attività successiva.

### <a name="task-2"></a>Attività 2

Con questa attività verranno esplorati Azure Secure Score e le raccomandazioni per migliorare il proprio punteggio di sicurezza.

1. Nella pagina Panoramica di Microsoft Defender per il cloud selezionare la scheda **Punteggio di sicurezza**.
1. Selezionare **Azure Pass – Sponsorizzazione**.  Annotarsi il proprio punteggio di sicurezza.
1. Nella pagina delle raccomandazioni selezionare **Implementa le procedure consigliate per la sicurezza** per espandere l'elenco. Si noti che lo stato di integrità delle risorse è visualizzato in rosso.
1. Selezionare l'elemento **Devono essere presenti più proprietari assegnati alla propria sottoscrizione**, che mostra lo stato di integrità risorse in rosso.
1. Sotto la voce **Risorse interessate** assicurarsi che l'opzione Risorse non integre sia selezionata o sottolineata, quindi selezionare la sottoscrizione di Azure elencata.
1. Dalla parte superiore della pagina del Controllo di accesso (IAM), selezionare **+ Aggiungi**, quindi dal menu a discesa selezionare **Add role assignment** (Aggiungi assegnazione di ruolo).
    1. Sul lato sinistro della pagina selezionare **Proprietario** (dovrebbe essere il primo elemento elencato) in modo che la riga sia evidenziata in grigio, quindi selezionare **Avanti** nella parte inferiore della pagina.
    1. Accanto a Membri selezionare **+ Selezionare i membri**.
    1. Nella finestra Selezionare i membri visualizzata sul lato destro della schermata selezionare **Alex Wilber** e quindi fare clic su **Seleziona** nella parte inferiore della pagina.  
    1. Nella pagina Aggiungi assegnazione di ruolo verificare che Alex Willber sia elencato come membro e quindi selezionare **Avanti** e infine **Verifica e assegna**.
    1. L'aggiornamento dello stato potrebbe richiedere fino a 24 ore, dopodiché verrà aggiornato anche il punteggio di sicurezza in quanto tutti gli elementi nel gruppo Manage access and permissions (Gestisci accesso e autorizzazioni) sono soddisfatti.
    1. Nell'angolo superiore sinistro della pagina, sopra dove è indicato Azure Pass, selezionare **Microsoft Defender per il cloud** per tornare alla pagina Panoramica di Microsoft Defender per il cloud.
1. Lasciare la pagina aperta per l'attività successiva.

### <a name="task-3"></a>Attività 3

Tenere presente che Microsoft Defender per il cloud è disponibile in due modalità: senza funzionalità di sicurezza avanzate (gratuito) e con funzionalità di sicurezza avanzate disponibili tramite i piani di Microsoft Defender per il cloud. Questa attività illustra come abilitare o disabilitare i vari piani di Microsoft Defender per il cloud.

1. Nella pagina Panoramica di Microsoft Defender per il cloud selezionare **Impostazioni ambiente** nel pannello di spostamento a sinistra.
1. Selezionare il segno di maggiore di **>** accanto a Gruppo radice tenant per espanderlo (non selezionare direttamente Gruppo radice tenant perché si verrebbe reindirizzati a una pagina diversa), quindi selezionare **Azure Pass - Sponsorship**
1. Nella pagina dei piani di Defender notare che è possibile selezionare Abilita tutti o selezionare singoli piani di Defender. Lasciare le impostazioni così come sono con tutti i piani disattivati.
1. Ora è possibile chiudere la scheda del browser per uscire dal portale di Azure.

### <a name="review"></a>Verifica

In questo lab è stato esplorato Microsoft Defender per il cloud e si è appreso come è possibile usare il punteggio di sicurezza di Azure per migliorare il profilo di sicurezza dell'organizzazione.
