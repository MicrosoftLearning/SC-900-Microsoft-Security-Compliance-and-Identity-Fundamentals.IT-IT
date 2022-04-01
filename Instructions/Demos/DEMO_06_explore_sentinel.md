---
Demo:
  title: Microsoft Sentinel
  module: 'Module 3 Lesson 3: Describe the capabilities of Microsoft security solutions: Describe security capabilities of Microsoft Sentinel'
ms.openlocfilehash: 607c8097d17041f711aa1f40601e8433fcfce7f0
ms.sourcegitcommit: a341c2fc38e9b37dafb792d82e3c948f7ba4a099
ms.translationtype: HT
ms.contentlocale: it-IT
ms.lasthandoff: 01/14/2022
ms.locfileid: "137894098"
---
# <a name="demo-microsoft-sentinel"></a>Dimostrazione: Microsoft Sentinel 

### <a name="demo-scenario"></a>Scenario demo
Questa demo illustrerà il processo di creazione di un'istanza di Microsoft Sentinel.  Verranno anche configurate le autorizzazioni per garantire l'accesso alle risorse che verranno distribuite per supportare Microsoft Sentinel.  Una volta terminata la configurazione di base, verranno illustrati i passaggi per connettere Microsoft Sentinel alle origini dati, usando l'analisi integrata per ricevere notifiche di eventuali eventi sospetti e, infine, si esamineranno le funzionalità di automazione.  

#### <a name="demo-part-1--create-an-microsoft-sentinel-instance"></a>Demo Parte 1:  Creare un'istanza di Microsoft Sentinel

1. Aprire la scheda del browser, **Home-Microsoft Azure**.  Se la scheda era stata chiusa in precedenza, aprire una pagina del browser e nella barra degli indirizzi inserire portal.azure.com e accedere di nuovo.

1. Nella casella di ricerca, nella barra blu nella parte superiore della pagina accanto a Microsoft Azure, immettere **Microsoft Sentinel** e quindi selezionare **Microsoft Sentinel** dai risultati della ricerca.

1. Nella pagina di Microsoft Sentinel selezionare **Crea Microsoft Sentinel**.

1. Nella pagina Aggiungi Microsoft Sentinel a un'area di lavoro selezionare **Crea una nuova area di lavoro**.

1. Dalla scheda generale di Crea area di lavoro Log Analytics, inserire quanto segue:
    1. Sottoscrizione:  **Azure Pass - Sponsorship**
    1. Gruppo di risorse: selezionare **Crea nuovo**, quindi inserire il nome **SC900-Sentinel-RG** e selezionare **OK**.
    1. Nome: **SC900-LogAnalytics-workspace**.
    1. Area: **Stati Uniti orientali** (lasciare questa impostazione predefinita)
    1. Al termine, selezionare **Avanti: Piano tariffario >**

1. Per il piano tariffario, lasciare le impostazioni predefinite: **Con pagamento in base al consumo (per GB 2018)** , quindi selezionare **Avanti: Tag >** .

1. Per i Tag, è possibile lasciare questo campo vuoto, quindi selezionare **Verifica + Crea**.

1. Verificare le informazioni inserite e selezionare **Crea**.

1. Potrebbe volerci un minuto o due perché la nuova area di lavoro compaia nell'elenco; se non compare, selezionare **Aggiorna**, quindi selezionare **Aggiungi**.

1. Dopo aver aggiunto la nuova area di lavoro, verrà visualizzata la pagina Microsoft Sentinel | Novità e guide.  Osservare i tre passaggi elencati nella pagina Guida introduttiva.

1. Tenere aperta la pagina poiché verrà usata nell'attività successiva.

#### <a name="demo-part-2--with-the-microsoft-sentinel-instance-created-you-will-want-to-make-sure-that-you-have-the-necessary-access-to-the-resources-that-get-deployed-to-support-microsoft-sentinel--in-this-task-you-will-go-to-the-access-control-iam-page-for-the-resource-group-that-you-created-with-the-instance-of-microsoft-sentinel-view-the-available-roles-and-assign-yourself-mod-administrator-the-required-role-assigning-the-role-at-the-resource-group-level-will-ensure-the-role-will-apply-to-all-the-resources-that-are-deployed-to-support-microsoft-sentinel"></a>Demo parte 2:  Una volta creata l'istanza di Microsoft Sentinel, ci si assicurerà di disporre dell'accesso necessario alle risorse distribuite per il supporto di Microsoft Sentinel.  In questa attività si accederà alla pagina del controllo di accesso (IAM) per il gruppo di risorse creato con l'istanza di Microsoft Sentinel, si visualizzeranno i ruoli disponibili e ci si assegnerà (amministratore MOD) il ruolo richiesto. L'assegnazione del ruolo a livello di gruppo di risorse garantirà che il ruolo venga applicato a tutte le risorse distribuite per il supporto di Microsoft Sentinel.

