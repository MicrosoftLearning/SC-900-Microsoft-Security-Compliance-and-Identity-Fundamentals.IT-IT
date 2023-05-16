---
lab:
  title: 'Esplorare Azure Active Directory'
  module: 'Modulo 1: Descrivere i servizi di base e i tipi di identità di Azure AD'
---


# <a name="lab-explore-azure-active-directory"></a>Laboratorio: Esplorazione di Azure Active Directory

Questo lab corrisponde al contenuto di Learn seguente:

- Percorso di apprendimento: Descrivere le funzionalità di Azure Active Directory (Azure AD), parte di Microsoft Entra
- Modulo: Descrivere i servizi di base e i tipi di identità di Azure AD
- Unità: Descrivere i tipi di identità di Azure AD

## <a name="lab-scenario"></a>Scenario del lab

In questo lab si accederà ad Azure Active Directory.  Inoltre, si creerà un utente e si configureranno le varie impostazioni, compresa l'aggiunta di licenze.  

**Tempo stimato**: 10-15 minuti

### <a name="task-1"></a>Attività 1

In qualità di abbonato a Microsoft 365, si usa già Azure AD.  Questa attività illustrerà i passaggi dettagliati per accedere ad Azure AD tramite il portale di amministrazione di Microsoft 365 e il portale di Azure.

1. Nel browser Microsoft Edge selezionare la scheda Home - Interfaccia di amministrazione di Microsoft 365.

