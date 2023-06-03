<a name="---"></a><!---
---
Lab: Titolo: 'Eseguire la configurazione'
---
--->

# <a name="lab-setup"></a>Laboratorio: Eseguire la configurazione

## <a name="lab-scenario"></a>Scenario del lab

Questo lab sulla configurazione illustra come abilitare il log di controllo Microsoft.

**Tempo stimato**: 5-10 minuti

### <a name="setup---enable-microsoft-365-audit-log"></a>Eseguire la configurazione - Abilitare il log di controllo di Microsoft 365

In questa attività di configurazione, si abiliterà la funzionalità Log di controllo in Microsoft 365.  Sebbene la documentazione indichi che il log di controllo è attivato per impostazione predefinita, questa funzionalità non è abilitata per la maggior parte dei tenant dei lab e la sua attivazione potrebbe richiedere parecchie ore.  È vantaggioso abilitare questa funzionalità, poiché Microsoft 365 utilizza i log di controllo per informazioni dettagliate e attività degli utenti identificate nei criteri e nelle informazioni dettagliate di analisi.

1. Aprire Microsoft Edge. Nella barra degli indirizzi immettere **admin.microsoft.com**.

1. Accedere con le credenziali di amministratore.
    1. Nella finestra Accedi immettere **admin@WWLxZZZZZZ.onmicrosoft.com** (dove ZZZZZZ è l'ID tenant univoco fornito dal proprio provider di hosting del lab) e quindi selezionare **Avanti**.
    1. Immettere la password di amministratore, che dovrebbe essere fornita dal proprio provider di hosting del lab. Fare clic su **Accedi**.
    1. Quando compare la domanda se rimanere connessi, selezionare **Sì**. In questo modo si accede alla pagina dell'interfaccia di amministrazione di Microsoft 365.

1. Dal riquadro di spostamento sinistro dell'interfaccia di amministrazione di Microsoft 365, selezionare **Mostra tutto**.

1. In Interfacce di amministrazione selezionare **Conformità**.  Si apre una nuova pagina del browser alla pagina di benvenuto del portale di conformità di Microsoft Purview.  

1. Dal riquadro di spostamento sinistro, sotto Soluzioni, selezionare **Controllo**.  Nota: la funzionalità di controllo è accessibile dalla home page di Microsoft 365 Defender (in precedenza chiamato Centro sicurezza Microsoft 365).

1. Verificare che la scheda **Nuova ricerca**sia selezionata (sottolineata).

1. Una volta arrivati nella pagina Controllo, attendere 2-3 minuti.  Se il controllo non è abilitato, verrà visualizzata una barra blu in cima alla pagina per avviare la registrazione delle attività di utenti e amministratori.  Selezionare **Avvia la registrazione delle attività di utenti e amministratori**.  Se viene chiesto di confermare che è necessario aggiornare le impostazioni dell'organizzazione, selezionare **Sì**. Una volta abilitato il controllo, la barra blu scompare.  Se la barra blu non è presente, il controllo è già abilitato e non sono richieste ulteriori azioni.  È possibile verificare se il controllo sia attivato anche tramite PowerShell, ma questo non rientra nell'ambito di questo corso.

1. Tornare alla home page del portale di conformità di Microsoft Purview selezionando **Home** dal riquadro di spostamento sinistro per disconnettersi da Microsoft 365. Per disconnettersi, selezionare l'icona nell'angolo superiore destro della finestra di Microsoft 365 visualizzata come cerchio con le lettere MA (accanto all'icona del punto interrogativo) e quindi selezionare **Disconnetti**. Chiudere il browser.

### <a name="review"></a>Verifica

In questa attività di configurazione è stata abilitata la funzionalità Log di controllo in Microsoft 365.
