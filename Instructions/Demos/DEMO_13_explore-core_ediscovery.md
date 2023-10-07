<!---
---
Demo: Titolo: "Esplora il flusso di lavoro eDiscovery (Standard)" Percorso di apprendimento/Modulo/Unità: "Percorso di apprendimento: Descrivere le funzionalità della conformità Microsoft; Modulo 5: Descrivere le funzionalità di controllo eDiscovery di Microsoft Purview; Unità 2: Descrivere le soluzioni eDiscovery in Microsoft 365'
---
--->

# Demo: Esplorare il flusso di lavoro eDiscovery (Standard)

Questa demo corrisponde al contenuto di Learn seguente:

- Percorso di apprendimento: Descrivere le funzionalità di conformità Microsoft
- Modulo: Descrivere le funzionalità eDiscovery e di controllo di Microsoft Purview
- Unità: Descrivere le soluzioni eDiscovery in Microsoft Purview

## Scenario demo

In questa demo verrà eseguita una procedura dettagliata dei passaggi necessari per configurare eDiscovery, tra cui la configurazione delle autorizzazioni per il ruolo, la creazione di un caso eDiscovery, la creazione di un blocco eDiscovery e la creazione di una query di ricerca.  Nota:  la licenza di eDiscovery (Standard) richiede che l'organizzazione disponga di un abbonamento appropriato e di licenze per ciascun utente. In caso di dubbi sulle licenze che supportano eDiscovery (Standard), vedere [Attività iniziali con eDiscovery (Standard) in Microsoft Purview](https://docs.microsoft.com/microsoft-365/compliance/get-started-core-ediscovery?view=o365-worldwide).

### Demo parte 1

Per accedere a eDiscovery (Standard) o essere aggiunti come membro di un caso di eDiscovery, a un utente devono essere assegnate le autorizzazioni appropriate. In questa parte della demo, l'amministratore globale illustra il processo di aggiunta di utenti specifici come membri del gruppo di ruoli eDiscovery Manager.

1. Aprire la scheda browser per la home page di Microsoft Purview.  Se è stata chiusa in precedenza, aprire una scheda del browser e immettere **https://admin.microsoft.com**. Accedere con le credenziali di amministratore per il tenant di Microsoft 365 fornito dall'hoster del lab autorizzato (ALH). Nel riquadro di spostamento a sinistra della interfaccia di amministrazione di Microsoft 365 selezionare **Mostra tutto** e quindi selezionare **Conformità**.  Si apre una nuova pagina del browser alla pagina di benvenuto del portale di conformità di Microsoft Purview.  

1. Nel riquadro di spostamento a sinistra espandere (selezionare la freccia giù) **Ruoli & Ambiti** e quindi selezionare **Autorizzazioni**.

1. In Soluzioni Microsoft Purview selezionare **Ruoli**.

1. Nel campo di ricerca immettere **eDiscovery** e quindi selezionare l'icona della ricerca (lente d'ingrandimento).  Selezionare **Manager di eDiscovery**.  Si notino i ruoli nel gruppo di ruoli.

1. Selezionare **Modifica**.  Si noti come sono presenti due sottogruppi, eDiscovery Manager e Amministratore eDiscovery.  
    1. La pagina "Gestisci eDiscovery Manager" consente di aggiungere utenti al ruolo di gestione eDiscovery. Per questa demo si aggiungeranno membri al sottogruppo amministratore eDiscovery, quindi selezionare **Avanti**.
    1. Nella pagina "Gestisci amministratore eDiscovery" selezionare **Scegli utenti** . Cercare e selezionare **Amministratore MOD** e **Megan Bowen** e quindi premere **Seleziona** nella parte inferiore della pagina, quindi selezionare **Avanti** e quindi **Salva**.
    1. Nella pagina "È stato aggiornato correttamente il gruppo di ruoli" selezionare **Fine**.

1. Mantenere aperta la scheda del browser.

### Demo parte 2

In questa parte, come amministratore di eDiscovery (amministratore MOD è un amministratore di eDiscovery), creerà un caso per iniziare a usare eDiscovery (Standard).

1. Dovrebbe essere ancora visualizzata la pagina Ruoli del portale di conformità. Dal riquadro di spostamento a sinistra, in Soluzioni, selezionare **eDiscovery** e quindi selezionare **Standard**.

1. Nella parte superiore della pagina eDiscovery (Standard), selezionare **+ Crea un caso**.

1. Nella finestra Nuovo caso, immettere un nome per il caso, **SC900 Caso di test**, quindi selezionare **Salva** in basso sulla pagina.

1. Il caso ora dovrebbe comparire nell'elenco.

1. In quanto creatore del caso e in possesso dei privilegi di Amministratore di eDiscovery, lo studente può ora iniziare a lavorare su di esso.  

