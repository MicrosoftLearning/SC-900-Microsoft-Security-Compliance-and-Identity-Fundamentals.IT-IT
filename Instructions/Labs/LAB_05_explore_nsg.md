---
lab:
  title: Esplorare i gruppi di sicurezza di rete di Azure (NSG)
  module: Describe the basic security capabilities in Azure
---

# Lab: Esplorare i gruppi di sicurezza di rete (NSG) di Azure

Questo lab corrisponde al contenuto di Learn seguente:

- Percorso di apprendimento: Descrivere le funzionalità delle soluzioni di sicurezza Microsoft
- Modulo: Descrivere le funzionalità di sicurezza di base in Azure
- Unità: Descrivere i gruppi di sicurezza di rete di Azure

## Scenario laboratorio

In questo lab, si esplorerà la funzione dei gruppi di sicurezza di rete in Azure.  A tale scopo, si creerà un gruppo di sicurezza di rete (NSG) e si assegnerà il gruppo di sicurezza di rete all'interfaccia di una macchina virtuale preesistente.  Dopo la configurazione, si osserveranno le regole predefinite in ingresso e in uscita, si creeranno nuove regole e infine si testeranno queste regole.  In questo lab, la macchina virtuale che verrà usata con il gruppo di sicurezza di rete viene creata automaticamente, quindi verranno visualizzate prima di tutto alcune delle informazioni associate alla macchina virtuale.
  
**Tempo** stimato: 45 minuti

### Attività 1

In questa attività verranno visualizzati alcuni parametri associati alla macchina virtuale creata per l'uso con questo lab.

1. Aprire Microsoft Edge.  Nella barra degli indirizzi, immettere **https://portal.azure.com**.

1. Accedere utilizzando le credenziali di amministratore.
    1. Nella finestra Accedi immettere il nome utente fornito dal provider di hosting del lab e quindi selezionare **Avanti**.
    1. Immettere la password di amministratore, che dovrebbe essere fornita dal proprio provider di hosting del lab. Fare clic su **Accedi**.
    1. Se in precedenza è stato eseguito l'accesso, potrebbe essere richiesto di completare un'autenticazione secondaria, come parte di MFA. Se non è stato eseguito l'accesso in precedenza, potrebbe essere richiesto di completare il processo di registrazione dell'autenticazione a più fattori. Seguire le istruzioni visualizzate sullo schermo per configurare l'autenticazione a più fattori.
    1. Se viene richiesto se si desidera rimanere connessi, selezionare **Sì**.

1. Nella parte superiore della pagina, sotto alla dicitura Servizi di Azure, selezionare **Macchine virtuali**.  Se questa opzione non è disponibile, nella casella di ricerca, nella barra blu nella parte superiore della pagina accanto a Microsoft Azure, immettere **Macchine virtuali** e quindi selezionare **Macchine virtuali** dai risultati della ricerca.

1. Dalla pagina Macchine virtuali selezionare la macchina virtuale elencata **SC900-WinVM**.

1. Ora ci si trova nella pagina SC900-WinVM.  Notare alcune informazioni di base sulla macchina virtuale.

1. Nel pannello di spostamento a sinistra espandere **Rete** e quindi selezionare **Impostazioni** di rete.  Le sezioni essenziali della finestra principale mostrano l'interfaccia di rete per la VM.  Si noti che accanto al gruppo di sicurezza di rete non è presente alcun elemento elencato: infatti non esiste un gruppo di sicurezza di rete assegnato all'interfaccia.

1. Mantenere aperta questa scheda.

### Attività 2

In questa attività si creerà un gruppo di sicurezza di rete, si assegnerà l'interfaccia di rete della macchina virtuale a tale gruppo di sicurezza di rete e si creerà una nuova regola in ingresso per il traffico RDP.

1. Nella scheda Apri Azure *fare clic con il pulsante destro del mouse* nel collegamento **Home** della parte superiore della pagina, quindi selezionare **Apri collegamento nella nuova scheda** per aprire un'altra pagina per i servizi di Azure.

1. Nella barra di ricerca di colore blu nella parte superiore della pagina, immettere **Gruppi di sicurezza di rete** e, tra i risultati, selezionare **Gruppi di sicurezza di rete**. Non selezionare *Gruppi di sicurezza di rete (versione classica)*.

