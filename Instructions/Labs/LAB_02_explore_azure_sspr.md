---
lab:
  title: Esplorazione dell'autenticazione di Azure AD con la reimpostazione della password self-service
  module: 'Module 2 Lesson 2: Describe the capabilities of Microsoft Identity and access management solutions: Describe the different authentication methods of Azure AD'
ms.openlocfilehash: 6e9bcabdacc0e7c7f4c821c9a2fe018341055799
ms.sourcegitcommit: 25998048c2e354ea23d6f497205e8a062d34ac80
ms.translationtype: HT
ms.contentlocale: it-IT
ms.lasthandoff: 05/04/2022
ms.locfileid: "144557471"
---
# <a name="lab-explore-azure-ad-authentication-with-self-service-password-reset"></a>Laboratorio: Esplorazione dell'autenticazione di Azure AD con la reimpostazione della password self-service

## <a name="lab-scenario"></a>Scenario del lab

In questo lab, in qualità di amministratore, si apprenderà in modo dettagliato il processo di abilitazione della reimpostazione della password self-service. Dopo l'abilitazione della reimpostazione della password self-service, si assumerà quindi il ruolo di un utente e si seguirà il processo di registrazione per la reimpostazione della password self-service e anche di reimpostazione della password.  Infine, in qualità di amministratore, sarà possibile visualizzare i log di controllo, i dati di utilizzo e le informazioni dettagliate per la reimpostazione della password self-service.

**Tempo stimato**: 15-20 minuti

### <a name="task-1"></a>Attività 1

In questa attività, in qualità di amministratore si aggiungerà un utente esistente, Adele Vance, al gruppo SSPRSecurityUsers.  Inoltre, sarà necessario reimpostare la password dell'utente in modo da poter effettuare il primo accesso, in qualità di utente, e la registrazione per la reimpostazione della password self-service.

1. Aprire Microsoft Edge.

