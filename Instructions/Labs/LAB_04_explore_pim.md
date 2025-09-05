---
lab:
  title: Esplorare Privileged Identity Management
  module: Describe the identity protection and governance capabilities of Microsoft Entra
---

# Lab: Esplorare Privileged Identity Management

Questo lab corrisponde al contenuto di Learn seguente:

- Percorso di apprendimento: Descrivere le funzionalità di Microsoft Entra
- Modulo: Descrivere le funzionalità di governance e di protezione delle identità di Microsoft Entra
- Descrivere le funzionalità di Privileged Identity Management

## Scenario laboratorio

In questo lab, si esploreranno alcune delle funzionalità di base di Privileged Identity Management (PIM). PIM richiede licenze P2 per Microsoft Entra ID.  In questo lab, l'amministratore configurerà uno degli utenti, Diego Siciliani, con un ruolo di amministratore utente di Microsoft Entra, tramite Privileged ID Management (PIM).   Con i privilegi di amministratore utente, Diego sarà in grado di creare licenze di gestione per utenti e gruppi e altro ancora.  Sia l'amministratore che l'utente, Diego, devono essere configurati per le licenze P2 di Microsoft Entra ID.

**Tempo stimato**: 60 minuti

### Attività 1

In questa attività, in qualità di amministratore, reimpostare la password per l'utente Diego Siciliani. Questo passaggio è necessario per poter accedere, inizialmente come utente, alle attività successive.

1. Aprire Microsoft Edge.  Nella barra degli indirizzi, immettere **https://entra.microsoft.com**.

