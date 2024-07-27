---
lab:
  title: Esplorare le impostazioni utente di Microsoft Entra ID
  module: Describe the function and identity types of Microsoft Entra ID
---

# Laboratorio: Esplorare le impostazioni utente di Microsoft Entra ID

Questo lab corrisponde al contenuto di Learn seguente:

- Percorso di apprendimento: Descrivere le funzionalità di Microsoft Entra
- Modulo: Descrivere la funzione e i tipi di identità di Microsoft Entra ID.
- Unità: Descrivere i tipi di identità.

## Scenario laboratorio

In questo lab, verrà effettuato l'accesso a Microsoft Entra ID (noto in precedenza come Azure Active Directory).  Inoltre, si creerà un utente e si configureranno le varie impostazioni, compresa l'aggiunta di licenze.  

**Tempo stimato**: 10-15 minuti

### Attività 1

Gli abbonati a Microsoft 365 usano già Microsoft Entra ID (noto in precedenza come Azure AD).  In questa attività si apprenderà come creare un nuovo utente in Microsoft Entra ID e verranno esplorati alcuni servizi gestibili a livello di utente.

1. Apri il browser Microsoft Edge. Nella barra degli indirizzi immettere **[admin.microsoft.com](https://admin.microsoft.com)** e accedere con le credenziali di Microsoft 365 fornite dal provider di servizi di hosting per lab autorizzato (ALH).
    1. Nella finestra Accedi, immettere **admin@WWLxZZZZZZ.onmicrosoft.com** (dove ZZZZZZ è l'ID tenant univoco fornito dal proprio ALH) e quindi selezionare **Avanti**.
    1. Immettere la password di amministratore, che dovrebbe essere fornita dal proprio provider di hosting del lab. Fare clic su **Accedi**.
    1. Quando viene richiesto di rimanere connessi, selezionare **Sì**.

1. In Interfacce di amministrazione, selezionare **Identità** (potrebbe essere necessario selezionare **Mostra tutto** e scorrere verso il basso).  Verrà visualizzata una nuova pagina del browser della pagina panoramica dell'Interfaccia di amministrazione di Microsoft Entra. Qui si potranno visualizzare informazioni di base sul tenant Contoso. Scorrendo verso il basso nella finestra principale, si potranno visualizzare anche informazioni su avvisi, feed, funzionalità in evidenza e altro ancora.

1. Nel riquadro di spostamento a sinistra, espandere **Utenti** quindi selezionare **Tutti gli utenti**. Tenere presente che il tenant è già configurato con gli utenti.

1. Nella parte superiore della pagina selezionare **+ Nuovo utente** e quindi nella casella a discesa selezionare **Crea nuovo utente**.

1. Ora ci si trova nella scheda **Nozioni di base** della pagina Crea nuovo utente. Compilare i campi nel modo indicato di seguito:
    1. Nome dell'entità utente: **Sara**.

    1. Nome alternativo di posta elettronica: lasciare come da impostazione predefinita, che viene derivata da Nome dell'entità utente.

    1. Nome visualizzato: **Sara Perez**.

    1. Password: deselezionare la casella che indica Password generata automaticamente e immettere una password temporanea conforme ai requisiti richiesti per la password e annotarla, sarà necessaria per completare l'attività successiva.

    1. Account abilitato: lasciare il segno di spunta per assicurarsi che l'account sia abilitato.

    1. Nella parte inferiore della pagina, selezionare **Avanti: Proprietà**.

1. Qui si potranno configurare alcuni campi della scheda **Proprietà**.

    1. Nome: Sara

    1. Cognome: Perez

    1. Tipi di utenti: lasciare l'impostazione predefinita **Membro**, ma notare che nell'elenco a discesa è possibile selezionare Guest.

    1. Posizione di utilizzo: scegliere il paese o l'area geografica in cui ci si trova.  Tenere presente che per accedere al campo posizione di utilizzo, sarà necessario scorrere verso il basso nella pagina, poiché è l'ultimo campo della pagina.  **NOTA**: se non si esegue questa operazione, non sarà possibile assegnare una licenza in un passaggio successivo.

    1. Selezionare **Avanti: Assegnazioni**.

1. Ora ci si trova nella scheda **Assegnazioni**, in cui viene aggiunta un'assegnazione di gruppo e visualizzate le opzioni disponibili per l'aggiunta di un ruolo.

    1. Selezionare **Aggiungi gruppo**.

    1. La finestra visualizzata mostra tutti i gruppi disponibili.  

    1. Notare l'elenco dei gruppi disponibili.  Dall'elenco, selezionare **Operazioni**.  Nella parte inferiore della pagina, selezionare il pulsante **Seleziona**.  Dopo alcuni secondi, nella pagina delle assegnazioni verrà visualizzato il gruppo Operazioni.

    1. Nella parte superiore della pagina, selezionare **Aggiungi ruolo**.  Verrà visualizzata una finestra che mostra tutti i ruoli della directory disponibili.  Visualizzare le opzioni disponibili, ma non aggiungere nuovi ruoli.  Chiudere questa pagina selezionando la **X** nell'angolo superiore a destra della pagina dei ruoli della directory.
    1. Nella parte inferiore della pagina selezionare **Rivedi e crea**. Viene visualizzato un riepilogo delle Impostazioni.  Nella parte inferiore della pagina selezionare **Salva**.

1. Si torna alla pagina degli utenti.  Dopo alcuni secondi, Sara Perez comparirà nell'elenco.  Potrebbe essere necessario selezionare l'icona di **aggiornamento** nella parte superiore della pagina.

1. Nell'elenco degli utenti selezionare l'utente creato, **Sara Perez**.  Viene visualizzata la pagina **Panoramica**.

1. Il riquadro di spostamento a sinistra mostra le varie opzioni che possono essere configurate per l'utente. Rivedere le opzioni disponibili.

1. Dal riquadro di spostamento a sinistra, selezionare **Licenze**.  Notare che non sono state trovate assegnazioni di licenza per questo utente.  NOTA: le licenze possono essere assegnate solo se è stata configurata una posizione di utilizzo. Se la posizione di utilizzo non è stata impostata, tornare a tale passaggio nell'attività precedente.

    1. Per aggiungere una licenza, selezionare **+ Assegnazioni** nella parte superiore della finestra principale.

    1. In Seleziona licenze selezionare **Microsoft Power Apps for Developer** e **Microsoft Power Automate Free** e quindi selezionare il **pulsante Salva** nella parte inferiore della schermata. Una notifica nell'angolo superiore a destra della schermata dovrebbe indicare che le assegnazioni di licenza sono state eseguite correttamente.

    1. Selezionare la **X** in alto a destra della schermata per chiudere la finestra Assegnazioni di licenza.

    1. Selezionare l'**icona Aggiorna** nella parte superiore della pagina per confermare le assegnazioni di licenza.

1. Tornare all'interfaccia di amministrazione di Microsoft Entra selezionando **Home** nel pannello di spostamento a sinistra o dalla parte superiore a sinistra dello schermo (nella barra di navigazione), sopra il punto in cui è indicato Sara Perez | Licenze.

1. Un utente in Microsoft Entra ID è stato creato e configurato correttamente.

1. Disconnettersi da tutte le schede del browser aperte. Disconnettersi selezionando l'icona dell'utente accanto all'indirizzo di posta elettronica nell'angolo in alto a destra della schermata, poi selezionare **Disconnetti**. Chiudere quindi tutte le finestre del browser.

### Attività 2

In questa attività, si effettuerà l'accesso come Sara Perez per la prima volta.

1. Aprire Microsoft Edge.

2. Nella barra degli indirizzi immettere **https://login.microsoft.com**.

3. Accedere come **sara@WWLxZZZZZ.onmicrosoft.com** (dove ZZZZZZ è l'ID tenant univoco fornito dal provider di servizi di hosting per i lab autorizzato).
4. Immettere la password temporanea impostata nell'attività precedente.

5. Viene chiesto di aggiornare la password. Nel campo Password corrente immettere la password temporanea dell'attività precedente.

6. Nel campo Nuova password immettere una nuova password, confermarla e quindi selezionare **Accedi**.  Prendere nota della nuova password perché sarà necessaria per l'esercizio del lab successivo sulla reimpostazione della password self-service.

7. A questo momento dovrebbe essere eseguito l'accesso all'account Microsoft di Sara.  Si noti che le licenze di Sara assegnate nell'attività precedente erano limitate solo a Power Automate Gratuito e Power Apps for Developer e non includevano le licenze E5.

8. Per disconnettersi, selezionare l'icona nell'angolo superiore destro della finestra di Microsoft 365 visualizzata come cerchio con le lettere SP (accanto all'icona del punto interrogativo), quindi selezionare **Disconnetti** e infine chiudere il browser.

### Revisione

In questo lab è stata avviata l'esplorazione iniziale di Microsoft Entra ID. Poiché gli abbonati di Microsoft 365 accedono automaticamente utilizzando Microsoft Entra ID, si è scoperto che è possibile accedere alle funzionalità e ai servizi di Microsoft Entra ID tramite il portale di amministrazione Microsoft 365 o il portale di Azure.  Qualunque approccio si preferisca si arriva alla stessa posizione.  Sono stati anche illustrati in modo dettagliato il processo di creazione di un nuovo utente e le diverse impostazioni configurabili, inclusi i gruppi a cui è possibile assegnare l'utente, la disponibilità dei ruoli e l'assegnazione di licenze utente.