2. Nella barra degli indirizzi immettere **portal.azure.com** e accedere con le proprie credenziali di amministratore.
    1. Nella finestra Accedi immettere **admin@WWLxZZZZZZ.onmicrosoft.com** (dove ZZZZZZ è l'ID tenant univoco fornito dal proprio provider di hosting del lab) e quindi selezionare **Avanti**.
    1. Immettere la password di amministratore, che dovrebbe essere fornita dal proprio provider di hosting del lab. Fare clic su **Accedi**.
    1. Quando compare la domanda se rimanere connessi, selezionare **Sì**.

3. Selezionare **Azure Active Directory**.  

4. Dal riquadro di spostamento sinistro, selezionare **Gruppi**.

5. Viene visualizzato un elenco dei gruppi esistenti. Nel campo Cerca gruppi, immettere **SSPR**, quindi selezionare **SSPRSecurityGroupUsers** dai risultati della ricerca.  Si passerà all'opzione di configurazione per questo gruppo.

6. Dal riquadro di spostamento sinistro, selezionare **Membri**.

7. Dalla parte superiore della pagina, selezionare **+ Aggiungi membri**.  

8. Nella casella di ricerca, immettere **Adele**.  Una volta visualizzato l'utente **Adele Vance** sotto la casella di ricerca, selezionarlo, quindi premere **Seleziona** in fondo alla pagina.

9. Chiudere la finestra SSPRSecurityUsers selezionando la **X** nell'angolo in alto a destra della schermata.

10. Tornare alla pagina Active Directory selezionando **Contoso** dall'angolo in alto a sinistra della schermata, sopra la dicitura Gruppi, per tornare alla pagina Azure Active Directory di Contoso.

11. Dal riquadro di spostamento a sinistra, selezionare **Utenti**.

12. Selezionare **Adele Vance** dall'elenco degli utenti.

13. Selezionare **Reimposta password** in cima alla pagina. Poiché non è stato effettuato l'accesso come Adele Vance in precedenza, sarà necessario reimpostare la password.

14. All'apertura della finestra Reimposta password, selezionare **Reimposta password**.  IMPORTANTE: prendere nota della nuova password, poiché servirà in un'attività successiva per poter accedere come utente.

15. Chiudere la finestra di reimpostazione della password selezionando la **X** nell'angolo in alto a destra della pagina.

16. Chiudere la finestra di Adele Vance selezionando la **X** nell'angolo in alto a destra della pagina.

17. Chiudere la finestra Utenti selezionando la **X** nell'angolo in alto a destra della pagina.

18. Tenere aperta la finestra Panoramica Contoso poiché verrà usata nell'attività successiva.

### <a name="task-2"></a>Attività 2

In questa attività, in qualità di amministratore, si apprenderà come configurare la reimpostazione della password per gli utenti, compresa la configurazione dei tipi di metodi di autenticazione da usare

1. Passare alla scheda Contoso – Microsoft Azure aperta nel browser. Se la scheda era stata chiusa, aprire una pagina del browser e, nella barra degli indirizzi, inserire portal.azure.com e selezionare Azure Active Directory.  Occorre aver effettuato l'accesso come amministratore nel portale di Azure. In caso contrario, eseguire di nuovo l'accesso.

1. Dal riquadro di spostamento sinistro, selezionare **Reimpostazione della password**.  

1. Vengono visualizzate le proprietà per la reimpostazione della password self-service.  Assicurarsi che **Reimpostazione della password self-service** sia **selezionata** per il gruppo elencato, **SSPRSecurityGroupUsers**.  Posizionare il cursore sull'icona di informazioni accanto a "Seleziona gruppo" e notare la dicitura "Definisce il gruppo di utenti autorizzati a reimpostare le proprie password". Occorre includere gli utenti nel gruppo, non è possibile selezionare gli utenti individualmente.  Inoltre, se si cambia il gruppo, il gruppo selezionato sostituisce quello attualmente elencato.  Pertanto, si raccomanda di aggiungere semplicemente gli utenti al gruppo di reimpostazione della password self-service.  Infine, notare la casella blu di informazioni "Queste impostazioni si applicano solo agli utenti finali dell'organizzazione. Gli amministratori sono sempre abilitati per la reimpostazione della password self-service e devono usare due metodi di autenticazione per reimpostare la propria password".

1. Dal riquadro di spostamento sinistro di Reimpostazione della password, selezionare **Metodi di autenticazione**.

1. In Numero di metodi da reimpostare, selezionare **1**. Notare la casella di informazioni nella schermata.

1. Osservare i diversi metodi disponibili per gli utenti.  **E-mail** e **Cellulare (solo SMS)** dovrebbero essere già selezionati; in caso contrario, selezionarli.

1. Dal riquadro di spostamento sinistro di Reimpostazione della password, selezionare **Registrazione**.  

1. Assicurarsi che l'opzione Richiedere agli utenti di registrarsi all'accesso sia impostata su **Sì**.  Lasciare l'opzione Numero di giorni prima che agli utenti venga chiesto di riconfermare le informazioni di autenticazione impostata sul valore predefinito di 180.   Notare la casella di informazioni nella pagina.

1. Dal riquadro di spostamento sinistro di Reimpostazione della password, selezionare **Notifiche**.  

1. Assicurarsi che l'opzione Notificare agli utenti le reimpostazioni delle password sia impostata su **Sì**.  Lasciare l'opzione Notificare agli amministratori quando altri amministratori reimpostano le proprie password impostata su No.

1. Notare come il riquadro di spostamento di Reimpostazione della password include anche le opzioni per visualizzare i log di audit e l'utilizzo e le informazioni dettagliate.

1. **Disconnettersi** da tutte le schede del browser selezionando l'icona dell'utente accanto all'indirizzo e-mail nell'angolo in alto a destra della schermata. Quindi, chiudere tutte le finestre del browser.

### <a name="task-3"></a>Attività 3

In questa attività, in qualità di Adele Vance, si seguirà il processo di registrazione per la reimpostazione della password self-service.  Questa attività richiede l'accesso a un dispositivo mobile su cui ricevere SMS o l'accesso a un account di posta elettronica personale

1. Aprire Microsoft Edge.

2. Nella barra degli indirizzi immettere **login.microsoftonline.com**.

3. Accedere come Adele Vance.
    1. Nella finestra Accedi immettere **AdedleV@WWLxZZZZZZ.onmicrosoft.com** (dove ZZZZZZ è l'ID tenant univoco fornito dal proprio provider di hosting del lab) e quindi selezionare **Avanti**.
    1. Immettere la password annotata nell'attività precedente. Fare clic su **Accedi**.
    1. Quando compare la domanda se rimanere connessi, selezionare **Sì**

4. Poiché si tratta del primo accesso come Adele Vance, verrà richiesto di reimpostare la password.  Immettere la password precedente.  Come nuova password, immettere **SC900-Lab**. Immettere **SC-900-Lab** nel campo di conferma della password.  Fare clic su **Accedi**.  Nota: si sta usando questa password solo per comodità del lab. Come procedura consigliata, sarebbe opportuno immettere una password più sicura.

5. Viene visualizzato un popup che segnala che sono necessarie altre informazioni.  Questo perché, come membro del gruppo SSPRSecurityGroupUsers, la configurazione richiede che i propri membri si registrino quando effettuano l'accesso.  Selezionare il pulsante **Avanti**.  Nota:  un'alternativa alla registrazione da parte degli stessi utenti è rappresentata dalla configurazione dei metodi di autenticazione direttamente da parte degli amministratori al momento dell'aggiunta di un utente. Questo richiede che gli amministratori conoscano e impostino i numeri di telefono e gli indirizzi di posta elettronica usati dagli utenti per la reimpostazione della password self-service e che reimpostino la password di un utente.

6. Si apre la pagina "Proteggi l'account".  La finestra che compare riguarda il metodo di autenticazione per il telefono; se non possiede un dispositivo mobile in grado di ricevere messaggi di testo, andare al passaggio successivo.  Viene richiesta l'immissione di un numero di telefono. Assicurarsi che l'opzione **Invia un SMS** sia abilitata.   Immettere il numero di telefono in cui è possibile ricevere un codice di testo e selezionare il pulsante **Avanti**.  Si apre una nuova finestra la quale indica che è stato appena inviato un codice al numero di telefono immesso.  Immettere il codice ricevuto e selezionare **Avanti**. Si apre una finestra che indica la corretta esecuzione e che mostra il metodo di accesso predefinito.  Selezionare **Fine**.  

7. Saltare questo passaggio se si è stati in grado di configurare la reimpostazione della password self-service con il proprio numero di telefono cellulare.  In alternativa, è possibile configurare un metodo diverso, così come illustrato in basso a sinistra nella finestra.  Se si sceglie di configurare un metodo diverso, selezionare **Si vuole configurare un metodo diverso**; viene visualizzata una finestra popup con la domanda Specificare il metodo da usare.  Dall'elenco a discesa, selezionare il metodo preferito, **E-mail**, quindi il pulsante **Conferma**.  Immettere l'indirizzo e-mail da usare, quindi selezionare **Avanti**.  Si apre una nuova finestra la quale indica che è stato appena inviato un codice all'indirizzo e-mail immesso.  Accedere all'e-mail immessa per ottenere il codice.  Immettere il codice ricevuto e selezionare **Avanti**. Si apre una finestra che indica la corretta esecuzione e che mostra il metodo di accesso predefinito.  Selezionare **Fine**.

8. È ora possibile completare l'accesso.  Si dovrebbe essere nella pagina di destinazione del portale di Azure.  Se si vede che il tempo per l'accesso è scaduto, immettere di nuovo la password, SC900-Lab.

9. Disconnettersi dal portale di Azure e chiudere la finestra del browser.

### <a name="task-4-optional"></a>Attività 4 (facoltativa)

In questa attività, in qualità di Adele Vance, si seguirà il processo di reimpostazione della propria password

1. Aprire Microsoft Edge.

2. Nella barra degli indirizzi immettere **login.microsoftonline.com**.

3. Accedere come Adele Vance immettendo l'indirizzo di posta elettronica **AdeleV@WWLxZZZZ.onmicrosoft.com** (dove ZZZZZZ è l'ID tenant univoco fornito dal provider di hosting del lab), quindi selezionare il pulsante **Avanti**. In alternativa, potrebbe essere visualizzata una finestra aperta Selezionare un account. In questo caso, selezionare l'account per Adele Vance.

4. Dalla finestra Immetti password, selezionare **Ho dimenticato la password**.

5. Si apre la finestra Ripristina l'accesso al tuo account.   Verificare che l'indirizzo di posta elettronica per Adele Vance, AdeleV@WWLxZZZZ.onmicrosoft.com, sia visualizzato nella casella dell'indirizzo di posta elettronica o del nome utente.  In caso contrario, immetterlo.  

6. Nella casella vuota, immettere i caratteri visualizzati nell'immagine o le parole dell'audio. Una volta effettuata questa operazione, selezionare **Avanti**.

7. La schermata mostra Ripristina l'accesso al tuo account e il passaggio di verifica 1 > scegliere una nuova password. Lasciare l'impostazione predefinita **Invia SMS sul telefono cellulare**.  Viene richiesta l'immissione del proprio numero di telefono cellulare.  Una volta effettuata questa operazione, selezionare il pulsante **SMS**.  Se durante la registrazione è stata selezionata l'e-mail, la finestra Ripristina l'accesso al tuo account indicherà Si riceverà un messaggio di posta elettronica contenente un codice di verifica all'indirizzo di posta elettronica alternativo.  Selezionare **E-mail**.

8. Immettere il codice di verifica, quindi premere **Avanti**.

9. Nella schermata successiva verranno richieste l'immissione della nuova password e la sua conferma.  Eseguire queste operazioni e selezionare il pulsante **Fine**.

10. Nella schermata comparirà un messaggio il quale indica che la password è stata reimpostata.  Selezionare **fare clic qui** per accedere con la nuova password.

11. Nella casella di informazioni Selezionare un account scegliere **AdeleV@WWLxZZZZZZ.onmicrosoft.com** , immettere la nuova password e quindi selezionare il pulsante **Accedi**.  Se viene richiesto se rimanere connessi, selezionare **No**.

12. Ora ci si dovrebbe trovare nel portale di Azure.

13. Disconnettersi selezionando l'icona dell'utente accanto all'indirizzo e-mail nell'angolo in alto a destra della schermata, quindi **Disconnetti**. Infine, chiudere tutte le finestre del browser.

### <a name="task-5-optional"></a>Attività 5 (facoltativa)

In questa attività, in qualità di amministratore, si vedranno i log di controllo e i dati di Utilizzo e informazioni dettagliate associati alla reimpostazione della password

1. Aprire Microsoft Edge.

2. Nella barra degli indirizzi immettere **portal.azure.com**

3. Accedere con le credenziali di amministratore.
    1. Nella finestra Accedi immettere **admin@WWLxZZZZZZ.onmicrosoft.com** (dove ZZZZZZ è l'ID tenant univoco fornito dal proprio provider di hosting del lab) e quindi selezionare **Avanti**.
    1. Immettere la password di amministratore, che dovrebbe essere fornita dal proprio provider di hosting del lab. Fare clic su **Accedi**.
    1. Quando compare la domanda se rimanere connessi, selezionare **Sì**.

4. Selezionare **Azure Active Directory**.  

5. Dal riquadro di spostamento sinistro, selezionare **Reimpostazione della password**.

6. Dal riquadro di spostamento sinistro, selezionare **Log di controllo**.  Notare le informazioni e i filtri disponibili.  Inoltre, notare che è possibile scaricare i log.  

7. Selezionare **Download**.  Notare che è possibile formattare il download come CSV o JSON.  Chiudere la finestra selezionando la **X** nell'angolo in alto a destra della schermata.

8. Dal riquadro di spostamento sinistro, selezionare **Utilizzo e informazioni dettagliate**.

9. Notare le informazioni disponibili relative alla registrazione.  L'aggiornamento di questi dati potrebbe richiedere del tempo, anche dopo aver selezionato Aggiorna, quindi potrebbero non rispecchiare ancora i dati di registrazione o di utilizzo dell'attività precedente.

10. In cima alla pagina, selezionare **Utilizzo** per visualizzare il numero di reimpostazioni di password self-service e di sblocchi di account in base al metodo.  L'aggiornamento di questi dati potrebbe richiedere del tempo, anche dopo aver selezionato Aggiorna, quindi potrebbero non rispecchiare ancora i dati di utilizzo dell'attività precedente.

11. Chiudere le schede del browser aperte.

### <a name="review"></a>Verifica

In questo lab, in qualità di amministratore, si è appreso il processo di abilitazione della reimpostazione della password self-service. Dopo l'abilitazione della reimpostazione della password self-service, si è assunto quindi il ruolo di un utente e si è seguito il processo di registrazione per la reimpostazione della password self-service e anche di reimpostazione della password.  Infine, in qualità di amministratore, si è appreso dove accedere ai log di controllo e ai dati di utilizzo e le informazioni dettagliate per la reimpostazione della password self-service.
