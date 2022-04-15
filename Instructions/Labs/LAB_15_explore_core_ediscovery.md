---
lab:
  title: Esplorazione del flusso di lavoro di Core eDiscovery
  module: 'Module 4 Lesson 5: Describe the capabilities of Microsoft compliance solutions: Describe the eDiscovery and audit capabilities of Microsoft 365'
ms.openlocfilehash: 0754237aa892e9fe31ad2eea0811642bce929fe8
ms.sourcegitcommit: c14538b208890797642cfe5c35abf6bea45364bf
ms.translationtype: HT
ms.contentlocale: it-IT
ms.lasthandoff: 04/15/2022
ms.locfileid: "142614375"
---
# <a name="lab-explore-the-core-ediscovery-workflow"></a>Laboratorio: Esplorazione del flusso di lavoro di Core eDiscovery

## <a name="lab-scenario"></a>Scenario del lab
In questo lab eseguiremo i passaggi necessari per configurare Core eDiscovery e poi eseguiremo il flusso di lavoro di Core eDiscovery, creando un blocco di eDiscovery e una query di ricerca e infine esportando i risultati della ricerca.  Nota:  La licenza di Core eDiscovery richiede un'appropriata sottoscrizione da parte dell'organizzazione e una licenza per ciascun utente. In caso di dubbi su quali licenze supportino Core eDiscovery, visitare la pagina Introduzione a Core eDiscovery.


**Tempo stimato**: 20-25 minuti

#### <a name="task-1--to-access-core-ediscovery-or-be-added-as-a-member-of-a-core-ediscovery-case-a-user-must-be-assigned-the-appropriate-permissions-in-this-task-you-as-the-global-admin-will-add-specific-users-as-members-of-the-ediscovery-manager-role-group"></a>Attività 1:  Per accedere a Core eDiscovery o essere aggiunti come membro di un caso di Core eDiscovery, a un utente devono essere assegnate le autorizzazioni appropriate. In questa attività, lo studente, in qualità di amministratore globale, aggiungerà specifici utenti come membri del gruppo di ruoli di eDiscovery Manager.

 Aprire Microsoft Edge. Nella barra degli indirizzi immettere **admin.microsoft.com**.

1. Accedere con le credenziali di amministratore.
    1. Nella finestra Accedi immettere **admin@WWLxZZZZZZ.onmicrosoft.com** (dove ZZZZZZ è l'ID tenant univoco fornito dal proprio provider di hosting del lab) e quindi selezionare **Avanti**.
    
    1. Immettere la password di amministratore, che dovrebbe essere fornita dal proprio provider di hosting del lab. Fare clic su **Accedi**.
    1. Quando compare la domanda se rimanere connessi, selezionare **Sì**. In questo modo si accede alla pagina dell'interfaccia di amministrazione di Microsoft 365.

1. Dal riquadro di spostamento sinistro dell'interfaccia di amministrazione di Microsoft 365, selezionare **Mostra tutto**.

1. In Interfacce di amministrazione selezionare **Conformità**.  Si apre una nuova pagina del browser alla pagina di benvenuto del Centro conformità Microsoft 365.  

1. Nel riquadro di spostamento sinistro selezionare **Autorizzazioni**. 

1. Nella pagina Autorizzazioni e ruoli, in Centro conformità selezionare **Ruoli**.

1. Nel campo di ricerca immettere **eDiscovery** e quindi selezionare l'icona della ricerca (lente d'ingrandimento).  Selezionare **Manager di eDiscovery**.

1. Nella finestra che si apre, notare la presenza di due sottogruppi, Manager di eDiscovery e Amministratore di eDiscovery.  Leggere la descrizione di ciascuno.  Per questo primo lab, aggiungeremo membri al sottogruppo Amministratore di eDiscovery. Selezionare **Modifica**, accanto ad Amministratore di eDiscovery.  Come procedura consigliata generale, agli utenti deve essere assegnato il minore privilegio richiesto per il loro ruolo.

1. Per aggiungere membri a questo ruolo, verificare di trovarsi nella scheda **Scegli amministratore di eDiscovery**, quindi selezionare **Scegli amministratore di eDiscovery**.

1. Selezionare **+ Aggiungi** dalla parte superiore della pagina.

1. Dall'elenco dei nomi, selezionare **Amministratore MOD**, **Megan Bowen** quindi selezionare **Aggiungi** nella parte inferiore della pagina, quindi selezionare **Fatto** nella parte inferiore della pagina.

