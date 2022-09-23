---
ms.openlocfilehash: 553860b67fc7cc2b181e874e4c57fb4bc972822b
ms.sourcegitcommit: 15658ca1c7bae8a4dbaa33ab6f897070bde521b9
ms.translationtype: HT
ms.contentlocale: it-IT
ms.lasthandoff: 09/12/2022
ms.locfileid: "147892702"
---
<a name="---"></a><!--->
---
Lab: Titolo: 'Esplorare la gestione dei rischi Insider in Microsoft Purview' Percorso di apprendimento/Modulo/Unità: 'Percorso di apprendimento: Descrivere le funzionalità di conformità Microsoft; Modulo 4: Descrivere le funzionalità per rischi Insider in Microsoft Purview; Unità 2: Descrivere la gestione dei rischi Insider'
---
--->

# <a name="lab-explore-insider-risk-management-in-microsoft-purview"></a>Laboratorio: Esplorazione della gestione dei rischi Insider in Microsoft Purview

Questo lab corrisponde al contenuto di Learn seguente:

- Percorso di apprendimento: Descrivere le funzionalità di conformità Microsoft
- Modulo: Descrivere le funzionalità per rischi Insider in Microsoft Purview
- Unità: Descrivere la gestione dei rischi Insider

## <a name="lab-scenario"></a>Scenario del lab

In questo lab, verrà descritto il processo di impostazione di un criterio di rischio Insider, insieme ai prerequisiti di base per configurare e usare i criteri di gestione del rischio Insider.  Nota: questo lab fornirà soltanto visibilità degli elementi richiesti per impostare la gestione dei rischi Insider e le opzioni associate alla creazione di un criterio.  Questo lab non include un'attività per attivare il criterio, in quanto il numero di eventi necessari per attivare un criterio non rientra nell'ambito di questo esercizio.

**Tempo stimato**: 25-30 minuti

### <a name="task-1"></a>Attività 1

In questa attività, l'utente, in qualità di amministratore globale, abiliterà le autorizzazioni per Gestione del rischio Insider.  Specificamente, verranno aggiunti utenti al gruppo di ruoli Gestione dei rischi Insider per assicurare che gli utenti designati possano accedere e gestire le funzionalità di gestione dei rischi Insider.  L'applicazione delle autorizzazioni del gruppo di ruoli agli utenti nell'organizzazione potrebbe impiegare fino a 30 minuti.

1. Aprire Microsoft Edge. Nella barra degli indirizzi immettere **admin.microsoft.com**.