1. Nel centro della pagina, selezionare il pulsante blu con l’etichetta **Crea gruppo di sicurezza di rete**.  In alternativa è possibile selezionare **+ Crea** nella parte superiore della pagina Gruppi di sicurezza di rete.

1. Nella scheda Informazioni di base della pagina Crea gruppo di sicurezza di rete, specificare le impostazioni seguenti:
    1. Sottoscrizione: lasciare il valore predefinito (si tratta della sottoscrizione di Azure fornita dal provider di servizi di hosting per i lab autorizzato)
    1. Gruppo di risorse: **LabsSC900**
    1. Nome: **NSG-SC900**
    1. Area: lasciare il valore predefinito.
    1. Selezionare **Rivedi e crea** e quindi **Crea**.

1. Una volta completata la distribuzione, selezionare **Vai alla risorsa**.

1. A questo punto ci si dovrebbe trovare nella pagina di panoramica per il gruppo di sicurezza di rete appena creato.  In caso contrario, nel pannello di navigazione a sinistra selezionare **Panoramica**. Nella parte superiore della pagina, sotto a Informazioni di base, verranno visualizzate alcune informazioni di base sul gruppo di sicurezza di rete creato.  Due punti da notare sono che non sono presenti regole di sicurezza personalizzate e non sono presenti subnet né interfacce di rete associate a questo gruppo di sicurezza di rete.  Anche se non sono presenti regole di sicurezza personalizzate, esistono regole predefinite in ingresso e in uscita incluse in ogni gruppo di sicurezza di rete, come illustrato nella pagina.  Esaminare sia le regole in ingresso che quelle in uscita. Le regole in ingresso predefinite negano tutto il traffico in ingresso che non proviene da una rete virtuale o da un servizio di bilanciamento del carico di Azure.  Le regole in uscita negano tutto il traffico in uscita, ad eccezione del traffico tra reti virtuali e del traffico in uscita verso Internet.

1. Nel riquadro di spostamento sinistro della pagina NSG-SC900 espandere **Impostazioni** e quindi selezionare **Interfacce** di rete.
    1. Selezionare **Associa**.
    2. Nel campo per le associazioni di interfaccia di rete, selezionare la **freccia giù**, selezionare **sc900-winvmXXX** e quindi selezionare **OK** nella parte inferiore della finestra. Una volta che l'interfaccia è associata al NSG, verrà visualizzata nell'elenco.  Ora il gruppo di sicurezza di rete è assegnato all'interfaccia di rete della VM.

1. Tornare alla **scheda SC900-WinVM - Microsoft Azure** nel browser.  Aggiorna la pagina. Accanto a dove è indicato Gruppo di sicurezza di rete, dovrebbe essere possibile visualizzare il nome del gruppo di sicurezza di rete appena creato.  Se ancora non è visualizzato, attendere un altro minuto e quindi aggiornare di nuovo la pagina.

1. Selezionare **Connetti** nel pannello di navigazione a sinistra. Nella finestra principale, accanto a dove viene visualizzato il numero di porta 3389, selezionare **Controlla accesso**. La funzione di controllo dell'accesso invia i segnali (di traffico) alla porta RDP predefinita 3389 della macchina virtuale, per verificare se è accessibile. L'operazione potrebbe richiedere un minuto, ma non sarà visualizzato Non accessibile.  Questo è previsto, perché la regola DenyAllInBound NSG nega il traffico in ingresso alla macchina virtuale.

1. Nel browser, tornare alla scheda **NSG-SC900 - Microsoft Azure**.

1. Dal riquadro di spostamento sinistro selezionare **Regole di sicurezza in ingresso**. Le regole in ingresso predefinite negano tutto il traffico in ingresso che non proviene da una rete virtuale o da un servizio di bilanciamento del carico di Azure, quindi è necessario configurare una regola per consentire il traffico RDP in ingresso (traffico sulla porta 3389). Tenere presente che non è possibile rimuovere le regole predefinite, ma è possibile sostituirle creando regole con priorità più alte.

