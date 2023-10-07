<!---
---
Lab: Titolo: 'Esplorare il flusso di lavoro di eDiscovery (Standard)' Percorso di apprendimento/Modulo/Unità: 'Percorso di apprendimento: Descrivere le funzionalità di conformità Microsoft; Modulo 5: Descrivere le funzionalità eDiscovery e di controllo di Microsoft Purview; Unità 2: Descrivere le soluzioni eDiscovery in Microsoft 365'
---
--->

# Laboratorio: Esplorare il flusso di lavoro di eDiscovery (Standard)

Questo lab corrisponde al contenuto di Learn seguente:

- Percorso di apprendimento: Descrivere le funzionalità di conformità Microsoft
- Modulo: Descrivere le funzionalità eDiscovery e di controllo di Microsoft Purview
- Unità: Descrivere le soluzioni eDiscovery in Microsoft Purview

## Scenario del lab

In questo lab verranno illustrati i passaggi necessari per configurare eDiscovery, tra cui la configurazione delle autorizzazioni per i ruoli, la creazione di un caso di eDiscovery, la creazione di un blocco di eDiscovery e la creazione di una query di ricerca.  Nota:  la licenza di eDiscovery (Standard) richiede che l'organizzazione disponga di un abbonamento appropriato e di licenze per ciascun utente. In caso di dubbi sulle licenze che supportano eDiscovery (Standard), vedere [Attività iniziali con eDiscovery (Standard) in Microsoft Purview](https://docs.microsoft.com/microsoft-365/compliance/get-started-core-ediscovery?view=o365-worldwide).

**Tempo stimato**: 25-30 minuti

### Attività 1

Per accedere a eDiscovery (Standard) o essere aggiunti come membro di un caso di eDiscovery, a un utente devono essere assegnate le autorizzazioni appropriate. In questa attività, lo studente, in qualità di amministratore globale, aggiungerà specifici utenti come membri del gruppo di ruoli di eDiscovery Manager.

1. Aprire la scheda del browser per la home page di Microsoft Purview.  Se è stata chiusa in precedenza, aprire una scheda del browser e immettere **https://admin.microsoft.com**. Accedere con le credenziali di amministratore per il tenant di Microsoft 365 fornito dall'host del lab autorizzato (ALH). Nel riquadro di spostamento sinistro del interfaccia di amministrazione di Microsoft 365 selezionare **Mostra tutto** e quindi Selezionare **Conformità**.  Si apre una nuova pagina del browser alla pagina di benvenuto del portale di conformità di Microsoft Purview.  


1. Nel riquadro di spostamento a sinistra espandere (selezionare la freccia giù) **Ruoli & Ambiti** e quindi selezionare **Autorizzazioni**.

1. In Soluzioni Microsoft Purview selezionare **Ruoli**.

1. Nel campo di ricerca immettere **eDiscovery e** premere INVIO sulla tastiera.  Selezionare **Manager di eDiscovery**.

1. Selezionare **Modifica**.  Si noti che sono presenti due sottogruppi, eDiscovery Manager e amministratore di eDiscovery.  
    1. La pagina "Gestione eDiscovery" consente di aggiungere utenti al ruolo di manager di eDiscovery. Per questo lab verranno aggiunti membri al sottogruppo amministratore di eDiscovery, quindi selezionare **Avanti**.
    1. Nella pagina "Gestisci amministratore di eDiscovery" selezionare **Scegli utenti** . Cercare e selezionare **Amministratore MOD** e **Megan Bowen** , quindi premere **Seleziona** nella parte inferiore della pagina, quindi selezionare **Avanti** e quindi **Salva**.
    1. Nella pagina "Il gruppo di ruoli è stato aggiornato correttamente", selezionare **Fine**.

1. Mantenere la scheda del browser aperta perché verrà usata nell'attività successiva.

### Attività 2

