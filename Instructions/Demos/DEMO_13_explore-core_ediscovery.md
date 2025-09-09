<!---
---
Demo: Title: 'Explore the eDiscovery' Learning Path/Module/Unit: 'Learning Path: Describe the capabilities of the Microsoft Priva and Microsoft Purview; Modulo 3: Descrivere le soluzioni di conformità dei dati di Microsoft Purview; Unità 2: Descrivere eDiscovery'
---
--->

# Demo: Esplorare eDiscovery (Standard)

Questa demo corrisponde al contenuto di Learn seguente:

- Percorso di apprendimento: Descrivere le funzionalità di Microsoft Priva e Microsoft Purview
- Modulo: Descrivere le soluzioni di conformità dei dati di Microsoft Purview
- Unità: Descrivere eDiscovery

## Scenario dimostrativo

In questa demo verranno illustrati i passaggi necessari per configurare eDiscovery, tra cui la configurazione delle autorizzazioni per i ruoli, la creazione di un caso di eDiscovery, la creazione di un blocco di eDiscovery e la creazione di una query di ricerca.  NOTA: gli aggiornamenti dell'interfaccia utente vengono eseguiti gradualmente nel portale di Microsoft Purview. Alcuni tenant lab/demo potrebbero non visualizzare ancora l'interfaccia utente più recente, quindi tutti i passaggi del lab vengono visualizzati usando l'interfaccia utente classica di eDiscovery.

### Demo parte 1

Per accedere a eDiscovery o essere aggiunti come membro di un caso eDiscovery, a un utente devono essere assegnate le autorizzazioni appropriate. In questa parte della demo, l'amministratore globale illustrerà il processo di aggiunta di utenti specifici come membri del gruppo di ruoli di eDiscovery Manager.

1. Aprire la scheda del browser per **Microsoft Purview**. Se è stata chiusa in precedenza, aprire una scheda del browser e nella barra degli indirizzi immettere **https://purview.microsoft.com** e quindi selezionare **Inizia.**  
1. Nel pannello di spostamento a sinistra selezionare **Impostazioni**.
1. Nel pannello di spostamento visualizzato selezionare **Ruoli e con ambito** per espandere l'opzione e quindi selezionare **Gruppi di ruoli**.
1. Nella casella di ricerca sul lato destro della schermata cercare il termine **eDiscovery**.  Selezionare **Manager di eDiscovery**.
    1. Seleziona **Modifica**
    1. Selezionare **Scegli utenti**.
    1. Cercare Amministratore MOD, selezionare la casella accanto a **Amministratore MOD** e quindi selezionare il **pulsante Seleziona** nella parte inferiore della pagina.
    1. Selezionare Avanti e quindi Salva** e infine Fine****.** ****

1. Mantenere aperta la scheda del browser.

### Demo parte 2

In questa parte, come amministratore di eDiscovery (amministratore MOD è un amministratore di eDiscovery), creerà un caso per iniziare a usare eDiscovery.

1. Dovrebbe trovarsi nella home page del portale di Microsoft Purview.

1. Nel pannello di spostamento a sinistra, in Soluzioni espandere **eDiscovery** e quindi selezionare **Casi**.

1. Nella pagina Casi selezionare **Crea caso**.

1. Nella finestra Nuovo caso immettere un nome case, **SC900 Test Case** e quindi selezionare Crea****.

1. Il caso dovrebbe ora apparire nell'elenco.

1. In qualità di autore del caso e grazie ai privilegi di amministratore di eDiscovery, è possibile iniziare a utilizzare il caso.  

1. Lasciare aperta questa scheda del browser, perché verrà usata nell'attività successiva.

### Demo parte 3

Con un caso creato, è possibile iniziare a lavorare con il caso. Ciò include la creazione di una query di ricerca per trovare dati e contenuti rilevanti per il caso, l'applicazione di un criterio di blocco, la creazione di un set di revisione e l'esportazione dei dati. In questa attività verranno esaminate alcune di queste opzioni. NOTA: è consigliabile passare attraverso la creazione di una ricerca e una revisione impostata prima del recapito, in modo che i risultati del set di ricerca e revisione siano prontamente disponibili durante la demo, perché queste azioni possono richiedere alcuni minuti per completare.  

1. Aprire la scheda SC900 Caso di test nel browser.

1. Nella pagina TEST CASE SC900 selezionare  **Crea una ricerca**.

1. Nel campo nome immettere **SC900 case search** e quindi selezionare **Crea**.

1. Selezionare **Aggiungi origini**. Prendere nota delle opzioni di filtro e delle impostazioni predefinite. Nella casella di ricerca immettere **`Pradeep`** e quindi selezionare **Cerca.** Nei risultati della ricerca selezionare Pradeep Gupta, quindi selezionare ****Salva e chiudi**.** Il generatore di condizioni consente di compilare una query di ricerca in base a parole chiave o condizioni specifiche soddisfatte, nella casella della parola chiave immettere **Sales**. Da qui è possibile selezionare **Esegui la query** dalla finestra Scegliere i risultati della ricerca. Per il tenant del lab, è disponibile solo la visualizzazione delle statistiche dei risultati della ricerca. Si notino le opzioni per disporre in base agli indicatori principali. Selezionare **Esegui query**.  Questa operazione può richiedere alcuni minuti.

1. Con i risultati delle query restituiti sotto forma di statistiche, è possibile esportare i risultati.  Nell'angolo in alto a destra della schermata (accanto a dove è indicato Aggiungi al set di revisione), selezionare **Esporta** per impostare le opzioni disponibili e quindi selezionare **Annulla**.

1. È possibile aggiungere a un insieme di revisione per un'ulteriore elaborazione.  Selezionare **Aggiungi per rivedere il set**. Immettere un nome per il nuovo set di revisione, **`SC900-review-set`**, lasciare le impostazioni predefinite e quindi selezionare **Aggiungi per rivedere set.** Questa operazione può richiedere alcuni minuti. Dopo aver presentato i risultati del set di revisione, è possibile esplorare le diverse opzioni, tra cui Analisi, Query, Azioni, File di tag e Gestione.

1. È anche possibile creare criteri di blocco per mantenere il contenuto pertinente al caso. Nella finestra Rivedi set selezionare la **scheda Blocco** .  Verrà visualizzata la finestra Criteri di blocco. Selezionare **Nuovi criteri**.  Immettere un nome di criteri, **`SC900-hold`** e selezionare **Crea.**  Come nella ricerca, è necessario aggiungere origini dati per il blocco ed è possibile aggiungere parole chiave e condizioni da usare nei criteri di blocco, quindi è possibile selezionare **Applica blocco**.  Le azioni che è possibile eseguire in un criterio di blocco includono un nuovo tentativo, disattivare un criterio ed eliminare un criterio di blocco.

1. Disconnettersi e chiudere tutte le finestre del browser aperte.

### Revisione

In questa demo sono stati illustrati i passaggi necessari per iniziare a usare eDiscovery, inclusa la configurazione delle autorizzazioni del ruolo per eDiscovery e la creazione di un caso eDiscovery.  Con il caso, sono state esaminate le impostazioni per la creazione di risultati di ricerca ed esportazione, l'aggiunta a un set di revisione e la creazione di un blocco.
