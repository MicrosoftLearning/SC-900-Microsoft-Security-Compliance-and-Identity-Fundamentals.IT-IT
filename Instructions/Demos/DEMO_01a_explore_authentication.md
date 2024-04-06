<!---
---
Demo: Titolo: "Esplorare le impostazioni utente di Microsoft Entra ID" Percorso di apprendimento/Modulo/Unità: "Percorso di apprendimento: Descrivere le funzionalità di Microsoft Entra; Modulo 2: Descrivere le funzionalità di autenticazione di Microsoft Entra ID; Unità 3: Descrivere i metodi di autenticazione e Unità 4: Descrivere l'autenticazione a più fattori"
---
--->

# Demo: metodi di autenticazione e autenticazione MFA

Questa demo corrisponde al contenuto di Learn seguente:

- Percorso di apprendimento: Descrivere le funzionalità di Microsoft Entra
- Modulo: Descrivere le funzionalità di autenticazione di Microsoft Entra ID.
- Unità: Descrivere i metodi di autenticazione e l'autenticazione a più fattori.

## Scenario dimostrativo

In questa demo verranno esaminate le varie impostazioni disponibili per l'autenticazione in Microsoft Entra.

1. Tornare alla scheda del browser aperta denominata "Interfaccia di amministrazione Home Microsoft Entra."  Se in precedenza è stata chiusa questa scheda del browser, aprire Microsoft Edge e accedere a**[entra.microsoft.com](https://entra.microsoft.com)** con le credenziali di amministratore Microsoft 365.

1. Nel riquadro di spostamento a sinistra, espandere **Protezione** e quindi selezionare **Metodi di autenticazione**.

1. Selezionando Metodi di autenticazione, viene visualizzata la pagina Criteri.  Qui si potranno visualizzare i metodi di autenticazione disponibili e se sono abilitati.  Verranno illustrati alcuni di questi metodi:  
    1. Selezionare **SMS**.  Leggere la descrizione nella parte superiore della pagina: "Questo metodo di autenticazione fornisce un codice monouso via telefono tramite SMS a un utente, che quindi lo immette per effettuare l'accesso. L'SMS è utilizzabile per l'autenticazione a più fattori e la reimpostazione della password self-service; può anche essere configurato per essere usato come primo fattore."
        1. Un punto da segnalare qui è che alcuni metodi di autenticazione possono essere usati per l'autenticazione MFA e/o reimpostazione della password self-service.  È possibile usarne solo alcuni come forma primaria di autenticazione, mentre altri solo come forma secondaria di autenticazione.
        1. Per configurare un metodo di autenticazione specifico, è necessario abilitarlo e quindi scegliere come destinazione gli utenti e/o i gruppi da includere.  È possibile anche selezionare i gruppi da escludere.
        1. Non modificare nessuna impostazione.  Chiudere la pagina delle impostazioni SMS selezionando la **X** in alto a destra della pagina.  
    1. Prendere in esame le impostazioni delle chiamate vocali.  Selezionare **Chiamata vocale**, dalla descrizione è possibile notare una differenza importante.  Le chiamate vocali non sono utilizzabili come metodo di autenticazione a primo fattore.
    1. Ora selezionare **Microsoft Authenticator**.  Questo è il metodo di autenticazione principale.  
        1. Qui vengono abilitate le funzionalità e la destinazione delle persone da includere.  È possibile eseguire questa operazione per tutti gli utenti o i gruppi. Dopo aver identificato quali utenti/gruppi includere, è possibile identificare gruppi specifici da escludere.  
        1. Nella scheda **Configura** è possibile selezionare che una determinata funzionalità venga gestita da Microsoft. Questa impostazione è un modo pratico per consentire a un'organizzazione di abilitare o disabilitare una funzionalità per impostazione predefinita. Ciò contribuisce ad aiutare un'organizzazione nel miglioramento della propria postura di sicurezza.
        1. Non modificare nessuna impostazione. Chiudere la pagina selezionando la **X** nell'angolo in alto a destra.
 
1. Ora verrà esaminata la protezione delle password. Selezionare **Protezione password**.  Notare i diversi parametri di configurazione disponibili.  
    1. Selezionare l'icona delle informazioni accanto a **Soglia di blocco** per visualizzare il significato di questo parametro.  Attualmente è impostata su 10, il che significa che possono essere presenti fino a 10 accessi non riusciti prima che l'account venga bloccato. Si tratta di un valore po' alto, quindi è possibile impostare la soglia su un valore diverso.
    1. Selezionare l'icona delle informazioni per ognuno dei diversi parametri e consultarli brevemente.  In particolare, è consigliabile illustrare l'elenco di password vietate personalizzate.

1. I punti di forza dell'autenticazione sono un controllo di accesso condizionale che consente agli amministratori di specificare quale combinazione di metodi di autenticazione può essere utilizzata per accedere a una risorsa. Questo argomento verrà presentato in Accesso condizionale.

1. Nel riquadro di spostamento a sinistra per Metodi di autenticazione, selezionare **Attività**.
    1. Viene visualizzata la **registrazione** evidenziata da una sottolineatura di colore blu.  Qui è possibile visualizzare l'attività di registrazione per metodi di autenticazione diversi.
    1. Selezionare **Utilizzo** per visualizzare i dettagli di utilizzo e notare la possibilità di aggiungere filtri diversi.

1. In questo modulo verrà trattata anche l'autenticazione a più fattori. Per ulteriori informazioni sull'autenticazione MFA, consultare la demo sull'accesso condizionale, ma è consigliabile dedicare qualche minuto alla visualizzazione di alcune impostazioni di base.  Nel pannello di spostamento dell'interfaccia** di amministrazione di Microsoft Entra selezionare **Autenticazione a più fattori.  Potrebbe essere necessario selezionare **Mostra altro** sotto la sezione Protezione, nel riquadro di spostamento a sinistra.
    1. Nella pagina **Introduzione**, viene illustrato che il modo migliore per abilitare questo metodo di autenticazione per gli utenti è l'accesso condizionato, ma qui ci sono alcune impostazioni specifiche da configurare.
    1. Selezionare **Blocco account** e illustrare i parametri di blocco configurabili.
    1. Selezionare **Blocca/sblocca utenti**, illustrando che in questa sezione un amministratore può bloccare/sbloccare manualmente gli utenti.  Notare che un utente bloccato rimarrà bloccato per 90 giorni, a meno che non venga sbloccato manualmente.
    1. Selezionare **Avviso di frode**.  In questo modo gli amministratori possono consentire agli utenti di segnalare una frode se ricevono una richiesta di verifica a due passaggi che non hanno avviato.
    1. Selezionare **Notifiche**.  È possibile configurare Microsoft Entra in modo che invii notifiche via e-mail quando gli utenti segnalano avvisi di frode. Queste notifiche vengono in genere inviate agli amministratori di identità, poiché le credenziali dell'account utente sono probabilmente compromesse.
    1. Chiudere la pagina selezionando la **X** nell'angolo superiore a destra della finestra.  Quindi ripetere questo passaggio per tornare all'interfaccia di amministrazione di Microsoft Entra.

1. Mantenere aperta la scheda del browser per tornare all'interfaccia di amministrazione di Microsoft Entra per la prossima demo.

### Revisione

In questa demo, sono illustrati i metodi di autenticazione disponibili in Microsoft Entra.  Sono stati inoltre visualizzati alcuni dei parametri configurabili associati all'autenticazione a più fattori.
