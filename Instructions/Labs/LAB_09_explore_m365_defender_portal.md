---
lab:
  title: 'Esplorare il portale di Microsoft 365 Defender'
  module: 'Modulo 4: Descrivere le funzionalità di protezione dalle minacce di Microsoft 365'
---


# <a name="lab-explore-the-microsoft-365-defender-portal"></a>Laboratorio: Esplorazione del portale di Microsoft 365 Defender

Questo lab corrisponde al contenuto di Learn seguente:

- Percorso di apprendimento: Descrivere le funzionalità delle soluzioni di sicurezza Microsoft
- Modulo: Descrivere le funzionalità di protezione dalle minacce di Microsoft 365
- Unità: Descrivere il portale di Microsoft 365 Defender

## <a name="lab-scenario"></a>Scenario del lab

In questo lab verrà esplorato il portale di Microsoft 365 Defender esaminando il contenuto visualizzato nella pagina di destinazione. Verranno anche esplorate le opzioni sul riquadro di spostamento che forniscono accesso rapido a funzionalità che fanno parte della soluzione Extended Detection and Response (XDR) di Microsoft: Microsoft Defender per endpoint e Microsoft Defender per Office 365 (posta elettronica e collaborazione).  Infine si vedrà anche in che modo Microsoft Secure Score può aiutare un'organizzazione a migliorare la propria postura di sicurezza.

**Tempo stimato**: 10-15 minuti

### <a name="task-1"></a>Attività 1

Esplorazione della pagina di destinazione di Microsoft 365 Defender

1. Aprire Microsoft Edge. Nella barra degli indirizzi immettere **admin.microsoft.com**.