In questa attività, lo studente, in qualità di Amministratore di eDiscovery (l'amministratore MOD è un amministratore di eDiscovery), creerà un caso per iniziare a utilizzare eDiscovery (Standard).

1. Dovrebbe essere ancora visualizzata la pagina Ruoli del portale di conformità. Se la scheda del browser è stata chiusa dall'attività precedente, aprire una nuova scheda del browser e immettere **compliance.microsoft.com**

1. Nel pannello di spostamento a sinistra, in Soluzioni espandere **eDiscovery** e quindi selezionare **Standard**.

1. Nella parte superiore della pagina eDiscovery (Standard), selezionare **+ Crea un caso**.

1. Nella finestra Nuovo caso, immettere un nome per il caso, **SC900 Caso di test**, quindi selezionare **Salva** in basso sulla pagina.

1. Il caso ora dovrebbe comparire nell'elenco.

1. In quanto creatore del caso e in possesso dei privilegi di Amministratore di eDiscovery, lo studente può ora iniziare a lavorare su di esso.  

1. Lasciare aperta questa scheda del browser, perché verrà usata nell'attività successiva.

### Attività 3

Ora che è stato creato un caso di eDiscovery (Standard), si può iniziare a lavorare su di esso.  In questa attività, lo studente creerà un blocco di eDiscovery per il caso creato.  Nello specifico, si dovrà creare un blocco per la cassetta postale di Exchange che appartiene ad Adele Vance.

1. Aprire la scheda eDiscovery (Standard) nel browser.

1. Dalla pagina eDiscovery (Standard), selezionare il caso creato nella scheda precedente, **SC900 Caso di test**.

1. Dalla Home page del caso, selezionare la scheda **Blocco**, quindi selezionare **+Crea**.

1. Nel campo del nome immettere **Blocco di test** e quindi selezionare **Avanti**.

1. Nella pagina Scegli posizioni, selezionare l'interruttore accanto a **Cassette postali Exchange** per impostare lo stato su **Attivata**.  

1. Selezionare ora **Scegli utenti, gruppi o team**.  Nella casella di ricerca, immettere **Adele**, quindi premere Invio sulla tastiera. Nei risultati della ricerca selezionare **Adele Vance** e quindi selezionare **Fatto**.

1. Nella pagina Scegli posizioni, selezionare **Avanti**.  Per non prolungare l'attività del lab, nel blocco non verranno incluse altre posizioni.

1. La pagina Condizioni della query consente di creare un blocco basato su specifiche parole chiave o condizioni che devono essere soddisfatte. Selezionare **+ Aggiungi condizione** per visualizzare le opzioni disponibili.  Selezionare **Avanti**. Se non si specificano condizioni, il blocco conserverà tutto il contenuto nella posizione specificata.

1. Verificare le impostazioni e selezionare **Invia**, l'invio potrebbe richiedere un minuto, quindi selezionare **Fatto**.  Il blocco di test ora dovrebbe comparire nell'elenco.  Se non viene visualizzata immediatamente, selezionare **Aggiorna**

1. Lasciare aperta questa scheda del browser, perché verrà usata nell'attività successiva.

### Attività 4

Una volta creato il blocco, occorre creare una query di ricerca.  Al termine della ricerca, eDiscovery supporta azioni, ad esempio l'esportazione e il download dei risultati per indagini successive.   Nota:  Le ricerche associate a un caso di eDiscovery (Standard) non sono elencate nella pagina Ricerca di contenuto del portale di conformità di Microsoft Purview. Queste ricerche sono elencate solo nella pagina Ricerche del caso di eDiscovery (Standard) associato.

1. Aprire la scheda SC900 Caso di test nel browser.

1. Nella pagina SC900 Caso di test selezionare **Ricerche**.

1. Nella pagina Ricerca, selezionare **+ Nuova ricerca**.

1. Nel campo Nome, immettere **Blocco di test – Ricerca vendite**, quindi selezionare **Avanti** in basso nella pagina.

1. Nella pagina Scegli posizioni selezionare **Posizioni con blocco** e deselezionare **Aggiungi il contenuto delle app per gli utenti locali**, perché l'ambiente lab non ha utenti locali, quindi selezionare **Avanti**.

1. La pagina Condizioni della Query permette di creare una ricerca basata su specifiche parole chiave o condizioni che devono essere soddisfatte; nel campo della parola chiave immettere **Vendite**, quindi selezionare **Avanti**.

1. Verificare le impostazioni e selezionare **Invia**, l'invio potrebbe richiedere un minuto, quindi selezionare **Fatto**.  la ricerca ora dovrebbe comparire nell'elenco.  Se non viene visualizzata immediatamente, selezionare **Aggiorna**

1. Nella finestra Ricerche selezionare la ricerca appena creata, **Blocco di test - Ricerca vendite**.  Viene visualizzata una finestra con la scheda Riepilogo selezionata.  Una volta eseguita la ricerca, lo stato ne indica il completamento.  Verrà visualizzata la scheda Statistiche ricerca (se la scheda Statistiche ricerca non compare, significa che la ricerca è in corso e richiede ancora qualche minuto per essere completata).  Selezionare la scheda **Statistiche ricerca** e selezionare l'elenco a discesa accanto a Contenuti ricerca.  Si possono visualizzare anche altre informazioni per Scheda condizione e Posizioni principali.  

1. In basso sulla pagina, selezionare **Azioni**.  Si notino le opzioni disponibili che includono le opzioni di esportazione (le opzioni di esportazione non possono essere selezionate dall'interno della piattaforma lab fornita dal provider di servizi di hosting per i lab autorizzato, ma sono disponibili in un ambiente di produzione e sono considerate parte del flusso di lavoro standard). Selezionare **Chiudi**.

1. Disconnettersi e chiudere tutte le finestre del browser aperte.

### Verifica

In questo lab sono stati eseguiti i passaggi necessari per iniziare a usare eDiscovery (Standard), incluse l'impostazione delle autorizzazioni per i ruoli di eDiscovery e la creazione di un caso di eDiscovery.  Dopo aver creato il caso sono stati presentati gli elementi del flusso di lavoro di eDiscovery (Standard), creando un blocco di eDiscovery e una query di ricerca.
