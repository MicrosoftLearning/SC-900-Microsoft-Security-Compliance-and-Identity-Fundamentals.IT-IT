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

**Tempo stimato**: 30 minuti

### Attività 1

Gli abbonati a Microsoft 365 usano già Microsoft Entra ID.  In questa attività si apprenderà come creare un nuovo utente in Microsoft Entra ID e verranno esplorati alcuni servizi gestibili a livello di utente.

1. Apri il browser Microsoft Edge. Nella barra degli indirizzi immettere **`https://admin.microsoft.com`** e accedere con le credenziali di Microsoft 365 fornite dall'host del lab autorizzato (ALH).
    1. Nella finestra Accedi, immettere **admin@WWLxZZZZZZ.onmicrosoft.com** (dove ZZZZZZ è l'ID tenant univoco fornito dal proprio ALH) e quindi selezionare **Avanti**.
    1. Immettere la password di amministratore, che dovrebbe essere fornita dal proprio provider di hosting del lab. Fare clic su **Accedi**.
    1. A seconda dell'host del lab e se è la prima volta che si esegue l'accesso al tenant, potrebbe essere richiesto di completare il processo di registrazione dell'autenticazione a più fattori. In tal caso, seguire le istruzioni visualizzate sullo schermo per configurare l'autenticazione a più fattori.
    1. Dopo aver eseguito l'accesso, viene visualizzata la pagina interfaccia di amministrazione di Microsoft 365.

1. In Interfacce di amministrazione, selezionare **Identità** (potrebbe essere necessario selezionare **Mostra tutto** e scorrere verso il basso).  Verrà visualizzata una nuova pagina del browser della pagina panoramica dell'Interfaccia di amministrazione di Microsoft Entra.

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

    1. Nella parte superiore della pagina selezionare **+ Aggiungi ruolo**.  Verrà visualizzata una finestra che mostra tutti i ruoli della directory disponibili.  Visualizzare le opzioni disponibili, ma non aggiungere nuovi ruoli.  Chiudere questa pagina selezionando la **X** nell'angolo superiore a destra della pagina dei ruoli della directory.
    1. Nella parte inferiore della pagina selezionare **Rivedi e crea**. Viene visualizzato un riepilogo delle Impostazioni.  Nella parte inferiore della pagina selezionare **Salva**.

1. Si torna alla pagina degli utenti.  Dopo alcuni secondi, Sara Perez comparirà nell'elenco.  Potrebbe essere necessario selezionare l'icona di **aggiornamento** nella parte superiore della pagina.

1. Nell'elenco degli utenti selezionare l'utente creato, **Sara Perez**.  Viene visualizzata la pagina **Panoramica**.

1. Il riquadro di spostamento a sinistra mostra le varie opzioni che possono essere configurate per l'utente. Rivedere le opzioni disponibili.

1. Dal riquadro di spostamento a sinistra, selezionare **Licenze**.  Si noti che non sono state trovate assegnazioni di licenza per questo utente, si noti anche l'icona di avviso che indica che l'aggiunta, la rimozione e la rielaborazione delle assegnazioni delle licenze sono disponibili solo nell'interfaccia di amministrazione di M365.  Questa operazione verrà eseguita nell'attività successiva.  NOTA: le licenze possono essere assegnate solo se è stata configurata una posizione di utilizzo. Se non è stata impostata la posizione di utilizzo, tornare a questo passaggio.

### Attività 2

In questa attività si assegnerà una licenza all'utente appena creato, usando il interfaccia di amministrazione di Microsoft 365.

1. Aprire la scheda **del browser Home - interfaccia di amministrazione di Microsoft 365**.

1. Nel pannello di spostamento a sinistra, in Utenti, selezionare **Utenti** attivi.  Nell'elenco degli utenti selezionare **Sara Perez**.  Viene visualizzata una finestra che mostra informazioni sull'utente.  

    1. Selezionare la **scheda Licenze e app** .
    1. Per ognuna delle licenze elencate, viene visualizzato il numero di licenze disponibili.  Poiché non sono disponibili licenze di Microsoft 365 E5 (sono già state assegnate ad altri utenti), assegnare le **licenze per sviluppatori** di Microsoft Power Apps e le **licenze gratuite** di Microsoft Power Automate selezionando la casella di controllo accanto a essi.
    1. Seleziona **Salva modifiche**. Una notifica nell'angolo superiore a destra della schermata dovrebbe indicare che le assegnazioni di licenza sono state eseguite correttamente.
    1. Chiudere la pagina selezionando la **X** nell'angolo superiore destro della pagina.

1. Tornare all'interfaccia di amministrazione di Microsoft Entra selezionando **Home** nel pannello di spostamento a sinistra o dalla parte superiore a sinistra dello schermo (nella barra di navigazione), sopra il punto in cui è indicato Sara Perez | Licenze.

1. Sono state assegnate le licenze all'utente.

1. Disconnettersi da tutte le schede del browser aperte. Disconnettersi selezionando l'icona dell'utente accanto all'indirizzo di posta elettronica nell'angolo in alto a destra della schermata, poi selezionare **Disconnetti**. Chiudere quindi tutte le finestre del browser.

### Attività 3

In questa attività, si effettuerà l'accesso come Sara Perez per la prima volta.

1. Aprire Microsoft Edge.

1. Nella barra degli indirizzi immettere **https://login.microsoft.com**.

1. Accedere come **sara@WWLxZZZZZ.onmicrosoft.com** (dove ZZZZZZ è l'ID tenant univoco fornito dal provider di servizi di hosting per i lab autorizzato).
1. Immettere la password temporanea impostata nell'attività precedente.

1. Viene chiesto di aggiornare la password. Nel campo Password corrente immettere la password temporanea dell'attività precedente.

1. Nel campo Nuova password immettere una nuova password, confermarla e quindi selezionare **Accedi**.  Prendere nota della nuova password perché sarà necessaria per l'esercizio del lab successivo sulla reimpostazione della password self-service.

1. Poiché questa è la prima volta che si esegue l'accesso come Sara Perez, potrebbe essere richiesto di configurare MFA. Seguire le istruzioni visualizzate sullo schermo per configurare l'autenticazione a più fattori.

1. A questo momento dovrebbe essere eseguito l'accesso all'account Microsoft di Sara.  Si noti che le licenze di Sara assegnate nell'attività precedente erano limitate solo a Power Automate Gratuito e Power Apps for Developer e non includevano le licenze E5.

1. Per disconnettersi, selezionare l'icona nell'angolo superiore destro della finestra di Microsoft 365 visualizzata come cerchio con le lettere SP (accanto all'icona del punto interrogativo), quindi selezionare **Disconnetti** e infine chiudere il browser.

### Revisione

In questo lab è stata avviata l'esplorazione iniziale di Microsoft Entra ID. Poiché gli abbonati di Microsoft 365 accedono automaticamente utilizzando Microsoft Entra ID, si è scoperto che è possibile accedere alle funzionalità e ai servizi di Microsoft Entra ID tramite il portale di amministrazione Microsoft 365 o il portale di Azure.  Qualunque approccio si preferisca si arriva alla stessa posizione.  Sono stati anche illustrati in modo dettagliato il processo di creazione di un nuovo utente e le diverse impostazioni configurabili, inclusi i gruppi a cui è possibile assegnare l'utente, la disponibilità dei ruoli e l'assegnazione di licenze utente.