1. Nella parte superiore della pagina selezionare **Aggiungi**. Nella finestra Aggiungi regola di sicurezza in ingresso specificare le impostazioni seguenti:
    1. Origine: **qualsiasi**
    1. Intervalli di porte di origine: **\***
    1. Destinazione: **qualsiasi**
    1. Servizio: **RDP**
    1. Azione: **Consenti**
    1. Priorità: **1000**. Le regole con i numeri più bassi hanno una priorità più alta e vengono elaborate per prime.
    1. Nome: lasciare il nome predefinito o creare un nome descrittivo personalizzato.
    1. Notare il simbolo di avviso nella parte inferiore della pagina.  Si usa RDP solo per scopi di test e per illustrare la funzionalità del gruppo di sicurezza di rete.
    1. Seleziona **Aggiungi**

1. Dopo aver effettuato il provisioning della regola, verrà visualizzata nell'elenco delle regole in ingresso (potrebbe essere necessario aggiornare la schermata).

1. Lasciare aperta la scheda del browser.  

### Attività 3

In questa attività si testerà la regola del gruppo di sicurezza di rete in ingresso appena creata per verificare che sia possibile stabilire una connessione Desktop remoto (RDP) alla macchina virtuale.  Una volta all'interno della macchina virtuale, si dovrà verificare la connettività in uscita verso Internet dalla macchina virtuale.

1. Aprire la scheda SC900-WinVM – Microsoft Azure nel browser.

1. Dal riquadro di spostamento a sinistra, selezionare **Connetti**.

1. Selezionare **Verifica accesso** (verificare che la porta sia impostata su 3389).  Lo stato dovrebbe essere "Accessibile".  Se viene ancora visualizzato "Non accessibile", aggiornare la pagina e riprovare, potrebbero essere necessari alcuni minuti prima che la nuova regola in ingresso venga visualizzata dall'opzione controlla l'accesso.

1. Connettersi direttamente alla macchina virtuale facendo clic su **Seleziona** nella casella che indica RDP nativo.
   
    1. Dalla finestra RDP nativo visualizzata, selezionare **Scarica file RDP**.
    1. Se viene visualizzato un avviso di download, selezionare **Mantieni**, quindi nella finestra popup visualizzata, selezionare **Apri file**.
    1. Verrà visualizzata una finestra Connessione Desktop remoto. Selezionare **Connetti**.
    1. Verranno chieste le credenziali.  Immettere nome utente e password per la macchina virtuale (fare riferimento alla scheda delle risorse nel pannello delle istruzioni del lab).
    1. Verrà visualizzata una finestra Connessione Desktop remoto che indica: *Impossibile verificare l'identità del computer remoto. Connettersi comunque? *  Selezionare **Sì**.

1. La connessione alla VM è stata ora stabilita. In questo caso, è stato possibile connettersi alla macchina virtuale perché la regola del traffico in ingresso creata consente il traffico in ingresso alla macchina virtuale tramite RDP.  Dopo alcuni secondi, nella schermata iniziale verrà visualizzata la finestra Scegli le impostazioni di privacy per il tuo dispositivo. Selezionare **Accetta**.  Qualora venga visualizzata la finestra Reti, selezionare **No**.

1. Con la macchina virtuale in esecuzione nella sessione RDP, verificare la connettività in uscita verso Internet dalla macchina virtuale.
    1. Dalla macchina virtuale, selezionare **Microsoft Edge** per aprire il browser. Poiché questa è la prima volta che si apre la macchina virtuale e il broswer, è possibile che vengano richieste alcune impostazioni di base.  
    1. Potrebbe essere richiesto di scegliere le impostazioni di privacy per il dispositivo. Lasciare il valore predefinito e selezionare **Accetta**.  
    1. Può essere visualizzato un pannello laterale per Reti.  Selezionare **No**.
    1. Potrebbe essere visualizzata una finestra con il messaggio "Sfoglia il Web con il browser con prestazioni migliori in Windows", selezionare Continua, selezionare **Avvia senza i dati**, confermare **e continuare**, selezionare **Continua senza questi dati**, quindi infine selezionare **Conferma e avviare l'esplorazione**.****
    1. Immettere **www.bing.com** nella barra degli indirizzi del browser e verificare di riuscire a connettersi al motore di ricerca.
    1. Dopo aver confermato che è possibile accedere a www.bing.com, chiudere la finestra del browser nella macchina virtuale, ma lasciare la macchina virtuale attiva.

