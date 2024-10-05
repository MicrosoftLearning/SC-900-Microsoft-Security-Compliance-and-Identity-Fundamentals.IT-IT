<!---
---
Demo: Title: 'The Microsoft Defender portal' Module: 'Learning Path: Describe the capabilities of Microsoft security solutions; Modulo 4: Descrivere le funzionalità di protezione dalle minacce di Microsoft Defender XDR; Unità 7: Descrivere il portale di Microsoft Defender
---
--->

# Demo: Portale di Microsoft Defender

Questa demo corrisponde al contenuto di Learn seguente:

- Percorso di apprendimento: Descrivere le funzionalità delle soluzioni di sicurezza Microsoft
- Modulo: Descrivere le funzionalità di protezione dalle minacce di Microsoft Defender XDR
- Unità: Descrivere il portale di Microsoft Defender

## Scenario dimostrativo

In questa demo verrà visualizzato il portale di Microsoft Defender esaminando il contenuto visualizzato nella pagina di destinazione. Verranno inoltre esplorate le opzioni nel riquadro di spostamento che forniscono accesso rapido a funzionalità che fanno parte della soluzione di rilevamento e risposta estesi (XDR, Extended Detection and Response) di Microsoft: Microsoft Defender per endpoint e Microsoft Defender per Office 365 (posta elettronica e collaborazione).  Infine, si vedrà anche come Microsoft Secure Score può aiutare un'organizzazione a migliorare la sua postura di sicurezza.

### Demo parte 1

Esplorare la pagina di destinazione di Microsoft Defender.

1. Aprire la scheda del browser per la home page di Microsoft Defender.  Se il browser è stato chiuso in precedenza, aprire Microsoft Edge. Nella barra degli indirizzi, digitare **https://admin.microsoft.com** e accedere con le credenziali di amministrazione del tenant Microsoft 365 fornite dall'ALH (provider di servizi di hosting per i lab autorizzato), per accedere all'interfaccia di amministrazione di Microsoft 365. Nel riquadro di spostamento a sinistra dell'interfaccia di amministrazione di Microsoft 365, selezionare **Mostra tutti**, quindi **Sicurezza**.  Viene aperta una nuova pagina del browser nella pagina iniziale del portale di Microsoft Defender.  

1. La home page del portale di Microsoft Defender mostra molte delle schede comuni necessarie ai team di sicurezza. La composizione delle schede e dei dati dipende dal ruolo dell'utente. Scorrere la pagina per visualizzare il set di schede predefinito per il proprio ruolo di amministratore globale.

1. Le schede visualizzate possono essere personalizzate in base alle proprie preferenze.  Selezionare **+ Aggiungi schede**. Verrà visualizzata una finestra che mostra le schede disponibili per essere aggiunte alla pagina iniziale.  È possibile che siano già state visualizzate tutte le schede, in questo caso verrà visualizzata la nota "Nella pagina iniziale sono già presenti tutte le schede". Chiudere la finestra selezionando la **X** nell'angolo superiore a destra della finestra.

1. Selezionando i puntini di sospensione in alto a destra di qualsiasi scheda sarà possibile rimuovere la scheda dalla pagina di destinazione.  

1. È anche possibile spostare le schede. Passando il cursore del mouse sulla barra del titolo di qualsiasi scheda, quando il cursore assume la forma di una croce, selezionare la scheda e spostarla nella posizione desiderata.  

1. Alcune schede hanno pulsanti nella parte inferiore della scheda selezionabili. Il titolo di alcune schede funge da collegamento alla pagina per tale argomento.  Ad esempio, se si seleziona il titolo della scheda Microsoft Secure Score, verrà visualizzata la pagina Microsoft Secure Score.  Altre informazioni su Microsoft Secure Score verranno esaminate in una sezione successiva di questa demo.

1. Tenere aperta la finestra del browser.

### Demo parte 2

In questa parte della demo verranno esaminate alcune delle opzioni disponibili nel pannello di spostamento a sinistra del portale di Defender.  Tramite il portale di Microsoft Defender, Microsoft offre la promessa di una piattaforma unificata per le operazioni di sicurezza. Il portale Microsoft Defender combina le funzionalità di protezione, rilevamento, indagine e risposta alle minacce nell'intera organizzazione e in tutti i relativi componenti in un'unica posizione centralizzata. Include l'accesso rapido alle soluzioni Microsoft Defender XDR, tra cui Microsoft Defender per endpoint, Defender per Office per 365, app Microsoft Defender per il cloud e altro ancora.  Esplorare queste opzioni selezionando alcuni dei collegamenti.   Per tornare alla home page del portale di Microsoft Defender, selezionare **Home** nel pannello di spostamento a sinistra.

**NOTA: lo scopo è esaminare alcune delle opzioni nel pannello di spostamento, non è destinato a una demo completa di tutte le opzioni**.

