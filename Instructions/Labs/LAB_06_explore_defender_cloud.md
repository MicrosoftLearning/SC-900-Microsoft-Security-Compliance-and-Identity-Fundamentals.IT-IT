---
lab:
  title: Esplorare Microsoft Defender per il cloud
  module: 'Module 3 Lesson 2: Describe the capabilities of Microsoft security solutions: Describe security management capabilities of Azure'
ms.openlocfilehash: 29933f0f33320aba85a58af7f0cbff4d8b430247
ms.sourcegitcommit: a69acc26ed3a09cea4a3af95719a6edc7fe2814d
ms.translationtype: HT
ms.contentlocale: it-IT
ms.lasthandoff: 06/29/2022
ms.locfileid: "146650078"
---
# <a name="lab-explore-microsoft-defender-for-cloud"></a>Laboratorio: Esplorare Microsoft Defender per il cloud

## <a name="lab-scenario"></a>Scenario del lab

In questo lab verrà esplorato Microsoft Defender per il cloud e si apprenderà in che modo il punteggio di sicurezza di Azure può essere usato per migliorare la postura di sicurezza dell'organizzazione.  NOTA: questa procedura dettagliata dimostrativa presuppone che il relatore disponga delle autorizzazioni a livello di amministratore per la sottoscrizione di Azure tramite un pass di Azure.  Una sottoscrizione di Azure, ad esempio una sottoscrizione Cloudslice gestita dal provider di servizi di hosting per i lab autorizzato, limita l'accesso e le funzionalità, quindi alcuni dei passaggi seguenti potrebbero non essere disponibili o non visualizzare alcuna informazione.

**Tempo stimato**: 30 minuti

### <a name="setup"></a>Installazione

In questa attività si eseguiranno operazioni di configurazione di base di Microsoft Defender per il cloud per preparare la sottoscrizione e abilitare e assegnare un criterio predefinito.

1. Aprire Microsoft Edge. Nella barra degli indirizzi immettere **portal.azure.com**.

