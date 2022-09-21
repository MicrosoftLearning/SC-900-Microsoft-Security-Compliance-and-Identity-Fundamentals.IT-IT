---
ms.openlocfilehash: ecea12b9b90c6dc3917d0ee93edcdba0436ccd0d
ms.sourcegitcommit: 15658ca1c7bae8a4dbaa33ab6f897070bde521b9
ms.translationtype: HT
ms.contentlocale: it-IT
ms.lasthandoff: 09/12/2022
ms.locfileid: "147892462"
---
<a name="---"></a><!---
---
Demo: Titolo: 'Microsoft Defender per il cloud' Percorso di apprendimento/Modulo/Unità: 'Percorso di apprendimento: Descrivere le funzionalità delle soluzioni di sicurezza Microsoft; Modulo 2: Descrivere le funzionalità di gestione della sicurezza di Azure; Unità 3: Descrivere Microsoft Defender per il cloud'
---
--->

# <a name="demo-microsoft-defender-for-cloud"></a>Dimostrazione: Microsoft Defender per il cloud

Questa demo corrisponde al contenuto di Learn seguente:

- Percorso di apprendimento: Descrivere le funzionalità delle soluzioni di sicurezza Microsoft
- Modulo: Descrivere le funzionalità di gestione della sicurezza di Azure
- Unità: Descrivere Microsoft Defender per il cloud

## <a name="demo-scenario"></a>Scenario demo

Questa demo illustra Microsoft Defender per il cloud e mostra come è possibile usare il punteggio di sicurezza di Azure per migliorare la postura di sicurezza di un'organizzazione.  NOTA: questa procedura dettagliata dimostrativa presuppone che il relatore disponga delle autorizzazioni a livello di amministratore per la sottoscrizione di Azure tramite un pass di Azure.  Una sottoscrizione di Azure, ad esempio una sottoscrizione Cloudslice gestita dal provider di servizi di hosting per i lab autorizzato, limita l'accesso e le funzionalità, quindi alcuni dei passaggi seguenti potrebbero non essere disponibili o non visualizzare alcuna informazione.

### <a name="demo-setup"></a>Configurazione demo

In questa attività di configurazione si eseguiranno operazioni di configurazione di base di Microsoft Defender per il cloud per preparare la sottoscrizione e abilitare e assegnare un criterio predefinito. Eseguire questa attività prima di eseguire la demo davanti alla classe. 

1. Aprire la scheda del browser, **Home-Microsoft Azure**.  Se la scheda era stata chiusa in precedenza, aprire una pagina del browser e nella barra degli indirizzi inserire portal.azure.com e accedere di nuovo.

1. Nella casella di ricerca, nella barra blu nella parte superiore della pagina accanto a Microsoft Azure, immettere **Microsoft Defender per il cloud** e quindi selezionare **Microsoft Defender per il cloud** dai risultati della ricerca.

1. Se questa è la prima volta che si accede a Microsoft Defender per il cloud con la propria sottoscrizione, potrebbe comparire la pagina introduttiva e potrebbe essere richiesto di eseguire l'aggiornamento.  Scorrere in fondo alla pagina e selezionare **salta**.  Verrà visualizzata la pagina Panoramica.
    1. Nella parte superiore della pagina verrà visualizzata una casella di informazioni blu chiaro con l'indicazione "Preparazione della sottoscrizione. L'operazione potrebbe richiedere alcuni minuti..."
    1. Quando la sottoscrizione è pronta, verrà visualizzata una nuova casella di informazioni con l'indicazione "Una sottoscrizione non ha il criterio predefinito assegnato. Per esaminare l'elenco delle sottoscrizioni, aprire la pagina Criteri di sicurezza."  Selezionare la freccia a destra alla fine della frase.
        1. Verrà visualizzata la pagina Impostazioni ambiente. Selezionare **Azure Pass – Sponsorizzazione**. 
        1. Dal riquadro di spostamento sinistro selezionare **Criteri di sicurezza**.
        1. Dalla pagina principale selezionare **Assegna criteri** sotto all'iniziativa predefinita.
        1. Nella parte inferiore della pagina selezionare **Rivedi e crea**.
        1. Nella parte inferiore della pagina selezionare **Salva**.
        1. Nella parte superiore della pagina, sotto la posizione in cui viene indicato Microsoft Azure, selezionare **Microsoft Defender per il cloud** dal percorso di navigazione per tornare alla pagina di panoramica.

### <a name="demo-task"></a>Attività demo

In questa attività demo si eseguirà una procedura dettagliata molto generale di alcune delle funzionalità di Microsoft Defender per il cloud.

1. Le informazioni nella parte superiore della pagina di panoramica di Microsoft Defender per il cloud includono il numero di sottoscrizioni di Azure, il numero di risorse valutate, il numero di raccomandazioni attive ed eventuali avvisi di sicurezza.  Il corpo principale della pagina contiene schede per Punteggio di sicurezza, Conformità con le normative, Informazioni dettagliate e altro.  

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

1. Si torna alla pagina Panoramica di Microsoft Defender per il cloud.  Dalla pagina principale, selezionare **Conformità alle normative**. (Si noti che questo equivale ad aver selezionato Raccomandazioni dal riquadro di spostamento sinistro della home page di Microsoft Defender per il cloud).
    1. La pagina della conformità alle normative offre un elenco di controlli di conformità.  Sotto ciascun controllo è riportata una serie di valutazioni che sono basate su Azure Security Benchmark che offre raccomandazioni su come proteggere le soluzioni cloud su Azure.
    1. Selezionare **IM. Gestione delle identità** e quindi selezionare **IM.6 Usare controlli di autenticazione avanzata**.  L'elenco mostra azioni di responsabilità che il cliente può intraprendere per migliorare il profilo di conformità.
    1. Selezionare la **X** nell'angolo in alto a destra dello schermo per chiudere la pagina e tornare alla pagina della conformità alle normative.
    1. Selezionare la **X** nell'angolo in alto a destra dello schermo per tornare alla pagina della panoramica.

1. Tenere presente che Microsoft Defender per il cloud è disponibile in due modalità: senza funzionalità di sicurezza avanzate (gratuito) e con funzionalità di sicurezza avanzate disponibili tramite i piani di Microsoft Defender per il cloud. Si scoprirà come abilitare o disabilitare i vari piani di Microsoft Defender per il cloud.
    1. Nella pagina Panoramica di Microsoft Defender per il cloud selezionare **Impostazioni ambiente** nel pannello di spostamento a sinistra.
    1. Selezionare il segno di maggiore di **>** accanto a Gruppo radice tenant per espanderlo (non selezionare direttamente Gruppo radice tenant perché si verrebbe reindirizzati a una pagina diversa), quindi selezionare **Azure Pass - Sponsorship**
    1. Nella pagina dei piani di Defender notare che è possibile selezionare Abilita tutti o selezionare singoli piani di Defender. Lasciare le impostazioni così come sono con tutti i piani disattivati.
    1. Selezionare la **X** nell'angolo in alto a destra della schermata per tornare alla pagina Impostazioni ambiente.
    1. Selezionare la **X** nell'angolo in alto a destra dello schermo per tornare alla pagina della panoramica.

1. Tornare alla home page del portale Azure selezionando **Home** nell'angolo in alto a sinistra della pagina.  Tenere questa scheda del browser a disposizione, perché servirà di nuovo in una demo successiva.

## <a name="review"></a>Verifica

In questa demo è stato presentato Microsoft Defender per il cloud e si è visto come usare il punteggio di sicurezza di Azure per migliorare la postura di sicurezza di un'organizzazione.
