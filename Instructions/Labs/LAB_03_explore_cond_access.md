---
lab:
  title: Accesso condizionale Microsoft Entra
  module: Describe the access management capabilities of Microsoft Entra
---

# Lab: Accesso condizionale a Microsoft Entra

Questo lab corrisponde al contenuto di Learn seguente:

- Percorso di apprendimento: Descrivere le funzionalità di Microsoft Entra
- Modulo: Descrivere le funzionalità di gestione degli accessi di Microsoft Entra
- Unità: Descrivere l'accesso condizionale

## Scenario laboratorio

In questo lab, si esplorerà l'autenticazione a più fattori (MFA) degli accessi condizionali dal punto di vista di un amministratore e di un utente.  In qualità di amministratore, verrà creato un criterio che richiederà all'utente di effettuare l'autenticazione a più fattori quando accede a uno qualsiasi dei portali di amministrazione di Microsoft.  Dal punto di vista di un utente, si vedrà l'impatto dei criteri di accesso condizionale, compreso il processo di registrazione per l'autenticazione a più fattori.

**Tempo stimato**: 30 minuti

### Attività 1

In questa attività, l'amministratore dovrà reimpostare la password dell'utente Debra Berger.  Questo passaggio è necessario per poter accedere, inizialmente come utente, alle attività successive.

1. Aprire Microsoft Edge.  Nella barra degli indirizzi, immettere **https://entra.microsoft.com** e accedere con le proprie credenziali di amministratore.
    1. Nella finestra Accedi immettere **admin@WWLxZZZZZZ.onmicrosoft.com** (dove ZZZZZZ è l'ID tenant univoco fornito dal proprio provider di hosting del lab) e quindi selezionare **Avanti**.
    1. Immettere la password di amministratore, che dovrebbe essere fornita dal proprio provider di hosting del lab. Fare clic su **Accedi**.
    1. A seconda dell'host del lab e se è la prima volta che si esegue l'accesso al tenant, potrebbe essere richiesto di completare il processo di registrazione dell'autenticazione a più fattori. In tal caso, seguire le istruzioni visualizzate sullo schermo per configurare l'autenticazione a più fattori.
    1. Dopo aver eseguito l'accesso, viene visualizzata la pagina interfaccia di amministrazione di Microsoft 365.

1. Nel riquadro di spostamento a sinistra, espandere **Identità**, **Utenti**, quindi selezionare **Tutti gli utenti**.

1. Selezionare **Debra Berger** dall'elenco degli utenti.

1. Selezionare **Reimposta password** nella parte superiore della pagina. Poiché non è stato effettuato l'accesso come Debra Berger in precedenza, non si conosce la sua password e sarà quindi necessario reimpostarla.

1. Nella finestra di Reimpostazione password visualizzata, selezionare **Reimposta password**.  IMPORTANTE: prendere nota della nuova password, perché servirà in un'attività successiva per poter accedere come utente.

1. Chiudere la finestra di reimpostazione della password selezionando la **X** nell'angolo in alto a destra della pagina, quindi chiudere la finestra Debra Berger selezionando la **X** nell'angolo in alto a destra della pagina.

1. Dal riquadro di spostamento a sinistra, selezionare **Home** per tornare all'interfaccia di amministrazione di Microsoft Entra.

1. Tenere aperta questa finestra.

### Attività 2

In questa attività, si seguirà il processo di creazione di criteri di accesso condizionale in Microsoft Entra ID.

1. Aprire la scheda del browser con la pagina iniziale dell'interfaccia di amministrazione di Microsoft Entra.   Se la scheda del browser è stata chiusa in precedenza, aprire Microsoft Edge e nella barra degli indirizzi digitare **`https://entra.microsoft.com`** e accedere con le credenziali di amministrazione di Microsoft 365 fornite dall'ALH.

1. Dal riquadro di spostamento a sinistra, espandere **Protezione** e selezionare **Accesso condizionale**.

1. Verrà visualizzata la pagina di panoramica dell'accesso condizionale. Quando si arriva alla pagina di panoramica, viene selezionata la **scheda Attività iniziali** (sottolineata). Selezionare la **scheda Panoramica** . Qui verranno visualizzati riquadri che mostrano il riepilogo dei criteri e gli avvisi generali.  Dal riquadro di spostamento a sinistra, selezionare **Criteri**.

1. Dal riquadro di spostamento a sinistra, selezionare **Criteri**. Tutti i criteri di accesso condizionale esistenti sono elencati qui. Selezionare **+ Nuovi criteri**.

1. Nel campo Nome immettere **Blocca portali** di amministrazione.

1. In Utenti, selezionare **0 utenti e gruppi selezionati**.

1. Diventerà ora visibile l'opzione per includere o escludere utenti o gruppi.  Assicurarsi che l'opzione **Includi** sia selezionata (sottolineata).

1. Selezionare l'opzione **Seleziona utenti e gruppi** e **Utenti e gruppi**.  Viene visualizzata la finestra per la selezione degli utenti e dei gruppi.  

1. Nella barra di ricerca, immettere **Debra**.  Selezionare **Debra Berger** dalla barra di ricerca, quindi premere il pulsante **Seleziona** nella parte inferiore della pagina.  Notare che una pratica comune è quella di assegnare il criterio agli utenti di un gruppo.  Per gli scopi di questo lab, i criteri verranno assegnati a un utente specifico.

1. In Risorse di destinazione, selezionare **Nessuna risorsa di destinazione selezionata**.

1. Nel campo sotto la dicitura **Seleziona a cosa si applica questo criterio**, selezionare la freccia giù e prendere nota delle opzioni disponibili.  Mantenere l'impostazione predefinita, **App cloud**.  Assicurarsi che la scheda **Includi** sia sottolineata.  Selezionare **Seleziona app**, quindi sotto la casella **Seleziona**, selezionare **Nessuna**.  Viene visualizzata la finestra Seleziona app cloud.

1. Selezionare **Portali** di amministrazione Microsoft, quindi premere **Seleziona** nella parte inferiore della pagina.  Notare l'avviso.  

1. In Rete selezionare **Qualsiasi rete o percorso**.  Esaminare le opzioni, ma non selezionare alcuna opzione.

1. In Condizioni, selezionare **0 condizioni selezionate**.  Notare le diverse opzioni che si possono configurare.  Attraverso il criterio, è possibile controllare l'accesso degli utenti in base a segnali provenienti da condizioni quali: rischio utente, rischio accesso, piattaforma dispositivo, posizione, app client o filtro per dispositivi.  Esplorare queste opzioni configurabili, ma non impostare alcuna condizione.

1. Ora si imposteranno i controlli di accesso.  In Concedi, selezionare **0 controlli selezionati**.

1. Viene aperta la finestra Concedi.  Selezionare **Blocca accesso**. Selezionare **OK** nella parte inferiore della pagina.

1. Nella parte inferiore della pagina, in Abilita criterio, selezionare **Attivato** e quindi selezionare **Crea**.

1. Nel riquadro di spostamento a sinistra selezionare **Criteri**. I **criteri Blocca portali** di amministrazione appena creati dovrebbero essere visualizzati nell'elenco dei criteri di accesso condizionale (se necessario, selezionare l'icona **** Aggiorna nella barra dei comandi nella parte superiore della pagina).

