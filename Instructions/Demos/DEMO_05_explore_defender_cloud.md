<!---
---
Demo: titolo: "Esplorare Microsoft Defender per il cloud" Percorso di apprendimento/Modulo/Unità: "Percorso di apprendimento: Descrivere le funzionalità delle soluzioni di sicurezza Microsoft; Modulo 2: Descrivere le funzionalità di gestione della sicurezza di Azure; Unità 3: Descrivere Cloud Security Posture Management"
---
--->

# Demo: Microsoft Defender per il cloud

Questa demo corrisponde al contenuto di Learn seguente:

- Percorso di apprendimento: Descrivere le funzionalità delle soluzioni di sicurezza Microsoft
- Modulo: Descrivere le funzionalità di gestione della sicurezza di Azure
- Unità: Descrivere Cloud Security Posture Management.

## Scenario dimostrativo

Questa demo illustra Microsoft Defender per il cloud e mostra come è possibile usarlo per migliorare la postura di sicurezza di un'organizzazione.  NOTA: la sottoscrizione di Azure gestita dal provider di servizi di hosting per i lab autorizzato potrebbe limitare l'accesso e si potrebbero riscontrare ritardi più lunghi del normale.

### Demo parte 1

In questa attività della demo verranno presente a livello generale alcune delle funzionalità di Microsoft Defender per il cloud.

1. Aprire la scheda del browser **Home-Microsoft Azure**.  Se la scheda è stata chiusa in precedenza, aprire una pagina del browser e nella barra degli indirizzi digitare **https://portal.azure.com**. Accedere con le credenziali di Azure fornite dal provider di servizi di hosting per il lab autorizzato (ALH).  In questo modo si verrà indirizzati alla home page dei servizi di Azure.

1. Nella barra di ricerca blu immettere **Microsoft Defender per il cloud** e quindi nell'elenco dei risultati selezionare **Microsoft Defender per il cloud**.

1. Se questa è la prima volta che si accede a Microsoft Defender per il cloud con la propria sottoscrizione, potrebbe comparire la pagina introduttiva e potrebbe essere richiesto di eseguire l'aggiornamento.  Scorrere fino in fondo alla pagina e selezionare **Ignora**.  Verrà visualizzata la pagina Panoramica. Notare le informazioni disponibili nella pagina Panoramica di Microsoft Defender per il cloud.  Le informazioni nella parte superiore della pagina includono il numero di sottoscrizioni di Azure, il numero di risorse valutate, il numero di raccomandazioni attive ed eventuali avvisi di sicurezza.  Il corpo principale della pagina contiene schede per Postura di sicurezza, Conformità con le normative, Informazioni dettagliate e altro.  Per impostazione predefinita, per tutte le sottoscrizioni è abilitato il CSPM di base, che fornisce un punteggio di sicurezza.  
    1. Se il punteggio di sicurezza viene visualizzato come 0%, significa che Azure può impiegare fino a 24 ore per riflettere un punteggio iniziale.  
    1. È inoltre importante illustrare che Defender per il cloud è una soluzione multi-cloud che può aiutare a migliorare la sicurezza non solo con Azure, ma anche con AWS e Google Cloud Platform.

1. La prima cosa da evidenziare è che Microsoft Defender per il cloud utilizza Microsoft Cloud Security Benchmark come iniziativa predefinita per i criteri.  Dal riquadro di spostamento a sinistra, selezionare **Impostazioni ambiente**. Nella finestra principale, selezionare **Espandi tutto**.  La visualizzazione estesa mostrerà la sottoscrizione di colore blu.  Selezionare la sottoscrizione **MOC Subscription--lodXXXXXX**.

1. Dal riquadro di spostamento a sinistra, selezionare **Criteri di sicurezza**, che si trova nell'elenco delle impostazioni dei criteri. Se l'iniziativa predefinita non è assegnata, selezionare **Assegna criterio**.
    1. Notare che nella scheda Informazioni di base, la definizione dell'iniziativa è Microsoft Cloud Security Benchmark.  L'opzione è disattivata perché l'iniziativa è quella predefinita e l'unica azione possibile è quella di assegnarla.
    1. Selezionare **Rivedi e crea** e quindi **Crea**. Se si desidera, è possibile consultare i parametri configurabili per le diverse schede prima di selezionare l'opzione di revisione e creazione.
    1. Si tratta di un passaggio importante per garantire la visualizzazione delle raccomandazioni di sicurezza basate su Microsoft Cloud Security Benchmark.  

1. Notare inoltre che è possibile aggiungere standard di settore e normativi predefiniti. Se quelli elencati risultano essere obsoleti, selezionare **Aggiungi altri standard** per visualizzare l'elenco completo.  Selezionarne uno dall'elenco e aggiungerlo manualmente selezionando **Rivedi e crea**, quindi **Crea**.  Verranno mostrati nell'elenco delle normative di settore e standard.

1. Selezionare **Panoramica**.  Il corpo principale della pagina contiene schede per Postura di sicurezza, Conformità con le normative, Informazioni dettagliate e altro.  Tutte le sottoscrizioni dispongono di un CSPM di base che fornisce un punteggio di sicurezza. Il valore visualizzato è 0% perché Azure può impiegare fino a 24 ore per riflettere un punteggio iniziale.  Sebbene il punteggio di sicurezza sia attualmente 0%, è opportuno illustrare che Defender per il cloud è una soluzione multi-cloud che può aiutare a migliorare la sicurezza non solo con Azure, ma anche con AWS e Google Cloud Platform.

