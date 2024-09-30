---
lab:
  title: Esplorare il portale di Microsoft Defender
  module: Describe the threat protection capabilities of Microsoft XDR
---

# Lab: Esplorare il portale di Microsoft Defender

Questo lab corrisponde al contenuto di Learn seguente:

- Percorso di apprendimento: Descrivere le funzionalità delle soluzioni di sicurezza Microsoft
- Modulo: Descrivere le funzionalità di protezione dalle minacce di Microsoft Defender XDR
- Unità: Descrivere il portale di Microsoft Defender

## Scenario laboratorio

In questo lab si esplorerà il portale di Microsoft Defender esaminando il contenuto visualizzato nella pagina di destinazione. Verranno anche esplorate le opzioni sul riquadro di spostamento che forniscono accesso rapido a funzionalità che fanno parte della soluzione Extended Detection and Response (XDR) di Microsoft: Microsoft Defender per endpoint e Microsoft Defender per Office 365 (posta elettronica e collaborazione).  Infine si vedrà anche in che modo Microsoft Secure Score può aiutare un'organizzazione a migliorare la propria postura di sicurezza.

**Tempo stimato**: 30 minuti

### Attività 1

Esplorare la pagina di destinazione di Microsoft Defender.

1. Aprire Microsoft Edge. Nella barra degli indirizzi immettere **admin.microsoft.com**.

