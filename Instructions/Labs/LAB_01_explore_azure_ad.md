<!---
---
Lab: Titolo: 'Esplora le impostazioni utente Microsoft Entra ID' Percorso di apprendimento/Modulo/Unità: "Percorso di apprendimento: Descrivere le funzionalità di Microsoft Entra; Modulo 1: Descrivere i tipi di funzione e identità di Microsoft Entra ID; Unità 3: Descrivere i tipi di identità Microsoft Entra
---
--->

# Lab: Esplorare l'ID Microsoft Entra

Questo lab corrisponde al contenuto di Learn seguente:

- Percorso di apprendimento: descrivere le funzionalità di Microsoft Entra.
- Modulo: descrivere i tipi di funzione e identità di Microsoft Entra ID.
- Unità: descrivere i tipi di identità.

## Scenario del lab

In questo lab si accederà all'ID Microsoft Entra (in precedenza denominato Azure Active Directory).  Inoltre, si creerà un utente e si configureranno le varie impostazioni, compresa l'aggiunta di licenze.  

**Tempo stimato**: 10-15 minuti

### Attività 1

Come sottoscrittore a Microsoft 365 si sta già usando Microsoft Entra ID (in precedenza denominato Azure AD).  In questa attività si apprenderà come creare un nuovo utente in Microsoft Entra ID ed esplorare alcuni dei servizi che possono essere gestiti a livello di utente.