1. Selezionare **Risorse valutate** nella parte superiore della pagina.  (Si noti che questo equivale ad aver selezionato Inventario dal riquadro di spostamento sinistro della home page di Microsoft Defender per il cloud).
    1. Verrà visualizzata la pagina **Inventario** che elenca le risorse correnti. Selezionare la risorsa macchina virtuale **sc900-winwm**. Questa risorsa è associata alla macchina virtuale usata nel precedente lab o demo.
    1. La pagina Integrità delle risorse per la macchina virtuale offre un elenco di raccomandazioni.  Nell'elenco disponibile selezionare qualsiasi elemento nell'elenco per cui è indicato lo stato **Non integro**.
    1. Notare la descrizione dettagliata.  Selezionare la freccia a discesa accanto a Passaggi per la correzione. Si noti che vengono fornite istruzioni per la correzione (o collegamenti alle istruzioni) insieme all'opzione per intervenire.  Uscire dalla finestra senza eseguire alcuna azione.
    1. Tornare alla pagina Panoramica di Microsoft Defender per il cloud selezionando **Microsoft Defender per il cloud | Panoramica** nella parte superiore della pagina, sopra a Integrità delle risorse.

1. Dal riquadro di spostamento sinistro selezionare **Raccomandazioni**.  (Si noti che questo equivale alla selezione di Raccomandazioni attive nella parte superiore della pagina di panoramica di Microsoft Defender per il cloud).
    1. Verificare che sia selezionata (sottolineata) la scheda **Tutte le raccomandazioni**.  Si noti la visualizzazione dashboard che mostra le raccomandazioni attive in base alla gravità, l'integrità delle risorse e altre informazioni.
    1. Si noti che alcuni elementi vengono visualizzati come risorse non integre, come indicato dalla barra rossa a destra della riga.  Nell'elenco selezionare qualsiasi risorsa non integra.  Nella pagina che si apre saranno presenti una descrizione, la procedura di correzione e le risorse interessate. Uscire da questa pagina selezionando la **X** nell'angolo superiore destro della schermata.
    1. Uscire dalla pagina Elementi consigliati selezionando la **X** nell'angolo superiore a destra della schermata, per tornare alla pagina di panoramica.

1. Dal riquadro di spostamento sinistro principale selezionare **Conformità con le normative**.  **NOTA**: se si nota che non è presente alcuna sottoscrizione per cui calcolare la conformità, il motivo potrebbe essere un ritardo di 24 ore per visualizzare le informazioni. Passare all'attività 2.  Se le informazioni vengono visualizzate, procedere con i passaggi seguenti.
    1. La pagina di conformità alle normative fornisce un elenco di controlli di conformità basati sul benchmark di sicurezza del cloud Microsoft (verificare che la scheda Microsoft Cloud Security Benchmark sia selezionata/sottolineata). In ogni dominio di controllo è disponibile un subset di controlli e per ogni controllo sono presenti una o più valutazioni. Ogni valutazione fornisce informazioni, tra cui descrizione, correzione e risorse interessate.
    1. Esaminiamo una delle aree dei domini di controllo. Selezionare (espandere) **SR. Sicurezza di rete**. Viene visualizzato un elenco di controlli correlati alla sicurezza di rete.
    1. Selezionare **SR-10. Microsoft Defender per DNS deve essere abilitato**. Si noti l'elenco delle valutazioni automatizzate (che includono valutazioni automatizzate per AWS) e il modo in cui ogni elemento di valutazione fornisce informazioni, tra cui il tipo di risorsa, le risorse con errori e le stazioni di conformità. Selezionare le valutazioni elencate.  Verranno visualizzate informazioni che includono una descrizione, la procedura di correzione e le risorse interessate.
    1. Selezionare la **X** nell'angolo in alto a destra della schermata per chiudere la pagina.
    1. Selezionare **Panoramica** nel riquadro di spostamento sinistro per tornare alla pagina Panoramica di Microsoft Defender per il cloud.
    1. Mantenere aperta la pagina Panoramica di Microsoft Defender per il cloud, che verrà usata nell'attività successiva.

### Demo parte 2

Tenere presente che Microsoft Defender per il cloud è disponibile in due modalità: senza funzionalità di sicurezza avanzate (gratuito) e con funzionalità di sicurezza avanzate disponibili tramite i piani di Microsoft Defender per il cloud. Questa attività illustra come abilitare o disabilitare i vari piani di Microsoft Defender per il cloud.

1. Nella pagina Panoramica di Microsoft Defender per il cloud selezionare **Impostazioni ambiente** nel pannello di spostamento a sinistra.
1. Selezionare la casella **Espandi tutto** e quindi selezionare la sottoscrizione **MOC Subscription--lodXXXXXXXX** elencata accanto all'icona della chiave gialla.
1. Nella pagina dei piani di Defender notare che è possibile selezionare Abilita tutti o selezionare singoli piani di Defender. 
    1. Verificare che lo stato di CSPM sia impostato su **Attivato**. In caso contrario, impostarlo ora.  
    1. Abilitare il piano per i server.  Selezionare **Attivato** per la riga Server e quindi selezionare **Salva** nella parte superiore della pagina.
1. Mantenere aperta la scheda Azure nel browser per la demo successiva di Azure.

## Revisione

In questa demo è stato presentato Microsoft Defender per il cloud ed è stato mostrato come è possibile usare il punteggio di sicurezza di Azure per migliorare il comportamento di sicurezza di un'organizzazione.