1. Accedere con le credenziali di amministratore.
    1. Nella finestra Accedi immettere **admin@WWLxZZZZZZ.onmicrosoft.com** (dove ZZZZZZ è l'ID tenant univoco fornito dal proprio provider di hosting del lab) e quindi selezionare **Avanti**.

    1. Immettere la password di amministratore, che dovrebbe essere fornita dal proprio provider di hosting del lab. Fare clic su **Accedi**.
    1. Quando compare la domanda se rimanere connessi, selezionare **Sì**. In questo modo si accede alla pagina dell'interfaccia di amministrazione di Microsoft 365.

1. Dal riquadro di spostamento sinistro dell'interfaccia di amministrazione di Microsoft 365, selezionare **Mostra tutto**.

1. In Interfacce di amministrazione selezionare **Conformità**.  Si apre una nuova pagina del browser alla pagina di benvenuto del portale di conformità di Microsoft Purview.  

1. Dal riquadro di spostamento sinistro del portale di conformità di Microsoft Purview, selezionare **Autorizzazioni**.

1. Nella pagina Autorizzazioni e ruoli, sotto il testo "Visualizzare e gestire i ruoli usati per eseguire attività specifiche della soluzione nel Centro conformità" selezionare **Ruoli**.

1. Nella barra di ricerca immettere **Rischio Insider**, quindi selezionare l'icona di ricerca (lente di ingrandimento).  Si notino i numerosi ruoli visualizzati.  Ciascuno ha diversi livelli di accesso.  Selezionare **Gestione dei rischi Insider**.

1. Nella finestra che viene aperta accanto a dove c'è scritto Membri selezionare **Modifica**.

1. Per aggiungere membri a questo gruppo di ruoli, selezionare **Scegli membri**.

1. Selezionare **+ Aggiungi** dalla parte superiore della pagina.

1. Dall'elenco dei nomi, selezionare **Amministratore MOD**, **Megan Bowen** quindi selezionare **Aggiungi** nella parte inferiore della pagina, quindi selezionare **Fatto** nella parte inferiore della pagina.

1. Verificare che i membri aggiunti siano corretti, quindi selezionare **Salva**.

1. Dalla parte inferiore della finestra Gestione dei rischi Insider selezionare **Chiudi**.

1. Dal riquadro di spostamento sinistro selezionare **Home** per tornare alla pagina del portale di conformità di Microsoft Purview.

1. Mantenere questa scheda del browser aperta, poiché servirà per un'attività successiva.

### <a name="task-2-skip-if-you-did-the-setup-lab-task-to-enable-the-audit-log"></a>Attività 2 (IGNORARE se è stata eseguita l'attività del lab di impostazione per abilitare il log di controllo)

Gestione dei rischi Insider usa i log di controllo Microsoft 365 per informazioni dettagliate e attività dell'utente identificate in criteri e informazioni dettagliate delle analisi. In questa attività, verrà abilitata la funzione di ricerca del log di controllo. Nota:  dopo l'attivazione della ricerca nel log di controllo, la restituzione di risultati quando si esegue la ricerca nel log di controllo potrebbe richiedere diverse ore.  Sebbene possa impiegare diverse ore prima di poter eseguire la ricerca nel log di controllo, non avrà un impatto sulla capacità di completare altre attività in questo lab.

1. Selezionare la scheda del browser con etichetta **Home - Conformità Microsoft 365**.  Se in precedenza è stata chiusa questa scheda del browser, aprire Microsoft Edge e nella barra degli indirizzi immettere **compliance.microsoft.com** e accedere con le credenziali di amministratore.

1. Dal riquadro di spostamento sinistro, sotto Soluzioni, selezionare **Controllo**.

1. Verificare che la scheda **Cerca** sia selezionata (sottolineata).

1. Una volta arrivati nella pagina Controllo, attendere 2-3 minuti.  Se il controllo non è abilitato, verrà visualizzata una barra blu in cima alla pagina per avviare la registrazione delle attività di utenti e amministratori.  Selezionare **Avvia la registrazione delle attività di utenti e amministratori**.  Una volta abilitato il controllo, la barra blu scompare.  Se la barra blu non è presente, il controllo è già abilitato e non sono richieste ulteriori azioni.

1. Tornare alla home page del portale di conformità di Microsoft Purview selezionando **Home** dal riquadro di spostamento sinistro.

1. Mantenere la scheda del browser aperta perché verrà usata nell'attività successiva.

### <a name="task-3"></a>Attività 3

In questa attività verranno esaminate le impostazioni associate alla soluzione Gestione dei rischi Insider.  Le impostazioni di Gestione dei rischi Insider si applicano a tutti i criteri di gestione dei rischi Insider, indipendentemente dal modello scelto durante la creazione di un criterio.

1. Dovrebbe essere ancora aperta la home page del portale di conformità di Microsoft Purview. In caso contrario, aprire la scheda del browser **Home page - Conformità Microsoft 365**.

1. Dal riquadro di spostamento a sinistra sotto Soluzioni, selezionare **Gestione dei rischi Insider**.

1. Prima di iniziare a impostare un criterio, è necessario configurare alcune impostazioni.  Dalla pagina Gestione dei rischi Insider, selezionare l'**icona di ingranaggio delle impostazioni** sull'angolo in alto a destra della pagina per accedere alle impostazioni di Rischio Insider.  
    1. Verificare di essere nella scheda **Privacy**: per gli utenti che eseguono attività che corrispondono ai criteri di rischio Insider, questa impostazione determinerà se mostrare i nomi effettivi o usare versioni anonime per nascondere le relative identità.  Selezionare **Non mostrare le versioni anonime dei nomi utente**, quindi selezionare **Salva**.

    1. Selezionare la scheda **Indicatori di criteri**. Una volta che si verifica un criterio che attiva un evento, le attività che mappano agli indicatori selezionati sono usate per determinare il punteggio di rischio per l'utente. Gli indicatori di criteri selezionati qui sono inclusi nei modelli dei criteri dei rischi Insider.  Scorrere per visualizzare tutti gli indicatori disponibili e le informazioni associate. Sotto **Indicatori Office**, selezionare **Seleziona tutto**, quindi selezionare **Salva**.
    1. Selezionare la scheda **Intervalli di criteri**. Gli intervalli scelti qui si applicano quando un utente attiva una corrispondenza per un criterio di rischio Insider.   La finestra Attivazione determina per quanto tempo i criteri rileveranno attivamente l'attività per gli utenti e viene attivata quando un utente esegue la prima attività corrispondente a un criterio. Il rilevamento di attività passate determina quanto indietro nel tempo deve andare un criterio per rilevare l'attività di utente e viene attivato quando un utente esegue la prima attività corrispondente a un criterio.  Lasciare invariati i valori predefiniti.  Selezionare la scheda **Rilevamenti intelligenti**.
    1. Selezionare la scheda **Rilevamenti intelligenti**. Esaminare le opzioni presenti.  Notare le impostazioni dei domini e la modalità con cui si correlano agli indicatori.
    1. Esplorare gli altri elementi elencati nelle impostazioni. Si noti che molti sono in anteprima.

1. Per tornare alla panoramica di Gestione dei rischi Insider, selezionare **Gestione dei rischi Insider** dall'angolo in alto a sinistra della pagina, sopra dove è visualizzato Impostazioni.

1. Mantenere la scheda del browser aperta perché verrà usata nell'attività successiva.

### <a name="task-4"></a>Attività 4

In questa attività verrà spiegata la creazione di un criterio.

1. È necessario trovarsi nella pagina Gestione dei rischi Insider.  In caso contrario, aprire la scheda del browser con etichetta, **Gestione dei rischi Insider - Conformità Microsoft 365**.

1. Dalla pagina di panoramica di Gestione dei rischi Insider selezionare la scheda **Criteri**, quindi selezionare **+ Crea criterio**.  Configurare ciascuna delle seguenti schede dei criteri.

    1. Modello criteri:  Dall'elenco di categorie, selezionare **Perdite di dati**, quindi selezionare **Perdite di dati generali**.  Tenere presente che per i modelli all'interno delle categorie possono esserci prerequisiti aggiuntivi.  Leggere i dettagli associati a questo modello, quindi selezionare **Avanti**.

    1. Nome e descrizione: immettere il nome **SC900-InsiderRiskPolicy**, quindi selezionare **Avanti**.
    1. Utenti e gruppi:  esaminare la casella delle informazioni.  Lasciare l'impostazione predefinita, **Includi tutti gli utenti e i gruppi**.  Selezionare **Avanti**.
    1. Contenuti a cui dare priorità: Leggere la descrizione. Selezionare **Desidero specificare siti SharePoint, etichette di riservatezza e/o tipi di informazioni sensibili come contenuto prioritario**, quindi selezionare **Avanti**.
        1. Sito SharePoint: per questo esempio di criterio, lasciare il campo vuoto, selezionare **Avanti**
        1. Tipi di informazioni sensibili: per questo esempio di criterio, lasciare il campo vuoto, quindi selezionare **Avanti**.
        1. Etichette di riservatezza: selezionare **+ Aggiungi o modifica etichette di riservatezza**.  Selezionare le etichette elencate:  **Riservato - Finanza** e **Riservatezza elevata/Progetto – Falcon**, selezionare **Aggiungi**, quindi **Avanti**.
    1. Trigger: esaminare le informazioni dettagliate.  Il criterio viene attivato dall'utente che esegue un'attività di esfiltrazione come definita (selezionare le icone di informazioni per ciascun elenco puntato per informazioni più dettagliate) OPPURE una corrispondenza a un criterio Prevenzione della perdita dei dati (DLP) esistente.  Poiché non si dispone di criteri DLP configurati come parte di questo esercizio, selezionare **L'utente esegue un'attività di esfiltrazione**.  Notare che gli indicatori di criteri abilitati nell'attività precedente sono selezionati.   Tenere a mente che questi indicatori saranno attivati solo dopo l'attivazione del criterio e le attività che mappano a questi indicatori saranno usate per calcolare un punteggio di rischio per l'utente. Selezionare **Avanti**.
    1. Soglie di indicatori: qui è possibile specificare soglie predefinite o personalizzate associate agli indicatori.  Tenere a mente che gli indicatori sono attivati solo dopo che si verifica l'attivazione del criterio in modo tale che le soglie non influiscano quando il criterio è attivato. Selezionare **Specifica soglie personalizzate**. La selezione di questa opzione consentirà di visualizzare i valori predefiniti correnti. Lasciare i valori predefiniti e selezionare **Avanti**.  
    1. Indicatori: si noti che tutti gli indicatori di Office selezionati nell'attività precedente sono selezionati.  Scorrere la pagina per visualizzare gli altri indicatori di criteri disponibili e gli altri elementi selezionati automaticamente.   Il rilevamento di sequenza è abilitato.  Se una sequenza di attività, come definita, viene rilevata, allora ne deriva un rischio maggiore.  Per informazioni dettagliate, passare il mouse sull'icona delle informazioni.  Questi elementi richiedono che determinati indicatori siano selezionati e che i dispositivi siano caricati.  Per maggiore semplicità e poiché non è stato caricato alcun dispositivo in questo tenant, deselezionare **Seleziona tutto**.
    1. Fine: esaminare le impostazioni, selezionare **Invia**, quindi selezionare **Fatto**.

1. Si è di nuovo nella scheda Criteri della pagina Gestione dei rischi Insider.  Il criterio appena creato sarà inserito nell'elenco.  

1. Nel criterio appena creato, il campo "Utenti nell'ambito" rappresenta gli utenti a cui vengono correntemente assegnati punteggi di rischio dal criterio.  L'assegnazione di punteggi di rischio agli utenti si verifica quando il criterio è attivato, ed è il motivo per cui il valore indica 0.  Un amministratore può configurare un criterio per iniziare ad assegnare punteggi di rischio a utenti specifici, in base all'attività rilevata dai criteri selezionati, E che bypassa il requisito per cui un evento di attivazione è rilevato per primo.  A questo scopo, selezionare il cerchio vuoto accanto al nome del criterio per selezionare il criterio, quindi selezionare **Inizia calcolo punteggio attività per utenti**, che è mostrato sopra alla tabella dei criteri.  Compilare ogni campo, quindi selezionare **Inizia calcolo punteggio attività**.  Prima che gli utenti siano visualizzati nella scheda "Utenti" potrebbero trascorrere 24 ore. Dopodiché, è possibile selezionare gli utenti dalla scheda per esaminare le attività rilevate.  Selezionare **Chiudi** nella parte inferiore della finestra.

1. Chiudere tutte le schede del browser aperte.

### <a name="review"></a>Verifica

In questo lab, è stato spiegato il processo di impostazione di un criterio di rischio Insider, insieme ai prerequisiti di base per configurare e usare i criteri di gestione di rischi Insider.
