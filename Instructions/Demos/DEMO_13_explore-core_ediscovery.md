<!---
---
Demo: Title: 'Explore the eDiscovery workflow' Learning Path/Module/Unit: 'Learning Path: Describe the capabilities of the Microsoft Priva and Microsoft Purview; Modulo 3: Descrivere le soluzioni di conformità dei dati di Microsoft Purview; Unità 2: Descrivere eDiscovery'
---
--->

# Demo: esplorare il flusso di lavoro di eDiscovery (Standard)

Questa demo corrisponde al contenuto di Learn seguente:

- Percorso di apprendimento: Descrivere le funzionalità di Microsoft Priva e Microsoft Purview
- Modulo: Descrivere le soluzioni di conformità dei dati di Microsoft Purview
- Unità: Descrivere eDiscovery

## Scenario dimostrativo

In questa demo verranno illustrati i passaggi necessari per configurare eDiscovery, tra cui la configurazione delle autorizzazioni per i ruoli, la creazione di un caso di eDiscovery, la creazione di un blocco di eDiscovery e la creazione di una query di ricerca.  NOTA: gli aggiornamenti dell'interfaccia utente vengono eseguiti gradualmente nel portale di Microsoft Purview. Alcuni tenant lab/demo potrebbero non visualizzare ancora l'interfaccia utente più recente, quindi tutti i passaggi del lab vengono visualizzati usando l'interfaccia utente classica di eDiscovery.

### Demo parte 1

Per accedere a eDiscovery (Standard) o essere aggiunti come membro di un caso di eDiscovery, a un utente devono essere assegnate le autorizzazioni appropriate. In questa parte della demo, l'amministratore globale illustrerà il processo di aggiunta di utenti specifici come membri del gruppo di ruoli di eDiscovery Manager.

1. Aprire la scheda del browser per **Microsoft Purview**. Se è stata chiusa in precedenza, aprire una scheda del browser e nella barra degli indirizzi immettere **https://purview.microsoft.com**. Per accedere al nuovo portale di Microsoft Purview, selezionare la casella accanto alla posizione in cui è indicato, **accetto le condizioni per la divulgazione del flusso di dati e le informative** sulla privacy, quindi selezionare **Inizia**.  
1. Nel pannello di spostamento a sinistra selezionare **Impostazioni**.
1. Nel pannello di spostamento visualizzato selezionare **Ruoli e con ambito** per espandere l'opzione e quindi selezionare **Gruppi di ruoli**.
1. Nella casella di ricerca sul lato destro della schermata cercare il termine **eDiscovery**.  Selezionare **Manager di eDiscovery**.
    1. Seleziona **Modifica**
    1. Selezionare **Scegli utenti**.
    1. Cercare Amministratore MOD, selezionare la casella accanto a **Amministratore MOD** e quindi selezionare il **pulsante Seleziona** nella parte inferiore della pagina.
    1. Selezionare Avanti e quindi Salva** e infine Fine****.** ****

1. Mantenere aperta la scheda del browser.

### Demo parte 2

In questa parte verrà creato un caso per iniziare a usare eDiscovery (Standard).

1. Nel pannello di spostamento a sinistra selezionare **Soluzioni**, selezionare **eDiscovery** e quindi Casi **standard**.

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

1. La pagina Condizioni della query consente di creare un blocco basato su specifiche parole chiave o condizioni che devono essere soddisfatte. Selezionare **+ Aggiungi condizione** per visualizzare le opzioni disponibili.  Selezionare **Avanti**. Senza alcuna condizione, il blocco conserva tutti i contenuti nella posizione specificata.

1. Esaminare le impostazioni e selezionare **Invia**; potrebbe essere necessario qualche minuto, quindi selezionare **Fine**.  Il blocco della prova dovrebbe apparire nell'elenco.  Se non viene visualizzato immediatamente, selezionare **Aggiorna**.

1. Mantenere aperta la scheda del browser.

### Demo parte 4

Una volta creato il blocco, occorre creare una query di ricerca.  Al termine della ricerca, eDiscovery supporta azioni, ad esempio l'esportazione e il download dei risultati per indagini successive.   Nota: le ricerche associate a un caso di eDiscovery (Standard) non sono elencate nella pagina Ricerca di contenuto del portale di conformità di Microsoft Purview. Queste ricerche sono elencate solo nella pagina Ricerche del caso di eDiscovery (Standard) associato.

1. Nella pagina SC900 Caso di test selezionare **Ricerche**.

1. Dalla pagina Ricerca, selezionare **+ Nuova ricerca**.

1. Nel campo Nome, immettere **Blocco test – Ricerca vendite** e quindi selezionare **Avanti** nella parte inferiore della pagina.

1. Nella pagina Scegli posizioni selezionare **le posizioni in attesa** e deselezionare **Aggiungi contenuto app per gli utenti** locali, in quanto l'ambiente lab non ha utenti locali, quindi selezionare **Avanti**.

1. La pagina Condizioni query consente di creare una ricerca, in base a parole chiave o condizioni specifiche soddisfatte. Nel campo parola chiave immettere **Vendite** e selezionare **Avanti**.

1. Esaminare le impostazioni e selezionare **Invia**; potrebbe essere necessario qualche minuto, quindi selezionare **Fine**.  La ricerca dovrebbe essere visualizzata nell'elenco.  Se non viene visualizzato immediatamente, selezionare **Aggiorna**.

1. Nella finestra Ricerche selezionare la ricerca appena creata, **Blocco di test - Ricerca vendite**.  Finestra visualizzata con la scheda Riepilogo selezionata.  Una volta eseguita la ricerca, lo stato ne indica il completamento.  Verrà visualizzata la scheda Statistiche ricerca (se la scheda Statistiche ricerca non compare, significa che la ricerca è in corso e richiede ancora qualche minuto per essere completata).  Selezionare la scheda **Cerca statistiche** e selezionare la freccia rivolta verso il basso, accanto a Cerca contenuto.  È possibile visualizzare anche altre informazioni relative al report Condizione e alle posizioni principali.  

1. Nella parte inferiore della pagina, selezionare **Azioni**.  Notare le opzioni disponibili che includono quelle di esportazione. Selezionare **Chiudi**.

1. Chiudere tutte le schede del browser aperte.

### Revisione

In questa demo sono stati eseguiti i passaggi necessari per iniziare a utilizzare eDiscovery (Standard), incluse l'impostazione delle autorizzazioni per i ruoli di eDiscovery e la creazione di un caso di eDiscovery.  Dopo aver creato il caso sono stati presentati gli elementi del flusso di lavoro di eDiscovery (Standard), creando un blocco di eDiscovery e una query di ricerca.
