---
lab:
  title: Esplorare la gestione dei rischi Insider in Microsoft Purview
  module: Describe the data security solutions of Microsoft Purview
---

# Lab: Esplorare la gestione dei rischi Insider in Microsoft Purview

Questo lab corrisponde al contenuto di Learn seguente:

- Percorso di apprendimento: Descrivere le funzionalità di Microsoft Priva e Microsoft Purview
- Modulo: Descrivere le soluzioni di sicurezza dei dati di Microsoft Purview
- Unità: Descrivere la gestione dei rischi Insider in Microsoft Purview

## Scenario laboratorio

In questo lab, verrà descritto il processo di impostazione di un criterio di rischio Insider, insieme ai prerequisiti di base per configurare e usare i criteri di gestione dei rischi Insider.  Nota: questo lab fornirà soltanto visibilità degli elementi richiesti per impostare la gestione dei rischi Insider e le opzioni associate alla creazione di un criterio.  Questo lab non include un'attività per attivare il criterio, in quanto il numero di eventi necessari per attivare un criterio e il tempo necessario non rientrano nell'ambito di questo esercizio.

**Tempo stimato**: 60 minuti

### Attività 1

In questa attività si esplorano le diverse autorizzazioni del ruolo per la gestione dei rischi Insider e si verifica che gli utenti specifici siano già stati inclusi nel gruppo di ruoli Di gestione dei rischi Insider. Assicurarsi che gli utenti dispongano delle autorizzazioni del ruolo appropriate garantisce che gli utenti designati possano accedere e gestire le funzionalità di gestione dei rischi Insider. Quando si aggiungono membri a un gruppo di ruoli, potrebbero essere necessari fino a 30 minuti prima che le autorizzazioni del gruppo di ruoli vengano applicate agli utenti nell'organizzazione.

1. Aprire la scheda del browser sulla Home page di Microsoft Purview.  Se in precedenza è stata chiusa, aprire una scheda del browser e immettere **https://admin.microsoft.com**. Accedere con le credenziali di amministratore per il tenant di Microsoft 365 fornito tramite un provider di servizi di hosting per lab autorizzato (ALH). 

1. Nel riquadro di spostamento sinistro del interfaccia di amministrazione di Microsoft 365 selezionare **Mostra tutto** e quindi Selezionare **Microsoft Purview**.  Verrà aperta una nuova pagina del browser nella pagina iniziale del portale di Microsoft Purview.  

1. Nel pannello di spostamento a sinistra selezionare **Impostazioni**, espandere **Ruoli e ambiti** e quindi selezionare **Gruppi di ruoli**.

1. Nel campo di ricerca, in alto a destra della pagina, digitare **Rischio** Insider e quindi premere INVIO sulla tastiera.  Si notino i numerosi ruoli visualizzati.  Ognuno di questi presenta diversi livelli di accesso.  Selezionare **Gestione dei rischi Insider** e rivedere la descrizione.  Scorrere verso il basso fino a Membri e notare che sono elencati l'amministratore MOD e Megan Bowen. Chiudere la finestra selezionando la **X** in alto a destra della finestra.

1. Nel pannello di spostamento a sinistra selezionare **Home** per tornare alla pagina del portale di Microsoft Purview.

1. Mantenere questa scheda del browser aperta, perché servirà per un'attività successiva.

### Attività 2

In questa attività verranno esaminate le impostazioni associate alla soluzione Gestione dei rischi Insider.  Le impostazioni di gestione dei rischi Insider si applicano a tutti i criteri di gestione dei rischi Insider, indipendentemente dal modello scelto al momento della creazione.

1. Si dovrebbe essere nella home page del portale di Microsoft Purview.

1. Prima di iniziare a configurare un criterio, esistono alcune impostazioni che un amministratore deve avere familiarità con e configurare in base alle esigenze dell'organizzazione. Nel riquadro di spostamento sinistro selezionare **Impostazioni** e quindi Gestione **dei rischi** Insider.  Qui verranno esaminate alcune delle impostazioni disponibili.
    1. Selezionare **Privacy**: per gli utenti che eseguono attività corrispondenti ai criteri di rischio Insider, questa impostazione determinerà se visualizzare i nomi effettivi o usare versioni anonime per mascherare le identità.  Per gli scopi di questa procedura dettagliata è possibile lasciare l'impostazione predefinita.
    1. Selezionare **Indicatori** di criteri. Quando si verifica un evento di attivazione dei criteri, le attività mappate agli indicatori selezionati vengono usate per determinare il punteggio di rischio, per l'utente. Gli indicatori di criteri qui selezionati sono inclusi nei modelli di criteri di rischio Insider.  Scorrere per visualizzare tutti gli indicatori disponibili e le informazioni associate.  In **Indicatori** di Office selezionare **Seleziona tutto**. Le opzioni selezionate in questa schermata sono incluse nei modelli di criteri.
    1. Selezionare **Intervalli di tempo dei criteri**. Gli intervalli di tempo scelti qui diventano effettivi per un utente quando attivano una corrispondenza per i criteri di rischio Insider.   La finestra Attivazione determina la durata del rilevamento delle attività degli utenti da parte dei criteri e viene attivata quando un utente esegue la prima attività corrispondente a un criterio. Rilevamento attività passate determina a quando risale un criterio per rilevare l'attività dell'utente e si attiva quando un utente esegue la prima attività che corrisponde a un criterio.  Lasciare invariati i valori predefiniti.
    1. Selezionare **Rilevamenti** intelligenti. Esaminare le opzioni qui.  Notare le impostazioni dei domini e del relativo rapporto con gli indicatori.
    1. Esplorare gli altri elementi elencati nelle impostazioni. Si noti che molti sono in anteprima.