1. Ridurre al minimo la macchina virtuale selezionando il carattere di sottolineatura **_** nella scheda di colore blu che mostra l'indirizzo IP della macchina virtuale. Si tornerà alla pagina SC900-WinVM \| Connetti.

1. Mantenere aperta la scheda del browser perché verrà usata nell'attività successiva.

### Attività 4

Nell'attività precedente è stata confermata la possibilità di stabilire una connessione RDP alla macchina virtuale. Dalla macchina virtuale è stata anche confermata la possibilità di stabilire una connessione in uscita a Internet.  Il traffico Internet in uscita era consentito perché le regole predefinite in uscita per il gruppo di sicurezza di rete consentono il traffico Internet in uscita.  In questa attività, si seguirà il processo di creazione di una regola in uscita personalizzata per bloccare il traffico Internet in uscita che verrà poi testata.

1. Dovrebbe essere visualizzata la pagina SC900-WinVM \| Connetti. Dal riquadro di spostamento sinistro selezionare **Rete**. Se in precedenza è stata chiusa la scheda del browser, selezionare la barra di ricerca blu nella parte superiore della pagina e selezionare Macchine virtuali, quindi selezionare la macchina virtuale **SC900-WinVM** e quindi selezionare **Rete**.

1. Selezionare la scheda **Regole porta in uscita**. Verranno visualizzate le regole in uscita predefinite.  Notare la regola predefinita "AllowInternetOutBound". Questa regola consente tutto il traffico Internet in uscita. Non è possibile rimuovere la regola predefinita, ma è possibile sostituirla creando una regola con priorità più alta. Nella parte destra della pagina, selezionare **Aggiungi regola porta in uscita**.

1. Nella pagina Aggiungi regola di sicurezza in uscita, specificare le seguenti impostazioni:
    1. Origine: **qualsiasi**
    1. Intervalli di porte di origine: **\***
    1. Destinazione: **tag del servizio**
    1. Tag del servizio di destinazione: **Internet**
    1. Servizio: **personalizzato** (lasciare l'impostazione predefinita)
    1. Intervalli di porte di destinazione: **\*** (assicurarsi di inserire un asterisco nel campo degli intervalli di porte di destinazione)
    1. Protocollo: **tutti**
    1. Azione: **nega**
    1. Priorità: **1000**
    1. Nome: lasciare il nome predefinito o creare un nome descrittivo personalizzato.
    1. Seleziona **Aggiungi**

1. Una volta che è stato effettuato il provisioning della regola, questa verrà visualizzata nell'elenco delle regole in uscita.  Anche se viene visualizzata nell'elenco, ci vorranno alcuni minuti prima che la regola abbia effetto (aspettare qualche minuto prima di continuare con i passaggi successivi).  


1. Tornare alla macchina virtuale (l'icona RDP della macchina virtuale dovrebbe essere visualizzata sulla barra delle applicazioni nella parte inferiore della pagina).

1. Aprire il browser Edge nella propria macchina virtuale e immettere **www.bing.com**. La pagina non dovrà essere visualizzata. Se si riesce a connettersi a Internet e si è verificata la corretta impostazione di tutti i parametri della regola in uscita, è possibile che ciò avvenga perché la regola impiega alcuni minuti per diventare attiva.  Chiudere il browser, attendere qualche minuto e riprovare. Le sottoscrizioni di Azure nell'ambiente lab potrebbero riscontrare ritardi più lunghi del normale.

1. Chiudere Connessione Desktop remoto, selezionando la **X** in alto al centro della pagina dove è indicato l'indirizzo IP.  Viene visualizzata una finestra popup che indica che la sessione remota verrà disconnessa. Seleziona **OK**.

1. Nell'angolo superiore a sinistra della finestra, subito sotto la barra blu, dove compare Microsoft Azure, selezionare **Home** per tornare alla home page dei servizi di Azure.

1. Mantenere aperta la scheda Azure nel browser.

### Revisione

In questo lab è stato illustrato il processo di configurazione di un gruppo di sicurezza di rete (NSG), associando il gruppo di sicurezza di rete all'interfaccia di rete di una macchina virtuale e aggiungendo nuove regole al gruppo di sicurezza di rete per consentire il traffico RDP in ingresso e bloccare il traffico Internet in uscita.
