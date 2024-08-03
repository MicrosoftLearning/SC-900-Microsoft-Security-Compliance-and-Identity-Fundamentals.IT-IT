---
lab:
  title: Reimpostazione della password self-service di Microsoft Entra
  module: Describe the authentication capabilities of Microsoft Entra ID
---

<!---
---
Lab: titolo: "Esplorare l'autenticazione di Azure AD con la reimpostazione della password self-service" Percorso di apprendimento/modulo/unità: "Percorso di apprendimento: Descrivere le funzionalità di Azure Active Directory (Azure AD), parte di Microsoft Entra; Modulo 2: descrivere le funzionalità di autenticazione di Azure AD; Unità 4: descrivere la reimpostazione della password self-service"
---
--->

# Lab: Reimpostazione della password self-service di Microsoft Entra

Questo lab corrisponde al contenuto di Learn seguente:

- Percorso di apprendimento: Descrivere le funzionalità di Microsoft Entra
- Modulo: Descrivere le funzionalità di autenticazione di Microsoft Entra ID
- Unità: Descrivere la reimpostazione della password self-service

## Scenario laboratorio

In questo lab, l'utente, in qualità di amministratore, seguirà il processo di aggiunta di un utente al gruppo di sicurezza per la reimpostazione della password self-service, già configurato nel tenant di Microsoft 365. Dopo l'abilitazione della reimpostazione della password self-service, si assumerà quindi il ruolo di un utente e si seguirà il processo di registrazione per la reimpostazione della password self-service e anche di reimpostazione della password.  Infine, l'utente, in qualità di amministratore, sarà in grado di visualizzare i log di controllo, i dati di utilizzo e le informazioni dettagliate per la reimpostazione della password self-service.

**Tempo stimato:** 15-20 minuti

### Attività 1

In questa attività, l'utente, in qualità di amministratore, esaminerà alcune delle impostazioni di configurazione disponibili per la reimpostazione della password self-service.

