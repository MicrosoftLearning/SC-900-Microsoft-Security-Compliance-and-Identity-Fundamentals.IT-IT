<!---
---
Lab: Title: 'Explore Autenticazione di Azure AD with self-service password reset' Learning Path/Module/Unit: 'Learning Path: Describe the capabilities of Azure Active Directory (Azure AD), part of Microsoft Entra; Modulo 2: Descrivere le funzionalità di autenticazione di Azure AD; Unità 4: Descrivere la password self-service'
---
--->

# Lab: Microsoft Entra reimpostazione della password self-service

Questo lab corrisponde al contenuto di Learn seguente:

- Percorso di apprendimento: Descrivere le funzionalità di Microsoft Entra
- Modulo: Descrivere le funzionalità di autenticazione di Microsoft Entra ID
- Unità: Descrivere la reimpostazione della password self-service

## Scenario del lab

In questo lab, l'utente, come amministratore, illustrerà il processo di aggiunta di un utente al gruppo di sicurezza della reimpostazione della password self-service, che è già configurato nel tenant di Microsoft 365. Dopo l'abilitazione della reimpostazione della password self-service, si assumerà quindi il ruolo di un utente e si seguirà il processo di registrazione per la reimpostazione della password self-service e anche di reimpostazione della password.  Infine, in qualità di amministratore, sarà possibile visualizzare i log di controllo, i dati di utilizzo e le informazioni dettagliate per la reimpostazione della password self-service.

**Tempo stimato**: 15-20 minuti

### Attività 1

In questa attività, come amministratore, verranno illustrate alcune delle impostazioni di configurazione disponibili per la reimpostazione della password self-service.

1. Aprire il browser Microsoft Edge. Nella barra degli indirizzi immettere **https://entra.microsoft.com** e accedere con le credenziali di amministratore di Microsoft 365 fornite dall'host del lab autorizzato (ALH).
    1. Nella finestra Accedi immettere **admin@WWLxZZZZZZ.onmicrosoft.com** (dove ZZZZZZ è l'ID tenant univoco fornito dall'ALH) e quindi selezionare **Avanti**.
    1. Immettere la password di amministratore, che dovrebbe essere fornita dal proprio provider di hosting del lab. Fare clic su **Accedi**.
    1. Quando compare la domanda se rimanere connessi, selezionare **Sì**.

1. Nel riquadro di spostamento a sinistra espandere l'opzione **Protezione** e quindi selezionare **Reimpostazione password**.  

1. Vengono visualizzate le proprietà per la reimpostazione della password self-service. Selezionare l'icona delle informazioni accanto alla posizione in cui viene visualizzata la **reimpostazione della password self-services abilitata** per visualizzare la descrizione. Assicurarsi che **Selected** sia evidenziato in blu. Posizionare ora il cursore sull'icona delle informazioni accanto alla posizione in cui viene indicato **Seleziona gruppo** e notare che viene indicato "Definisce il gruppo di utenti autorizzati a reimpostare le proprie password". Occorre includere gli utenti nel gruppo, non è possibile selezionare gli utenti individualmente. Si noti che esiste già un gruppo elencato: SSPRSecurityGroupUsers (questo gruppo è stato preconfigurato come parte del tenant di Microsoft 365). Infine, notare la casella blu di informazioni "Queste impostazioni si applicano solo agli utenti finali dell'organizzazione. Gli amministratori sono sempre abilitati per la reimpostazione della password self-service e devono usare due metodi di autenticazione per reimpostare la propria password".

1. Dal riquadro di spostamento sinistro di Reimpostazione della password, selezionare **Metodi di autenticazione**.

1. In Numero di metodi da reimpostare, selezionare **1**. Notare la casella di informazioni nella schermata.

1. Osservare i diversi metodi disponibili per gli utenti.  **E-mail** e **Cellulare (solo SMS)** dovrebbero essere già selezionati; in caso contrario, selezionarli.

1. Dal riquadro di spostamento sinistro di Reimpostazione della password, selezionare **Registrazione**.  

1. Assicurarsi che l'opzione Richiedere agli utenti di registrarsi all'accesso sia impostata su **Sì**.  Lasciare l'opzione Numero di giorni prima che agli utenti venga chiesto di riconfermare le informazioni di autenticazione impostata sul valore predefinito 180.   Notare la casella di informazioni nella pagina.

1. Dal riquadro di spostamento sinistro di Reimpostazione della password, selezionare **Notifiche**.  

1. Assicurarsi che l'opzione Notificare agli utenti le reimpostazioni delle password sia impostata su **Sì**.  Lasciare l'opzione Notificare agli amministratori quando altri amministratori reimpostano le proprie password impostata su No.

1. Notare come il riquadro di spostamento di Reimpostazione della password include anche le opzioni per visualizzare i log di audit e l'utilizzo e le informazioni dettagliate.

1. Chiudere la finestra di reimpostazione della password selezionando la **X** nell'angolo superiore destro della finestra. Verrà visualizzata l'interfaccia di amministrazione di Microsoft Entra.

