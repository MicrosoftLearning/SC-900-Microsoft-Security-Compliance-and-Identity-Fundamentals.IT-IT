<!---
---
Lab: Title: 'Explore Privileged Identity Management. ' Percorso di apprendimento/Modulo/Unità: 'Percorso di apprendimento: Descrivere le funzionalità di Microsoft Entra; Modulo 4: Descrivere le funzionalità di protezione delle identità e governance di Microsoft Entra; Unità 4: Descrivere le funzionalità di Privileged Identity Management'
---
--->

# Lab: Esplorare Privileged Identity Management

Questo lab corrisponde al contenuto di Learn seguente:

- Percorso di apprendimento: Descrivere le funzionalità di Microsoft Entra
- Modulo: Descrivere le funzionalità di protezione delle identità e governance di Microsoft Entra
- Descrivere le funzionalità di Privileged Identity Management

## Scenario del lab

In questo lab, si esploreranno alcune delle funzionalità di base di Privileged Identity Management (PIM). PIM richiede licenze Microsoft Entra ID P2.  In questo lab, l'amministratore configurerà uno degli utenti, Diego Siciliani, con un ruolo di amministratore utente Microsoft Entra tramite Privileged ID Management (PIM).   Attraverso i privilegi di amministratore, Diego riuscirà a creare utenti e gruppi, gestire licenze e altro ancora.  Sia l'amministratore che l'utente, Diego, devono essere configurati per la licenza Microsoft Entra ID P2.

**Tempo stimato**: 45-60 minuti

### Attività 1

In questa attività, in qualità di amministratore, si reimposterà la password per l'utente Diego Siciliani. Questo passaggio è necessario in modo da poter effettuare l'accesso iniziale come utente nelle attività successive.

1. Aprire Microsoft Edge.  Nella barra degli indirizzi immettere **https://entra.microsoft.com**.

1. Accedere con le credenziali di amministratore di Microsoft 365 fornite da ALH.
    1. Nella finestra Accedi immettere **admin@WWLxZZZZZZ.onmicrosoft.com** (dove ZZZZZZ è l'ID tenant univoco fornito dall'ALH) e quindi selezionare **Avanti**.
    1. Immettere la password di amministratore, che dovrebbe essere fornita dal proprio provider di hosting del lab. Fare clic su **Accedi**.
    1. Quando compare la domanda se rimanere connessi, selezionare **Sì**.

1. Nel pannello di spostamento a sinistra espandere **Identità**, espandere **Utenti**, quindi selezionare **Tutti gli utenti**.

1. Selezionare **Diego Siciliani** dall'elenco degli utenti.

1. Selezionare **Reimposta password** in cima alla pagina. Poiché non è stato effettuato l'accesso come Diego in precedenza, non si conosce la sua password e sarà quindi necessario reimpostarla.

1. All'apertura della finestra Reimposta password, selezionare **Reimposta password**.  IMPORTANTE: prendere nota della nuova password, perché servirà in un'attività successiva per poter accedere come utente.

1. Nel pannello di spostamento a sinistra selezionare **Home** per restituire la home page per l'interfaccia di amministrazione di Microsoft Entra.

1. Tenere aperta la pagina del browser perché verrà usata nelle attività successive.

### Attività 2

In questa attività, in qualità di amministratore si assegnerà a Diego un ruolo di Azure AD in Privileged Identity Management.

1. Aprire la scheda del browser per la home page dell'interfaccia di amministrazione Microsoft Entra.

1. Nel pannello di spostamento a sinistra, in "Identità", espandere **Identity Governance** e quindi selezionare **Privileged Identity Management**.

1. Si è ora nella pagina di avvio rapido Privileged Identity Management. Esaminare le informazioni nella pagina Attività iniziali. Selezionare **Gestisci**.

1. Ora ci si trova nella pagina Ruoli di Contoso.  Nella barra della ricerca in cima alla pagina, immettere **utente**.  Selezionare **Amministratore utenti** dai risultati della ricerca.

1. Nella parte superiore della pagina selezionare **+ Aggiungi assegnazioni**.

1. Nella pagina Aggiungi assegnazioni, assicurarsi che **Appartenenza** sia sottolineato.  Qui verranno configurate le impostazioni di appartenenza per il ruolo di amministratore utenti in PIM.

1. Lasciare Tipo di ambito impostato sul valore predefinito, Directory.  

1. In Seleziona membri selezionare **Nessun membro selezionato**. In questo modo si apre la finestra Seleziona un membro.