1. Accedere utilizzando le credenziali di amministratore.
    1. Nella finestra Accedi immettere **admin@WWLxZZZZZZ.onmicrosoft.com** (dove ZZZZZZ è l'ID tenant univoco fornito dal proprio provider di hosting del lab) e quindi selezionare **Avanti**.

    1. Immettere la password di amministratore fornita dal proprio provider di hosting del lab. Fare clic su **Accedi**.
    1. Quando viene richiesto di rimanere connessi, selezionare **Sì**. Verrà visualizzata la pagina dell'interfaccia di amministrazione di Microsoft 365.

1. Nel riquadro di spostamento a sinistra dell'interfaccia di amministrazione di Microsoft 365, in Interfacce di amministrazione, selezionare **Sicurezza**.  Se l'opzione Sicurezza non è elencata, selezionare **Mostra tutto** e quindi **Sicurezza**.  Viene aperta una nuova pagina del browser nella pagina iniziale del portale di Microsoft Defender.  

1. Se questa è la prima volta che si visita il portale di Microsoft Defender, è possibile che venga visualizzata una finestra popup per un rapido tour.  È consigliabile completare la presentazione.  Selezionare **Presentazione rapida**.  Leggere la descrizione fornita in ogni finestra a comparsa, quindi selezionare **Avanti**. Continuare con la presentazione fino alla fine, quindi selezionare **Fine**.

1. La home page del portale di Microsoft Defender mostra molte delle schede comuni necessarie ai team di sicurezza. La composizione delle schede e dei dati dipende dal ruolo dell'utente. Scorrere la pagina per visualizzare il set di schede predefinito per il proprio ruolo di amministratore globale.

1. Le schede visualizzate possono essere personalizzate in base alle proprie preferenze.  Selezionare **+ Aggiungi schede**. Verrà visualizzata una finestra che mostra le schede disponibili per essere aggiunte alla pagina iniziale.  È possibile che siano già state visualizzate tutte le schede, in questo caso verrà visualizzata la nota "Nella pagina iniziale sono già presenti tutte le schede". Chiudere la finestra selezionando la **X** nell'angolo superiore a destra della finestra.

1. Selezionando i puntini di sospensione in alto a destra di qualsiasi scheda sarà possibile rimuovere la scheda dalla pagina di destinazione.  

1. È anche possibile spostare le schede. Passando il cursore del mouse sulla barra del titolo di qualsiasi scheda, quando il cursore assume la forma di una croce, selezionare la scheda e spostarla nella posizione desiderata.  

1. Alcune schede hanno pulsanti nella parte inferiore della scheda selezionabili. Il titolo di alcune schede funge da collegamento alla pagina per tale argomento.  Ad esempio, se si seleziona il titolo della scheda Microsoft Secure Score, verrà visualizzata la pagina Microsoft Secure Score.  Altre informazioni su Microsoft Secure Score verranno esaminate in una sezione successiva di questo lab.

1. Tenere aperta la finestra del browser.

### Attività 2

In questa parte del lab verranno esaminate alcune delle opzioni disponibili nel pannello di spostamento sinistro del portale di Defender.  Tramite il portale di Microsoft Defender, Microsoft offre la promessa di una piattaforma unificata per le operazioni di sicurezza. Il portale Microsoft Defender combina le funzionalità di protezione, rilevamento, indagine e risposta alle minacce nell'intera organizzazione e in tutti i relativi componenti in un'unica posizione centralizzata.  

1. Esplorare il pannello di spostamento a sinistra.

1. Per tornare alla home page del portale di Microsoft Defender, selezionare **Home** nel pannello di spostamento a sinistra.

### Attività 3

In questa attività si vedrà come Microsoft Secure Score può aiutare un'organizzazione a migliorare la propria postura di sicurezza.

1. Nella pagina iniziale del portale di Microsoft Defender selezionare **Microsoft Secure Score**, dalla barra del titolo della scheda (il testo diventerà blu).  In alternativa, è possibile selezionare **Punteggio di sicurezza** dal riquadro di spostamento a sinistra.

1. La pagina Microsoft Secure Score viene aperta nella scheda Panoramica. Microsoft Secure Score è una misurazione della postura di sicurezza di un'organizzazione. Il punteggio di sicurezza dell'organizzazione è mostrato come percentuale, insieme al numero di punti raggiunti rispetto al totale dei punti possibili e suddiviso per categoria. Selezionare **Includi** accanto alla posizione in cui è indicato Il punteggio di sicurezza.  Si apre una piccola finestra che consente di includere il punteggio realizzabile, il punteggio pianificato e il punteggio della licenza corrente nella suddivisione del punteggio di sicurezza dell'organizzazione.  Selezionare di nuovo **Includi** per chiudere la finestra.

1. La pagina di panoramica include anche le principali azioni di miglioramento, il punteggio di confronto, la cronologia e le risorse aggiuntive.

1. Selezionare **Azioni consigliate** nella parte superiore della pagina.  Notare le informazioni disponibili nella tabella.  

1. Selezionare il primo elemento dall'elenco ed esaminare le informazioni disponibili. Nella finestra visualizzata notare le opzioni di stato disponibili. Selezionare la scheda **Implementazione** per visualizzare le informazioni correlate all'implementazione. Selezionare la **X** nell'angolo in alto a destra per chiudere questa finestra.

1. Selezionare la scheda **Cronologia** nella parte superiore della pagina.  Per ogni attività elencata è presente una breve istruzione che ne fornisce il contesto.  Selezionare una voce nella tabella della cronologia.  Nella parte superiore a destra della pagina Dettagli, in Cronologia, selezionare **Eventi X** (dove X è un numero).  Viene aperta la finestra della cronologia delle azioni con ulteriori informazioni.  Per tornare alla pagina Cronologia, selezionare **Chiudi** nella parte inferiore della pagina, quindi selezionare la **X** nell'angolo in alto a destra della pagina Dettagli.

1. Nella parte superiore della pagina, selezionare **Metriche e tendenze**.  Notare le informazioni disponibili.  Dall'angolo in alto a destra della pagina, selezionare l'**icona calendario**.  È possibile restringere la visualizzazione a un intervallo di date personalizzato.  Selezionando l'**icona del filtro** è possibile filtrare la visualizzazione per identità e/o app.  Chiudere la finestra e selezionare **Home** nel pannello di spostamento a sinistra per tornare alla home page di Microsoft Defender.

1. Chiudere tutte le schede del browser aperte.

### Revisione

In questo lab è stato esplorato il portale di Microsoft Defender esaminando il contenuto visualizzato nella pagina di destinazione, sono state esaminate le opzioni nel pannello di spostamento che fornisce un accesso rapido alle funzionalità che fanno parte della soluzione Rilevamento esteso e risposta (XDR) di Microsoft, Microsoft Defender per endpoint e Microsoft Defender per Office 365 (posta elettronica e collaborazione).  Infine sarà possibile esplorare il modo in cui Microsoft Secure Score può aiutare un'organizzazione a migliorare il proprio comportamento di sicurezza.
