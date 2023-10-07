<!---
---
Lab: Learning Path: 'Describe the capabilities of Microsoft Entra' Module: 'Describe the access management capabilities of Microsoft Entra ID' Unit: 'Describe Conditional Access'
---
--->

# Lab: Microsoft Entra l'accesso condizionale

Questo lab corrisponde al contenuto di Learn seguente:

- Percorso di apprendimento: Descrivere le funzionalità di Microsoft Entra
- Modulo: Descrivere le funzionalità di gestione degli accessi di Microsoft Entra ID
- Unità: Descrivere l'accesso condizionale

## Scenario del lab

In questo lab, si esplorerà l'autenticazione a più fattori (MFA) degli accessi condizionali dal punto di vista di un amministratore e di un utente.  In qualità di amministratore, si creerà un criterio che richiederà a un utente di eseguire l'autenticazione a più fattori durante l'accesso a un'applicazione di gestione di Microsoft Azure basata su cloud.  Dal punto di vista di un utente, si vedrà l'impatto dei criteri di accesso condizionale, compreso il processo di registrazione per l'autenticazione a più fattori.

**Tempo stimato**: 30 minuti

### Attività 1

In questa attività, in qualità di amministratore, si reimposterà la password per l'utente Debra Berger.  Questo passaggio è necessario in modo da poter effettuare l'accesso iniziale come utente nelle attività successive.

