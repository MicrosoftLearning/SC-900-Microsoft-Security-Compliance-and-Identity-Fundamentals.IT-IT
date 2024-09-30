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
    1. Quando viene richiesto di rimanere connessi, selezionare **Sì**.

1. Nel riquadro di spostamento a sinistra, espandere **Identità**, **Utenti**, quindi selezionare **Tutti gli utenti**.

1. Selezionare **Debra Berger** dall'elenco degli utenti.

1. Selezionare **Reimposta password** nella parte superiore della pagina. Poiché non è stato effettuato l'accesso come Debra Berger in precedenza, non si conosce la sua password e sarà quindi necessario reimpostarla.

1. Nella finestra di Reimpostazione password visualizzata, selezionare **Reimposta password**.  IMPORTANTE: prendere nota della nuova password, perché servirà in un'attività successiva per poter accedere come utente.

1. Chiudere la finestra di reimpostazione della password selezionando la **X** nell'angolo in alto a destra della pagina, quindi chiudere la finestra Debra Berger selezionando la **X** nell'angolo in alto a destra della pagina.

1. Dal riquadro di spostamento a sinistra, selezionare **Home** per tornare all'interfaccia di amministrazione di Microsoft Entra.

1. Tenere aperta questa finestra.

### Attività 2

In questa attività, si seguirà il processo di creazione di criteri di accesso condizionale in Microsoft Entra ID.

1. Aprire la scheda del browser con la pagina iniziale dell'interfaccia di amministrazione di Microsoft Entra.   Se la scheda del browser è stata chiusa in precedenza, aprire Microsoft Edge e nella barra degli indirizzi digitare **https://entra.microsoft.com** e accedere con le credenziali di amministrazione di Microsoft 365 fornite dall'ALH.

1. Dal riquadro di spostamento a sinistra, espandere **Protezione** e selezionare **Accesso condizionale**.

1. Verrà visualizzata la pagina di panoramica dell'accesso condizionale.  Qui verranno visualizzati i riquadri che mostrano il riepilogo dei criteri e gli avvisi generali.  Dal riquadro di spostamento a sinistra, selezionare **Criteri**.

1. Dal riquadro di spostamento a sinistra, selezionare **Criteri**. Tutti i criteri di accesso condizionale esistenti sono elencati qui. Selezionare **+ Nuovi criteri**.

1. Nel campo Nome, immettere **Criterio test MFA**.

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

1. Viene aperta la finestra Concedi.  Assicurarsi che l'opzione **Concedi accesso** sia selezionata e quindi selezionare **Richiedi l'autenticazione a più fattori**. Scorrere verso il basso nella finestra destra e nella sezione Per più controlli lasciare l'impostazione predefinita **Richiedi tutti i controlli selezionati**.  Selezionare **OK** nella parte inferiore della pagina.

1. Nella parte inferiore della pagina, in Abilita criterio, selezionare **Attivato** e quindi selezionare **Crea**.

1. Nel riquadro di spostamento a sinistra selezionare **Criteri**. Il criterio MFA Pilot dovrebbe apparire nell'elenco dei criteri di accesso condizionale (se necessario, selezionare l'icona **Aggiorna** nella barra dei comandi nella parte superiore della pagina).

1. Disconnettersi selezionando l'icona utente accanto all'indirizzo e-mail nell'angolo in alto a destra dello schermo e selezionando **Esci**. Chiudere quindi tutte le finestre del browser

### Attività 3

In questa attività si vedrà l'impatto dei criteri di accesso condizionale dal punto di vista dell'utente Debra Berger. Per prima cosa, è necessario accedere a un'applicazione non inclusa nel criterio di accesso condizionale (portale di Microsoft 365 all'indirizzo https://login.microsoftonline.com)).  Quindi ripetere la procedura per un'applicazione inclusa nel criterio di accesso condizionale (portale di Azure all'indirizzo https://portal.azure.com)).  Occorre ricordare che il criterio richiede all'utente di passare attraverso l'autenticazione MFA durante l'accesso a qualsiasi portale di amministrazione Microsoft, compreso il portale di Azure.  Per utilizzare l'autenticazione MFA, l'utente deve prima registrare il metodo di autenticazione che verrà utilizzato, ad esempio un codice inviato a un dispositivo mobile o un'applicazione di autenticazione.