1. Mantenere aperta la scheda del browser.

### Demo parte 3

Ora che è stato creato un caso di eDiscovery (Standard), si può iniziare a lavorare su di esso.  In questa parte si creerà un blocco eDiscovery per il caso creato.  Nello specifico, si dovrà creare un blocco per la cassetta postale di Exchange che appartiene ad Adele Vance.

1. Nella pagina eDiscovery (Standard) selezionare il caso creato - **SC900 Test Case**.

1. Dalla Home page del caso, selezionare la scheda **Blocco**, quindi selezionare **+Crea**.

1. Nel campo del nome immettere **Blocco di test** e quindi selezionare **Avanti**.

1. Nella pagina Scegli posizioni, selezionare l'interruttore accanto a **Cassette postali Exchange** per impostare lo stato su **Attivata**.  

1. Selezionare ora **Scegli utenti, gruppi o team**.  Nella casella di ricerca, immettere **Adele**, quindi premere Invio sulla tastiera. Nei risultati della ricerca selezionare **Adele Vance** e quindi selezionare **Fatto**.

1. Nella pagina Scegli posizioni, selezionare **Avanti**.  Per la necessità di usare la demo, nessun'altra posizione verrà inclusa in questo blocco.

1. La pagina Condizioni della query consente di creare un blocco basato su specifiche parole chiave o condizioni che devono essere soddisfatte. Selezionare **+ Aggiungi condizione** per visualizzare le opzioni disponibili.  Selezionare **Avanti**. Se non si specificano condizioni, il blocco conserverà tutto il contenuto nella posizione specificata.

1. Verificare le impostazioni e selezionare **Invia**, l'invio potrebbe richiedere un minuto, quindi selezionare **Fatto**.  Il blocco di test ora dovrebbe comparire nell'elenco.  Se non viene visualizzata immediatamente, selezionare **Aggiorna**

1. Mantenere aperta la scheda del browser.

### Demo parte 4

Una volta creato il blocco, occorre creare una query di ricerca.  Al termine della ricerca, eDiscovery supporta azioni, ad esempio l'esportazione e il download dei risultati per indagini successive.   Nota:  Le ricerche associate a un caso di eDiscovery (Standard) non sono elencate nella pagina Ricerca di contenuto del portale di conformità di Microsoft Purview. Queste ricerche sono elencate solo nella pagina Ricerche del caso di eDiscovery (Standard) associato.

1. Nella pagina SC900 Caso di test selezionare **Ricerche**.

1. Nella pagina Ricerca, selezionare **+ Nuova ricerca**.

1. Nel campo Nome, immettere **Blocco di test – Ricerca vendite**, quindi selezionare **Avanti** in basso nella pagina.

1. Nella pagina Scegli posizioni selezionare **Posizioni con blocco** e deselezionare **Aggiungi il contenuto delle app per gli utenti locali**, perché l'ambiente lab non ha utenti locali, quindi selezionare **Avanti**.

1. La pagina Condizioni della Query permette di creare una ricerca basata su specifiche parole chiave o condizioni che devono essere soddisfatte; nel campo della parola chiave immettere **Vendite**, quindi selezionare **Avanti**.

1. Verificare le impostazioni e selezionare **Invia**, l'invio potrebbe richiedere un minuto, quindi selezionare **Fatto**.  la ricerca ora dovrebbe comparire nell'elenco.  Se non viene visualizzata immediatamente, selezionare **Aggiorna**

1. Nella finestra Ricerche selezionare la ricerca appena creata, **Blocco di test - Ricerca vendite**.  Viene visualizzata una finestra con la scheda Riepilogo selezionata.  Una volta eseguita la ricerca, lo stato ne indica il completamento.  Verrà visualizzata la scheda Statistiche ricerca (se la scheda Statistiche ricerca non compare, significa che la ricerca è in corso e richiede ancora qualche minuto per essere completata).  Selezionare la scheda **Statistiche di ricerca** e selezionare la freccia giù accanto al contenuto ricerca.  Si possono visualizzare anche altre informazioni per Scheda condizione e Posizioni principali.  

1. In basso sulla pagina, selezionare **Azioni**.  Si notino le opzioni disponibili che includono le opzioni di esportazione. Selezionare **Chiudi**.

1. Chiudere tutte le schede del browser aperte.

### Verifica

In questa demo sono stati illustrati i passaggi necessari per iniziare a usare eDiscovery (Standard), inclusa la configurazione delle autorizzazioni di ruolo per eDiscovery e la creazione di un caso eDiscovery.  Dopo aver creato il caso sono stati presentati gli elementi del flusso di lavoro di eDiscovery (Standard), creando un blocco di eDiscovery e una query di ricerca.