1. Disconnettersi selezionando l'icona utente accanto all'indirizzo e-mail nell'angolo in alto a destra dello schermo e selezionando **Esci**. Chiudere quindi tutte le finestre del browser

### Attività 3

In questa attività si vedrà l'impatto dei criteri di accesso condizionale dal punto di vista dell'utente Debra Berger. Per prima cosa, è necessario accedere a un'applicazione non inclusa nel criterio di accesso condizionale (portale di Microsoft 365 all'indirizzo https://login.microsoftonline.com)).  Quindi ripetere la procedura per un'applicazione inclusa nel criterio di accesso condizionale (portale di Azure all'indirizzo https://portal.azure.com)).  Tenere presente che i criteri bloccano l'accesso a qualsiasi portale di amministrazione di Microsoft, incluso il portale di Azure.  NOTA: per motivi di sicurezza, tutti gli account utente che accedono a qualsiasi portale sono necessari per l'uso dell'autenticazione a più fattori.  Il requisito dell'autenticazione a più fattori è indipendente da questo esercizio del lab.

1. Aprire Microsoft Edge.  Nella barra degli indirizzi, immettere **https://login.microsoftonline.com**.
    1. Accedere come **DebraB@WWLxZZZZZZ.onmicrosoft.com**, dove ZZZZZZ è l'ID del tenant univoco fornito dal provider di hosting del lab, quindi selezionare **Avanti**.
    1. Immettere la password annotata nell'attività precedente. Fare clic su **Accedi**.
    1. Poiché la password specificata quando l'amministratore reimposta la password è temporanea, è necessario aggiornare la password. Immettere la password attuale, quindi immettere una nuova password e confermarla.  Annotare la nuova password, poiché sarà necessaria per completare l'attività.
    1. Poiché questa è la prima volta che si esegue l'accesso come Debra Berger, potrebbe essere richiesto di configurare MFA. Seguire le istruzioni visualizzate sullo schermo per configurare l'autenticazione a più fattori.
    1. Quando viene richiesto di rimanere connessi, selezionare **Sì**.  L'accesso all'account Microsoft 365 dovrebbe essere completato.

1. A questo punto si proverà ad accedere a un'applicazione che soddisfi i criteri dei criteri di accesso condizionale. Aprire una nuova scheda del browser e immettere **https://portal.azure.com**, ovvero il portale di amministrazione per Azure.  Viene visualizzata una finestra popup che indica che "Non si ha accesso a questo".  Questo è il risultato dei criteri di accesso condizionale che bloccano l'accesso a tutti i portali di amministrazione Microsoft.

1. Disconnettersi selezionando l'icona dell'utente accanto all'indirizzo di posta elettronica nell'angolo in alto a destra della schermata, quindi Disconnetti. Chiudere quindi tutte le finestre del browser.

### Revisione

In questo lab è stato eseguito il processo di configurazione di criteri di accesso condizionale che bloccano l'accesso ai portali di amministrazione Microsoft per tutti gli utenti inclusi nei criteri.  Quindi, come utente si è verificato l'impatto dei criteri di accesso condizionale quando si accede al portale di Azure.
