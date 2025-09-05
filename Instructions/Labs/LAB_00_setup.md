---
lab:
  title: Configurazione del laboratorio
  module: Setup your Microsoft 365 lab tenant (not associated with a Learn module)
---

# Lab: Configurazione del tenant di Microsoft 365

## Tenant WWL: condizioni per l'utilizzo
Se, nell'ambito di una consegna di un corso con istruttore, viene fornito un tenant, tenere presente che il tenant viene messo a disposizione per supportare i lab pratici di tale corso.

I tenant non devono essere condivisi o usati per scopi diversi dai lab pratici. Il tenant utilizzato in questo corso è un tenant di valutazione e non può essere utilizzato o reso accessibile dopo il termine della lezione e non è idoneo per l'estensione.

I tenant non devono essere convertiti in un abbonamento a pagamento. I tenant ottenuti nell'ambito di questo corso rimangono di proprietà di Microsoft Corporation, che si riserva il diritto di accedervi e di recuperarli in qualsiasi momento.

## Scenario laboratorio

Questo lab di installazione consiste nell'abilitare le funzionalità di monitoraggio dei file e del log di controllo Microsoft nel tenant di Microsoft 365.

**Tempo stimato**: 10-15 minuti

### Installazione - Abilitare il log di controllo e il monitoraggio dei file di Microsoft 365

In questa attività di installazione si abiliteranno le funzionalità di monitoraggio dei log di controllo e dei file in Microsoft 365.  

1. Aprire Microsoft Edge. Nella barra degli indirizzi immettere **`https://admin.microsoft.com`**.

1. Accedere con le credenziali di amministrazione del tenant Microsoft 365 fornite dall'ALH (provider di servizi di hosting per i lab autorizzato).

1. Dal riquadro di spostamento a sinistra dell'interfaccia di amministrazione di Microsoft 365, selezionare **Mostra tutto**.

1. In Interfacce di amministrazione selezionare **Sicurezza**.  Verrà visualizzata una nuova pagina del browser nella pagina iniziale di Microsoft Defender.

1. Nel pannello di spostamento sinistro scorrere verso il basso ed espandere **Sistema**.  Nell'elenco espanso selezionare **Controlla**.  Nota: la funzionalità di controllo è accessibile anche tramite il portale di Microsoft Purview.

1. Una volta atterrato nella pagina Controllo, attendere 1-2 minuti.  Se il controllo NON è abilitato, verrà visualizzata una barra blu nella parte superiore della pagina con l'indicazione di avviare la registrazione delle attività di utenti e amministratori.  Selezionare **Avvia la registrazione delle attività di utenti e amministratori**.  Una volta abilitato il controllo, la barra blu scompare.  Se la barra blu non è presente, il controllo è già abilitato e non sono richieste ulteriori azioni.  Se viene visualizzato un messaggio: "Si è verificato un problema se l'attività viene registrata. Provare ad aggiornare la pagina." Se non è stata apportata alcuna modifica dopo l'aggiornamento della pagina, sarà necessario abilitare il controllo tramite PowerShell.
    1. Selezionare l'icona blu di Windows PowerShell sulla barra delle applicazioni e selezionare **Esegui come amministratore**.
    1. Installare il modulo PowerShell di Exchange Online immettendo **`Install-Module -Name ExchangeOnlineManagement`**.  Quando richiesto, "Assicurarsi di voler installare i moduli da 'PSGallery'", selezionare **`[A]` Sì a tutti**
    1. Caricare ora il modulo immettendo **`Import-Module ExchangeOnlineManagement`**.
    1. Per connettersi, immettere **`Connect-ExchangeOnline -UserPrincipalName admin@WWLxZZZZZZ.onmicrosoft.com`**.  Per l'UPN immettere il nome utente dell'amministratore trovato nella scheda risorse del lab.
    1. Verrà richiesto di effettuare l'accesso.  Immettere il nome utente e la password amministrativi disponibili nella scheda risorse del lab.
    1. Per attivare Controllo, immettere **`Set-AdminAuditLogConfig -UnifiedAuditLogIngestionEnabled $true`**. Viene visualizzato un messaggio che informa che la modifica potrebbe richiedere fino a 60 minuti.
    1. Anche se potrebbero essere necessari fino a 60 minuti, è possibile verificare che il comando sia stato ricevuto immettendo **`Get-AdminAuditLogConfig | FL UnifiedAuditLogIngestionEnabled`**.  Se il controllo è abilitato, la proprietà UnifiedAuditLogIngestionEnabled mostrerà il valore true.

1. Nel pannello di spostamento a sinistra, in Sistema, selezionare **Impostazioni**.

1. Nella pagina delle impostazioni selezionare **App cloud**.   Scorrere verso il basso, quindi in **Information Protection** selezionare **File**.

1. Se non è già abilitato, selezionare la casella accanto a dove è indicato **Abilita monitoraggio** file e quindi selezionare **Salva**.  

1. Questo conclude la configurazione del lab nel tenant di Microsoft 365.
1. È possibile chiudere la scheda del browser "Cloud Apps-Microsoft Defender", ma mantenere aperta la scheda "interfaccia di amministrazione di Microsoft 365" per l'esercizio successivo.

### Revisione

In questa configurazione sono state abilitate le funzionalità di monitoraggio dei log di controllo e dei file in Microsoft 365.