1. Nella casella di ricerca, nella barra blu nella parte superiore della pagina accanto a Microsoft Azure, inserire **gruppi di risorse** quindi selezionare **Gruppi di risorse** dai risultati della ricerca.

1. Nella pagina Gruppi di risorse selezionare il gruppo di risorse creato con Microsoft Sentinel, **SC900-Sentinel-RG**.

1. Dalla pagina SC900-Sentinel-RG, selezionare **Controllo di accesso (IAM)** dal riquadro di spostamento sinistro.

1. Dalla pagina Controllo di accesso selezionare **Visualizza accesso personale**.  Notare che il ruolo corrente è Amministratore del servizio.  Chiudere la finestra delle assegnazioni di Amministratore MOD selezionando la **X** nell'angolo in alto a destra della finestra.

1. Dalla pagina Controllo di accesso selezionare **+Aggiungi**, quindi selezionare **Add role assignment** (Aggiungi assegnazione di ruolo).

1. Si apre la finestra Add role assignment (Aggiungi assegnazione di ruolo).  Selezionare la freccia a discesa nel campo Seleziona un ruolo per visualizzare i ruoli disponibili. Nella casella di ricerca per la selezione di un ruolo immettere **Microsoft Sentinel** per visualizzare i 4 ruoli associati a Microsoft Sentinel. Come procedura consigliata si dovrebbe assegnare il privilegio minimo richiesto per il ruolo.  Ai fini di questa esercitazione, inserire **Proprietario** nella casella di ricerca e selezionare **Proprietario** dai risultati.  Per riferimento, controllare le autorizzazioni in Microsoft Sentinel: https://docs.microsoft.com/en-us/azure/sentinel/roles

1. Dall'elenco degli utenti visualizzati, selezionare **Amministratore MOD**.

1. Selezionare **Salva** nella parte inferiore della pagina.

1. Dalla pagina Controllo di accesso selezionare **Visualizza accesso personale** per confermare che il ruolo è stato aggiunto, quindi chiudere la finestra selezionando la **X** nell'angolo in alto a destra della finestra.

#### <a name="demo-part-3--in-this-part-of-the-demo-you-will-walk-through-the-process-of-connecting-microsoft-sentinel-to-your-data-source-to-begin-to-collect-data--note-it-can-take-a-bit-time-to-show-the-connected-status-of-a-connector-30-minutes-depending-on-the-tenant"></a>Demo parte 3:  Questa parte della demo illustrerà il processo di connessione di Microsoft Sentinel all'origine dati per iniziare a raccogliere dati.  Nota: la visualizzazione dello stato connesso di un connettore può impiegare un po' di tempo (circa 30 minuti, a seconda del tenant).

1. Nella casella di ricerca, nella barra blu nella parte superiore della pagina accanto a Microsoft Azure, immettere **Microsoft Sentinel** e quindi selezionare **Microsoft Sentinel** dai risultati della ricerca.

1. Nella pagina di Microsoft Sentinel selezionare l'area di lavoro creata con l'istanza di Microsoft Sentinel, **SC900-LogAnalytics-workspace**.

1. Il primo passaggio con Microsoft Sentinel prevede di essere in grado di raccogliere dati. Dal riquadro di spostamento sinistro selezionare **Connettori dati**, elencati sotto la configurazione.

1. Dalla pagina Connettori dati, scorrere verso il basso nella finestra principale per visualizzare l'elenco completo dei connettori disponibili. Nella casella di ricerca della pagina dei connettori dati, immettere **Azure** e poi dall'elenco selezionare **Azure Active Directory**.

1. Verrà aperta la finestra del connettore di Azure Active Directory.  Selezionare **Apri la pagina del connettore**.

1. Dalla pagina del connettore di Azure Active Directory, esaminare la descrizione e notare il contenuto correlato che include cartelle di lavoro, query e modelli di regole analitiche.  

1. La scheda delle istruzioni nella finestra principale illustra i requisiti per l'integrazione di Microsoft Sentinel con Azure Active Directory.   Sotto Configurazione, selezionare **Log di accesso**, quindi selezionare Applica modifiche (è possibile scegliere più connettori).  Nota: possono volerci alcuni minuti per vedere lo stato connesso del connettore (circa 30 minuti).  Per riferimento:
    1. Controllare le autorizzazioni in Microsoft Sentinel: https://docs.microsoft.com/en-us/azure/sentinel/roles
    1. Connettersi ad Azure Active Directory: https://docs.microsoft.com/en-us/azure/sentinel/connect-azure-active-directory

