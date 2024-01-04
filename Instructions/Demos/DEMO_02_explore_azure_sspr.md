<!---
---
Demo: tiolo: "Reimpostazione della password self-service Microsoft Entra (SSPR)" Percorso di apprendimento/Modulo/Unità: Percorso di apprendimento: Descrivere le funzionalità di Microsoft Entra; Modulo 2: Descrivere le funzionalità di autenticazione di Microsoft Entra ID; Unità 4: Descrivere la reimpostazione della password self-service"
---
--->

# Demo: Reimpostazione della password self-service di Microsoft Entra (SSPR)

Questa demo corrisponde al contenuto di Learn seguente:

- Percorso di apprendimento: Descrivere le funzionalità di Microsoft Entra
- Modulo: Descrivere le funzionalità di autenticazione di Microsoft Entra ID
- Unità: Descrivere la reimpostazione della password self-service

## Scenario dimostrativo

Questa demo illustra le varie impostazioni associate all'abilitazione della reimpostazione della password self-service.

1. Tornare alla scheda del browser aperta denominata "Interfaccia di amministrazione Home Microsoft Entra."  Se in precedenza è stata chiusa questa scheda del browser, aprire Microsoft Edge e accedere a**[entra.microsoft.com](https://entra.microsoft.com)** con le credenziali di amministratore Microsoft 365.

1. Nel riquadro di spostamento a sinistra, espandere **Protezione** e selezionare **Reimpostazione della password**.

1. La scheda Proprietà è evidenziata.  Nella finestra Proprietà, notare che la reimpostazione della password self-service può essere abilitata per Nessuno, Selezionati o Tutti.
    1. Posizionare il cursore sull'icona delle informazioni accanto alla dicitura "Ripristino password self-service abilitato" e illustrare che è possibile scegliere "Selezionati" per limitare la reimpostazione della password a un gruppo di utenti, oppure selezionare Nessuno o Tutti.
    1. Posizionare il cursore sull'icona delle informazioni accanto alla dicitura "seleziona gruppo" e illustrare che in questa posizione viene identificato il gruppo di utenti a cui è consentito reimpostare la password.   È necessario includere gli utenti nel gruppo, non è possibile selezionarli individualmente.  Inoltre, se si modifica il gruppo, il gruppo selezionato sostituisce quello attualmente elencato.  Pertanto, si raccomanda di aggiungere gli utenti al gruppo di reimpostazione della password self-service.
    1. Prendere nota del riquadro azzurro delle informazioni e illustrarlo agli studenti: queste impostazioni si applicano solo agli utenti finali dell'organizzazione. Gli amministratori sono sempre abilitati per la reimpostazione della password self-service e devono usare due metodi di autenticazione per reimpostare la propria password.

1. Dal riquadro di spostamento a sinistra di Reimpostazione della password, selezionare Metodi di autenticazione.
    1. Posizionare il cursore sull'icona delle informazioni accanto alla dicitura "Numero di metodi richiesti per il ripristino".  Illustrare che questo parametro stabilisce il numero di metodi alternativi di identificazione che un utente della directory deve avere per reimpostare la propria password.   Non modificare l'impostazione.
    1. Illustrare i diversi "metodi disponibili per gli utenti", compreso il punto secondo cui la reimpostazione della password self-service supporta le domande di sicurezza. Selezionare Domande di sicurezza per visualizzare le opzioni d'utilizzo delle domande di sicurezza. Dopo aver finito di parlare delle opzioni, tornare indietro e selezionare Domande di sicurezza per rimuovere il segno di spunta.

1. Dal riquadro di spostamento a sinistra di Reimpostazione della password, selezionare Registrazione.
    1. Passare con il puntatore del mouse sull'icona delle informazioni accanto alla dicitura "Richiedi agli utenti di registrarsi al momento dell'accesso".   Illustrarlo agli utenti.  
    1. Passare il mouse sull'icona delle informazioni accanto a: "Numero di giorni prima che all'utente venga chiesto di riconfermare le informazioni di autenticazione".   Illustrarlo agli utenti.  

1. Dal riquadro di spostamento a sinistra di Reimpostazione della password, selezionare Notifiche.  Illustrare le due impostazioni: passare con il puntatore del mouse sull'icona delle informazioni per visualizzare la descrizione.

1. Notare che il riquadro di spostamento Reimpostazione password include anche opzioni per visualizzare i log di controllo e di utilizzo e le informazioni dettagliate.

1. Selezionare la X nell'angolo in alto a destra della pagina. Questo consente di ritornare alla pagina principale del tenant Contoso.

1. Tenere aperta questa pagina del browser per la prossima demo.

### Revisione

In questa demo sono state mostrate le impostazioni associate alla reimpostazione della password self-service.