1. Verificare che i membri aggiunti siano corretti, quindi selezionare **Salva**.

1. In basso sulla finestra di eDiscovery, selezionare **Chiudi**.

1. Mantenere la scheda del browser aperta perché verrà usata nell'attività successiva.

#### <a name="task-2--in-this-task-you-as-an-ediscovery-administrator-mod-admin-is-an-ediscovery-administrator-will-create-a-case-to-start-using-core-ediscovery"></a>Attività 2:  In questa attività, lo studente, in qualità di Amministratore di eDiscovery (l'amministratore MOD è un amministratore di eDiscovery), creerà un caso per iniziare a utilizzare Core eDiscovery.

1. Dovrebbe essere ancora visualizzata la pagina Ruoli del Centro conformità. Se la scheda del browser è stata chiusa dall'attività precedente, aprire una nuova scheda del browser e immettere **compliance.microsoft.com**

1. Dal riquadro di spostamento a sinistra, sotto Soluzioni, selezionare **eDiscovery**, quindi selezionare **Core**.

1. In alto sulla pagina di Core eDiscovery, selezionare **+ Crea un caso**.

1. Nella finestra Nuovo caso, immettere un nome per il caso, **SC900 Caso di test**, quindi selezionare **Salva** in basso sulla pagina.

1. Il caso ora dovrebbe comparire nell'elenco.

1. In quanto creatore del caso e in possesso dei privilegi di Amministratore di eDiscovery, lo studente può ora iniziare a lavorare su di esso.  

1. Lasciare aperta questa scheda del browser, in quanto verrà riutilizzata per la successiva attività.

#### <a name="task-3--now-that-you-have-created-a-core-ediscovery-case-you-can-begin-to-work-with-the-case--in-this-task-you-will-create-an-ediscovery-hold-for-the-case-for-you-just-created--specifically-you-will-crate-a-hold-for-the-the-exchange-mailbox-belonging-to-adele-vance"></a>Attività 3:  Ora che è stato creato un caso di Core eDiscovery, si può iniziare a lavorare su di esso.  In questa attività, lo studente creerà un blocco di eDiscovery per il caso appena creato.  Nello specifico, si dovrà creare un blocco per la cassetta postale di Exchange che appartiene ad Adele Vance.

1. Aprire la scheda Core eDiscovery nel browser.

1. Dalla pagina Core eDiscovery, selezionare il caso creato nella scheda precedente, **SC900 Caso di test**. 

1. Dalla Home page del caso, selezionare la scheda **Blocco**, quindi selezionare **+Crea**.

1. Nel campo del nome, immettere **Blocco di test**, quindi selezionare Avanti.

1. Nella pagina Scegli posizioni, selezionare l'interruttore accanto a **Cassette postali Exchange** per impostare lo stato su **Attivata** e quindi selezionare **Scegli utenti, gruppi o team**.  Nella casella di ricerca, immettere **Adele**, quindi premere Invio sulla tastiera. Dai risultati della ricerca, selezionare **Adele Vance**, quindi selezionare Scegli e infine selezionare **Fatto**.

1. Nella pagina Scegli posizioni, selezionare **Avanti**.  Per non prolungare l'attività del lab, nel blocco non verranno incluse altre posizioni.

1. La pagina Condizioni della Query permette di creare un blocco basato su specifiche parole chiave o condizioni che devono essere soddisfatte; selezionare **+Condizioni** per visualizzare le opzioni disponibili.  Selezionare **Avanti**. Se non si specificano condizioni, il blocco conserverà tutto il contenuto nella posizione specificata.

1. Verificare le impostazioni e selezionare **Invia**, l'invio potrebbe richiedere un minuto, quindi selezionare **Fatto**.  Il blocco di test ora dovrebbe comparire nell'elenco.  Se non viene visualizzata immediatamente, selezionare **Aggiorna**

1. Lasciare aperta questa scheda del browser, in quanto verrà riutilizzata per la successiva attività.

#### <a name="task-4--with-a-hold-in-place-you-will-create-a-search-query--once-your-search-is-complete-you-will-go-export-and-download-the-results-for-future-investigation---note--searches-associated-with-a-core-ediscovery-case-are-not-listed-on-the-content-search-page-in-the-microsoft-365-compliance-center-these-searches-are-listed-only-on-the-searches-page-of-the-associated-core-ediscovery-case"></a>Attività 4:  Una volta creato il blocco, occorre creare una query di ricerca.  Una volta completata la ricerca, si dovranno esportare e scaricare i risultati per futura indagine.   Nota:  Le ricerche associate a un caso di Core eDiscovery non sono elencate nella pagina Ricerca di contenuto del Centro conformità Microsoft 365. Queste ricerche sono elencate solo nella pagina Ricerche del caso di Core eDiscovery associato.