1. Nella barra di ricerca immettere **Diego**.  Selezionare **Diego Siciliani** dai risultati della ricerca, quindi premere **Seleziona** in fondo alla pagina.  

1. In Seleziona membri si vedrà 1 membro selezionato e il nome e l'indirizzo di posta elettronica del membro selezionato, Diego Siciliani. In fondo alla pagina Aggiungi assegnazioni, selezionare **Avanti**.  

1. Ora ci si trova nella pagina Impostazione.  Lasciare Tipo di assegnazione impostato sul valore predefinito, Idoneo.

1. Se la casella Idoneità permanente è selezionata, selezionare **Idoneità permanente** per rimuovere il segno di spunta.

1. Nei campi Ora di inizio dell'assegnazione, tenere la data e l'ora predefinite, ossia data e ora correnti.

1. Nei campi Ora di fine dell'assegnazione, modificare la data in data odierna (notare che l'impostazione predefinita è un anno a partire dalla data odierna, quindi è necessario modificare l'anno). Per l'ora, impostarla su due ore dopo l'ora corrente. Dopo aver impostato il campo dell'ora di fine dell'assegnazione, premere il tasto TAB della tastiera e selezionare **Assegna** in fondo alla pagina.  

1. In questo modo si torna alla finestra Assegnazioni.  Dopo alcuni secondi, Diego Siciliani dovrebbe essere visibile nella tabella Amministratore utenti, insieme ai dettagli dell'assegnazione. Se dopo alcuni secondi non si vede ancora l'aggiornamento, selezionare **Aggiorna** nella parte superiore della pagina.

1. Dalla parte superiore della pagina, selezionare **Impostazioni**.

1. Nei dettagli dell'impostazione Ruolo per l'amministratore utenti, notare le varie opzioni.  Osservare che l'opzione "Richiedi giustificazione all'attivazione" è impostata su Sì e che anche "All'attivazione richiedi Azure MFA" è impostata su Sì.  Queste impostazioni saranno entrambe visibili nell'attività successiva, quando Diego attiverà il ruolo.  Si noti anche che l'opzione "Richiedi l'approvazione per l'attivazione" è impostata su No.  Lasciare i valori predefiniti per tutte le impostazioni.  Chiudere la pagina selezionando la **X** nell'angolo in alto a destra della schermata.

1. Disconnettersi selezionando l'icona dell'utente accanto all'indirizzo e-mail nell'angolo in alto a destra della schermata, quindi **Disconnetti**. Quindi, chiudere tutte le finestre del browser.

### Attività 3

In questa attività, come Diego Siciliani, accederà all'interfaccia di amministrazione di Microsoft Entra, per accedere alla funzionalità di Privileged Identity Management di Microsoft Entra per attivare l'assegnazione come amministratore utente.  Una volta attivata, si apporteranno alcune modifiche alla configurazione di un utente esistente. Nota: per questa attività sarà necessario avere accesso immediato a un dispositivo mobile che può ricevere SMS.

1. Aprire Microsoft Edge.  Nella barra degli indirizzi del browser immettere **Entra.microsoft.com**.