1. Accedere con le credenziali di amministratore di Microsoft 365 fornite dall'ALH.
    1. Nella finestra Accedi, immettere **admin@WWLxZZZZZZ.onmicrosoft.com** (dove ZZZZZZ è l'ID tenant univoco fornito dal proprio ALH) e quindi selezionare **Avanti**.
    1. Immettere la password di amministratore, che dovrebbe essere fornita dal proprio provider di hosting del lab. Fare clic su **Accedi**.
    1. A seconda dell'host del lab e se è la prima volta che si esegue l'accesso al tenant, potrebbe essere richiesto di completare il processo di registrazione dell'autenticazione a più fattori. In tal caso, seguire le istruzioni visualizzate sullo schermo per configurare l'autenticazione a più fattori.
    1. Dopo aver eseguito l'accesso, viene visualizzata la pagina interfaccia di amministrazione di Microsoft 365.

1. Nel pannello di spostamento a sinistra espandere **Identità**, **Utenti**, quindi selezionare **Tutti gli utenti**.

1. Selezionare **Diego Siciliani** dall'elenco di utenti.

1. Selezionare **Reimposta password** nella parte superiore della pagina. Poiché non è stato effettuato l'accesso come Diego in precedenza, non si conosce la sua password e sarà quindi necessario reimpostarla.

1. Nella pagina Reimpostazione password selezionare **Reimposta password**.  IMPORTANTE: prendere nota della nuova password, perché servirà in un'attività successiva per poter accedere come utente.

1. Dal riquadro di spostamento a sinistra, selezionare **Home** per tornare alla pagina dell'Interfaccia di amministrazione di Microsoft Entra.

1. Tenere aperta la pagina del browser perché verrà usata nelle attività successive.

### Attività 2

In questa attività, in qualità di amministratore, assegnerà a Diego un ruolo di ID Entra Microsoft in Privileged Identity Management.

1. Aprire la scheda del browser per raggiungere la home page dell'interfaccia di amministrazione di Microsoft Entra.

1. Nel pannello di spostamento a sinistra espandere **IF Governance**, quindi selezionare **Privileged Identity Management**.

1. Ora ci si trova nella finestra di avvio rapido di Privileged Identity Management. Rivedere le informazioni nella pagine Attività iniziali. Nella finestra principale, in cui è indicato Gestisci accesso, selezionare **Gestisci**.

1. Ora ci si trova nella pagina Ruoli di Contoso.  Nella barra di ricerca della parte superiore della pagina, immettere **Utente**.  Dai i risultati della ricerca, selezionare **Amministratore utenti**.

1. Nella parte superiore della pagina, selezionare **+ Aggiungi assegnazioni**.

1. Nella pagina Aggiungi assegnazioni, verificare che la voce **Appartenenza** sia sottolineata.  Qui verranno configurate le impostazioni di appartenenza per il ruolo di amministratore utenti in PIM.

1. Mantenere il tipo di ambito sul valore predefinito, Directory.  

1. In Seleziona membri, selezionare **Nessun membro selezionato**. Verrà visualizzata la finestra Seleziona un membro.

1. Nella barra di ricerca, immettere **Diego**.  Nei risultati della ricerca selezionare **Diego Siciliani** e quindi premere **Seleziona** nella parte inferiore della pagina.  

1. In Seleziona membri si vedrà 1 membro selezionato e il nome e l'indirizzo di posta elettronica del membro selezionato, Diego Siciliani. Nella parte inferiore della pagina Aggiungi assegnazioni, selezionare **Avanti**.  

1. Ora ci si trova nella pagina Impostazione.  Lasciare il tipo di Assegnazione all'impostazione predefinita: Idoneo.

1. Se la casella Idoneo in modo permanente è selezionata, selezionare **Idoneo in modo permanente** per rimuovere il segno di spunta.

1. Nei campi Inizio assegnazione, tenere la data e l'ora predefinite, ovvero oggi e l'ora corrente.

1. Nei campi Fine assegnazione, modificare la data in data odierna (notare che il valore predefinito è impostato a un anno dalla data odierna, quindi è necessario modificare l'anno). Per quanto riguarda l'ora, impostarla a due ore dall'ora corrente. Dopo aver impostato il valore del campo Ora sull'ora in cui termina l'assegnazione, premere il tasto Tab sulla tastiera e selezionare **Assegna** nella parte inferiore della pagina.  

1. Si verrà reindirizzati di nuovo alla finestra Assegnazioni.  Dopo qualche secondo, Diego Siciliani sarà presente nell'elenco della tabella Amministratore utenti, insieme ai dettagli dell'assegnazione. Se dopo qualche secondo l'aggiornamento non viene ancora visualizzato, selezionare **Aggiorna** nella parte superiore della pagina.

1. Nella parte superiore della pagina, selezionare **Impostazioni**.

1. In Dettagli dell'impostazione del ruolo per Amministrazione utente, notare le diverse opzioni.  Notare che l'impostazione "Richiedi motivazione all'attivazione" è impostata su "Sì" e anche "Richiedere Azure MFA all'attivazione" è impostata su "Sì".  Queste impostazioni saranno entrambe visibili nell'attività successiva, quando Diego attiverà il ruolo.  Si noti anche che l'opzione "Richiedi l'approvazione per l'attivazione" è impostata su No.  Lasciare i valori predefiniti per tutte le impostazioni.  Chiudere la pagina selezionando la **X** nell'angolo superiore a destra dello schermo.

1. Disconnettersi selezionando l'icona dell'utente accanto all'indirizzo e-mail nell'angolo in alto a destra della schermata, quindi **Disconnetti**. Chiudere quindi tutte le finestre del browser.

### Attività 3

In questa attività, l'utente, in qualità di Diego Siciliani, effettuerà l'accesso all'interfaccia di amministrazione di Microsoft Entra, per accedere alla funzionalità Privileged Identity Management di Microsoft Entra e attivare la propria assegnazione di Amministratore utente.  Una volta attivata, si apporteranno alcune modifiche alla configurazione di un utente esistente. Nota: per questa attività, è necessario accedere a un dispositivo mobile da usare con l'app Microsoft Authenticator.

1. Aprire Microsoft Edge.  Nella barra degli indirizzi del browser, immettere **entra.microsoft.com**.

1. Accedere come Diego Siciliani.
    1. Nella finestra Accedi immettere **DiegoS@WWLxZZZZZZ.onmicrosoft.com** (dove ZZZZZZ è l'ID tenant univoco fornito dal proprio provider di hosting del lab) e quindi selezionare **Avanti**.
    1. Immettere la password temporanea annotata nell'attività precedente, quindi selezionare **Accedi**.  Fare clic su **Accedi**.
    1. Poiché la password immessa era una password temporanea, ora occorre aggiornarla. Immettere la password corrente, immettere una nuova password, quindi confermare la nuova password.  Prendete nota della nuova password, che servirà per completare l'operazione.
    1. Poiché questa è la prima volta che si esegue l'accesso come Diego, potrebbe essere richiesto di configurare MFA. Seguire le istruzioni visualizzate sullo schermo per configurare l'autenticazione a più fattori.
    1. Quando viene richiesto di rimanere connessi, selezionare **Sì**.

1. L'accesso all'interfaccia di amministrazione di Microsoft Entra dovrebbe essere completato.
1. Nel pannello di spostamento a sinistra espandere **Governance ID** e quindi selezionare **Privileged Identity Management**.
1. Dal riquadro di spostamento a sinistra, selezionare **I miei ruoli**.  Verranno visualizzate le informazioni relative alle assegnazioni idonee.  Si vedrà che all'utente Diego è stato assegnato il ruolo di amministratore utenti.  
1. Nell'ultima colonna della tabella, etichettata come azione, selezionare **Attiva**.
1. Verrà visualizzata un'icona di avviso che indica che è necessaria una verifica aggiuntiva.  Selezionare **Fai clic per continuare**.  Ricordare che le impostazioni di PIM per il ruolo di amministratore utenti richiedono l'autenticazione a più fattori.  Inoltre, poiché le informazioni di contatto di Diego per l'utilizzo di MFA (metodi di autenticazione) non sono state configurate in precedenza, è necessario registrarle per poter usare l'autenticazione MFA.  Anche se Diego dovrà effettuare l'autenticazione MFA a ogni accesso come amministratore utenti, il processo di registrazione MFA è richiesto una sola volta durante il periodo di assegnazione.
1. La finestra visualizzata e i passaggi seguenti sono relativi al metodo dell'app Microsoft Authenticator. .
    1. Se nel dispositivo mobile è già installata l'app Microsoft Authenticator selezionare **Avanti**. In caso contrario, selezionare **Scarica adesso** e seguire la procedura.
    1. Si inizierà a configurare l'account.  Selezionare **Avanti**.
    1. Usando l'app Microsoft Authenticator nel dispositivo mobile, selezionare l'elemento per aggiungere un account e selezionare **Account aziendale o dell'istituto di istruzione**.**+**
    1. Selezionare l'opzione **Analizza il codice** a matrice, quindi usando il dispositivo mobile, analizzare il codice a matrice sullo schermo del PC.
    1. Usando l'app Microsoft Authenticator nel dispositivo mobile, eseguire la scansione del codice a matrice.
    1. Seguire i passaggi nel PC e nel dispositivo mobile, quindi selezionare **Avanti**.
    1. Dopo aver configurato le informazioni di sicurezza, verrà visualizzata una finestra Operazione completata.  Selezionare **Fatto**.

1. Dopo aver completato il processo di registrazione dell'autenticazione a più fattori, si torna alla pagina Amministratore utenti attivi PIM.
1. Verrà visualizzata la finestra Attiva amministratore utente.  È necessario immettere un motivo per l'attivazione.  Nella casella visualizzata, inserire il motivo desiderato (massimo 500 caratteri), quindi selezionare **Attiva**.
1. Durante l'elaborazione dell'attivazione verrà visualizzato il relativo stato (3 stadi di avanzamento).
1. Una volta completata l'attivazione, si torna ai ruoli personali | Pagina dei ruoli ID di Microsoft Entra, in cui verrà visualizzata una notifica che informa che è stato attivato un ruolo.  Selezionare **Fai clic qui** per visualizzare i ruoli attivi.  Se si nota che l'ora di fine è diversa da quella originariamente configurata, selezionare il pulsante di aggiornamento nella parte superiore della pagina (l'aggiornamento potrebbe richiedere alcuni minuti).
1. Tornare alla pagina iniziale dell'interfaccia di amministrazione di Microsoft Entra selezionando **Home** dal riquadro di spostamento a sinistra. 
1. In qualità di amministratore utente di Microsoft Entra ID, è possibile creare utenti e gruppi, gestire licenze e altro ancora. Nel pannello di spostamento sinistro espandere **Identità**, selezionare **Utenti**.
1. Dall'elenco degli utenti, selezionare **Bianca Pisani**.
1. Dal riquadro di spostamento a sinistra, selezionare **Gruppi**.
1. Si notino i gruppi a cui Bianca è già assegnato. Nella parte superiore della pagina selezionare **+ Appartenenze**.
1. Nell'elenco dei gruppi selezionare **Mark 8 Project Team(Contrassegna 8 Team** progetto).
1. Nella parte inferiore della pagina selezionare **Seleziona**.
1. Nella pagina Gruppi si noti che il gruppo Mark 8 Project Team è stato aggiunto all'elenco (se non viene visualizzato immediatamente, selezionare il **pulsante Aggiorna** ).
1. Disconnettersi selezionando l'icona dell'utente accanto all'indirizzo e-mail nell'angolo in alto a destra della schermata, quindi **Disconnetti**. Chiudere quindi tutte le finestre del browser.
1. La durata del ruolo di Amministratore utente è limitata al tempo configurato.

### Revisione

In questo lab, si è esplorato PIM.  L'utente, in qualità di amministratore, ha configurato Diego con i privilegi di amministratore utente per un determinato periodo di tempo.  Quindi, come Diego, ha illustrato il processo di attivazione dei privilegi di amministratore utente e di un utente a un gruppo.  Tenere presente che PIM richiede licenze Microsoft Entra ID Premium P2.
