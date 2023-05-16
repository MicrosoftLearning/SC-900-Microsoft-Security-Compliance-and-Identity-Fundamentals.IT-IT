---
lab:
  title: 'Esplorare il portale di conformità di Microsoft Purview e Compliance Manager'
  module: 'Modulo 2: Descrivere le funzionalità di gestione della conformità in Microsoft Purview'
---


# <a name="lab-explore-the-microsoft-purview-compliance-portal--compliance-manager"></a>Laboratorio: Esplorare il portale di conformità di Microsoft Purview e Compliance Manager

Questo lab corrisponde al contenuto di Learn seguente:

- Percorso di apprendimento: Descrivere le funzionalità di conformità Microsoft
- Modulo: Descrivere le funzionalità di gestione della conformità in Microsoft Purview
- Unità: Descrivere il portale di conformità di Microsoft Purview

## <a name="lab-scenario"></a>Scenario del lab

In questo lab, verrà esplorata la home page del portale di conformità di Microsoft Purview e verranno presentati i modi in cui le funzionalità di Compliance Manager possono aiutare le organizzazioni a migliorare il proprio profilo di conformità.

**Tempo stimato**: 30-45 minuti

### <a name="task-1"></a>Attività 1

Esplorare la home page del portale di conformità di Microsoft Purview e imparare a personalizzare la visualizzazione delle schede e il riquadro di spostamento.

