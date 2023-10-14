<!---
---
Demo: Titolo: "Accesso condizionale di Azure AD" Percorso di apprendimento/Modulo/Unità: "Percorso di apprendimento: Descrivere le funzionalità di Microsoft Entra; Modulo 3: Descrivere le funzionalità di gestione degli accessi di Microsoft Entra ID; Unità 2: Descrivere l'accesso condizionale'
---
--->

# Demo: accesso condizionale Microsoft Entra

Questa demo corrisponde al contenuto di Learn seguente:

- Percorso di apprendimento: Descrivere le funzionalità di Microsoft Entra
- Modulo: Descrivere le funzionalità di gestione degli accessi di Microsoft Entra ID
- Unità: Descrivere l'accesso condizionale

## Scenario demo

Questa demo presenterà le varie opzioni disponibili per i criteri di accesso condizionale.

1. Tornare alla scheda open browser denominata "Home-Microsoft Entra admin center".  Se in precedenza è stata chiusa la scheda del browser, aprire Microsoft Edge e accedere a **[entra.microsoft.com](https://entra.microsoft.com)** con le credenziali di amministratore di Microsoft 365.

1. Nel riquadro di spostamento a sinistra espandere **Protezione** e quindi selezionare **Accesso condizionale**.

1. Viene visualizzata la pagina Panoramica dell'accesso condizionale.  Qui verranno visualizzati i riquadri che mostrano il riepilogo dei criteri e gli avvisi generali.  Nel pannello di spostamento a sinistra selezionare **Criteri**.

1. Compare la schermata Criteri di accesso condizionale. Qualsiasi criterio di accesso condizionale esistente è elencato qui. Per mostrare le impostazioni associate all'accesso condizionale, selezionare **+ Nuovo criterio**.

1. Nel campo **Nome** immettere un nome per il criterio.

1. Sotto **Assegnazioni** sono disponibili diverse opzioni.  Poiché i criteri di accesso condizionale sono come le istruzioni if/then, le impostazioni di assegnazione sono come le istruzioni "if".
    1. **Utenti** : passare il mouse sull'icona delle informazioni accanto a dove si dice "Utenti" e chiamare che questa è la posizione in cui si selezionano le identità nella directory a cui si applicano i criteri, inclusi gli utenti, i gruppi e le entità servizio. Selezionare **0 utenti e gruppi selezionati**.  Diventerà ora visibile l'opzione per includere o escludere utenti o gruppi. Selezionare le impostazioni disponibili per la scheda **Includi** e selezionare le impostazioni disponibili per la scheda **Escludi**.
    1. **Risorse di destinazione** : selezionare **Risorse di destinazione**.  In questo caso si controlla l'accesso in base a tutto o a un traffico di accesso di rete specifico, alle app o alle azioni cloud.  Espandere il campo sotto dove si dice selezionare a quale criterio si applica questo criterio.  Qui è possibile selezionare se il criterio si applica alle app cloud, alle azioni utente o al contesto di autenticazione.  
        1. Selezionare **App cloud** e quindi nella scheda Includi selezionare l'opzione **Seleziona app** e quindi sotto dove si dice **Seleziona**, selezionare **Nessuna**, verrà aperta una finestra per selezionare una o più app per cui verrà applicato il criterio.
        1. Chiudere la finestra Seleziona app cloud selezionando **X** nell'angolo superiore destro della finestra.
        1. Quando il tempo consente di scegliere di passare attraverso le altre opzioni (azioni utente e contesto di autenticazione) per visualizzare le opzioni di configurazione per ognuna.
    1. **Condizioni** : passare il mouse sull'icona delle informazioni accanto a dove si dice "Condizioni" e chiamare che queste condizioni definiscono quando verranno applicati i criteri. Ad esempio, 'posizione. Selezionare **0 condizioni selezionate**. Considerare i diversi "segnali" elencati.   Selezionare alcune delle opzioni selezionando prima l'icona delle informazioni per definire cos'è e poi selezionando **Non configurato** per la voce specifica per mostrare le varie opzioni.
        1. **Rischio utente** - Un rischio utente rappresenta la probabilità che una data identità o account siano compromessi. Questi rischi vengono calcolati offline usando le origini di intelligence sulle minacce interne ed esterne di Microsoft.
        1. **Rischio di accesso** - Un rischio di accesso rappresenta la probabilità che una data richiesta di autenticazione non sia autorizzata dal proprietario dell'identità. Gli esempi possono includere se l'accesso è da un indirizzo IP anonimo o uno spostamento fisico atipico, ecc.
        1. **Piattaforma del dispositivo** - Piattaforma da cui l'utente sta effettuando l'accesso. Ad esempio, "iOS".
        1. **Posizione** - Posizione (determinata usando l'intervallo di indirizzi IP) da cui l'utente sta effettuando l'accesso
        1. **App cliente** - Software usato dall'utente per accedere all'app cloud. Ad esempio, "Browser".
        1. **Filtra per dispositivi** - Quando si creano criteri di accesso condizionale, gli amministratori possono definire dispositivi di destinazione o escludere dispositivi specifici nel proprio ambiente. L'amministratore può definire dispositivi specifici usando gli operatori e le proprietà supportati per i filtri dei dispositivi e le altre condizioni di assegnazione disponibili nei criteri di accesso condizionale.

1. **Controlli di accesso**: tornando all'analogia che i criteri di accesso condizionale sono come le istruzioni if/then, i controlli di accesso sono analoghi all'istruzione "then".
    1. **Concessione** - Passare il mouse sull'icona delle informazioni accanto a "Concessione" per la descrizione.  Selezionare **0 controlli selezionati** per mostrare le diverse opzioni.  Considerarne alcuni.  In particolare segnalare l'opzione **Richiedi autenticazione a più fattori**, in Concedi accesso, e come questa può essere usata per fornire un controllo granulare su quando richiedere la MFA.   Ricordare inoltre che è possibile impostare più controlli e richiedere tutti o solo uno dei controlli selezionati.
    1. **Sessione** - Passare il mouse sull'icona delle informazioni accanto a "Sessione" per la descrizione.  Ricordare che i Controlli sessione permettono un'esperienza limitata all'interno di un'applicazione cloud.  Ad esempio, l'utente potrebbe essere in grado di accedere all'app cloud ma non essere autorizzato a eseguire il download di contenuti né a stampare.  Questo è un argomento più complesso, quindi deve essere spiegato in modo semplice.

1. Una volta configurato un criterio, è possibile attivare un criterio selezionando **Attiva**, quindi premere il pulsante **Crea** per creare un criterio.

1. Selezionare **la X** nell'angolo superiore destro della pagina per chiudere il criterio.

1. Chiudere le schede del browser aperte.

### Verifica

In questa demo sono state presentate le varie opzioni disponibili per un criterio di accesso condizionale.
