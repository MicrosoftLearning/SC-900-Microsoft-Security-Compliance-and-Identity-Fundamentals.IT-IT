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

Questa demo illustra Microsoft Defender per il cloud e mostra come è possibile usarlo per migliorare la postura di sicurezza di un'organizzazione.  NOTA: la sottoscrizione di Azure gestita dal provider di servizi di hosting per i lab autorizzato potrebbe limitare l'accesso e si potrebbero riscontrare ritardi più lunghi del normale.

### <a name="demo-task-1"></a>Attività demo 1

In questa attività della demo verranno presente a livello generale alcune delle funzionalità di Microsoft Defender per il cloud.

1. Aprire Microsoft Edge. Nella barra degli indirizzi immettere **portal.azure.com**.
1. Accedere con le credenziali di amministratore.
    1. Nella finestra Accedi immettere il nome utente fornito dal provider di hosting del lab e quindi selezionare **Avanti**.
    1. Immettere la password di amministratore, che dovrebbe essere fornita dal proprio provider di hosting del lab. Fare clic su **Accedi**.
    1. Quando compare la domanda se rimanere connessi, selezionare **Sì**.

1. Nella barra di ricerca blu immettere **Microsoft Defender per il cloud** e quindi nell'elenco dei risultati selezionare **Microsoft Defender per il cloud**.

1. Se questa è la prima volta che si accede a Microsoft Defender per il cloud con la propria sottoscrizione, potrebbe comparire la pagina introduttiva e potrebbe essere richiesto di eseguire l'aggiornamento.  Scorrere fino in fondo alla pagina e selezionare **Ignora**.  Verrà visualizzata la pagina Panoramica.

1. Notare le informazioni disponibili nella pagina Panoramica di Microsoft Defender per il cloud.  Le informazioni nella parte superiore della pagina includono il numero di sottoscrizioni Azure, il numero di risorse valutate, il numero di raccomandazioni attive ed eventuali avvisi di sicurezza.  Il corpo principale della pagina contiene schede per Postura di sicurezza, Conformità con le normative, Informazioni dettagliate e altro.  Nota: l'iniziativa di criteri predefinita di Microsoft Defender per il cloud, che normalmente deve essere assegnata dall'amministratore, è già stata assegnata come parte della configurazione della sottoscrizione di Azure. Il punteggio di sicurezza, tuttavia, mostrerà 0% perché possono essere richieste fino a 24 ore prima che Azure indichi un punteggio iniziale.

1. Nella parte superiore della pagina selezionare **Assessed resources** (Risorse valutate).  (Si noti che questo equivale ad aver selezionato Inventario dal riquadro di spostamento sinistro della home page di Microsoft Defender per il cloud).
    1. Verrà visualizzata la pagina **Inventario** che elenca le risorse correnti. Selezionare la risorsa macchina virtuale **sc900-winwm**. Questa risorsa è associata alla macchina virtuale usata nel lab precedente.
    1. La pagina Integrità delle risorse per la macchina virtuale offre un elenco di raccomandazioni.  Nell'elenco disponibile selezionare qualsiasi elemento nell'elenco per cui è indicato lo stato **Non integro**.
    1. Notare la descrizione dettagliata.  Selezionare la freccia a discesa accanto a Procedura di correzione. Si noti che vengono fornite istruzioni per la correzione (o collegamenti alle istruzioni) insieme all'opzione per intervenire.  Uscire dalla finestra senza eseguire alcuna azione.
    1. Tornare alla pagina Panoramica di Microsoft Defender per il cloud selezionando **Microsoft Defender per il cloud | Panoramica** nella parte superiore della pagina, sopra a Integrità delle risorse.

1. Dal riquadro di spostamento sinistro selezionare **Raccomandazioni**.  (Si noti che questo equivale alla selezione di Raccomandazioni attive nella parte superiore della pagina di panoramica di Microsoft Defender per il cloud).
    1. Verificare che sia selezionata (sottolineata) la scheda **Tutte le raccomandazioni**.  Si noti la visualizzazione dashboard che mostra le raccomandazioni attive in base alla gravità, l'integrità delle risorse e altre informazioni.
    1. Si noti che alcuni elementi vengono visualizzati come risorse non integre, come indicato dalla barra rossa a destra della riga.  Nell'elenco selezionare qualsiasi risorsa non integra.  Nella pagina che si apre saranno presenti una descrizione, la procedura di correzione e le risorse interessate. Uscire da questa pagina selezionando la **X** nell'angolo in alto a destra dello schermo.
    1. Uscire dalla pagina delle raccomandazioni selezionando la **X** nell'angolo in alto a destra dello schermo per tornare alla pagina della panoramica.

1. Dal riquadro di spostamento sinistro principale selezionare **Conformità con le normative**. La pagina di conformità alle normative fornisce un elenco di controlli di conformità basati sul benchmark di sicurezza del cloud Microsoft (verificare che la scheda Microsoft Cloud Security Benchmark sia selezionata/sottolineata). In ogni dominio di controllo è disponibile un subset di controlli e per ogni controllo sono presenti una o più valutazioni. Ogni valutazione fornisce informazioni, tra cui descrizione, correzione e risorse interessate.
    1. Esaminiamo una delle aree dei domini di controllo. Selezionare (espandere) **SR. Sicurezza di rete**. Viene visualizzato un elenco di controlli correlati alla sicurezza di rete.
    1. Selezionare **SR-10. Microsoft Defender per DNS deve essere abilitato**. Si noti l'elenco delle valutazioni automatizzate (che includono valutazioni automatizzate per AWS) e il modo in cui ogni elemento di valutazione fornisce informazioni, tra cui il tipo di risorsa, le risorse con errori e le stazioni di conformità. Selezionare le valutazioni elencate.  Verranno visualizzate informazioni che includono una descrizione, la procedura di correzione e le risorse interessate.
    1. Selezionare la **X** nell'angolo in alto a destra della schermata per chiudere la pagina.
    1. Selezionare **Panoramica** nel riquadro di spostamento sinistro per tornare alla pagina Panoramica di Microsoft Defender per il cloud.
    1. Mantenere aperta la pagina Panoramica di Microsoft Defender per il cloud, che verrà usata nell'attività successiva.

### <a name="demo-task-2"></a>Attività demo 2

Tenere presente che Microsoft Defender per il cloud è disponibile in due modalità: senza funzionalità di sicurezza avanzate (gratuito) e con funzionalità di sicurezza avanzate disponibili tramite i piani di Microsoft Defender per il cloud. Questa attività illustra come abilitare o disabilitare i vari piani di Microsoft Defender per il cloud.

1. Nella pagina Panoramica di Microsoft Defender per il cloud selezionare **Impostazioni ambiente** nel pannello di spostamento a sinistra.
1. Selezionare la casella **Espandi tutto** e quindi selezionare la sottoscrizione **MOC Subscription--lodXXXXXXXX** elencata accanto all'icona della chiave gialla.
1. Nella pagina dei piani di Defender notare che è possibile selezionare Abilita tutti o selezionare singoli piani di Defender. 
    1. Verificare che lo stato di CSPM sia impostato su **Attivato**. In caso contrario, impostarlo ora.  
    1. Abilitare il piano per i server.  Selezionare **Attivato** per la riga Server e quindi selezionare **Salva** nella parte superiore della pagina.
1. Chiudere tutte le schede del browser aperte.

## <a name="review"></a>Verifica

In questa demo è stato presentato Microsoft Defender per il cloud e si è visto come usare il punteggio di sicurezza di Azure per migliorare la postura di sicurezza di un'organizzazione.