1. Aprire Microsoft Edge.  Nella barra degli indirizzi, immettere **https://login.microsoftonline.com**.
    1. Accedere come **DebraB@WWLxZZZZZZ.onmicrosoft.com**, dove ZZZZZZ è l'ID del tenant univoco fornito dal provider di hosting del lab, quindi selezionare **Avanti**.
    1. Immettere la password annotata nell'attività precedente. Fare clic su **Accedi**.
    1. Poiché la password fornita quando, in qualità di amministratore, è stata reimpostata è temporanea, sarà necessario aggiornare la password (questo non fa parte dei criteri MFA). Immettere la password attuale, quindi immettere una nuova password e confermarla.  Annotare la nuova password, poiché sarà necessaria per completare l'attività.
    1. Quando viene richiesto di rimanere connessi, selezionare **Sì**.  L'accesso all'account Microsoft 365 dovrebbe essere completato. L'autenticazione MFA non è richiesta per questa applicazione, in quanto non fa parte del criterio.

1. Ora si proverà a effettuare l'accesso a un'applicazione che soddisfa i criteri per la MFA. Aprire una nuova scheda del browser e immettere **https://portal.azure.com**.

1. Verrà visualizzata una finestra con l'indicazione Sono necessarie altre informazioni.  Selezionare **Avanti**.  Notare che in questo modo si avvierà il processo di registrazione MFA, poiché si tratta del primo accesso all'app cloud identificata nei criteri di accesso condizionale.  Questa procedura di registrazione viene richiesta una sola volta.   Un'alternativa al processo di registrazione dell'utente è quella di far configurare all'amministratore il metodo di autenticazione da utilizzare.

1. Nella finestra Mantieni sicuro il tuo account, è possibile selezionare il metodo da utilizzare per l'autenticazione MFA.  Microsoft Authenticator è una delle opzioni disponibili. Per comodità, in questo esercizio del lab si sceglierà un metodo diverso.  Selezionare **Desidero configurare un altro metodo**.  Nella finestra popup Scegli un metodo diverso, selezionare la **freccia giù** e selezionare **Telefono**, quindi selezionare **Conferma**.

1. La finestra visualizzata e i passaggi seguenti sono relativi al metodo dell'app Microsoft Authenticator. .
    1. Se nel dispositivo mobile è già installata l'app Microsoft Authenticator selezionare **Avanti**. In caso contrario, selezionare **Scarica adesso** e seguire la procedura.
    1. Si inizierà a configurare l'account.  Selezionare **Avanti**.
    1. Usando l'app Microsoft Authenticator nel dispositivo mobile, selezionare l'elemento per aggiungere un account e selezionare **Account aziendale o dell'istituto di istruzione**.**+**
    1. Selezionare l'opzione **Analizza il codice** a matrice, quindi usando il dispositivo mobile, analizzare il codice a matrice sullo schermo del PC.
    1. Usando l'app Microsoft Authenticator nel dispositivo mobile, eseguire la scansione del codice a matrice.
    1. Seguire i passaggi nel PC e nel dispositivo mobile, quindi selezionare **Avanti**.
    1. Dopo aver configurato le informazioni di sicurezza, verrà visualizzata una finestra Operazione completata.  Selezionare **Fatto**.

1. Ora è possibile accedere al portale di Azure.  Il portale di Azure è un portale di amministrazione Microsoft e pertanto richiede l'autenticazione a più fattori, in base al criterio di accesso condizionato che è stato creato.  
    1. Se viene visualizzato un messaggio che indica che l'accesso è scaduto, immettere la password e selezionare **Accedi**.
    1. Verrà visualizzata una finestra che richiede di approvare la richiesta di accesso.  Prendere nota del numero nel PC e seguire le istruzioni nell'app Microsoft Authenticator.
    1. Se viene richiesto se si vuole rimanere connessi, selezionare **No**.

1. Disconnettersi selezionando l'icona dell'utente accanto all'indirizzo di posta elettronica nell'angolo in alto a destra della schermata, quindi Disconnetti. Chiudere quindi tutte le finestre del browser.

### Revisione

In questo lab è stato presentato il processo di impostazione di un criterio di accesso condizionale che richiede agli utenti di effettuare l'autenticazione MFA quando accedono a qualsiasi portale di amministrazione Microsoft.  Quindi, in qualità di utente, è stata eseguita la procedura di registrazione per l'autenticazione MFA ed è stato illustrato l'effetto dei criteri di accesso condizionale che richiedono l'utilizzo dell'autenticazione MFA durante l'accesso al portale di Azure.
