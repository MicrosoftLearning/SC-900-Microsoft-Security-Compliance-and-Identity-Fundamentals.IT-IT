<!---
---
Demo: titolo: "Accesso condizionale di Azure AD" Percorso di apprendimento/modulo/unità: "Percorso di apprendimento: Descrivere le funzionalità di Microsoft Entra; Modulo 3: Descrivere le funzionalità di gestione degli accessi di Microsoft Entra ID; Unità 2: Descrivere l'accesso condizionale"
---
--->

# Demo: Accesso condizionale a Microsoft Entra

Questa demo corrisponde al contenuto di Learn seguente:

- Percorso di apprendimento: Descrivere le funzionalità di Microsoft Entra
- Modulo: Descrivere le funzionalità di gestione degli accessi di Microsoft Entra ID
- Unità: Descrivere l'accesso condizionale

## Scenario dimostrativo

Questa demo presenterà le varie opzioni disponibili per i criteri di accesso condizionale.

1. Tornare alla scheda del browser aperta denominata "Interfaccia di amministrazione Home Microsoft Entra."  Se in precedenza è stata chiusa questa scheda del browser, aprire Microsoft Edge e accedere a**[entra.microsoft.com](https://entra.microsoft.com)** con le credenziali di amministratore Microsoft 365.

1. Dal riquadro di spostamento a sinistra, espandere **Protezione** e selezionare **Accesso condizionale**.

1. Verrà visualizzata la pagina di panoramica dell'accesso condizionale.  Qui verranno visualizzati i riquadri che mostrano il riepilogo dei criteri e gli avvisi generali.  Dal riquadro di spostamento a sinistra, selezionare **Criteri**.

1. Viene visualizzata la schermata Criteri di accesso condizionale. Tutti i criteri di accesso condizionale esistenti sono elencati qui. Per visualizzare le impostazioni associate all'accesso condizionale, selezionare **+ Nuovo criterio**.

1. Nel campo **Nome** immettere un nome per il criterio.

1. Notare che sono disponibili diverse opzioni in **Assegnazioni**.  Poiché i criteri di accesso condizionale sono simili alle istruzioni if/then, le impostazioni di assegnazione sono simili alle istruzioni "if".
    1. **Utenti**: passare con il puntatore del mouse sull'icona delle informazioni accanto alla dicitura "Utenti" e illustrare che in questa sezione vengono selezionate le identità della directory a cui si applica il criterio, compresi gli utenti, i gruppi e le entità servizio. Selezionare **0 utenti e gruppi selezionati**.  Diventerà ora visibile l'opzione per includere o escludere utenti o gruppi. Selezionare e illustrare le impostazioni disponibili per la scheda **Includi**, quindi selezionare e descrivere le impostazioni disponibili per la scheda **Escludi**.
    1. **Risorse di destinazione**: selezionare **Risorse di destinazione**.  Qui è possibile controllare l'accesso in base a tutto o a uno specifico traffico di accesso alla rete, alle applicazioni cloud o alle azioni.  Espandere il campo sotto la dicitura "Selezionare l'ambito a cui si applica questo criterio".  Qui è possibile selezionare se il criterio si applica alle app cloud, alle azioni dell'utente o al contesto di autenticazione.  
        1. Selezionare **App cloud**, quindi nella scheda Includi, selezionare l'opzione **Seleziona app**. Sotto la dicitura **Seleziona**, selezionare **Nessuna** e verrà aperta una finestra per selezionare una o più applicazioni a cui applicare il criterio.
        1. Chiudere la finestra Seleziona app cloud selezionando la **X** nell'angolo in alto a destra della finestra.
        1. Se il tempo lo consente, si può scegliere di analizzare le altre opzioni (azioni utente e contesto di autenticazione) per vedere le opzioni di configurazione per ciascuna di esse.
    1. **Condizioni**: passare con il puntatore del mouse sull'icona delle informazioni accanto alla dicitura "Condizioni" e illustrare che si tratta di condizioni che definiscono quando si applica il criterio. Ad esempio, "posizione". Selezionare **0 condizioni selezionate**. Illustrare i diversi "segnali" elencati.   Selezionare alcune delle opzioni selezionando prima l'icona delle informazioni per definire di cosa si tratta e quindi **Non configurato** per l'elemento specifico per visualizzare le varie opzioni.
        1. **Rischio utente** - Un rischio utente rappresenta la probabilità che una data identità o account siano compromessi. Questi rischi vengono calcolati offline usando le origini di intelligence sulle minacce interne ed esterne di Microsoft.
        1. **Rischio di accesso** - Un rischio di accesso rappresenta la probabilità che una data richiesta di autenticazione non sia autorizzata dal proprietario dell'identità. Ad esempio, se l'accesso avviene da un indirizzo IP anonimo o da un spostamento fisico atipico, ecc.
        1. **Piattaforma del dispositivo** - Piattaforma da cui l'utente sta effettuando l'accesso. Ad esempio, "iOS".
        1. **Posizione** - Posizione (determinata usando l'intervallo di indirizzi IP) da cui l'utente sta effettuando l'accesso
        1. **App cliente** - Software usato dall'utente per accedere all'app cloud. Ad esempio, "Browser"
        1. **Filtra per dispositivi** - Quando si creano criteri di accesso condizionale, gli amministratori possono definire dispositivi di destinazione o escludere dispositivi specifici nel proprio ambiente. L'amministratore può definire dispositivi specifici usando gli operatori e le proprietà supportati per i filtri dei dispositivi e le altre condizioni di assegnazione disponibili nei criteri di accesso condizionale.

1. **Controlli di accesso**: tornando all'analogia secondo cui i criteri di accesso condizionale sono simili alle istruzioni if/then, i controlli di accesso sono analoghi all'istruzione "then".
    1. **Concessione** - Passare il mouse sull'icona delle informazioni accanto a "Concessione" per la descrizione.  Selezionare **0 controlli selezionati** per visualizzare le diverse opzioni.  Illustrarne alcuni.  In particolare segnalare l'opzione **Richiedi autenticazione a più fattori**, in Concedi accesso, e come questa può essere usata per fornire un controllo granulare su quando richiedere la MFA.   Illustrare inoltre che è possibile impostare più controlli e richiedere tutti o solo uno dei controlli selezionati.
    1. **Sessione** - Passare il mouse sull'icona delle informazioni accanto a "Sessione" per la descrizione.  Illustrare che i controlli di sessione consentono un'esperienza limitata all'interno di un'app cloud.  Ad esempio, l'utente potrebbe essere in grado di accedere all'app cloud ma non essere autorizzato a eseguire il download di contenuti né a stampare.  Si tratta di un argomento più complesso, per cui è opportuno non complicarlo.

1. Una volta configurato un criterio, è possibile attivarlo selezionando **Attiva**, quindi premere il pulsante **Crea** per creare un criterio.

1. Selezionare la **X** nell'angolo in alto a destra della pagina per chiudere il criterio.

1. Chiudere le schede del browser aperte.

### Revisione

In questa demo sono state presentate le varie opzioni disponibili per un criterio di accesso condizionale.