1. Aprire la scheda SC900 Caso di test nel browser.

1. Nella pagina Blocchi relativa al caso, selezionare **Ricerche**.

1. Nella pagina Ricerca, selezionare **+ Nuova ricerca**.

1. Nel campo Nome, immettere **Blocco di test – Ricerca vendite**, quindi selezionare **Avanti** in basso nella pagina.

1. Nella pagina Scegli posizioni selezionare **Posizioni con blocco** e deselezionare **Aggiungi il contenuto delle app per gli utenti locali**, perché l'ambiente lab non ha utenti locali, quindi selezionare **Avanti**.

1. La pagina Condizioni della Query permette di creare una ricerca basata su specifiche parole chiave o condizioni che devono essere soddisfatte; nel campo della parola chiave immettere **Vendite**, quindi selezionare **Avanti**.

1. Verificare le impostazioni e selezionare **Invia**, l'invio potrebbe richiedere un minuto, quindi selezionare **Fatto**.  la ricerca ora dovrebbe comparire nell'elenco.  Se non viene visualizzata immediatamente, selezionare **Aggiorna**

1. Nella finestra Ricerche, selezionare la ricerca appena creata, **Blocco di test - Ricerca vendite**.  Viene visualizzata una finestra con la scheda Riepilogo selezionata.  Una volta eseguita la ricerca, lo stato ne indica il completamento.  Viene visualizzata la scheda Statistiche ricerca (se la scheda Statistiche ricerca non compare, significa che la ricerca è in corso e richiede ancora qualche minuto per essere completata).  Selezionare la scheda **Statistiche ricerca** e selezionare l'elenco a discesa accanto a Contenuti ricerca.  Si possono visualizzare anche altre informazioni per Scheda condizione e Posizioni principali.  

1. In basso sulla pagina, selezionare **Azioni**.  Vedere le opzioni disponibili, quindi selezionare **Esporta risultati**.
    
    1. Nella finestra Esporta risultati, lasciare le impostazioni predefinite e selezionare **Esporta** in basso sulla pagina. Si ritornerà automaticamente alla finestra "Blocco di test - Ricerca vendite". Selezionare **Chiudi** in basso sulla pagina.
    
    1. Nella pagina SC900-Caso di test, selezionare **Esportazioni** in alto sulla pagina.
    1. Selezionare **Blocco di test - Ricerca vendite_Export**
    1. Nella finestra visualizzata, "Blocco di test - Ricerca vendite_Export", è visibile una chiave di esportazione, selezionare **Copia negli appunti**.
    1. In alto sulla finestra, selezionare **Scarica i risultati**. Viene aperta una nuova pagina del browser e viene visualizzata una finestra popup che chiede se si desidera aprire questo file, selezionare **Apri**.
    1. Se questa è la prima volta che si esegue il download di una ricerca di contenuti, verrà richiesto di installare lo strumento di esportazione di eDiscovery di Microsoft Office 365.  Selezionare **Installa**.
    1. Una volta completata l'installazione, viene aperta la finestra dello strumento di esportazione di eDiscovery.  Nel primo campo, incollare la chiave di esportazione copiata negli appunti, incollarla subito (Ctrl V sulla tastiera oppure fare doppio clic con il mouse e selezionare Incolla).
    1. Nel secondo campo, selezionare la posizione in cui si desidera archiviare il file dell'esportazione, quindi selezionare **Avvia**.  Una volta completato il download, selezionare **Chiudi** e chiudere questa scheda del browser.
    1. Si ritorna di nuovo alla finestra "Blocco di test - Ricerca vendite_Export".  Selezionare **Chiudi**.
    1. Controllare la posizione specificata per il download per verificare che il download sia stato completato correttamente. 


#### <a name="review"></a>Verifica

In questo lab sono stati eseguiti i passaggi necessari per iniziare a usare Core eDiscovery, incluse l'impostazione delle autorizzazioni per i ruoli di eDiscovery e la creazione di un caso di eDiscovery.  Dopo aver creato il caso, è stato eseguito il flusso di lavoro di Core eDiscovery, creando un blocco di eDiscovery e una query di ricerca e poi esportando i risultati della ricerca da utilizzare per ulteriori indagini.