1. Aprire Microsoft Edge.  Nella barra degli indirizzi immettere **https://entra.microsoft.com**e accedere con le credenziali di amministratore.
    1. Nella finestra Accedi immettere **admin@WWLxZZZZZZ.onmicrosoft.com** (dove ZZZZZZ è l'ID tenant univoco fornito dal proprio provider di hosting del lab) e quindi selezionare **Avanti**.
    1. Immettere la password di amministratore, che dovrebbe essere fornita dal proprio provider di hosting del lab. Fare clic su **Accedi**.
    1. Quando compare la domanda se rimanere connessi, selezionare **Sì**.

1. Nel riquadro di spostamento a sinistra espandere **Identità**, espandere **Utenti**, quindi selezionare **Tutti gli utenti**.

1. Selezionare **Debra Berger** dall'elenco degli utenti.

1. Selezionare **Reimposta password** in cima alla pagina. Poiché non è stato effettuato l'accesso come Debra Berger in precedenza, non si conosce la sua password e sarà quindi necessario reimpostarla.

1. All'apertura della finestra Reimposta password, selezionare **Reimposta password**.  IMPORTANTE: prendere nota della nuova password, perché servirà in un'attività successiva per poter accedere come utente.

1. Chiudere la finestra di reimpostazione della password selezionando la **X** nell'angolo in alto a destra della pagina, quindi chiudere la finestra Debra Berger selezionando la **X** nell'angolo in alto a destra della pagina.

1. Nel pannello di spostamento a sinistra selezionare **Home** per tornare all'interfaccia di amministrazione di Microsoft Entra.

1. Tenere aperta questa finestra.

### Attività 2

In questa attività, si seguirà il processo di creazione di criteri di accesso condizionale in Azure AD.

1. Aprire la scheda del browser nella home page dell'interfaccia di amministrazione di Microsoft Entra.   Se in precedenza è stata chiusa la scheda del browser, aprire Microsoft Edge e nella barra degli indirizzi immettere **https://entra.microsoft.com** e accedere con le credenziali di amministratore di Microsoft 365 fornite da ALH.

1. Nel riquadro di spostamento a sinistra espandere **Protezione** e quindi selezionare **Accesso condizionale**.

1. Viene visualizzata la pagina Panoramica dell'accesso condizionale.  Qui verranno visualizzati riquadri che mostrano il riepilogo dei criteri e gli avvisi generali.  Nel pannello di spostamento a sinistra selezionare **Criteri**.

1. Nel pannello di spostamento a sinistra selezionare **Criteri**. Qualsiasi criterio di accesso condizionale esistente è elencato qui. Selezionare **+ Nuovi criteri**.

1. Nel campo Nome, immettere **MFA Test Policy** (Criteri MFA di test).

1. In Utenti selezionare **0 utenti e gruppi selezionati**.

1. Diventerà ora visibile l'opzione per includere o escludere utenti o gruppi.  Assicurarsi che sia selezionato (sottolineato) **Includi**.

1. Scegliere l'opzione per **Seleziona utenti e gruppi**, quindi **Utenti e gruppi**.  Si apre la finestra Seleziona utenti e gruppi.  

1. Nella barra di ricerca immettere **Debra**.  Selezionare **Debra Berger** da sotto la barra di ricerca, quindi premere il pulsante **Seleziona** in fondo alla pagina.  Notare che una prassi comune consiste nell'assegnare i criteri agli utenti di un gruppo.  Per gli scopi di questo lab, i criteri verranno assegnati a un utente specifico.

1. In Risorse di destinazione selezionare **Nessuna risorsa di destinazione selezionata**.

1. Nel campo sotto dove viene indicato **Selezionare a quale criterio si applica questo criterio**, selezionare la freccia giù e prendere nota delle opzioni disponibili.  Mantenere l'impostazione predefinita App **cloud**.  Assicurarsi che la scheda **Includi** sia sottolineata.  **Selezionare Seleziona app**, quindi in cui viene indicato **Seleziona**, **selezionare Nessuno**.  Si apre la finestra Select Cloud apps (Seleziona le app cloud).

1. Nella barra di ricerca immettere **Azure**.  Dai risultati della ricerca che compaiono sotto la casella di ricerca, selezionare **Gestione di Microsoft Azure**, quindi premere **Seleziona** in fondo alla pagina.  Notare l'avviso.  

1. In Condizioni, scegliere **0 condizioni selezionate**.  Notare le diverse opzioni che è possibile configurare.  Tramite i criteri, è possibile controllare l'accesso utente in base ai segnali provenienti da condizioni, tra cui: rischio utente, rischio di accesso, piattaforma del dispositivo, posizione, app client o filtro per i dispositivi.  Esplorare queste opzioni configurabili, ma non impostare alcuna condizione.

1. Ora si imposteranno i controlli di accesso.  In Concedi, scegliere **0 controlli selezionati**.

1. Si apre la finestra Concedi.  Assicurarsi che l'opzione **Concedi accesso** sia selezionata e quindi selezionare **Richiedi l'autenticazione a più fattori**. Scorrere verso il basso nella finestra destra e nella sezione Per più controlli lasciare l'impostazione predefinita **Richiedi tutti i controlli selezionati**.  Premere **Seleziona** in fondo alla pagina.

1. Nella parte inferiore della pagina, in Abilita criterio, selezionare **Attivato** e quindi selezionare **Crea**.

1. Nel riquadro di spostamento a sinistra selezionare **Criteri**. I criteri pilota MFA devono essere visualizzati nell'elenco dei criteri di accesso condizionale (se necessario, selezionare **l'icona Aggiorna** nella barra dei comandi nella parte superiore della pagina).

1. Disconnettersi selezionando l'icona dell'utente accanto all'indirizzo e-mail nell'angolo in alto a destra della schermata, quindi **Disconnetti**. Infine, chiudere tutte le finestre del browser.

### Attività 3

In questa attività si vedrà l'impatto dei criteri di accesso condizionale dal punto di vista dell'utente Debra Berger. Si inizierà prima accedendo a un'applicazione non inclusa nei criteri di accesso condizionale (il portale di Microsoft 365 all'indirizzo https://login.microsoftonline.com).  Si ripeterà quindi il processo per un'applicazione inclusa nei criteri di accesso condizionale (il portale di Azure all'indirizzo https://portal.azure.com).  È opportuno ricordare che i criteri richiedono che l'utente effettui l'autenticazione a più fattori al momento dell'accesso a una applicazione di gestione di Microsoft Azure.  Per utilizzare la MFA, l'utente deve innanzitutto registrare il metodo di autenticazione che verrà utilizzato per la MFA, ad esempio un codice inviato a un dispositivo mobile o un'app di autenticazione.