1. Nel riquadro di spostamento a sinistra selezionare **Soluzioni**, quindi selezionare **Gestione dei** rischi Insider.

1. Mantenere la scheda del browser aperta perché verrà usata nell'attività successiva.

### Attività 3

Quando si creano criteri per la gestione dei rischi Insider, è necessario scegliere un criterio rapido o un criterio personalizzato. Le impostazioni rapide dei criteri vengono popolate automaticamente dalle procedure consigliate o dai risultati dell'analisi analitica più recente nell'organizzazione.  In questa attività verranno dettagliate le impostazioni per la creazione di un criterio personalizzato. L'obiettivo è semplicemente quello di farsi un'idea delle varie opzioni e della flessibilità associate alla creazione di un criterio.

1. Si dovrebbe essere nella pagina di panoramica per la gestione dei rischi Insider.  Se non è già presente, selezionare Soluzioni nel riquadro di spostamento sinistro, quindi selezionare Insider Risk Management .If not there there, select **Solutions** from the left navigation pane, then select **Insider Risk Management** .

1. Nella pagina di panoramica della gestione dei rischi Insider selezionare la **scheda Criteri** , selezionare **+ Crea criterio**, quindi selezionare **Criteri personalizzati**. Configurare ciascuna delle seguenti schede di criteri.

    1. Modello di criterio: nella categoria Perdite di dati selezionare **Perdite di dati**.  Leggere i dettagli associati a questo modello. Nei prerequisiti, i criteri DLP vengono visualizzati con un segno di spunta in un cerchio verde per indicare che il prerequisito è soddisfatto.  È disponibile un criterio di prevenzione della perdita dei dati preconfigurato per questo tenant del lab. Selezionare **Avanti**.
    1. Nome e descrizione: immettere un nome, **`SC900-InsiderRiskPolicy`**, quindi selezionare **Avanti**.
    1. Utenti e gruppi: esaminare la casella informazioni.  Lasciare l'impostazione predefinita, **Includi tutti gli utenti e i gruppi**.  Selezionare **Avanti**.
    1. Escludere utenti e gruppi (facoltativo): qui è possibile elencare utenti e gruppi da escludere. Non cambiare nulla. Selezionare **Avanti**.
    1. Contenuti a cui dare priorità: per ogni descrizione, i punteggi di rischio vengono aumentati per qualsiasi attività contenente contenuto prioritario, che a sua volta aumenta la possibilità di generare un avviso di gravità elevata. Per semplicità, selezionare **Non assegnare priorità al contenuto in questo momento** e quindi selezionare **Avanti**.
    1. Trigger: l'evento di attivazione determina quando un criterio inizierà ad assegnare punteggi di rischio all'attività di un utente.  È possibile scegliere un criterio DLP esistente o se l'utente esegue un'attività di esfiltrazione. Selezionare **Corrispondenza dell'utente con un criterio di prevenzione della perdita dei dati (DLP)** e quindi nell'elenco a discesa selezionare **Dati finanziari USA**. Selezionare **Avanti**.
    1. Indicatori: espandere **gli indicatori** di Office. Si noti che l'area indicatori di Office già selezionata si basa sulle impostazioni dell'attività precedente.  È possibile deselezionare alcuni indicatori selezionati o aggiungerne di nuovi selezionando Scegli indicatori. Per questo esercizio, lasciare le impostazioni correnti come e selezionare **Avanti**.
    1. Nella pagina Opzioni di rilevamento lasciare tutte le impostazioni predefinite, ma leggere la descrizione associata alle varie opzioni e passare il puntatore del mouse sull'icona delle informazioni per ottenere informazioni più dettagliate su un'impostazione specifica.  Selezionare **Avanti**.
    1. Nella pagina Decidere se usare le soglie predefinite o degli indicatori dei clienti lasciare l'impostazione predefinita **Applica soglie fornite da Microsoft**, quindi selezionare **Avanti**.
    1. Termine: esaminare le impostazioni, selezionare **Invia**.
    1. Esaminare la descrizione di ciò che accade successivamente, quindi selezionare **Fine**.

1. Si è di nuovo nella scheda Criteri della pagina Gestione dei rischi Insider.  Il criterio creato sarà incluso nell'elenco.  Se non è visualizzato, selezionare l'icona **Aggiorna**.

1. Gli amministratori possono iniziare immediatamente ad assegnare punteggi di rischio agli utenti in base all'attività rilevata dai criteri selezionati. In questo modo viene ignorato il requisito che prevede che venga prima rilevato un evento di attivazione, ad esempio una corrispondenza con criteri DLP.  A questo scopo, un amministratore dovrà selezionare il quadratino vuoto accanto al nome del criterio per selezionarlo e quindi selezionare l'opzione **Inizia calcolo punteggio attività per utenti**, disponibile sopra alla tabella dei criteri.  Verrà visualizzata una nuova finestra che richiede all'amministratore di popolare i campi disponibili. Lasciare vuoti i campi perché questa opzione non verrà configurata. Per altre informazioni sul motivo per cui un amministratore potrebbe voler eseguire questa operazione, selezionare **Perché eseguire questa operazione?**.  Chiudere la finestra selezionando la **X** nell'angolo in alto a destra della finestra.

1. Nel pannello di spostamento a sinistra selezionare **Home** per tornare alla pagina di destinazione del portale di Microsoft Purview.

1. Mantenere aperta la scheda del browser.

### Revisione

In questo lab, è stato descritto il processo di impostazione di un criterio di rischio Insider, insieme ai prerequisiti di base per configurare e usare i criteri di gestione dei rischi Insider.
