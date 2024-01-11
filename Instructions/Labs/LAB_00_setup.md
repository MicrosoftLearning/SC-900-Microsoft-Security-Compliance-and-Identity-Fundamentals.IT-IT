<!---
---
Lab: Titolo: 'Eseguire la configurazione'
---
--->

# Lab: configurazione

## Tenant WWL: condizioni per l'utilizzo
Se, nell'ambito di una consegna di un corso con istruttore, viene fornito un tenant, tenere presente che il tenant viene messo a disposizione per supportare i lab pratici di tale corso.

I tenant non devono essere condivisi o usati per scopi diversi dai lab pratici. Il tenant utilizzato in questo corso è un tenant di valutazione e non può essere utilizzato o reso accessibile dopo il termine della lezione e non è idoneo per l'estensione.

I tenant non devono essere convertiti in un abbonamento a pagamento. I tenant ottenuti nell'ambito di questo corso rimangono di proprietà di Microsoft Corporation, che si riserva il diritto di accedervi e di recuperarli in qualsiasi momento.

## Scenario laboratorio

Questo lab sulla configurazione illustra come abilitare il log di controllo Microsoft.

**Tempo stimato:** 5-10 minuti

### Eseguire la configurazione - Abilitare il log di controllo di Microsoft 365

In questa attività di configurazione, viene abilita la funzionalità di log di controllo in Microsoft 365.  Sebbene la documentazione indichi che il log di controllo è attivato per impostazione predefinita, questa funzionalità non è abilitata per la maggior parte dei tenant dei lab e la sua attivazione potrebbe richiedere parecchie ore.  Abilitare questa funzionalità costituisce un vantaggio, poiché Microsoft 365 utilizza i log di controllo per informazioni dettagliate e attività degli utenti identificate nei criteri e nelle informazioni dettagliate di analisi.

1. Aprire Microsoft Edge. Nella barra degli indirizzi immettere **admin.microsoft.com**.

1. Accedere utilizzando le credenziali di amministratore.
    1. Nella finestra Accedi immettere **admin@WWLxZZZZZZ.onmicrosoft.com** (dove ZZZZZZ è l'ID tenant univoco fornito dal proprio provider di hosting del lab) e quindi selezionare **Avanti**.
    1. Immettere la password di amministratore, che dovrebbe essere fornita dal proprio provider di hosting del lab. Selezionare **Accedi**.
    1. Quando viene richiesto di rimanere connessi, selezionare **Sì**. Verrà visualizzata la pagina dell'interfaccia di amministrazione di Microsoft 365.

1. Dal riquadro di spostamento a sinistra dell'interfaccia di amministrazione di Microsoft 365, selezionare **Mostra tutto**.

1. In Interfacce di amministrazione selezionare **Conformità**.  Si apre una nuova pagina del browser alla pagina di benvenuto del portale di conformità di Microsoft Purview.  

1. Nel riquadro di spostamento a sinistra, sotto Soluzioni, selezionare **Controllo**.  Nota: la funzionalità di controllo è accessibile anche attraverso la pagina iniziale di Microsoft 365 Defender (precedentemente denominata Centro di sicurezza di Microsoft 365).

1. Verificare che la scheda **Nuova ricerca**sia selezionata (sottolineata).

1. Una volta visualizzata la pagina Controllo, attendere 2-3 minuti.  Se Controllo NON è abilitato, verrà visualizzata una barra blu nella parte superiore della pagina con l'indicazione di avviare la registrazione delle attività degli utenti e degli amministratori.  Selezionare **Avvia la registrazione delle attività di utenti e amministratori**.  Se viene chiesto di confermare che è necessario aggiornare le impostazioni dell'organizzazione, selezionare **Sì**. Una volta abilitato il controllo, la barra blu scompare.  Se la barra blu non è presente, il controllo è già abilitato e non sono richieste ulteriori azioni.  Un altro modo per verificare se il controllo è abilitato è utilizzare PowerShell, ma non rientra nell'ambito di questo corso.

1. Tornare alla home page del portale di conformità di Microsoft Purview selezionando **Home** dal riquadro di spostamento sinistro per disconnettersi da Microsoft 365. Per disconnettersi, selezionare l'icona nell'angolo superiore destro della finestra di Microsoft 365 visualizzata come cerchio con le lettere MA (accanto all'icona del punto interrogativo) e quindi selezionare **Disconnetti**. Chiudere il browser.

### Revisione

In questa attività di configurazione è stata abilitata la funzionalità Log di controllo in Microsoft 365.