1. Apri il browser Microsoft Edge. Nella barra degli indirizzi, inserire **https://entra.microsoft.com** e accedere con le credenziali di amministratore di Microsoft 365 fornite dall'ALH (provider di servizi di hosting per i lab autorizzato)
    1. Nella finestra Accedi, immettere **admin@WWLxZZZZZZ.onmicrosoft.com** (dove ZZZZZZ è l'ID tenant univoco fornito dal proprio ALH) e quindi selezionare **Avanti**.
    1. Immettere la password di amministratore, che dovrebbe essere fornita dal proprio provider di hosting del lab. Fare clic su **Accedi**.
    1. Quando viene richiesto di rimanere connessi, selezionare **Sì**.

1. Nel riquadro di spostamento a sinistra, espandere l'opzione **Protezione**, quindi selezionare **Reimpostazione della password**.  

1. Verranno visualizzate le proprietà per la reimpostazione della password self-service. Selezionare l'icona delle informazioni accanto alla dicitura **Reimpostazione della password self-service abilitata** per visualizzare la descrizione. Assicurarsi che l'opzione **Selezionata** sia evidenziata in blu. Ora posizionare il cursore sull'icona di informazioni accanto a **Seleziona gruppo** e notare la dicitura "Definisce il gruppo di utenti autorizzati a reimpostare le proprie password". È necessario includere gli utenti nel gruppo, non è possibile selezionarli individualmente. Notare che esiste già un gruppo elencato: SSPRSecurityGroupUsers (questo gruppo è stato preconfigurato come parte del tenant di Microsoft 365). Infine, notare la casella di informazioni blu "Queste impostazioni si applicano solo agli utenti finali dell'organizzazione. Gli amministratori sono sempre abilitati per la reimpostazione della password self-service e devono utilizzare due metodi di autenticazione per reimpostare la propria password".

1. Nel riquadro di spostamento a sinistra di Reimpostazione della password, selezionare **Metodi di autenticazione**.

1. In Numero di metodi richiesti per la reimpostazione, selezionare **1**. Notare la casella di informazioni sullo schermo.

1. Notare i diversi metodi a disposizione degli utenti.  **La posta elettronica** e **il telefono** cellulare devono essere già controllati; in caso contrario, selezionarli.

1. Nel riquadro di spostamento a sinistra di Reimpostazione della password, selezionare **Registrazione**.  

1. Assicurarsi che l'impostazione "Richiedi agli utenti di registrarsi all'accesso" sia impostata su **Sì**.  Lasciare il valore predefinito **180** per il numero di giorni prima che agli utenti venga chiesto di riconfermare le informazioni di autenticazione.   Notare la casella di informazioni sulla pagina.

1. Dal riquadro di spostamento a sinistra di Reimpostazione della password, selezionare **Notifiche**.  

1. Assicurarsi che l'impostazione "Inviare notifiche agli utenti al momento della reimpostazione della password" sia impostata su **Sì**.  Lasciare l'impostazione Invia una notifica a tutti gli amministratori quando altri amministratori reimpostano la password su **No**.

1. Notare che il riquadro di spostamento Reimpostazione password include anche opzioni per visualizzare i log di controllo e di utilizzo e le informazioni dettagliate.

1. Chiudere la finestra di reimpostazione della password selezionando la **X** nell'angolo in alto a destra della finestra. Questo consente di ritornare all'interfaccia di amministrazione di Microsoft Entra.

1. Tenere aperta la finestra di Microsoft Entra.

### Attività 2

In questa attività, l'utente, in qualità di amministratore, aggiungerà al gruppo di sicurezza per la reimpostazione della password self-service l'utente creato nell'esercizio del lab precedente.

1. Aprire la scheda del browser sulla pagina iniziale dell'interfaccia di amministrazione di Microsoft Entra **[entra.microsoft.com](https://entra.microsoft.com)**. Se necessario, espandere **Identità**.

1. Nel riquadro di spostamento a sinistra, in "Identità", espandere **Gruppi** e selezionare **Tutti i gruppi**.

1. Verrà visualizzato un elenco dei gruppi esistenti. Nel campo Gruppi di ricerca, immettere **Reimpostazione della password self-service**, quindi, dai risultati della ricerca, selezionare **SSPRSecurityGroupUsers**.  Verrà visualizzata l'opzione di configurazione per questo gruppo.

1. Nel riquadro di spostamento a sinistra, selezionare **Membri**.

1. Nella parte superiore della pagina, selezionare **+ Aggiungi membri**.  

1. Nella casella di ricerca, immettere **Sara Perez**.  Una volta che l'utente, **Sara Perez**, appare sotto la casella di ricerca, selezionarlo e quindi premere **Seleziona** nella parte inferiore della pagina.  Questo riporterà alla pagina dei membri.  Selezionare **Aggiorna** dalla parte superiore della pagina. Ora Sara Perez sarà presente nell'elenco come membro del gruppo di sicurezza per la reimpostazione della password self-service.

1. Uscire da tutte le schede del browser facendo clic sull'icona dell'utente accanto all'indirizzo e-mail nell'angolo in alto a destra dello schermo. Quindi chiudere tutte le finestre del browser.

### Attività 3

In questa attività, l'utente Sara Perez dovrà eseguire il processo di registrazione per la reimpostazione della password self-service.  Questa attività richiede l'accesso a un dispositivo mobile in cui è possibile ricevere sms.

1. Aprire Microsoft Edge e nella barra degli indirizzi, immettere **https://login.microsoft.com**.

1. Accedere come Sara Perez.

1. Verrà visualizzato un messaggio popup in cui è indicato che sono necessarie ulteriori informazioni.  Questo perché, come membro del gruppo SSPRSecurityGroupUsers, la configurazione richiede che i propri membri si registrino quando effettuano l'accesso.  Seleziona il pulsante **Avanti**.  Nota: un'alternativa alla registrazione degli utenti è la configurazione diretta dei metodi di autenticazione da parte degli amministratori quando aggiungono un utente. Questo richiede che gli amministratori conoscano e impostino i numeri di telefono e gli indirizzi di posta elettronica usati dagli utenti per la reimpostazione della password self-service e che reimpostino la password di un utente.

1. Viene visualizzata la pagina "Proteggi l'account".  La finestra visualizzata è per il metodo Phone.
    1. Viene richiesta l'immissione di un numero di telefono. Verificare che l'opzione **Ricevi un codice** sia abilitata.   Immettere il numero di telefono in cui è possibile ricevere il codice e selezionare **Avanti**.  
    1. Si apre una nuova finestra, la quale indica che è stato inviato un codice al numero di telefono immesso.  Immettere il codice ricevuto e selezionare **Avanti**. Viene visualizzata una finestra che indica che il telefono è stato registrato. Selezionare ****Avanti** e quindi Fine**.  
    1. Se invece si vuole usare la posta elettronica, selezionare Desidero configurare **un metodo** diverso e seguire la procedura. 

1. È ora possibile completare l'accesso. Se si nota che il tempo per l'accesso è scaduto, immettere nuovamente la password.

1. Uscire da tutte le schede del browser facendo clic sull'icona dell'utente accanto all'indirizzo e-mail nell'angolo in alto a destra dello schermo. Quindi chiudere tutte le finestre del browser.

### Attività 4 (facoltativa)

In questa attività, l'utente Sara Perez dovrà eseguire il processo di reimpostazione della password.

1. Aprire Microsoft Edge.

1. Nella barra degli indirizzi, immettere **https://login.microsoftonline.com**.

1. Accedere come Sara Perez, inserendo l'e-mail **sara@WWLxZZZZ.onmicrosoft.com** (dove ZZZZZZ è l'ID tenant univoco fornito dal provider di hosting del lab) e selezionare il pulsante **Avanti**. Potrebbe invece essere visualizzata la finestra Scegli un account, in tal caso, selezionare l'account di Sara Perez.