1. **** Gestione dell'esposizione: le opzioni elencate offrono una visualizzazione unificata del comportamento di sicurezza tra asset e carichi di lavoro aziendali.
    1. **Superficie** di attacco: è possibile visualizzare la mappa della superficie di attacco per l'organizzazione. I percorsi di attacco generano automaticamente percorsi di attacco in base ai dati raccolti tra asset e carichi di lavoro. Simula scenari di attacco e identifica vulnerabilità e punti deboli che un utente malintenzionato potrebbe sfruttare.
    1. **Informazioni dettagliate sulla sicurezza: informazioni dettagliate** sull'esposizione in Microsoft Security Exposure Management aggregano continuamente i dati sul comportamento di sicurezza e le informazioni dettagliate tra carichi di lavoro e risorse in una singola pipeline.
    1. **Punteggio di sicurezza: il punteggio** di sicurezza fornisce una suddivisione del punteggio, le azioni di miglioramento che possono aumentare il punteggio dell'organizzazione e il livello di confronto tra il punteggio di sicurezza dell'organizzazione e altre organizzazioni simili.
    1. **Connettori** dati: consente di connettere le origini dati per un'esperienza di gestione dell'esposizione più completa e centralizzata.
1. **Indagine e risposta** : da qui vedrai diverse opzioni:
    1. **Eventi imprevisti e avvisi**: da qui è possibile visualizzare gli eventi imprevisti o i singoli avvisi delle diverse soluzioni XDR di Defender (Defender per identità, app Defender per il cloud, Defender per Office 365 e Defender per identità) e altre soluzioni Microsoft, tra cui Microsoft Sentinel, Microsoft Defender per il cloud, Microsoft Entra e Microsoft Purview.
    1. **Ricerca** : da qui è possibile creare regole di rilevamento personalizzate e cercare minacce specifiche nell'ambiente.
    1. **Azioni e invii**: il Centro notifiche unificato riunisce le azioni correttive in Microsoft Defender per endpoint e Microsoft Defender per Office 365. Elenca le azioni di correzione in sospeso e completate per i dispositivi, i contenuti di posta elettronica e collaborazione e le identità in un'unica posizione. Nelle organizzazioni Microsoft 365 con cassette postali di Exchange Online, gli amministratori possono usare la pagina Invii nel portale Microsoft Defender per inviare messaggi, URL e allegati a Microsoft per farli esaminare.
    1. **** Catalogo dei partner: il catalogo dei partner elenca i partner tecnologici supportati e i servizi professionali che consentono all'organizzazione di migliorare le funzionalità di rilevamento, indagine e intelligence sulle minacce della piattaforma.
1. **** Intelligence sulle minacce: dalla scheda Intelligence per le minacce gli utenti accedono a Microsoft Defender Threat Intelligence e alle funzionalità supportate dalla soluzione, tra cui Analisi delle minacce, profili intel, intel explorer e progetti Intel.
1. **Asset: la scheda Asset** consente di visualizzare e gestire l'inventario dell'organizzazione di asset protetti e individuati (dispositivi e identità).
1. **Microsoft Sentinel: alcune funzionalità di Microsoft Sentinel** sono disponibili nella sezione Microsoft Sentinel del portale di Defender.  Questa operazione richiede la configurazione dell'integrazione tramite la pagina Impostazioni.
1. **** Identità: il nodo Identità esegue il mapping alle funzionalità associate a Microsoft Defender per identità. Il dashboard fornisce informazioni dettagliate critiche e dati in tempo reale sul rilevamento e la risposta alle minacce per le identità (ITDR). La pagina Problemi di integrità elenca eventuali problemi di integrità correnti per la distribuzione e i sensori di Defender per identità, segnalando eventuali problemi rilevati nella distribuzione di Defender per identità. Nella pagina degli strumenti sono elencate informazioni aggiuntive che consentono di gestire l'ambiente di Microsoft Defender per identità.
1. **** Endpoint : nodo endpoint nel pannello di spostamento sinistro del portale di Microsoft Defender viene mappato alle funzionalità associate alle Microsoft Defender per endpoint.
    1. Gestione delle vulnerabilità: consente di gestire le vulnerabilità e altre origini di rischio nei dispositivi. Da qui è possibile accedere al dashboard di gestione delle vulnerabilità, alle raccomandazioni, al rimedio, ai punti deboli e altro ancora.
    1. Partner e API: da qui è possibile selezionare Applicazioni connesse ed Esplora API.
    1. Gestione della configurazione: qui è possibile visualizzare il dashboard gestione della configurazione del dispositivo.  È anche possibile definire i criteri degli endpoint e tenere traccia della distribuzione.