1. Mantenere aperta la finestra di Microsoft Entra.

### Attività 2

In questa attività, come amministratore, aggiungerà l'utente creato nell'esercizio di lab precedente al gruppo di sicurezza della reimpostazione della password self-service.

1. Aprire la scheda del browser per la home page del entra.microsoft.com centrale **[Microsoft Entra Amministrazione](https://entra.microsoft.com)**. Se necessario, espandere **Identità**.

1. Nel pannello di spostamento a sinistra, in "Identità", espandere **Gruppi** e quindi selezionare **Tutti i gruppi**.

1. Viene visualizzato un elenco dei gruppi esistenti. Nel campo Cerca gruppi, immettere **SSPR**, quindi selezionare **SSPRSecurityGroupUsers** dai risultati della ricerca.  Si passerà all'opzione di configurazione per questo gruppo.

1. Dal riquadro di spostamento sinistro, selezionare **Membri**.

1. Dalla parte superiore della pagina, selezionare **+ Aggiungi membri**.  

1. Nella casella Cerca immettere **Sara Perez**.  Quando l'utente **Sara Perez** viene visualizzato sotto la casella di ricerca, selezionarlo e quindi premere **Seleziona** nella parte inferiore della pagina.  Si tornerà alla pagina dei membri.  Selezionare **Aggiorna** nella parte superiore della pagina. Sara Perez dovrebbe essere elencata come membro del gruppo di sicurezza della reimpostazione della password self-service.

1. Disconnettersi da tutte le schede del browser selezionando l'icona dell'utente accanto all'indirizzo e-mail nell'angolo in alto a destra della schermata. Quindi, chiudere tutte le finestre del browser.

### Attività 3

In questa attività, come utente Sara Perez, eseguirà il processo di registrazione per la reimpostazione della password self-service.  Questa attività richiede l'accesso a un dispositivo mobile su cui ricevere SMS o l'accesso a un account di posta elettronica personale

1. Aprire Microsoft Edge e nella barra degli indirizzi immettere **https://login.microsoft.com**.

1. Accedi come Sara Perez.

1. Viene visualizzato un popup che segnala che sono necessarie altre informazioni.  Questo perché, come membro del gruppo SSPRSecurityGroupUsers, la configurazione richiede che i propri membri si registrino quando effettuano l'accesso.  Selezionare il pulsante **Avanti**.  Nota:  un'alternativa alla registrazione da parte degli stessi utenti è rappresentata dalla configurazione dei metodi di autenticazione direttamente da parte degli amministratori al momento dell'aggiunta di un utente. Questo richiede che gli amministratori conoscano e impostino i numeri di telefono e gli indirizzi di posta elettronica usati dagli utenti per la reimpostazione della password self-service e che reimpostino la password di un utente.

1. Si apre la pagina "Proteggi l'account".  La finestra che compare riguarda il metodo di autenticazione per il telefono; se non possiede un dispositivo mobile in grado di ricevere messaggi di testo, andare al passaggio successivo.  Viene richiesta l'immissione di un numero di telefono. Assicurarsi che l'opzione **Invia un SMS** sia abilitata.   Immettere il numero di telefono in cui è possibile ricevere un codice di testo e selezionare il pulsante **Avanti**.  Si apre una nuova finestra, la quale indica che è stato inviato un codice al numero di telefono immesso.  Immettere il codice ricevuto e selezionare **Avanti**. Si apre una finestra che indica la corretta esecuzione e che mostra il metodo di accesso predefinito.  Selezionare **Fine**.  
    1. In alternativa, è possibile configurare un metodo diverso, come illustrato in basso a sinistra nella finestra.  Se si sceglie di configurare un metodo diverso, selezionare **Si vuole configurare un metodo diverso**. Viene visualizzata una finestra popup con la domanda Specificare il metodo da usare.  Nell'elenco a discesa, selezionare il metodo preferito, **Posta elettronica** e quindi selezionare il pulsante **Conferma**.  Immettere l'indirizzo e-mail da usare, quindi selezionare **Avanti**.  Si apre una nuova finestra, la quale indica che è stato inviato un codice all'indirizzo di posta elettronica immesso.  Accedere all'e-mail immessa per ottenere il codice.  Immettere il codice ricevuto e selezionare **Avanti**. Si apre una finestra che indica la corretta esecuzione e che mostra il metodo di accesso predefinito.  Selezionare **Fine**.

1. È ora possibile completare l'accesso. Se si noterà che il tempo di accesso è scaduto, immettere di nuovo la password.

1. Disconnettersi da tutte le schede del browser selezionando l'icona dell'utente accanto all'indirizzo e-mail nell'angolo in alto a destra della schermata. Quindi, chiudere tutte le finestre del browser.

### Attività 4 (facoltativa)

In questa attività, come utente Sara Perez, passerà attraverso il processo di reimpostazione della password

1. Aprire Microsoft Edge.

1. Nella barra degli indirizzi immettere **https://login.microsoftonline.com**.

1. Accedere come Sara Perez, immettendo il messaggio di posta elettronica **sara@WWLxZZZZ.onmicrosoft.com** (dove ZZZZZZ è l'ID tenant univoco fornito dal provider di hosting lab) e selezionare il pulsante **Avanti** . È invece possibile visualizzare una finestra Seleziona un account aperta, in tal caso, selezionare l'account per Sara Perez.

1. Dalla finestra Immetti password, selezionare **Ho dimenticato la password**.

1. Si apre la finestra Ripristina l'accesso al tuo account.   Verificare che il messaggio di posta elettronica per Sara Perez, , sia visualizzato nella casella email o username .Verify that the email for Sara Perez, sara@WWLxZZZZ.onmicrosoft.com, is shown in the email or username box.  In caso contrario, immetterlo.  

1. Nella casella vuota, immettere i caratteri visualizzati nell'immagine o le parole dell'audio. Una volta effettuata questa operazione, selezionare **Avanti**.

1. La schermata mostra Ripristina l'accesso al tuo account e il passaggio di verifica 1 > scegliere una nuova password. Lasciare l'impostazione predefinita **Invia SMS sul telefono cellulare**.  Viene richiesta l'immissione del proprio numero di telefono cellulare.  Una volta effettuata questa operazione, selezionare il **pulsante SMS**.  Se durante la registrazione è stata selezionata la posta elettronica come metodo, nella finestra Ripristina l'accesso al tuo account verrà indicato che si riceverà un messaggio di posta elettronica contenente un codice di verifica all'indirizzo di posta elettronica alternativo.  Selezionare **E-mail**.

1. Immettere il codice di verifica, quindi premere **Avanti**.

1. Nella schermata successiva verranno richieste l'immissione della nuova password e la sua conferma.  Eseguire queste operazioni e selezionare il pulsante **Fine**.

1. Nella schermata comparirà un messaggio che indica che la password è stata reimpostata.  Selezionare **fare clic qui** per accedere con la nuova password.

1. Nella casella di informazioni Selezionare un account scegliere **sara@WWLxZZZZZZ.onmicrosoft.com** , immettere la nuova password e quindi selezionare il pulsante **Accedi**.  Se viene richiesto se si vuole rimanere connessi, selezionare **No**.

1. A questo punto ci si dovrebbe trovare nel portale di Office.

1. Disconnettersi selezionando l'icona dell'utente accanto all'indirizzo e-mail nell'angolo in alto a destra della schermata, quindi **Disconnetti**. Infine, chiudere tutte le finestre del browser.

### Attività 5 (facoltativa)

In questa attività, in qualità di amministratore, si vedranno i log di controllo e i dati di Utilizzo e informazioni dettagliate associati alla reimpostazione della password

1. Aprire Microsoft Edge.

1. Nella barra degli indirizzi immettere **https://entra.microsoft.com** e accedere con le credenziali di amministratore di Microsoft 365 fornite dall'host del lab autorizzato (ALH).

1. Si è in Microsoft Entra interfaccia di amministrazione.  Nel riquadro di spostamento a sinistra espandere l'opzione **Protezione** e quindi selezionare **Reimpostazione password**.

1. Dal riquadro di spostamento sinistro, selezionare **Log di controllo**.  Notare le informazioni e i filtri disponibili.  Inoltre, notare che è possibile scaricare i log.  

1. Selezionare **Download**.  Notare che è possibile formattare il download come CSV o JSON.  Chiudere la finestra selezionando la **X** nell'angolo in alto a destra della schermata.

1. Dal riquadro di spostamento sinistro, selezionare **Utilizzo e informazioni dettagliate**.

1. Notare le informazioni disponibili relative alla registrazione.  L'aggiornamento di questi dati potrebbe richiedere del tempo, anche dopo aver selezionato Aggiorna, quindi potrebbero non rispecchiare ancora i dati di registrazione o di utilizzo dell'attività precedente.

1. In cima alla pagina, selezionare **Utilizzo** per visualizzare il numero di reimpostazioni di password self-service e di sblocchi di account in base al metodo.  L'aggiornamento di questi dati potrebbe richiedere del tempo, anche dopo aver selezionato Aggiorna, quindi potrebbero non rispecchiare ancora i dati di utilizzo dell'attività precedente.

1. Chiudere le schede del browser aperte.

### Verifica

In questo lab, in qualità di amministratore, si è appreso il processo di abilitazione della reimpostazione della password self-service. Dopo l'abilitazione della reimpostazione della password self-service, si è assunto quindi il ruolo di un utente per seguire il processo di registrazione per la reimpostazione della password self-service e anche di reimpostazione della password.  Infine, in qualità di amministratore, si è appreso dove accedere ai log di controllo e ai dati di utilizzo e le informazioni dettagliate per la reimpostazione della password self-service.