1. Aprire Microsoft Edge.  Nella barra degli indirizzi immettere **https://login.microsoftonline.com**.
    1. Accedere come **DebraB@WWLxZZZZZZ.onmicrosoft.com** , dove ZZZZZZ è l'ID del tenant univoco fornito dal provider di hosting del lab, quindi selezionare **Avanti**.
    1. Immettere la password annotata nell'attività precedente. Fare clic su **Accedi**.
    1. Poiché la password fornita quando, in qualità di amministratore, è stata reimpostata è temporanea, sarà necessario aggiornare la password (questo non fa parte dei criteri MFA). Immettere la password corrente, quindi immettere una nuova password e quindi confermare la nuova password.  Prendere nota della nuova password perché sarà necessaria per completare l'attività.
    1. Quando compare la domanda se rimanere connessi, selezionare **Sì**.  Dovrebbe essere stato effettuato correttamente l'accesso al proprio account di Microsoft 365. La MFA non era richiesta per questa applicazione poiché non fa parte dei criteri.

1. Ora si proverà a effettuare l'accesso a un'applicazione che soddisfa i criteri per la MFA. Aprire una nuova scheda del browser e immettere **https://portal.azure.com**.

1. Verrà visualizzata una finestra con l'indicazione Sono necessarie altre informazioni.  Selezionare **Avanti**.  Notare che in questo modo si avvierà il processo di registrazione MFA, poiché si tratta del primo accesso all'app cloud identificata nei criteri di accesso condizionale.  Questo processo di registrazione è richiesto una sola volta.   Un'alternativa all'esecuzione del processo di registrazione da parte dell'utente prevede che sia l'amministratore a configurare il metodo di autenticazione da utilizzare.

1. Nella finestra Proteggi l'account, è possibile selezionare il metodo da utilizzare per la MFA.  Microsoft Authenticator è un'opzione. Per comodità, in questo esercizio del lab si sceglierà un metodo diverso.  Selezionare **Si vuole configurare un metodo diverso**.  Dalla finestra popup Scegliere un metodo diverso, selezionare **la freccia a discesa**, quindi **Telefono** e infine **Conferma**.

1. Nella finestra che si apre assicurarsi che sia selezionato il proprio paese, quindi immettere il numero di telefono cellulare da usare.  Verificare che sia selezionato **Invia un SMS** e quindi selezionare **Avanti**.  Si riceverà un SMS nel telefono con un codice che sarà necessario immettere dove indicato.  Immettere il codice ricevuto e quindi selezionare **Avanti**.  Dopo la conferma, nella schermata comparirà "Verificato tramite SMS. Il telefono è stato registrato".  Selezionare **Avanti**. Selezionare quindi **Fine**.  In questo modo si completa il processo di registrazione da effettuare una sola volta.

1. Ora si dovrebbe poter accedere al portale di Azure.  Il portale di Azure è un'applicazione di gestione di Microsoft Azure e pertanto richiede l'autenticazione a più fattori, conformemente ai criteri di accesso condizionale creati.  
    1. Se viene visualizzato un messaggio che indica che è stato effettuato il timeout dell'accesso, immettere la password e selezionare **Accedi**.
    1. Verrà visualizzata una finestra che richiede di verificare l'identità.  Selezionare dove viene indicato Invia un SMS al numero =X XXXXXXX per ricevere un codice sul telefono cellulare, immettere il codice e selezionare **Verifica**.
    1. Se viene richiesto se si vuole rimanere connessi, selezionare **No**.

1. Disconnettersi selezionando l'icona dell'utente accanto all'indirizzo di posta elettronica nell'angolo in alto a destra della schermata, quindi Disconnetti. Chiudere quindi tutte le finestre del browser.

### Verifica

In questo lab è stato presentato il processo di configurazione dei criteri di accesso condizionale, che richiedono che gli utenti effettuino la MFA quando accedono all'applicazione cloud di gestione di Microsoft Azure.  Quindi, in qualità di utente, si è seguito il processo di registrazione per la MFA e si è visto l'impatto dei criteri di accesso condizionale che richiedono l'utilizzo della MFA quando si accede al portale di Azure.