1. Aprire il browser Microsoft Edge. Nella barra degli indirizzi immettere **[admin.microsoft.com](https://admin.microsoft.com)** e accedere con le credenziali di Microsoft 365 fornite dall'host del lab autorizzato (ALH).
    1. Nella finestra Accesso immettere **admin@WWLxZZZZZZ.onmicrosoft.com** (dove ZZZZZZ è l'ID tenant univoco fornito dall'ALH) e quindi selezionare **Avanti**.
    1. Immettere la password di amministratore, che dovrebbe essere fornita dal proprio provider di hosting del lab. Fare clic su **Accedi**.
    1. Quando compare la domanda se rimanere connessi, selezionare **Sì**.

1. In Amministrazione centri selezionare **Identità** (potrebbe essere necessario selezionare **Mostra tutto** e scorrere verso il basso).  Verrà visualizzata una nuova pagina del browser alla pagina di panoramica dell'interfaccia di amministrazione Microsoft Entra. Qui verranno visualizzate informazioni di base sul tenant Contoso. Se si scorre verso il basso la finestra principale, verranno visualizzate anche informazioni sugli avvisi, il feed, le evidenziazioni delle funzionalità e altro ancora.

1. Nel riquadro di spostamento a sinistra espandere **Utenti** e quindi **Tutti gli utenti**. Si ricorda che il tenant è già configurato con gli utenti.

1. Nella parte superiore della pagina selezionare **+ Nuovo utente** e quindi nella casella a discesa selezionare **Crea nuovo utente**.

1. Nella scheda **Nozioni di base** della pagina crea nuovo utente. Popolare i campi come indicato di seguito:
    1. Nome entità utente: **sara**.

    1. Nickname di posta: lasciare il valore predefinito, che è impostato per derivare dal nome dell'entità utente.

    1. Nome visualizzato: **Sara Perez**.

    1. Password: deselezionare la casella che indica la password generata automaticamente e immettere una password temporanea che rispetta i requisiti della password e prendere nota di esso, perché sarà necessario completare l'attività successiva.

    1. Account abilitato: lasciare il segno di spunta per assicurarsi che l'account sia abilitato.

    1. Nella parte inferiore della pagina selezionare **Avanti: Proprietà**.

1. In questo articolo verranno configurati alcuni campi nella scheda **Proprietà** .

    1. Nome: Sara

    1. Cognome: Perez

    1. Tipi di utente: lasciare l'impostazione predefinita **membro**, ma si noti che dall'elenco a discesa è possibile selezionare guest.

    1. Posizione di utilizzo: scegliere il paese/area geografica in cui si trova.  Si noti che per accedere al campo percorso di utilizzo, sarà necessario scorrere verso il basso nella pagina perché è l'ultimo campo della pagina.  **NOTA**: se non si esegue questa operazione, non sarà possibile assegnare una licenza in un passaggio successivo.

    1. Selezionare **Avanti: Assegnazioni**.

1. Si è ora nella scheda **Assegnazioni** in cui si aggiunge un'assegnazione di gruppo e si visualizzano le opzioni disponibili per l'aggiunta di un ruolo.

    1. Selezionare **Aggiungi gruppi**.

    1. La finestra che apre mostra tutti i gruppi disponibili.  

    1. Notare l'elenco dei gruppi disponibili.  Nell'elenco selezionare **Operazioni**.  Nella parte inferiore della pagina selezionare il pulsante **Seleziona** .  Potrebbe richiedere alcuni secondi, ma dovrebbe essere visualizzato il gruppo di operazioni nella pagina assegnazioni.

    1. Nella parte superiore della pagina selezionare **Aggiungi ruolo**.  Verrà visualizzata una finestra che mostra tutti i ruoli della directory disponibili.  Visualizzare le opzioni disponibili, ma non aggiungere nuovi ruoli.  Chiudere questa pagina selezionando **X** nell'angolo superiore destro della pagina dei ruoli della directory.
    1. Nella parte inferiore della pagina selezionare **Rivedi e crea**. Verrà visualizzato un riepilogo delle impostazioni.  Nella parte inferiore della pagina selezionare **Salva**.

1. Viene restituito alla pagina utenti.  Dopo alcuni secondi, Sara Perez sarà elencato.  Potrebbe essere necessario selezionare l'icona **di aggiornamento** nella parte superiore della pagina.

1. Nell'elenco degli utenti selezionare l'utente creato, **Sara Perez**.  Verrà visualizzata la pagina **Panoramica** .

1. Il riquadro di spostamento a sinistra mostra le varie opzioni che è possibile configurare per l'utente. Visualizzare le opzioni disponibili.

1. Dal riquadro di spostamento sinistro, selezionare **Licenze**.  Notare che per questo utente non sono state trovate assegnazioni di licenze.  NOTA: le licenze possono essere assegnate solo se è stata configurata una posizione di utilizzo. Se non è stata impostata la posizione di utilizzo, tornare a tale passaggio nell'attività precedente.

    1. Per aggiungere una licenza, selezionare **+ Assegnazioni** nella parte superiore della finestra principale.

    1. In Selezionare le licenze scegliere **Office 365 E3** e **Windows 10/11 Enterprise E3**, quindi selezionare il pulsante **Salva** in fondo alla pagina. Nell'angolo in alto a destra dovrebbe comparire una notifica indicante che le assegnazioni delle licenze sono avvenute correttamente.

    1. Selezionare la **X** nell'angolo in alto a destra della schermata per chiudere la finestra Assegnazioni di licenze.

    1. Selezionare l'icona **Aggiorna** in cima alla pagina per confermare le assegnazioni delle licenze.

1. Tornare all'interfaccia di amministrazione Microsoft Entra selezionando **Home** nel pannello di spostamento sinistro o dall'alto a sinistra dello schermo (il pane-crumb), sopra dove dice Sara Perez | Licenze.

1. È stato creato e configurato un utente in Microsoft Entra ID.

1. Disconnettersi da tutte le schede del browser aperte. Disconnettersi selezionando l'icona utente accanto all'indirizzo di posta elettronica nell'angolo superiore destro della schermata **** e quindi selezionando Disconnettersi. Chiudere tutte le finestre del browser.

### Attività 2

In questa attività, si effettuerà l'accesso come Sara Perez per la prima volta.

1. Aprire Microsoft Edge.

2. Nella barra degli indirizzi immettere **https://login.microsoft.com**.

3. Accedere come **sara@WWLxZZZZZ.onmicrosoft.com**, (dove ZZZZZZ è l'ID tenant univoco fornito dall'ALH)
4. Immettere la password temporanea impostata nell'attività precedente.

5. Ora viene richiesto l'aggiornamento della password. Nel campo Password corrente immettere la password temporanea dall'attività precedente.

6. Nel campo Nuova password immettere una nuova password, confermare la password e quindi selezionare **Accedi**.  Prendere nota della nuova password perché sarà necessaria per l'esercizio del lab successivo sulla reimpostazione della reimpostazione della password.

7. Ora dovrebbe essere stato effettuato l'accesso a Microsoft 365.

8. Per disconnettersi, selezionare l'icona nell'angolo superiore destro della finestra di Microsoft 365 visualizzata come cerchio con le lettere SP (accanto all'icona del punto interrogativo), quindi selezionare **Disconnetti** e infine chiudere il browser.

### Verifica

In questo lab è stata avviata l'esplorazione iniziale di Azure AD. Poiché gli abbonati di Microsoft 365 accedono automaticamente utilizzando Azure AD, si è scoperto che è possibile accedere alle funzionalità e ai servizi di Azure AD tramite il portale di amministrazione Microsoft 365 o il portale di Azure.  Entrambi gli approcci portano alla stessa destinazione.  Sono stati anche illustrati in modo dettagliato il processo di creazione di un nuovo utente e le diverse impostazioni configurabili, inclusi i gruppi a cui è possibile assegnare l'utente, la disponibilità dei ruoli e l'assegnazione di licenze utente.