1. Aprire Microsoft Edge. Nella barra degli indirizzi immettere **admin.microsoft.com**.
1. Accedere con le credenziali di amministratore.
    1. Nella finestra Accedi immettere **admin@WWLxZZZZZZ.onmicrosoft.com** (dove ZZZZZZ è l'ID tenant univoco fornito dal proprio provider di hosting del lab) e quindi selezionare **Avanti**.
    1. Immettere la password di amministratore, che dovrebbe essere fornita dal proprio provider di hosting del lab. Fare clic su **Accedi**.
    1. Quando compare la domanda se rimanere connessi, selezionare **Sì**. In questo modo si accede alla pagina dell'interfaccia di amministrazione di Microsoft 365.
1. Dal riquadro di spostamento sinistro dell'interfaccia di amministrazione di Microsoft 365, selezionare **Mostra tutto**.
1. In Interfacce di amministrazione selezionare **Conformità**.  Si apre una nuova pagina del browser alla pagina di benvenuto del portale di conformità di Microsoft Purview.  
1. La sezione della scheda sulla home page mostra, a colpo d'occhio, la situazione dell'organizzazione in termini di posizione di conformità, quali soluzioni sono disponibili per l'organizzazione, e altro ancora.
1. Dalla finestra principale, scorrere in basso per visualizzare le diverse schede. Le schede disponibili nella schermata iniziale e la posizione delle schede possono essere modificate per soddisfare le preferenze di ogni amministratore.  
1. Posizionando il cursore del mouse sulla barra del titolo di qualsiasi scheda, la barra del titolo diventa grigia.  Quando il cursore assume una forma a croce, è possibile spostare la scheda nella posizione desiderata.
1. Sulla barra del titolo di ogni scheda saranno anche visibili dei puntini di sospensione che consentono di accedere alle azioni disponibili.  Selezionare i puntini di sospensione su Catalogo soluzioni e selezionare **Rimuovi**
1. È possibile aggiungere schede selezionando **+ Aggiungi schede**.  Si apre la finestra Aggiungi schede alla home page.  Posizionare il puntatore del mouse sulla scheda mostrata in questa finestra e trascinarla nella posizione di destinazione desiderata nella schermata iniziale.
1. L'amministratore della conformità potrebbe essere incaricato della gestione di un set di soluzioni per l'organizzazione e, di conseguenza, potrebbe essere utile visualizzare solo tali soluzioni nel pannello di spostamento visualizzato. Per personalizzare le preferenze, selezionare **Personalizza navigazione**.  
1. Nella finestra Personalizzare il riquadro di spostamento notare che è possibile selezionare gli elementi da visualizzare nel pannello di spostamento e deselezionare gli elementi che non si vuole visualizzare. Ai fini di questi lab, mantenere selezionati tutti gli elementi e fare clic su **Salva** nella parte inferiore della finestra.  
1. Lasciare la scheda del browser aperta.

### <a name="task-2"></a>Attività 2

Scoprire la posizione di conformità dell'organizzazione attraverso Compliance Manager.

1. Dal riquadro di spostamento sinistro del portale di conformità di Microsoft Purview selezionare **Compliance Manager**.  In alternativa, è possibile selezionare Compliance Manager sulla barra del titolo della scheda Compliance Manager.

1. Dalla parte superiore della pagina del Compliance Manager, assicurarsi che sia selezionato **Panoramica** (sottolineato). Scorrere verso il basso per vedere tutte le informazioni disponibili sulla pagina.  Le informazioni in questa pagina includono il punteggio di conformità, il punteggio realizzato e i punti gestiti da Microsoft.   Verranno visualizzate le azioni di miglioramento chiave, le soluzioni che influiscono sul punteggio e la suddivisione del punteggio di conformità per categoria.

1. Dalla parte superiore della pagina Panoramica, selezionare **Azioni di miglioramento**.  Si tratta di azioni che possono migliorare il punteggio di conformità dell'organizzazione. Si noti che quando vengono eseguite azioni di miglioramento, per l'aggiornamento dei punti possono essere richieste fino a 24 ore.  Notare i filtri disponibili.

1. Dall'elenco delle azioni di miglioramento, selezionare **Abilita reimpostazione della password self-service**.  Esaminare le informazioni disponibili per l'azione di miglioramento.  Il lato sinistro della finestra fornisce una breve panoramica sull'implementazione, lo stato del test e altro ancora. A destra della panoramica è disponibile la pagina dei dettagli da cui è possibile selezionare l'implementazione, i test, gli standard e i requisiti normativi correlati e i documenti. Ognuna di queste schede fornisce informazioni più dettagliate per l'azione di miglioramento.

1. Uscire da questa azione di miglioramento selezionando **Azioni di miglioramento** dalla barra di navigazione in alto a sinistra nella pagina.  Ora si è di nuovo nella pagina delle azioni di miglioramento.

1. Dalla parte superiore della pagina selezionare **Soluzioni**. Questa pagina mostra come le soluzioni contribuiscono al punteggio e le rispettive opportunità di miglioramento rimanenti.

1. Dalla parte superiore della pagina selezionare **Valutazioni**. Questa pagina mostra la Baseline per la protezione dei dati per Microsoft 365.  Questa è una valutazione della baseline predefinita offerta da Microsoft in Compliance Manager per Microsoft 365.  Questa valutazione della baseline ha una serie di controlli per i principali regolamenti e standard per la protezione dei dati e la governance generale dei dati. Compliance Manager diventa più utile quando si aggiungono valutazioni personalizzate in base alle specifiche esigenze della propria organizzazione.

1. Selezionare **Baseline per la protezione dei dati**.  Sul lato sinistro della pagina è disponibile la panoramica che include dettagli e informazioni.  Espandere **Informazioni** ed esaminare la descrizione della baseline di protezione dei dati di Microsoft 35.  Sul lato destro della pagina notare le informazioni disponibili nella scheda dello stato e per le azioni di miglioramento. Nella parte superiore della pagina sono disponibili schede che è possibile selezionare per visualizzare informazioni più dettagliate sui controlli, le azioni di miglioramento e le azioni Microsoft. Esplorare questi elementi. 

1. Nella parte superiore sinistra della pagina, sopra Baseline per la protezione dei dati per Microsoft 365 (il percorso di navigazione), selezionare **Valutazione** per tornare alla scheda delle valutazioni in Compliance Manager.  

1. Dalla parte superiore della pagina selezionare **Assessment templates** (Modelli di valutazione).  Questa pagina elenca i modelli disponibili ed è organizzata in Modelli inclusi e Modelli premium (potrebbe essere necessario scorrere verso il basso e/o espandere l'elenco per visualizzarli).  È possibile creare valutazioni per la propria organizzazione usando un modello esistente oppure creare un nuovo modello.
    1. Selezionare un modello nell'elenco dei modelli inclusi. Dalla parte superiore destra della pagina, selezionare **+ Create assessment** (Crea valutazione).  Qui è possibile visualizzare i pochi passaggi e le poche informazioni necessari per creare una valutazione da un modello esistente: identificare il prodotto per la valutazione, specificare un nome per la valutazione e assegnarla a un gruppo.  Selezionare Annulla dalla parte inferiore della pagina.

1. Chiudere tutte le schede del browser aperte.

### <a name="review"></a>Verifica

In questo lab è stata esplorata la home page del portale di conformità di Microsoft Purview e sono stati presentati i modi in cui le funzionalità di Compliance Manager possono aiutare le organizzazioni a migliorare il proprio profilo di conformità.
