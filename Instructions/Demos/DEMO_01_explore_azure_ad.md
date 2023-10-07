<!---
---
Demo: Titolo: 'Esplora impostazioni utente Microsoft Entra ID' Percorso di apprendimento/Modulo/Unità: "Percorso di apprendimento: Descrivere le funzionalità di Microsoft Entra; Modulo 1: Descrivere i tipi di funzione e identità di Microsoft Entra ID; Unità 3: Descrivere i tipi di identità Microsoft Entra
---
--->

# Demo: impostazioni utente Microsoft Entra ID

Questa demo corrisponde al contenuto di Learn seguente:

- Percorso di apprendimento: descrivere le funzionalità di Microsoft Entra.
- Modulo: descrivere i tipi di funzione e identità di Microsoft Entra ID.
- Unità: descrivere i tipi di identità.

## Scenario demo

In questa demo si accederà Microsoft Entra ID e si esamineranno le varie impostazioni per un utente esistente.

1. Aprire Microsoft Edge.

1. Nella barra degli indirizzi immettere **admin.microsoft.com** per accedere all'interfaccia di amministrazione di Microsoft 365.

1. Accedere con le credenziali di amministratore.
    1. Nella finestra Accedi immettere **admin@WWLxZZZZZZ.onmicrosoft.com** (dove ZZZZZZ è l'ID tenant univoco fornito dal proprio provider di hosting del lab) e quindi selezionare **Avanti**.
    1. Immettere la password di amministratore, che dovrebbe essere fornita dal proprio provider di hosting del lab. Fare clic su **Accedi**.
    1. Quando compare la domanda se rimanere connessi, selezionare **Sì**.

1. Dal riquadro di spostamento sinistro dell'interfaccia di amministrazione di Microsoft 365, selezionare **Mostra tutto**.

1. In Amministrazione center selezionare **Identità** (potrebbe essere necessario scorrere verso il basso).  Verrà visualizzata una nuova pagina del browser alla pagina di panoramica dell'interfaccia di amministrazione Microsoft Entra. Qui verranno visualizzate informazioni di base sul tenant Contoso. Se si scorre verso il basso la finestra principale, verranno visualizzate anche informazioni sugli avvisi, il feed, le evidenziazioni delle funzionalità e altro ancora.  
    1. Nota per relatore/insegnante: è anche possibile accedere al centro Microsoft Entra Amministrazione direttamente passando a **[entra.microsoft.com](https://entra.microsoft.com)**.

1. Nel riquadro di spostamento a sinistra espandere **Utenti** e quindi **Tutti gli utenti**.  Nella pagina utenti è possibile visualizzare opzioni di spostamento aggiuntive e l'elenco degli utenti. Il tenant è già configurato con gli utenti.

1. Dall'elenco degli utenti, selezionare **Adele Vance**.

1. Si noti che nel pannello di spostamento a sinistra, **Panoramica** è evidenziata in grigio chiaro.  Mostra/parla alle informazioni visualizzate nella pagina di panoramica.  Selezionare la scheda **Monitoraggio** nella parte superiore della pagina che mostra gli accessi utente (non verrà visualizzato alcun accesso, a meno che non sia stato eseguito l'accesso in precedenza come Adele Vance).  Selezionare quindi **Proprietà** per visualizzare tutte le proprietà per l'oggetto utente Adele Vance.

1. Dal riquadro di spostamento sinistro, selezionare **Ruoli assegnati**.  A questo utente non è assegnato alcun ruolo di amministratore.  Nella parte superiore della pagina selezionare **+ Aggiungi assegnazioni**, quindi dalla pagina Aggiungi assegnazioni espandere il campo Ruolo di ricerca in Seleziona ruolo per visualizzare un elenco dei tipi di ruoli amministrativi disponibili.  Non aggiungerne nessuno, basta chiudere la pagina selezionando la **X** nella parte superiore destra della pagina.

1. Dal riquadro di spostamento sinistro, selezionare **Gruppi**.  Attestare che l'utente è un membro di diversi gruppi.  Qui è possibile attestare i tipi di gruppi.  Per aggiungere questo utente ad altri gruppi, occorre selezionare **+ Aggiungi appartenenze**.  Non aggiungere nuovi gruppi, è sufficiente sottolineare quanto sia facile aggiungere un utente ai gruppi esistenti. Chiudere la finestra Seleziona gruppi **selezionando X** nell'angolo superiore destro della pagina.

1. Dal riquadro di spostamento sinistro, selezionare **Licenze**. Si ricorda che a questo utente sono assegnate le licenze Microsoft 365 E5 e la licenza EMS.  Per aggiungere una licenza, selezionare **+ Assegnazioni** dalla parte superiore della finestra principale.  Mostrare le licenze per questo utente. NON modificare nulla.  Chiudere questa finestra selezionando la **X** nell'angolo in alto a destra della pagina.

1. Dal riquadro di spostamento sinistro selezionare **Dispositivi**.  Non appare nulla, ma si può dire che se questo utente avesse dei dispositivi assegnati apparirebbero qui.

1. Dal riquadro di spostamento sinistro, selezionare **Assegnazioni di ruolo di Azure**.  Nota:
    1. Questa opzione è diversa dalla scheda ruoli assegnati illustrata in precedenza in quella scheda precedente per il controllo degli accessi in base al ruolo in Microsoft Entra.
    1. Anche se qui non è elencato nulla, questa è la scheda in cui è possibile visualizzare le assegnazioni di ruolo, assegnate a Adele, per le risorse di Azure. Per esempio, se si dovesse creare un gruppo di risorse di Azure, e si assegnasse ad Adele un ruolo specifico, come proprietaria o collaboratrice del gruppo di risorse, si vedrebbe quel ruolo elencato qui. Questo fa parte del controllo degli accessi in base al ruolo di Azure (RBAC Azure). Tale assegnazione di ruolo viene aggiunta e gestita come parte di tale risorsa specifica.

1. Dal pannello di navigazione sinistro, selezionare **Metodi di autenticazione**.  Ricordare la descrizione che dice: "In questa pagina è possibile configurare i numeri di telefono e gli indirizzi di posta elettronica usati dagli utenti per eseguire Multi-Factor Authentication e la reimpostazione della password self-service e reimpostare la password di un utente". Se un utente è configurato per la reimpostazione della password self-service o è richiesto l'uso della MFA, e in qualità di amministratore si popola questo campo, allora saranno già registrati e non dovranno passare attraverso la procedura di registrazione per la reimpostazione della password self-service o MFA.  È comune che l'utente si registri autonomamente piuttosto che rivolgersi a un amministratore per farlo.

1. Selezionare la **X** nell'angolo in alto a destra della pagina. In questo modo si torna all'elenco degli utenti.

1. Selezionare la **X** nell'angolo in alto a destra della pagina. Verrà restituita la pagina principale per l'interfaccia di amministrazione di Microsoft Entra.

1. Mantenere aperta questa scheda del browser perché verrà usata per la demo successiva.

### Verifica

In questa demo sono state presentate le impostazioni di un utente esistente, compresi i gruppi a cui l'utente può essere assegnato, la disponibilità dei ruoli e l'assegnazione delle licenze utente.