1. Dalla scheda Passaggi successivi, notare l'elenco delle cartelle di lavoro raccomandate.   Sotto alle cartelle di lavoro raccomandate, selezionare **Log di accesso di Azure** (è possibile scegliere cartelle di lavoro aggiuntive).

1. Dalla pagina delle cartelle di lavoro e con la scheda dei modelli selezionata (sottolineata), selezionare **Log di accesso di Azure**.

1. Dalla finestra Log di accesso di Azure AD che si apre, esaminare la descrizione e selezionare **Visualizza modello**.  Uscire dal modello selezionando la **X** nell'angolo in alto a destra dello schermo.  Selezionare **Salva** dalla parte inferiore della pagina, quindi selezionare **OK** per salvare la cartella di lavoro nella posizione predefinita.

1. Nell'angolo in alto a sinistra della pagina Cartelle di lavoro, sopra Cartelle di lavoro, selezionare **Microsoft Sentinel**. In questo modo si torna alla pagina Connettori di dati di Microsoft Sentinel.

1. La parte alta della pagina dei connettori dati dovrebbe mostrare 1 connesso, per indicare che si è ora connessi ad Azure Active Directory.

1. Dal riquadro di spostamento sinistro, selezionare **Cartelle di lavoro**.

1. Dalla pagina Cartelle di lavoro, selezionare la scheda **Cartelle di lavoro personali** sopra la casella di ricerca.  La cartella di lavoro appena salvata è elencata e disponibile per visualizzare e monitorare i dati.  Gli accessi successivi si rifletteranno nella cartella di lavoro, quindi si può scegliere di mostrarli.

1. Tenere aperta la pagina poiché verrà usata nell'attività successiva.

#### <a name="demo-part-4-optional--in-this-part-of-the-demo-you-will-walk-through-the-process-of-using-a-built-in-analytics-rule-template-to-create-a-rule-to-get-notified-when-something-suspicious-occurs"></a>Demo Parte 4 (opzionale):  Questa parte della demo illustrerà il processo di utilizzo di un modello di regola di analisi integrata per creare una regola per ricevere una notifica quando si verifica un evento sospetto.

1. Dal riquadro di spostamento sinistro, selezionare **Analisi**.

1. La pagina Analisi mostrerà le regole attive (il rilevamento avanzato degli attacchi multistadio è abilitato per impostazione predefinita) e fornirà anche l'accesso ai Modelli di regola.  Selezionare la scheda **Modelli di regola**.  Notare l'elenco dei modelli disponibili e i diversi modi per filtrare l'elenco.  Usando gli avvisi di analisi predefiniti nell'area di lavoro di Microsoft Sentinel, si riceverà una notifica per ogni evento sospetto.

1. Nella barra di ricerca immettere **Portale di Azure**.  Selezionare **Tentativi di accesso non riusciti al portale di Azure**.  

1. Dalla finestra che si apre, leggere la descrizione ed esaminare le informazioni associate al modello.  Selezionare **Crea regola** nella parte inferiore della pagina.
    1. Nella procedura guidata delle regole di analisi esaminare le informazioni e quindi selezionare **Avanti: Imposta la logica della regola>** .
    1. Nella pagina Imposta logica regola è possibile definire la logica per la nuova regola di analisi. Il modello offre già alcune logiche e impostazioni predefinite.  Scorrere la pagina per visualizzare le impostazioni disponibili.  Lasciare i valori predefiniti. Al termine, selezionare **Avanti: Impostazioni eventi imprevisti (anteprima)>** .
    1. Con Impostazioni eventi imprevisti, gli avvisi di Microsoft Sentinel possono essere raggruppati in un evento imprevisto da esaminare. È possibile impostare se gli avvisi che vengono attivati da questa regola di analisi devono generare eventi imprevisti.  Lasciare le impostazioni predefinite e selezionare **Avanti: Risposta automatica>** .
    1. Nella scheda Risposta automatica è possibile aggiungere un playbook per automatizzare la risposta.  Analogamente, è possibile creare una regola di automazione dell'evento imprevisto.  Selezionare **+Aggiungi nuovo** sotto Automazione dell'evento imprevisto.  Viene aperta una finestra per creare una nuova regola di automazione.  Ogni regola di automazione creata su questa pagina viene attivata tramite la regola di analisi selezionata in origine, in questo caso, Tentativi di accesso non riusciti al portale di Azure.  Tenere presente che è possibile aggiungere condizioni e impostare azioni per la regola.   Selezionare **Annulla** per uscire dalla finestra.
    1. Al termine, selezionare **Avanti: Verifica>** per esaminare tutti i dettagli associati alla regola e basati sul modello scelto. A questo punto, è possibile scegliere di creare la regola, selezionando **Crea** o uscire senza creare la regola selezionando **X** nell'angolo in alto a destra della pagina.