1. Accedere come Diego Siciliani.
    1. Nella finestra Accedi immettere **DiegoS@WWLxZZZZZZ.onmicrosoft.com** (dove ZZZZZZ è l'ID tenant univoco fornito dal proprio provider di hosting del lab) e quindi selezionare **Avanti**.
    1. Immettere la password temporanea annotata nell'attività precedente, quindi selezionare **Accedi**.  Fare clic su **Accedi**.
    1. Poiché la password immessa era una password temporanea, ora occorre aggiornarla. Immettere la password corrente, immettere una nuova password, quindi confermare la nuova password.  Prendere nota di questa nuova password perché sarà necessario completare l'attività.
    1. Quando compare la domanda se rimanere connessi, selezionare **Sì**.

1. Si dovrebbe accedere correttamente all'interfaccia di amministrazione di Microsoft Entra.
1. Nel pannello di spostamento a sinistra espandere **Identity Governance** e quindi selezionare **Privileged Identity Management**.
1. Dal riquadro di spostamento sinistro, selezionare **Ruoli personali**.  Vengono visualizzate informazioni per le assegnazioni idonee.  Si vedrà che all'utente Diego è stato assegnato il ruolo di amministratore utenti.  
1. Nell'ultima colonna della tabella, chiamata Azione, selezionare **Attiva**.
1. Verrà visualizzata un'icona di avviso che indica che è necessaria una verifica aggiuntiva.  Selezionare **Fare clic per continuare**.  Ricordare che le impostazioni di PIM per il ruolo di amministratore utenti richiedono l'autenticazione a più fattori.  Inoltre, poiché le informazioni di contatto di Diego da usare con la MFA (metodi di autenticazione) non erano state configurate in precedenza, Diego dovrà registrare le proprie informazioni per poter utilizzare la MFA.  Sebbene Diego dovrà effettuare la MFA ogni volta che accede come amministratore utenti, nel corso del periodo di assegnazione, il processo di registrazione MFA deve essere eseguito una sola volta.
1. Verrà visualizzata una notifica per segnalare che sono necessarie altre informazioni. Selezionare **Avanti**.
1. Immettere la password.
1. Nella parte inferiore della finestra di Microsoft Authenticator, selezionare **Si vuole configurare un metodo diverso**.
1. Viene richiesto di scegliere un metodo diverso.  Accanto alla dicitura App Authenticator, selezionare il tasto freccia GIÙ.   Selezionare **Telefono**, quindi **Conferma**.
1. Viene richiesto di immettere il numero di telefono che si vuole usare. Assicurarsi della correttezza del paese per il prefisso internazionale del proprio numero di telefono.  Immettere il numero di telefono, assicurarsi che **Invia un SMS** sia selezionato, quindi premere **Avanti**.
1. Immettere il codice a 6 cifre ricevuto sul telefono e selezionare **Avanti**.
1. Verrà visualizzata una notifica dell'avvenuta registrazione del telefono. Selezionare **Avanti**, quindi **Fatto**.
1. Viene richiesto se si vuole rimanere connessi.  Selezionare **Sì**.
1. Viene visualizzata la finestra Activate User Administrator (Attiva amministratore utenti).  È necessario immettere un motivo per l'attivazione.  Nella casella visualizzata, immettere un motivo a scelta (con un massimo di 500 caratteri), quindi selezionare **Attiva**.
1. Durante l'elaborazione dell'attivazione verrà visualizzato il relativo stato (3 stadi di avanzamento).
1. Al termine dell'attivazione, viene nuovamente visualizzata la pagina Ruoli personali | Ruoli di Azure AD, dove sarà visibile una notifica indicante che è stato attivato un ruolo.  Selezionare **Fare clic qui** per visualizzare i propri ruoli attivi.  Se si nota che l'ora di fine è diversa dalla configurazione originale, selezionare il pulsante di aggiornamento in cima alla pagina (l'aggiornamento potrebbe richiedere alcuni minuti).
1. Tornare alla home page dell'interfaccia di amministrazione Microsoft Entra selezionando **Home** nel pannello di spostamento a sinistra. 
1. In qualità di amministratore utenti di Azure AD, è possibile creare utenti e gruppi, gestire licenze e altro ancora. Nel pannello di spostamento a sinistra, expnad **Identity** selezionare **Utenti** e quindi **Tutti gli utenti**.
1. Dall'elenco degli utenti, selezionare **Bianca Pisani**.
1. Dal riquadro di spostamento sinistro, selezionare **Licenze**.
1. Notare che Bianca non ha licenze assegnate.  Dalla parte superiore della pagina, selezionare **+ Assegnazioni**.
1. Dall'elenco Selezionare le licenze, scegliere **Office 365 E3** e **Windows 10 Enterprise E3**.
1. In fondo alla pagina, selezionare **Salva**.  In alto a destra nella pagina verrà visualizzata una breve notifica che indica che le licenze sono state assegnate.
1. Chiudere la pagina delle assegnazioni delle licenze aggiornate selezionando la **X** nell'angolo in alto a destra della schermata.
1. Disconnettersi selezionando l'icona dell'utente accanto all'indirizzo e-mail nell'angolo in alto a destra della schermata, quindi **Disconnetti**. Quindi, chiudere tutte le finestre del browser.
1. La durata del ruolo Amministratore utente è limitata al tempo configurato.

### Verifica

In questo lab, si è esplorato PIM.  In qualità di amministratore, si è configurato Diego con privilegi di amministratore utenti per un determinato periodo di tempo.  Quindi, in qualità di Diego, si è seguito il processo di attivazione dei privilegi di amministratore utenti e di configurazione delle impostazioni utente.  Ricordare che PIM richiede la licenza Azure AD Premium P2.
