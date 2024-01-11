<!---
---
Demo: Titolo: "Esplorare il flusso di lavoro di eDiscovery (Standard)" Percorso di apprendimento/Modulo/Unità: "Percorso di apprendimento: Descrivere le funzionalità di conformità Microsoft; Modulo 5: Descrivere le funzionalità eDiscovery e di controllo di Microsoft Purview; Unità 2: Descrivere le soluzioni eDiscovery in Microsoft 365"
---
--->

# Demo: esplorare il flusso di lavoro di eDiscovery (Standard)

Questa demo corrisponde al contenuto di Learn seguente:

- Percorso di apprendimento: Descrivere le funzionalità di conformità Microsoft
- Modulo: Descrivere le funzionalità eDiscovery e di controllo di Microsoft Purview
- Unità: Descrivere le soluzioni eDiscovery in Microsoft Purview

## Scenario dimostrativo

In questa demo verranno illustrati i passaggi necessari per configurare eDiscovery, tra cui la configurazione delle autorizzazioni per i ruoli, la creazione di un caso di eDiscovery, la creazione di un blocco di eDiscovery e la creazione di una query di ricerca.  Le licenze per eDiscovery (Standard) richiedono un abbonamento dell'organizzazione appropriata e licenze per utente. In caso di dubbi sulle licenze che supportano eDiscovery (Standard), vedere [Attività iniziali con eDiscovery (Standard) in Microsoft Purview](https://docs.microsoft.com/microsoft-365/compliance/get-started-core-ediscovery?view=o365-worldwide).

### Demo parte 1

Per accedere a eDiscovery (Standard) o essere aggiunti come membro di un caso di eDiscovery, a un utente devono essere assegnate le autorizzazioni appropriate. In questa parte della demo, l'amministratore globale illustrerà il processo di aggiunta di utenti specifici come membri del gruppo di ruoli di eDiscovery Manager.

1. Aprire la scheda del browser sulla Home page di Microsoft Purview.  Se in precedenza è stata chiusa, aprire una scheda del browser e immettere **https://admin.microsoft.com**. Accedere con le credenziali di amministratore per il tenant di Microsoft 365 fornito tramite un provider di servizi di hosting per lab autorizzato (ALH). Dal riquadro di spostamento dell'interfaccia di amministrazione di Microsoft 365, selezionare **Mostra tutto**, quindi selezionare **Conformità**.  Si apre una nuova pagina del browser alla pagina di benvenuto del portale di conformità di Microsoft Purview.  

1. Nel riquadro di spostamento a sinistra, espandere (selezionando la freccia in giù) **Ruoli e ambiti** e selezionare **Autorizzazioni**.

1. Sotto le soluzioni Microsoft Purview, selezionare **Ruoli**.

1. Nel campo di ricerca immettere **eDiscovery** e quindi selezionare l'icona della ricerca (lente d'ingrandimento).  Selezionare **Manager di eDiscovery**.  Notare i ruoli nel gruppo di ruoli.

1. Seleziona **Modifica**.  Notare che ci sono due sottogruppi, Manager di eDiscovery e Amministratore di eDiscovery.  
    1. La pagina "Gestisci Manager di eDiscovery" consente di aggiungere utenti al ruolo di Manager di eDiscovery. Per questa prima demo, verranno aggiunti membri al sottogruppo Amministratore di eDiscovery, quindi selezionare **Avanti**.
    1. Nella pagina "Gestisci Amministratore di eDiscovery", selezionare **Scegli utenti**. Cercare e selezionare **Amministratore MOD** e **Megan Bowen**, quindi premere **Seleziona** nella parte inferiore della pagina, quindi selezionare **Avanti** e **Salva**.
    1. Nella pagina "Il gruppo di ruoli è stato aggiornato correttamente", selezionare **Fine**.

1. Mantenere aperta la scheda del browser.

### Demo parte 2