1. Accedere con le credenziali di amministratore.
    1. Nella finestra Accedi immettere **admin@WWLxZZZZZZ.onmicrosoft.com** (dove ZZZZZZ è l'ID tenant univoco fornito dal proprio provider di hosting del lab) e quindi selezionare **Avanti**.
    1. Immettere la password di amministratore, che dovrebbe essere fornita dal proprio provider di hosting del lab. Fare clic su **Accedi**.
    1. Quando compare la domanda se rimanere connessi, selezionare **Sì**.

1. Nell'angolo superiore sinistro della schermata, accanto al punto in cui è indicato Microsoft Azure, selezionare l'icona Mostra menu portale (le tre linee orizzontali note anche come icona hamburger) e quindi nel pannello di spostamento a sinistra, in Preferiti, selezionare **Microsoft Defender per il cloud**.  Se non è elencato nei Preferiti, nella casella di ricerca immettere **Microsoft Defender per il cloud** e quindi nell'elenco dei risultati selezionare **Microsoft Defender per il cloud**.

1. Se questa è la prima volta che si accede a Microsoft Defender per il cloud con la propria sottoscrizione, potrebbe comparire la pagina introduttiva e potrebbe essere richiesto di eseguire l'aggiornamento.  Scorrere in fondo alla pagina e selezionare **salta**.  Verrà visualizzata la pagina Panoramica.
    1. Nella parte superiore della pagina verrà visualizzata una casella di informazioni blu chiaro con l'indicazione "Preparazione della sottoscrizione. L'operazione potrebbe richiedere alcuni minuti..."
    1. Quando la sottoscrizione è pronta, potrebbe essere visualizzata una nuova casella di informazioni con l'indicazione "Una sottoscrizione non ha il criterio predefinito assegnato. Per esaminare l'elenco delle sottoscrizioni, aprire la pagina Criteri di sicurezza."  Selezionare la freccia a destra alla fine della frase o selezionare **Impostazioni ambiente** nel riquadro di spostamento a sinistra.
        1. Verrà visualizzata la pagina Impostazioni ambiente. Selezionare **Azure Pass – Sponsorizzazione**.  Nota:  se l'ambiente di Azure è basato su una sottoscrizione di Azure gestita dal provider di servizi di hosting per i lab autorizzato, invece di un Azure Pass, verrà visualizzato un riferimento a tale provider. Espandere l'opzione selezionando il segno di maggiore fino a quando non è più possibile espandere le opzioni e viene visualizzata la sottoscrizione.
        1. Dal riquadro di spostamento sinistro selezionare **Criteri di sicurezza**.
        1. Dalla pagina principale selezionare **Assegna criteri** sotto all'iniziativa predefinita.
        1. Nella parte inferiore della pagina selezionare **Rivedi e crea**.
        1. Nella parte inferiore della pagina selezionare **Salva**.  Azure Security Benchmark viene così assegnato come iniziativa relativa ai criteri predefinita.  Aggiornare la schermata (potrebbero essere necessari alcuni minuti prima che l'impostazione diventi effettiva).
        1. Uscire dalla pagina delle impostazioni dell'ambiente selezionando la **X** nella pagina.  
        1. Nella pagina dei servizi di Azure selezionare **Microsoft Defender per il cloud** per tornare alla pagina di panoramica.

### <a name="task-1"></a>Attività 1

In questa attività si eseguirà una procedura dettagliata molto generale di alcune delle funzionalità di Microsoft Defender per il cloud

1. Notare le informazioni disponibili nella pagina Panoramica di Microsoft Defender per il cloud.  Le informazioni nella parte superiore della pagina includono il numero di sottoscrizioni Azure, il numero di risorse valutate, il numero di raccomandazioni attive ed eventuali avvisi di sicurezza.  Il corpo principale della pagina contiene schede per Punteggio di sicurezza, Conformità con le normative, Informazioni dettagliate e altro.

1. Nella parte superiore della pagina selezionare **Assessed resources** (Risorse valutate).  (Si noti che questo equivale ad aver selezionato Inventario dal riquadro di spostamento sinistro della home page di Microsoft Defender per il cloud).
    1. In questo modo si verrà reindirizzati alla pagina **Inventario** che mostra la sottoscrizione di Azure Pass.  Selezionare **Azure Pass – Sponsorizzazione**.
    1. La pagina Integrità risorse offre un elenco di raccomandazioni.  Dall'elenco disponibile, selezionare **There should be more than one owner assigned to your subscription** (È consigliabile assegnare più di un proprietario all'abbonamento).
    1. Selezionare la freccia a discesa accanto a Procedura di correzione. Osservare in che modo sono forniti i passaggi di correzione insieme all'opzione per intraprendere un'azione.  
    1. Selezionare **Microsoft Defender per il cloud** nell'angolo superiore sinistro della schermata per tornare alla pagina Panoramica di Microsoft Defender per il cloud.

1. Dalla parte superiore della pagina selezionare **Raccomandazioni attive**.  (Si noti che questo equivale ad aver selezionato Raccomandazioni dal riquadro di spostamento sinistro della home page di Microsoft Defender per il cloud).
    1. La pagina delle raccomandazioni mostra la Dashboard del punteggio di sicurezza.
    1. Sotto alla Dashboard del punteggio di sicurezza è presente un elenco di controlli. Ciascun controllo di sicurezza rappresenta un rischio di sicurezza che deve essere mitigato e include anche informazioni sul punteggio massimo associato al rispettivo controllo, il punteggio attuale, il potenziale aumento del punteggio e lo stato di integrità della risorsa.  
    1. Selezionare uno dei controlli, ad esempio **Implementa le procedure consigliate per la sicurezza**.  Selezionare uno degli elementi secondari, ad esempio **È consigliabile assegnare più di un proprietario alla sottoscrizione**.  Nella pagina che si apre saranno presenti una descrizione, la procedura di correzione e le risorse interessate. Uscire da questa pagina selezionando la **X** nell'angolo in alto a destra dello schermo.
    1. Uscire dalla pagina delle raccomandazioni selezionando la **X** nell'angolo in alto a destra dello schermo per tornare alla pagina della panoramica.

1. Dalla pagina principale, selezionare **Conformità alle normative**. La pagina della conformità alle normative offre un elenco di controlli di conformità.  Sotto ciascun controllo è riportata una serie di valutazioni che sono basate su Azure Security Benchmark che offre raccomandazioni su come proteggere le soluzioni cloud su Azure.
    1. Selezionare **IM. Gestione delle identità** e quindi selezionare **IM.6 Usare controlli di autenticazione avanzata**.  L'elenco mostra azioni di responsabilità che il cliente può intraprendere per migliorare il profilo di conformità.
    1. Selezionare la **X** nell'angolo in alto a destra della schermata per chiudere la pagina e tornare alla pagina Panoramica di Microsoft Defender per il cloud.
    1. Mantenere aperta la pagina Panoramica di Microsoft Defender per il cloud, che verrà usata nell'attività successiva.

### <a name="task-2"></a>Attività 2

Tenere presente che Microsoft Defender per il cloud è disponibile in due modalità: senza funzionalità di sicurezza avanzate (gratuito) e con funzionalità di sicurezza avanzate disponibili tramite i piani di Microsoft Defender per il cloud. Questa attività illustra come abilitare o disabilitare i vari piani di Microsoft Defender per il cloud.

1. Nella pagina Panoramica di Microsoft Defender per il cloud selezionare **Impostazioni ambiente** nel pannello di spostamento a sinistra.
1. Selezionare il segno di maggiore di **>** accanto a Gruppo radice tenant per espanderlo (non selezionare direttamente Gruppo radice tenant perché si verrebbe reindirizzati a una pagina diversa), quindi selezionare **Azure Pass - Sponsorship**
1. Nella pagina dei piani di Defender notare che è possibile selezionare Abilita tutti o selezionare singoli piani di Defender. Lasciare le impostazioni così come sono con tutti i piani disattivati.
1. Chiudere tutte le schede del browser aperte.

### <a name="review"></a>Verifica

In questo lab è stato esplorato Microsoft Defender per il cloud e si è appreso come è possibile usare il punteggio di sicurezza di Azure per migliorare il profilo di sicurezza dell'organizzazione.