1. Nella finestra Inserisci password, selezionare **Password dimenticata**.

1. Viene visualizzata la finestra Recupera l'accesso al tuo account.   Verificare che l'e-mail di Sara Perez, sara@WWLxZZZZ.onmicrosoft.com, sia visualizzato nella casella e-mail o nome utente.  In caso contrario, immetterlo.  

1. Nella casella vuota, immettere i caratteri visualizzati nell'immagine o le parole dell'audio. Una volta effettuata questa operazione, selezionare **Avanti**.

1. Viene visualizzata la schermata Recupera l'accesso al tuo account che mostra il passaggio di verifica 1 > scegli una nuova password. Lasciare l'impostazione predefinita **Invia SMS sul telefono cellulare**.  Viene richiesta l'immissione del proprio numero di telefono cellulare.  Una volta effettuata questa operazione, selezionare il **pulsante SMS**. 

1. Immettere il codice di verifica e quindi selezionare **Avanti**.

1. Nella schermata successiva verranno richieste l'immissione della nuova password e la sua conferma.  Immetterle ora e selezionare il pulsante **Fine**.

1. Nella schermata comparirà un messaggio che indica che la password è stata reimpostata.  Selezionare **fai clic qui** per accedere con la nuova password.

1. Nella casella di informazioni Selezionare un account scegliere **sara@WWLxZZZZZZ.onmicrosoft.com**, immettere la nuova password e quindi selezionare il pulsante **Accedi**.  Se viene richiesto se si vuole rimanere connessi, selezionare **No**.

1. A questo momento si dovrebbe accedere all'account Microsoft di Sara.

1. Disconnettersi selezionando l'icona utente accanto all'indirizzo e-mail nell'angolo in alto a destra dello schermo e selezionando **Esci**. Chiudere quindi tutte le finestre del browser

### Attività 5 (facoltativa)

In questa attività, in qualità di amministratore, si vedranno i log di controllo e i dati di Utilizzo e informazioni dettagliate associati alla reimpostazione della password

1. Aprire Microsoft Edge.

1. Nella barra degli indirizzi, inserire **https://entra.microsoft.com** e accedere con le credenziali di amministratore di Microsoft 365 fornite dall'ALH (provider di servizi di hosting per i lab autorizzato)

1. Ci si trova nell'interfaccia di amministrazione di Microsoft Entra.  Nel riquadro di spostamento a sinistra, espandere l'opzione **Protezione**, quindi selezionare **Reimpostazione della password**.

1. Nel riquadro di spostamento a sinistra, selezionare **Log di controllo**.  Notare le informazioni e i filtri disponibili.  Notare inoltre che è possibile scaricare i log.  

1. Selezionare **Download**.  È possibile effettuare il download in formato CSV o JSON.  Chiudere la finestra selezionando la **X** nell'angolo in alto a destra dello schermo.

1. Nel riquadro di spostamento a sinistra, selezionare **Utilizzo e informazioni dettagliate**.

1. Notare le informazioni disponibili che riguardano la Registrazione.  Notare che potrebbe essere necessario qualche minuto per aggiornare questi dati, anche dopo aver effettuato un aggiornamento, quindi i dati di registrazione o di utilizzo dell'attività precedente potrebbero ancora non essere riflessi.

1. Nella parte superiore della pagina, selezionare **Utilizzo** per visualizzare il numero di reimpostazioni della password self-service e di sblocchi dell'account in base al metodo.  Notare che potrebbe essere necessario qualche minuto per aggiornare questi dati, anche dopo l'aggiornamento, quindi i dati di utilizzo dell'attività precedente potrebbero non essere ancora riflessi.

1. Chiudere le schede aperte del browser.

### Revisione

In questo lab, l'utente, in qualità di amministratore, ha seguito il processo di abilitazione della reimpostazione della password self-service. Dopo l'abilitazione della reimpostazione della password self-service, si è assunto quindi il ruolo di un utente per seguire il processo di registrazione per la reimpostazione della password self-service e anche di reimpostazione della password.  Infine, in qualità di amministratore, è stato appreso come accedere ai log di controllo e ai dati di utilizzo e informazioni dettagliate per la reimpostazione della password self-service.