1. Accedere con le credenziali di amministratore.
    1. Nella finestra Accedi immettere **admin@WWLxZZZZZZ.onmicrosoft.com** (dove ZZZZZZ è l'ID tenant univoco fornito dal proprio provider di hosting del lab) e quindi selezionare **Avanti**.

    1. Immettere la password di amministratore fornita dal proprio provider di hosting del lab. Fare clic su **Accedi**.
    1. Quando compare la domanda se rimanere connessi, selezionare **Sì**. In questo modo si accede alla pagina dell'interfaccia di amministrazione di Microsoft 365.

1. Dal riquadro di spostamento sinistro dell'interfaccia di amministrazione di Microsoft 365 selezionare **Sicurezza**.  Se l'opzione Sicurezza non è elencata, selezionare **Mostra tutto** e quindi **Sicurezza**.  Si apre una nuova pagina del browser alla pagina di benvenuto del portale Microsoft 365 Defender.  

1. Se è la prima volta che si visita il portale Microsoft 365 Defender, potrebbe comparire una finestra pop-up per una breve presentazione.  È consigliabile completare la presentazione.  Selezionare **Take a quick tour** (Segui una breve presentazione).  Leggere la descrizione fornita in ciascuna finestra popup, quindi selezionare **Avanti**. Continuare con la presentazione fino alla fine, quindi selezionare **Fatto**.

1. La pagina di benvenuto del portale Microsoft 365 Defender, mostra molte delle schede comuni di cui hanno bisogno i team di sicurezza. La composizione di schede e dati dipende dal ruolo dell'utente. Scorrere la pagina per visualizzare l'insieme di schede predefinito per il proprio ruolo di amministratore globale.

1. Le schede visualizzate possono essere personalizzate secondo le proprie preferenze.  Selezionare **+ Aggiungi schede**. Viene aperta una finestra la quale indica che tutte le schede sono già presenti nella home page.  Chiudere la finestra selezionando la **X** nell'angolo in alto a destra della finestra.

1. La selezione dei puntini di sospensione nell'angolo in alto a destra di qualsiasi scheda fornirà ulteriori azioni che è possibile eseguire.  

1. Le schede possono anche essere spostate. Passando il cursore del mouse sulla barra del titolo di qualsiasi scheda, quando il cursore assume la forma di una croce, selezionare la scheda e spostarla nella posizione desiderata.

1. Selezionando il titolo di una scheda si accede a informazioni aggiuntive per quell'argomento. Questo passaggio sarà approfondito nell'attività successiva.

1. Il riquadro di spostamento sinistro offre collegamenti/accesso alle informazioni che fanno parte della soluzione di rilevamento e risposta estesi (XDR, Extended Detection and Response) di Microsoft, che include incidenti e avvisi, ricerca, centro operativo, analisi delle minacce, punteggio di sicurezza e molto altro.  Include inoltre accesso rapido a Microsoft Defender per endpoint (i collegamenti elencati sotto Endpoint) e Defender per Office 365 (i collegamenti elencati sotto E-mail e collaborazione), Microsoft Defender for Cloud Apps (i collegamenti elencati sotto App cloud).  Esplorare queste opzioni selezionando alcuni collegamenti.   Per tornare alla home page del portale Microsoft 365 Defender, selezionare **Home** sul riquadro di spostamento sinistro.

1. Tenere aperta la finestra del browser.

### <a name="task-2"></a>Attività 2

In questa attività si vedrà come Microsoft Secure Score può aiutare un'organizzazione a migliorare la propria postura di sicurezza.

1. Dalla pagina di benvenuto del portale Microsoft 365 Defender, selezionare **Microsoft Secure Score**, dalla barra del titolo della scheda (il testo diventerà blu).  In alternativa, è possibile selezionare **Secure Score** dal riquadro di spostamento sinistro.

1. La pagina Microsoft Secure Score viene aperta nella scheda Panoramica. Microsoft Secure Score è una misurazione della postura di sicurezza di un'organizzazione. Il punteggio di sicurezza dell'organizzazione è mostrato come percentuale, insieme al numero di punti raggiunti rispetto al totale dei punti possibili e suddiviso per categoria. Selezionare **Includi** accanto alla posizione in cui è indicato Il punteggio di sicurezza.  Si apre una piccola finestra che consente di includere il punteggio realizzabile, il punteggio pianificato e il punteggio della licenza corrente nella suddivisione del punteggio di sicurezza dell'organizzazione.  Selezionare di nuovo **Includi** per chiudere la finestra.

1. La pagina panoramica include anche le azioni di miglioramento più importanti, il punteggio di confronto, la cronologia e le risorse aggiuntive.

1. Selezionare **Azioni consigliate** nella parte superiore della pagina.  Notare le informazioni disponibili nella tabella, per ciascun elemento, che includono l'impatto del punteggio e i punti realizzati.  

1. Selezionando una voce dall'elenco si ottengono informazioni dettagliate.  Selezionare **Richiedi la MFA per i ruoli amministrativi** ed esaminare le informazioni disponibili.  Selezionare **Modifica stato e piano di azione**.  Nella finestra visualizzata notare le opzioni di stato disponibili. Selezionare la **X** nell'angolo in alto a destra per chiudere questa finestra.

1. Selezionare la scheda **Cronologia** dalla parte superiore della pagina. Selezionare una voce nella tabella della cronologia.  Verrà visualizzata una pagina dettagliata per l'elemento selezionato.  Esplorare le opzioni disponibili.  Per uscire dalla pagina dei dettagli e tornare alla pagina della cronologia, selezionare la **X** nell'angolo in alto a destra della pagina.

1. Dalla parte superiore della pagina, selezionare **Metriche e tendenze**.  Consultare le informazioni disponibili.  Dall'angolo superiore destro della pagina, selezionare l'**icona del calendario**.  È possibile limitare la vista a un intervallo di date personalizzato.  Selezionando l'**icona del filtro** è possibile filtrare la visualizzazione per identità e/o app.  Chiudere la finestra e selezionare **Home** dal riquadro di spostamento sinistro per tornare alla home page di Microsoft 365 Defender.

1. Chiudere tutte le schede del browser aperte.

### <a name="review"></a>Verifica

In questo lab è stato esplorato il portale di Microsoft 365 Defender esaminando il contenuto visualizzato nella pagina di destinazione, sono state esplorate le opzioni nel riquadro di spostamento che forniscono un rapido accesso alle funzionalità che fanno parte della soluzione Extended Detection and Response (XDR) di Microsoft, Microsoft Defender per endpoint e Microsoft Defender per Office 365 (posta elettronica e collaborazione).  Infine, è stato esplorato in che modo Microsoft Secure Score può aiutare un'organizzazione a migliorare il proprio profilo di sicurezza.