In questa parte, lo studente, in qualità di Amministratore di eDiscovery (l'amministratore MOD è un amministratore di eDiscovery), creerà un caso per iniziare a utilizzare eDiscovery (Standard).

1. Dovrebbe essere ancora visualizzata la pagina Ruoli del portale di conformità. Dal riquadro di spostamento a sinistra, in Soluzioni, selezionare **eDiscovery** e quindi selezionare **Standard**.

1. Nella parte superiore della pagina eDiscovery (Standard), selezionare **+ Crea un caso**.

1. Nella finestra Nuovo caso, immettere il nome del caso, **SC900 Caso di test** e selezionare **Salva** in fondo alla pagina.

1. Il caso dovrebbe ora apparire nell'elenco.

1. In qualità di autore del caso e grazie ai privilegi di amministratore di eDiscovery, è possibile iniziare a utilizzare il caso.  

1. Mantenere aperta la scheda del browser.

### Demo parte 3

Ora che è stato creato un caso di eDiscovery (Standard), si può iniziare a lavorare su di esso.  In questa parte, lo studente creerà un blocco di eDiscovery per il caso creato.  Nello specifico, si dovrà creare un blocco per la cassetta postale di Exchange che appartiene ad Adele Vance.

1. Dalla pagina eDiscovery (Standard), selezionare il caso creato: **SC900 Caso di test**.

1. Dalla pagina iniziale del caso, selezionare la scheda **Blocco**, quindi selezionare **+Crea**.

1. Nel campo del nome immettere **Blocco di test** e quindi selezionare **Avanti**.

1. Nella pagina Scegli posizioni, selezionare l'interruttore accanto a **Cassette postali Exchange** per impostare lo stato su **Attivata**.  

1. Selezionare ora **Scegli utenti, gruppi o team**.  Nella casella di ricerca, immettere **Adele**, quindi premere INVIO sulla tastiera. Nei risultati della ricerca selezionare **Adele Vance** e quindi selezionare **Fatto**.

1. Nella pagina Scegli posizioni, selezionare **Avanti**.  Per motivi di praticità con la demo, non saranno incluse altre posizioni in questo blocco.

1. La pagina Condizioni della query consente di creare un blocco basato su specifiche parole chiave o condizioni che devono essere soddisfatte. Selezionare **+ Aggiungi condizione** per visualizzare le opzioni disponibili.  Seleziona **Avanti**. Senza alcuna condizione, il blocco conserva tutti i contenuti nella posizione specificata.

1. Esaminare le impostazioni e selezionare **Invia**; potrebbe essere necessario qualche minuto, quindi selezionare **Fine**.  Il blocco della prova dovrebbe apparire nell'elenco.  Se non viene visualizzato immediatamente, selezionare **Aggiorna**.

1. Mantenere aperta la scheda del browser.

### Demo parte 4

Una volta creato il blocco, occorre creare una query di ricerca.  Al termine della ricerca, eDiscovery supporta azioni, ad esempio l'esportazione e il download dei risultati per indagini successive.   Nota: le ricerche associate a un caso di eDiscovery (Standard) non sono elencate nella pagina Ricerca di contenuto del portale di conformità di Microsoft Purview. Queste ricerche sono elencate solo nella pagina Ricerche del caso di eDiscovery (Standard) associato.

1. Nella pagina SC900 Caso di test selezionare **Ricerche**.

1. Dalla pagina Ricerca, selezionare **+ Nuova ricerca**.

1. Nel campo Nome, immettere **Blocco test – Ricerca vendite** e quindi selezionare **Avanti** nella parte inferiore della pagina.

1. Nella pagina Scegli posizioni selezionare **Posizioni con blocco** e deselezionare **Aggiungi il contenuto delle app per gli utenti locali**, perché l'ambiente lab non ha utenti locali, quindi selezionare **Avanti**.

1. La pagina Condizioni query consente di creare una ricerca, in base a parole chiave o condizioni specifiche soddisfatte. Nel campo parola chiave immettere **Vendite** e selezionare **Avanti**.

1. Esaminare le impostazioni e selezionare **Invia**; potrebbe essere necessario qualche minuto, quindi selezionare **Fine**.  La ricerca dovrebbe essere visualizzata nell'elenco.  Se non viene visualizzato immediatamente, selezionare **Aggiorna**.

1. Nella finestra Ricerche selezionare la ricerca appena creata, **Blocco di test - Ricerca vendite**.  Finestra visualizzata con la scheda Riepilogo selezionata.  Una volta eseguita la ricerca, lo stato ne indica il completamento.  Verrà visualizzata la scheda Statistiche ricerca (se la scheda Statistiche ricerca non compare, significa che la ricerca è in corso e richiede ancora qualche minuto per essere completata).  Selezionare la scheda **Cerca statistiche** e selezionare la freccia rivolta verso il basso, accanto a Cerca contenuto.  È possibile visualizzare anche altre informazioni relative al report Condizione e alle posizioni principali.  

1. Nella parte inferiore della pagina, selezionare **Azioni**.  Notare le opzioni disponibili che includono quelle di esportazione. Selezionare **Chiudi**.

1. Chiudere tutte le schede del browser aperte.

### Revisione

In questa demo sono stati eseguiti i passaggi necessari per iniziare a utilizzare eDiscovery (Standard), incluse l'impostazione delle autorizzazioni per i ruoli di eDiscovery e la creazione di un caso di eDiscovery.  Dopo aver creato il caso sono stati presentati gli elementi del flusso di lavoro di eDiscovery (Standard), creando un blocco di eDiscovery e una query di ricerca.