1. Tenere aperta la pagina poiché verrà usata nell'attività successiva.

#### <a name="demo-step-5-optional--in-the-previous-step-you-created-an-analytics-rule-to-be-alerted-of-suspicious-activities--embedded-in-that-wizard-is-the-option-to-automate-the-response-to-an-incident-based-on-the-specific-rule--but-you-can-also-create-automation-rules-by-going-directly-to-the-automation-configuration-option"></a>Demo Passaggio 5 (opzionale):  Nel passaggio precedente è stata creata una regola di analisi per ricevere un avviso in caso di attività sospette.  Incorporata in questa procedura guidata c'è l'opzione per automatizzare la risposta a un incidente in base alla regola specifica.  Ma è anche possibile creare regole di automazione andando direttamente all'opzione di configurazione dell'automazione.

1. Dal riquadro di spostamento sinistro, selezionare **Automazione**.  

1. Selezionare **[+] Create** ([+] Crea). Dal menu a discesa notare come è possibile selezionare o aggiungere un nuovo playbook o aggiungere una nuova regola.  Selezionare **Aggiungi nuova regola**.  
    1. Viene aperta una finestra per creare una nuova regola di automazione.  Tenere presente che è possibile aggiungere condizioni e impostare azioni per la regola.  L'unica distinzione è che la prima condizione è quella di associare la regola o le regole di analisi a cui si vuole applicare questa regola di automazione.  Compare in grigio nell'attività precedente perché l'automazione è stata configurata per la regola specifica.  Selezionare **Annulla** per uscire dalla finestra Crea nuova regola di automazione.

1. Tenere aperta la pagina poiché verrà usata nell'attività successiva.

#### <a name="step-6-tear-down---instructor-do-this-step-after-class-delete-microsoft-sentinel-resource-group--microsoft-sentinel-is-billed-based-on-the-volume-of-data-ingested-for-analysis-in-microsoft-sentinel-although-the-amount-of-data-ingested-as-a-result-of-this-lab-is-minimal-it-is-recommended-that-you-delete-the-microsoft-sentinel-resource-group-when-you-are-done-exploring-the-features-of-capabilities-of-microsoft-sentinel"></a>Passaggio 6: ELIMINARE - L'istruttore esegue questo passaggio dopo la lezione. Eliminare il gruppo di risorse di Microsoft Sentinel.  Microsoft Sentinel viene fatturato in base al volume di dati inseriti per l'analisi in Microsoft Sentinel. Sebbene la quantità di dati inseriti come conseguenza di questo lab sia minima, è consigliabile eliminare il gruppo di risorse di Microsoft Sentinel una volta completata l'esplorazione delle funzionalità e capacità di Microsoft Sentinel.

1. Nella pagina di Microsoft Sentinel, nell'angolo in alto a sinistra della pagina, sopra a dove è visualizzato Microsoft Sentinel, selezionare **Tutti i servizi**.

1. Nella casella dei servizi del filtro, immettere i gruppi di risorse, quindi dall'elenco fornito selezionare **Gruppi di risorse**.

1. Nella pagina Gruppi di risorse selezionare il gruppo di risorse creato con Microsoft Sentinel, **SC900-Sentinel-RG**.

1. Dalla parte centrale in alto della pagina, selezionare **Elimina gruppo di risorse**.  Esaminare l'avviso.  Inserire il nome del gruppo di risorse, **SC900-Sentinel-RG**, quindi selezionare **Elimina** dalla parte inferiore della pagina.  L'eliminazione del gruppo di risorse impiegherà diversi minuti.

1. Una volta verificato che il gruppo di risorse è stato eliminato, chiudere la pagina del browser. 

#### <a name="review"></a>Verifica

In questa demo è stato illustrato il processo di creazione di un'istanza di Microsoft Sentinel.  Sono state illustrate le procedure per configurare le autorizzazioni per garantire l'accesso alle risorse associate all'istanza di Microsoft Sentinel.  Dopo aver creato l'istanza di Microsoft Sentinel, sono stati eseguiti i passaggi per la connessione di Microsoft Sentinel alle origini dati e per usare le regole di analisi predefinite per ricevere notifica di eventuali eventi sospetti. Infine, sono state esaminate le funzionalità di automazione. La demo è terminata con l'eliminazione del gruppo di risorse associato all'istanza di Microsoft Sentinel creata.