<!---
---
Demo: Titolo: 'Esplora impostazioni utente Microsoft Entra ID' Percorso di apprendimento/Modulo/Unità: "Percorso di apprendimento: Descrivere le funzionalità di Microsoft Entra; Modulo 2: Descrivere le funzionalità di autenticazione di Microsoft Entra ID; Unità 3: Descrivere i metodi di autenticazione e l'unità 4: Descrivere l'autenticazione a più fattori
---
--->

# Demo: metodi di autenticazione e MFA

Questa demo corrisponde al contenuto di Learn seguente:

- Percorso di apprendimento: descrivere le funzionalità di Microsoft Entra.
- Modulo: descrivere le funzionalità di autenticazione di Microsoft Entra ID.
- Unità: descrivere i metodi di autenticazione e Descrivere l'autenticazione a più fattori.

## Scenario demo

In questa demo verranno esaminate le varie impostazioni disponibili per l'autenticazione in Microsoft Entra.

1. Tornare alla scheda open browser denominata "Home-Microsoft Entra admin center".  Se in precedenza è stata chiusa la scheda del browser, aprire Microsoft Edge e accedere a **[entra.microsoft.com](https://entra.microsoft.com)** con le credenziali di amministratore di Microsoft 365.

1. Nel riquadro di spostamento a sinistra espandere **Protezione** e quindi selezionare **Metodi di autenticazione**.

1. La selezione dei metodi di autenticazione visualizza la pagina dei criteri.  Qui verranno visualizzati i metodi di autenticazione disponibili e se sono abilitati.  Verranno illustrati alcuni di questi metodi:.  
    1. Selezionare **SMS**.  Leggere la descrizione nella parte superiore della pagina, "Questo metodo di autenticazione recapita un codice una volta tramite SMS al telefono di un utente e l'utente immette quindi il codice per l'accesso. SMS è utilizzabile per l'autenticazione a più fattori e Self-Service Reimpostazione password; può anche essere configurato per essere usato come primo fattore."
        1. Un punto da chiamare qui è che alcuni metodi di autenticazione possono essere usati per MFA e/o SSPR.  Alcuni possono essere usati solo come forma primaria di autenticazione, mentre altri possono essere usati solo come forma secondaria di autenticazione.
        1. Per configurare un metodo di autenticazione specifico, è necessario abilitarlo e quindi specificare quali utenti e/o gruppi includere.  È anche possibile selezionare i gruppi da escludere.
        1. Non modificare le impostazioni.  Chiudere la pagina impostazioni SMS **selezionando X nella** parte superiore destra della pagina.  
    1. Esaminiamo le impostazioni della chiamata vocale.  Selezionare **Chiamata vocale** dalla descrizione che è possibile visualizzare una differenza importante.  Le chiamate vocali non sono utilizzabili come metodo di autenticazione a primo fattore.
    1. Selezionare **Ora Microsoft Authenticator**.  Si tratta dei metodi di autenticazione di punta.  
        1. In questo caso si abilitano le funzionalità e si punta a chi includere.  È possibile eseguire questa operazione per tutti gli utenti o i gruppi. Dopo aver identificato quali utenti/gruppi includere è possibile identificare gruppi specifici da escludere.  
        1. Nella scheda Configura è possibile **selezionare** se una funzionalità specifica è gestita da Microsoft. Questa impostazione è un modo pratico per un'organizzazione per consentire a Microsoft di abilitare o disabilitare una funzionalità per impostazione predefinita. Ciò può aiutare un'organizzazione a migliorare il proprio comportamento di sicurezza.
        1. Non modificare le impostazioni. Chiudere **la pagina** selezionando X nell'angolo superiore destro della pagina.
 
1. Ora esaminiamo la protezione delle password. Selezionare **Protezione password**.  Si notino i diversi parametri di configurazione disponibili.  
    1. Selezionare l'icona delle informazioni accanto alla **soglia di blocco** per visualizzare il significato di questo parametro.  Attualmente è impostato su 10, il che significa che possono essere presenti fino a 10 accessi non riusciti prima che l'account venga bloccato.  Sembra un po'alto, quindi è possibile impostare su un valore diverso.
    1. Selezionare l'icona delle informazioni per ognuno dei diversi parametri e parlarne brevemente.  Si vuole in particolare chiamare l'elenco di password vietato personalizzato.

1. I punti di forza di autenticazione sono un controllo di accesso condizionale che consente agli amministratori di specificare quale combinazione di metodi di autenticazione può essere usata per accedere a una risorsa. Verrà visualizzato in Accesso condizionale.

1. Nel riquadro di spostamento a sinistra per i metodi di autenticazione selezionare **Attività**.
    1. La **registrazione** viene visualizzata con una sottolineatura blu.  Qui è possibile visualizzare l'attività di registrazione per metodi di autenticazione diversi.
    1. Selezionare Utilizzo per visualizzare i dettagli **sull'utilizzo** e notare che è possibile aggiungere filtri diversi.

1. In questo modulo si è parlato anche dell'autenticazione a più fattori. Verranno illustrate altre informazioni sull'autenticazione a più fattori nella demo sull'accesso condizionale, ma è consigliabile richiedere un minuto per visualizzare alcune impostazioni di base.  Nel pannello di spostamento dell'interfaccia di amministrazione Microsoft Entra selezionare **Autenticazione a più fattori**.  Potrebbe essere necessario selezionare **Mostra altro** nella sezione Protezione nel pannello di spostamento a sinistra.
    1. Nella pagina **Introduzione** viene illustrato che il modo migliore per applicarlo agli utenti è tramite l'accesso condizionale, ma sono presenti alcune impostazioni specifiche configurate qui.
    1. Selezionare **Blocco account** e chiamare i parametri di blocco configurabili.
    1. Selezionare **Blocca/sblocca utenti**, chiamarlo qui dove un amministratore può bloccare/sbloccare manualmente gli utenti.  Si noti che un utente bloccato rimarrà bloccato per 90 giorni a meno che non venga sbloccato manualmente.
    1. Selezionare **Avviso di frode**.  Ciò consente agli amministratori di consentire agli utenti di segnalare frodi se ricevono una richiesta di verifica in due passaggi che non hanno avviato.
    1. Selezionare **Notifiche**.  È possibile configurare Microsoft Entra per inviare notifiche tramite posta elettronica quando gli utenti segnalano avvisi di frode. Queste notifiche vengono in genere inviate agli amministratori delle identità, perché le credenziali dell'account dell'utente sono probabilmente compromesse.
    1. Chiudere **la pagina** selezionando X nell'angolo superiore destro della finestra.  Ripetere quindi questo passaggio per tornare all'interfaccia di amministrazione Microsoft Entra.

1. Mantenere aperta la scheda del browser quando si tornerà all'interfaccia di amministrazione Microsoft Entra per la demo successiva.

### Verifica

In questa demo sono stati illustrati i metodi di autenticazione disponibili in Microsoft Entra.  Vengono inoltre visualizzati alcuni parametri configurabili associati all'autenticazione a più fattori.