1. Se in precedenza la scheda del browser è stata chiusa, seguire questa procedura:
    1. Nella barra degli indirizzi immettere **admin.microsoft.com** e accedere con le credenziali di amministratore come indicato di seguito:
    1. Nella finestra Accedi immettere **admin@WWLxZZZZZZ.onmicrosoft.com** (dove ZZZZZZ è l'ID tenant univoco fornito dal proprio provider di hosting del lab) e quindi selezionare **Avanti**.
    1. Immettere la password di amministratore, che dovrebbe essere fornita dal proprio provider di hosting del lab. Fare clic su **Accedi**.
    1. Quando compare la domanda se rimanere connessi, selezionare **Sì**.
    1. Dal riquadro di spostamento sinistro dell'interfaccia di amministrazione di Microsoft 365, selezionare **Mostra tutto**.

1. In Interfacce di amministrazione selezionare **Azure Active Directory** (potrebbe essere necessario scorrere verso il basso).  Si apre una nuova pagina del browser con la pagina Dashboard dell'interfaccia di amministrazione di Azure Active Directory. Nelle finestre principali del dashboard saranno visibili vari riquadri, compresi il riquadro Identità dell'organizzazione (Contoso, il tenant e l'edizione di Azure AD), un riquadro per gli utenti e i gruppi e altro ancora.

1. Dal riquadro di spostamento a sinistra, in Preferiti, selezionare **Azure Active Directory**.  Nella finestra principale sarà visibile un altro riquadro di spostamento che elenca tutti i servizi disponibili in Azure AD. A destra verranno visualizzate informazioni sul tenant Contoso, collegamenti ai tipi di identità che è possibile creare e i servizi offerti.  

1. Aprire ora una nuova finestra del browser e, nella barra degli indirizzi, immettere **portal.azure.com**.  Poiché è già stato effettuato l'accesso come admin@WWLxZZZZZZ.onmicrosoft.com e queste stesse credenziali erano state usate in origine per riscattare l'Azure Pass, l'accesso al portale di Azure dovrebbe essere avvenuto come amministratore.  È possibile verificarlo controllando l'indirizzo e-mail nell'angolo in alto a destra della pagina e passando il mouse sopra l'icona dell'utente.

1. La pagina di destinazione del portale di Azure mostra i servizi di Azure, compresi Azure Active Directory, macchine virtuali, account di archiviazione, database e altro ancora.  Selezionare **Altri servizi** e quindi **Azure Active Directory**. Se non viene visualizzato immediatamente, è possibile immettere Azure Active Directory nella barra di ricerca blu e selezionarlo da questa posizione.  

1. È ora visibile Azure Active Directory per il tenant Contoso di Microsoft 365.    Qualsiasi approccio si adotti per l'accesso ai servizi di Azure Active Directory (il portale di amministrazione Microsoft 365 o il portale Azure), la destinazione non cambia: Azure Active Directory di Contoso, in cui è possibile gestire tutti i servizi di Azure AD.

1. Lasciare aperta questa pagina del browser per la prossima attività.

### <a name="task-2"></a>Attività 2

In questa attività, si apprenderà come creare un nuovo utente in Azure Active Directory e si esploreranno alcuni dei servizi che possono essere gestiti a livello di utente.

1. Passare alla scheda Contoso – Microsoft Azure aperta nel browser. Se la scheda era stata chiusa, aprire una pagina del browser e, nella barra degli indirizzi, inserire portal.azure.com e selezionare Azure Active Directory.  Occorre aver effettuato l'accesso come amministratore nel portale di Azure. In caso contrario, eseguire di nuovo l'accesso.

1. Dal riquadro di spostamento sinistro, selezionare **Utenti**.  Si ricorda che il tenant è già configurato con gli utenti.

1. Nella parte superiore della pagina selezionare **+ Nuovo utente** e quindi nella casella a discesa selezionare **Crea nuovo utente**.

1. L'opzione **Crea nuovo utente** dovrebbe essere già selezionata. In caso contrario, selezionarla.

1. Compilare i campi **Identità** nel seguente modo:

    1. Nome utente: **sara**.

    1. Campo Nome: **Sara Perez**.

    1. Nome: **Sara**.

    1. Cognome: **Perez**.

1. Compilare i campi **Password** nel seguente modo:

    1. Selezionare **Consenti la creazione manuale della password**.

    1. Password iniziale: **Naja8996**. Quando Sara accede per la prima volta, le verrà richiesto di modificare la password.

1. Configurare **Gruppi e ruoli**.

    1. Accanto a Gruppi, selezionare **0 gruppi selezionati**.  In questo modo vengono visualizzati i gruppi disponibili.  Notare l'elenco dei gruppi disponibili.

    1. Selezionare **Operazioni** (potrebbe essere necessario scorrere verso il basso), quindi premere **Seleziona**. Notare come il testo accanto ai gruppi è stato aggiornato per rispecchiare la selezione di 1 gruppo.  

    1. Accanto a Ruoli, selezionare **Utente**. Viene visualizzato l'elenco dei ruoli della directory.  Scorrere verso il basso per visualizzare i vari ruoli predefiniti, i diversi ruoli, ma non modificare il ruolo dell'utente.  Chiudere questa finestra selezionando la **X** nell'angolo in alto a destra della pagina.

1. Configurare le **impostazioni**

    1. Blocca l'accesso:  **No** (lasciare l'impostazione predefinita).

    1. Località di utilizzo: selezionare l'elenco a discesa e quindi selezionare **Stati Uniti** (scorrere verso il basso per trovare questa opzione) o il paese in cui ci si trova.  La configurazione della località di utilizzo è obbligatoria per l'assegnazione delle licenze.

1. Nella parte inferiore della pagina, selezionare il pulsante **Crea**.

1. Verificare che l'utente venga visualizzato nell'elenco degli utenti (i nomi sono elencati in ordine alfabetico). Potrebbe essere necessario aggiornare la pagina del browser.

1. Nell'elenco degli utenti selezionare l'utente creato, **Sara Perez**.  Si apre la pagina del profilo.

1. Il riquadro di spostamento a sinistra mostra le varie opzioni che è possibile configurare per l'utente.  Selezionare **Gruppi**.  Qui è possibile visualizzare ulteriori informazioni sul gruppo.  Verificare che il gruppo Operazioni sia presente nell'elenco (la visualizzazione dell'assegnazione del gruppo potrebbe richiedere alcuni minuti).  Nota: verrà visualizzato anche il gruppo Contoso, anche se al momento della creazione dell'utente è stato assegnato un solo gruppo.  Questo è il risultato di un criterio preconfigurato nel tenant, che assegna automaticamente i nuovi utenti al gruppo Contoso.

1. Dal riquadro di spostamento sinistro, selezionare **Licenze**.  Notare che per questo utente non sono state trovate assegnazioni di licenze.  

1. Per aggiungere una licenza, selezionare **+ Assegnazioni** nella parte superiore della finestra principale.

1. In Selezionare le licenze scegliere **Office 365 E3** e **Windows 10/11 Enterprise E3**, quindi selezionare il pulsante **Salva** in fondo alla pagina. Nell'angolo in alto a destra dovrebbe comparire una notifica indicante che le assegnazioni delle licenze sono avvenute correttamente.

1. Selezionare la **X** nell'angolo in alto a destra della schermata per chiudere la finestra Assegnazioni di licenze.

1. Selezionare l'icona **Aggiorna** in cima alla pagina per confermare le assegnazioni delle licenze.

1. Tornare alla pagina di Azure Active Directory Panoramica di Contoso selezionando **Contoso** nell'angolo in alto a sinistra della schermata (nella barra di navigazione), sopra il punto in cui è indicato Sara Perez | Licenze.

1. È stato creato e configurato correttamente un utente in Azure Active Directory.

1. Disconnettersi da tutte le schede del browser aperte.  Per disconnettersi, nel portale di Azure selezionare l'icona dell'utente accanto all'indirizzo di posta elettronica nell'angolo in alto a destra della schermata e quindi selezionare **Disconnetti**. In Microsoft 365 disconnettersi selezionando l'icona nell'angolo superiore destro della finestra Microsoft 365 visualizzata come cerchio con le lettere SP (accanto all'icona del punto interrogativo), quindi selezionando **Disconnetti**. Chiudere tutte le finestre del browser.

### <a name="task-3"></a>Attività 3

In questa attività, si effettuerà l'accesso come Sara Perez per la prima volta.

1. Aprire Microsoft Edge.

2. Nella barra degli indirizzi immettere **login.microsoft.com**.

3. Accedere come **sara@WWLxZZZZZ.onmicrosoft.com** , dove ZZZZZZ è l'ID tenant univoco fornito dal provider di hosting del lab.

4. Immettere la password temporanea **Naja8996**.

5. Ora viene richiesto l'aggiornamento della password. Nel campo Password corrente immettere **Naja8996**.

6. Nel campo Nuova password immettere **SC900-Lab**.  Nel campo Confermare la password immettere SC900-Lab, quindi selezionare Accedi.  Nota: è consigliabile utilizzare una password più sicura. Questa password è stata selezionata come espediente e solo per questo lab.

7. Ora dovrebbe essere stato effettuato l'accesso a Microsoft 365.

8. Per disconnettersi, selezionare l'icona nell'angolo superiore destro della finestra di Microsoft 365 visualizzata come cerchio con le lettere SP (accanto all'icona del punto interrogativo), quindi selezionare **Disconnetti** e infine chiudere il browser.

### <a name="review"></a>Verifica

In questo lab è stata avviata l'esplorazione iniziale di Azure AD. Poiché gli abbonati di Microsoft 365 accedono automaticamente utilizzando Azure AD, si è scoperto che è possibile accedere alle funzionalità e ai servizi di Azure AD tramite il portale di amministrazione Microsoft 365 o il portale di Azure.  Entrambi gli approcci portano alla stessa destinazione.  Sono stati anche illustrati in modo dettagliato il processo di creazione di un nuovo utente e le diverse impostazioni configurabili, inclusi i gruppi a cui è possibile assegnare l'utente, la disponibilità dei ruoli e l'assegnazione di licenze utente.