1. **Email & collaboration** : qui trovi Microsoft Defender per Office 365 funzionalità che consente di tenere traccia e analizzare le minacce alla posta elettronica degli utenti, tenere traccia delle campagne e altro ancora.
1. **App** cloud: qui è possibile trovare Microsoft Defender per il cloud funzionalità delle app. Per altre informazioni, vedere la demo sulle app Microsoft Defender per il cloud.
1. **Ottimizzazione** SOC: l'ottimizzazione SOC illustra i modi in cui è possibile ottimizzare i controlli di sicurezza, ottenendo più valore dai servizi di sicurezza Microsoft man mano che il tempo va avanti.
1. **Report** : i report vengono unificati nel portale di Microsoft Defender. Gli amministratori possono iniziare con un report della sicurezza generale e passare a report specifici sugli endpoint, la posta elettronica e la collaborazione, le app cloud, l'infrastruttura e le identità. I collegamenti disponibili qui vengono generati dinamicamente in base alla configurazione del carico di lavoro.
1. **Hub Leraning: l'hub** di apprendimento collega Microsoft Learn in cui è possibile accedere a corsi di formazione, esercitazioni, documentazione e altro materiale pertinente.
1. **Sistema** : include le selezioni per configurare le autorizzazioni, visualizzare l'integrità dei servizi e le impostazioni generali.
    1. Autorizzazioni: qui è possibile assegnare le autorizzazioni di ruolo per le diverse soluzioni XDR di Microsoft Defender.
    1. Impostazioni: qui si configurano le impostazioni per il portale di Defender, Defender XDR, le soluzioni che fanno parte di Microsoft Defender XDR e Microsoft Sentinel.  Esplorare questi elementi come si vuole.
1. **Personalizza spostamento** : qui è possibile selezionare per mostrare o nascondere gli elementi nel riquadro di spostamento. Gli altri amministratori non visualizzeranno le modifiche apportate.

### Demo parte 3

Questa parte della demo mostrerà come Microsoft Secure Score può aiutare un'organizzazione a migliorare la sua postura di sicurezza.

1. Nel pannello di spostamento a sinistra espandere **Gestione dell'esposizione** e quindi selezionare **Punteggio** di sicurezza.

1. La pagina Microsoft Secure Score viene aperta nella scheda Panoramica. Microsoft Secure Score è una misurazione della postura di sicurezza di un'organizzazione. Il punteggio di sicurezza dell'organizzazione è mostrato come percentuale, insieme al numero di punti raggiunti rispetto al totale dei punti possibili e suddiviso per categoria. Selezionare **Includi** accanto alla posizione in cui è indicato Il punteggio di sicurezza. Per la visualizzazione del punteggio, è possibile scegliere di includere il punteggio realizzabile, il punteggio pianificato e il punteggio della licenza corrente.

1. La pagina di panoramica include anche le azioni consigliate principali, il punteggio di confronto, la cronologia e le risorse.

1. Selezionare **Azioni consigliate** nella parte superiore della pagina.  Notare le informazioni disponibili per ogni elemento della tabella.  

1. Selezionare il primo elemento dall'elenco ed esaminare le informazioni disponibili. Nella finestra visualizzata notare le opzioni di stato disponibili. Selezionare la scheda **Implementazione** per visualizzare le informazioni correlate all'implementazione. Selezionare la **X** nell'angolo in alto a destra per chiudere questa finestra.

1. Selezionare la scheda **Cronologia** nella parte superiore della pagina.  Per ogni attività elencata è presente una breve istruzione che ne fornisce il contesto.  Selezionare una voce nella tabella della cronologia.  Nella parte superiore a destra della pagina Dettagli, in Cronologia, selezionare **Eventi X** (dove X è un numero).  Viene aperta la finestra della cronologia delle azioni con ulteriori informazioni.  Per tornare alla pagina Cronologia, selezionare **Chiudi** nella parte inferiore della pagina, quindi selezionare la **X** nell'angolo in alto a destra della pagina Dettagli.

1. Nella parte superiore della pagina, selezionare **Metriche e tendenze**.  Notare le informazioni disponibili.  Dall'angolo in alto a destra della pagina, selezionare l'**icona calendario**.  È possibile restringere la visualizzazione a un intervallo di date personalizzato.  Selezionando l'**icona del filtro** è possibile filtrare la visualizzazione per identità, dispositivi e/o app.  Selezionare Chiudi per chiudere la finestra.

1. Nel pannello di spostamento a sinistra selezionare **Home** nella home page di Microsoft Defender.

1. Se si prevede di continuare con la demo successiva, mantenere aperta la scheda del browser.

### Revisione

In questa demo è stato esplorato il portale di Microsoft Defender esaminando il contenuto visualizzato nella pagina di destinazione, sono state esaminate le opzioni nel pannello di spostamento che fornisce un accesso rapido alle funzionalità che fanno parte di Microsoft Defender XDR.  Infine, è stato illustrato come Microsoft Secure Score può aiutare un'organizzazione a migliorare il proprio comportamento di sicurezza.
