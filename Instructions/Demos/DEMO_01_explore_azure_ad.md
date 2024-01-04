<!---
---
Demo: titolo: "Esplorare le impostazioni utente di Microsoft Entra ID" Percorso di apprendimento/Modulo/Unità: "Percorso di apprendimento: descrivere le funzionalità di Microsoft Entra; Modulo 1: Descrivere la funzionalità e i tipi di identità di Microsoft Entra ID; Unità 3: Descrivere i tipi di identità di Microsoft Entra"
---
--->

# Demo: impostazioni utente di Microsoft Entra ID

Questa demo corrisponde al contenuto di Learn seguente:

- Percorso di apprendimento: Descrivere le funzionalità di Microsoft Entra
- Modulo: Descrivere la funzione e i tipi di identità di Microsoft Entra ID.
- Unità: Descrivere i tipi di identità.

## Scenario dimostrativo

In questa demo, verrà eseguito l'accesso a Microsoft Entra ID ed esaminate le varie impostazioni per un utente esistente.

1. Aprire Microsoft Edge.

1. Nella barra degli indirizzi immettere **admin.microsoft.com** per accedere all'interfaccia di amministrazione di Microsoft 365.

1. Accedere utilizzando le credenziali di amministratore.
    1. Nella finestra Accedi immettere **admin@WWLxZZZZZZ.onmicrosoft.com** (dove ZZZZZZ è l'ID tenant univoco fornito dal proprio provider di hosting del lab) e quindi selezionare **Avanti**.
    1. Immettere la password di amministratore, che dovrebbe essere fornita dal proprio provider di hosting del lab. Selezionare **Accedi**.
    1. Quando viene richiesto di rimanere connessi, selezionare **Sì**.

1. Dal riquadro di spostamento a sinistra dell'interfaccia di amministrazione di Microsoft 365, selezionare **Mostra tutto**.

1. In Interfaccia di amministrazione, selezionare **Identità** (potrebbe essere necessario scorrere verso il basso).  Verrà visualizzata una nuova pagina del browser della pagina panoramica dell'Interfaccia di amministrazione di Microsoft Entra. Qui si potranno visualizzare informazioni di base sul tenant Contoso. Scorrendo verso il basso nella finestra principale, si potranno visualizzare anche informazioni su avvisi, feed, funzionalità in evidenza e altro ancora.  
    1. Nota per il presentatore/istruttore: è anche possibile accedere direttamente all'interfaccia di amministrazione di Microsoft Entra andando su **[entra.microsoft.com](https://entra.microsoft.com)**.

1. Nel riquadro di spostamento a sinistra, espandere **Utenti** quindi selezionare **Tutti gli utenti**.  Nella pagina utenti è possibile visualizzare ulteriori opzioni di navigazione e l'elenco degli utenti. Il tenant è già configurato con gli utenti.

1. Dall'elenco degli utenti, selezionare **Adele Vance**.

1. Notare che nel riquadro di spostamento a sinistra, l'opzione **Panoramica** è evidenziata in grigio chiaro.  Mostrare/illustrare le informazioni visualizzate nella pagina di panoramica.  Selezionare la scheda **Monitoraggio** nella parte superiore della pagina che mostra gli accessi degli utenti (non verrà visualizzato alcun accesso, a meno che non si sia precedentemente effettuato l'accesso come Adele Vance).  Quindi selezionare **Proprietà** per visualizzare tutte le proprietà dell'oggetto utente Adele Vance.

1. Dal riquadro di spostamento a sinistra, selezionare **Ruoli assegnati**.  A questo utente non è assegnato alcun ruolo di amministratore.  Nella parte superiore della pagina, selezionare **+ Aggiungi assegnazioni**, quindi dalla pagina Aggiungi assegnazioni, in Seleziona ruolo, espandere il campo Cerca ruolo per visualizzare un elenco dei tipi di ruoli amministrativi disponibili.  Non è necessario aggiungere nulla, basta chiudere la pagina selezionando la **X** in alto a destra della pagina.

1. Dal riquadro di spostamento a sinistra, selezionare **Gruppi**.  Illustrare che si tratta di un utente che fa parte di diversi gruppi.  Qui è possibile illustrare i tipi di gruppi.  Per aggiungere questo utente ad altri gruppi, occorre selezionare **+ Aggiungi appartenenze**.  Non aggiungere nuovi gruppi, è sufficiente sottolineare quanto sia facile aggiungere un utente ai gruppi esistenti. Chiudere la finestra Seleziona gruppi selezionando la **X** nell'angolo in alto a destra della pagina.

1. Dal riquadro di spostamento a sinistra, selezionare **Licenze**. Notare che a questo utente sono state assegnate le licenze Microsoft 365 E5 e la licenza EMS.  Per aggiungere una licenza, selezionare **+ Assegnazioni** dalla parte superiore della finestra principale.  Visualizzare le licenze di questo utente. Non modificare nulla.  Chiudere questa finestra selezionando la **X** nell'angolo in alto a destra della pagina.

1. Dal riquadro di spostamento sinistro selezionare **Dispositivi**.  Non viene visualizzato nulla, ma si può illustrare che, se a questo utente venissero assegnati dei dispositivi, questo è il punto in cui verrebbero visualizzati.

1. Dal riquadro di spostamento a sinistra, selezionare **Assegnazioni di ruolo Azure**.  Illustrare:
    1. Si tratta di una scheda diversa da quella dei ruoli assegnati visualizzata in precedenza, in quanto questa scheda è destinata al controllo degli accessi in base al ruolo in Microsoft Entra.
    1. Anche se non è elencato nulla, in questa scheda è possibile visualizzare le assegnazioni di ruolo, assegnate ad Adele, per le risorse di Azure. Ad esempio, se viene creato un gruppo di risorse di Azure e viene assegnato un ruolo specifico ad Adele, come quello di proprietario o di collaboratore del gruppo di risorse, il ruolo sarà elencato qui. Fa parte del Controllo degli accessi in base al ruolo di Azure. Tale assegnazione di ruolo viene aggiunta e gestita come parte di tale specifica risorsa.

1. Dal riquadro di spostamento a sinistra, selezionare **Metodi di autenticazione**.  Illustrare la descrizione che indica: "Qui è possibile impostare i numeri di telefono e gli indirizzi e-mail che gli utenti utilizzano per eseguire l'autenticazione a più fattori e la reimpostazione della password self-service e per reimpostare la password di un utente". Se un utente è configurato per la reimpostazione della password self-service o è richiesto l'uso della MFA, e in qualità di amministratore si popola questo campo, allora saranno già registrati e non dovranno passare attraverso la procedura di registrazione per la reimpostazione della password self-service o MFA.  È comune che l'utente si registri autonomamente piuttosto che rivolgersi a un amministratore per farlo.

1. Selezionare la **X** nell'angolo in alto a destra della pagina. Questo consente di ritornare all'elenco degli utenti.

1. Selezionare la **X** nell'angolo in alto a destra della pagina. Questo consente di ritornare alla pagina principale dell'interfaccia di amministrazione di Microsoft Entra.

1. Mantenere aperta questa scheda del browser, che verrà utilizzata per la prossima demo.

### Revisione

In questa demo sono state presentate le impostazioni di un utente esistente, compresi i gruppi a cui l'utente può essere assegnato, la disponibilità dei ruoli e l'assegnazione delle licenze utente.
