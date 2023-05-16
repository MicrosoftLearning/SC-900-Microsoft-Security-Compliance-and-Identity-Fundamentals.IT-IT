---
lab:
  title: 'Esplorare i gruppi di sicurezza di rete di Azure (NSG)'
  module: 'Modulo 1: Descrivere le funzionalità di sicurezza di base in Azure'
---


# <a name="lab-explore-azure-network-security-groups-nsgs"></a>Laboratorio: Esplorazione dei gruppi di sicurezza di rete di Azure (NSG)

Questo lab corrisponde al contenuto di Learn seguente:

- Percorso di apprendimento: Descrivere le funzionalità delle soluzioni di sicurezza Microsoft
- Modulo: Descrivere le funzionalità di sicurezza di base in Azure
- Unità: Descrivere i gruppi di sicurezza di rete di Azure

## <a name="lab-scenario"></a>Scenario del lab

In questo lab, si esplorerà la funzione dei gruppi di sicurezza di rete in Azure.  A tale scopo, si creerà un gruppo di sicurezza di rete (NSG) e si assegnerà il gruppo di sicurezza di rete all'interfaccia di una macchina virtuale preesistente.  Dopo la configurazione, si osserveranno le regole predefinite in ingresso e in uscita, si creeranno nuove regole e infine si testeranno queste regole.  In questo lab, la macchina virtuale che verrà usata con il gruppo di sicurezza di rete viene creata automaticamente, quindi verranno visualizzate prima di tutto alcune delle informazioni associate alla macchina virtuale.
  
**Tempo stimato**: 30-45 minuti

### <a name="task-1"></a>Attività 1

In questa attività verranno visualizzati alcuni parametri associati alla macchina virtuale creata per l'uso con questo lab.

1. Aprire Microsoft Edge.  Nella barra degli indirizzi immettere **portal.azure.com**.

1. Accedere con le credenziali di amministratore.
    1. Nella finestra Accedi immettere il nome utente fornito dal provider di hosting del lab e quindi selezionare **Avanti**.
    1. Immettere la password di amministratore, che dovrebbe essere fornita dal proprio provider di hosting del lab. Fare clic su **Accedi**.
    1. Se viene richiesto se si desidera rimanere connessi, selezionare **Sì**.

1. Nella parte superiore della pagina, sotto alla dicitura Servizi di Azure, selezionare **Macchine virtuali**.  Se questa opzione non è disponibile, nella casella di ricerca, nella barra blu nella parte superiore della pagina accanto a Microsoft Azure, immettere **Macchine virtuali** e quindi selezionare **Macchine virtuali** dai risultati della ricerca.

1. Dalla pagina Macchine virtuali selezionare la macchina virtuale elencata **SC900-WinVM**.

1. Ora ci si trova nella pagina SC900-WinVM.  Si noti il nome del gruppo di risorse LabsSC900, in cui risiede la macchina virtuale.

1. Dalla parte superiore della pagina selezionare **Connetti**, quindi selezionare **RDP** dall'elenco a discesa. Si noti che il prerequisito della porta non è soddisfatto.  Per soddisfare il prerequisito, è necessario configurare una regola di sicurezza di rete in ingresso con la porta di destinazione 3389, usata da RDP.  Questa operazione verrà eseguita nell'attività successiva, quando si crea un gruppo di sicurezza di rete.

1. Dal riquadro di spostamento sinistro selezionare **Rete**.  
    1. La visualizzazione predefinita è per le regole della porta in ingresso.  Si noti che non ci sono gruppi di sicurezza di rete configurati per questa macchina virtuale.  Lo stesso vale se si selezionano regole di porta in uscita.
    1. Selezionare **Regole di sicurezza valide** accanto a Interfaccia di rete.  Notare il messaggio "All'interfaccia di rete non sono associati gruppi di sicurezza di rete o gruppi di sicurezza delle applicazioni".
1. Lasciare aperta la scheda del browser.

### <a name="task-2"></a>Attività 2

In questa attività si creerà un gruppo di sicurezza di rete, si assegnerà l'interfaccia di rete della macchina virtuale a tale gruppo di sicurezza di rete e si creerà una nuova regola in ingresso per il traffico RDP.

1. Aprire la scheda SC900-WinVM – Microsoft Azure nel browser.

1. Nella barra di ricerca blu nella parte superiore della pagina immettere **Gruppi di sicurezza di rete**. Nei risultati selezionare **Gruppi di sicurezza di rete** (non selezionare Gruppi di sicurezza di rete classici).

1. Dalla parte superiore della pagina Gruppi di sicurezza di rete, selezionare **+ Crea**.

1. Nella scheda Generale della pagina Crea gruppo di sicurezza di rete specificare le impostazioni seguenti:
    1. Sottoscrizione: lasciare il valore predefinito (si tratta della sottoscrizione di Azure fornita dal provider di servizi di hosting per i lab autorizzato)
    1. Gruppo di risorse:  **LabsSC900**
    1. Nome:  **NSG-SC900**
    1. Area: lasciare il valore predefinito.
    1. Selezionare **Verifica + Crea**, quindi **Crea**.

1. Una volta completata la distribuzione, selezionare **Vai alla risorsa**.

1. Nella parte superiore della pagina, sotto a Informazioni di base, verranno visualizzate alcune informazioni di base sul gruppo di sicurezza di rete creato.  Due punti da notare sono che non sono presenti regole di sicurezza personalizzate e non sono presenti subnet né interfacce di rete associate a questo gruppo di sicurezza di rete.  Anche se non sono presenti regole di sicurezza personalizzate, esistono regole predefinite in ingresso e in uscita incluse in ogni gruppo di sicurezza di rete, come illustrato nella pagina.  Esaminare sia le regole in ingresso che quelle in uscita. Le regole in ingresso predefinite negano tutto il traffico in ingresso che non proviene da una rete virtuale o da un servizio di bilanciamento del carico di Azure.  Le regole in uscita negano tutto il traffico in uscita, ad eccezione del traffico tra reti virtuali e del traffico in uscita verso Internet.

1. Dal riquadro di spostamento a sinistra nella pagina NSG-SC900, selezionare **Interfacce di rete** sotto Impostazioni.
    1. Selezionare **Associa**.
    2. Nel campo per le associazioni di interfaccia di rete selezionare la **freccia in giù**, selezionare **sc900-winvmXXX** e quindi selezionare **OK** nella parte inferiore della finestra. Una volta effettuata l'associazione dell'interfaccia al NSG, questa verrà visualizzata nell'elenco.

1. Dal riquadro di spostamento sinistro selezionare **Regole di sicurezza in ingresso**.

1. Le regole in ingresso predefinite negano tutto il traffico in ingresso che non proviene da una rete virtuale o da un servizio di bilanciamento del carico di Azure, quindi è necessario configurare una regola per consentire il traffico RDP in ingresso (traffico sulla porta 3389). Tenere presente che non è possibile rimuovere le regole predefinite, ma è possibile sostituirle creando regole con priorità più alte.

1. Nella parte superiore della pagina selezionare **Aggiungi**. Nella finestra Aggiungi regola di sicurezza in ingresso specificare le impostazioni seguenti:
    1. Origine:  **Qualsiasi**
    1. Intervalli di porte di origine: **\***
    1. Destinazione:  **Qualsiasi**
    1. Servizio:  **RDP**
    1. Azione:  **Consenti**
    1. Priorità: **1000**. Nota: le regole con i numeri più bassi hanno una priorità più alta e vengono elaborate per prime.
    1. Nome: lasciare il nome predefinito o creare un nome descrittivo personalizzato.
    1. Notare il simbolo di avviso nella parte inferiore della pagina.  Si usa RDP solo per scopi di test e per illustrare la funzionalità del gruppo di sicurezza di rete.
    1. Selezionare **Aggiungi**

1. Dopo aver effettuato il provisioning della regola, verrà visualizzata nell'elenco delle regole in ingresso (potrebbe essere necessario aggiornare la schermata). Nella regola appena aggiunta verrà visualizzato un simbolo di avviso.  Come indicato in precedenza, si usa RDP solo per scopi di test e per illustrare la funzionalità del gruppo di sicurezza di rete. Selezionare la regola appena aggiunta.

### <a name="task-3"></a>Attività 3

In questa attività si testerà la regola del gruppo di sicurezza di rete in ingresso appena creata per verificare che sia possibile stabilire una connessione Desktop remoto (RDP) alla macchina virtuale.  Una volta all'interno della macchina virtuale, si verificherà la connettività in uscita verso Internet dalla macchina virtuale.

1. Aprire la scheda SC900-WinVM – Microsoft Azure nel browser. Se in precedenza è stata chiusa la scheda del browser, selezionare la barra di ricerca blu nella parte superiore della pagina e selezionare Macchine virtuali, quindi selezionare la macchina virtuale **SC900-WinVM**.

1. Nella parte superiore della pagina selezionare **Connetti** e quindi **RDP**.

1. Verificare che l'indirizzo IP sia impostato su Indirizzo IP pubblico, lasciare il numero di porta predefinito e selezionare **Scarica file DRP**.

1. Nella finestra popup visualizzata selezionare **Apri file**.

1. Verrà visualizzata una finestra Connessione Desktop remoto. Selezionare **Connetti**.

1. Verranno chieste le credenziali.  Immettere nome utente e password (fare riferimento alla scheda delle risorse nel pannello delle istruzioni del lab).

1. Si apre una finestra di connessione al Desktop remoto con l'avviso "The identity of the remote computer cannot be verified.  Do you wish to connect anyway?" (Non è possibile verificare l'identità del computer remoto. Connettersi comunque?)  Selezionare **Sì**.

1. La connessione alla VM è stata ora stabilita. In questo caso, è stato possibile connettersi alla VM perché la regola del traffico in ingresso creata consente il traffico in ingresso alla VM tramite RDP.

1. Dopo alcuni secondi, nella schermata iniziale verrà visualizzata la finestra Scegli le impostazioni di privacy per il tuo dispositivo. Selezionare **Accetta**.  Nella finestra Reti selezionare **No**.

1. Con la macchina virtuale in esecuzione, testare la connettività in uscita a Internet dalla macchina virtuale.
    1. Dalla macchina virtuale selezionare **Microsoft Edge** per aprire il browser.  Trattandosi della prima volta che si apre Microsoft Edge, è possibile che venga visualizzata una finestra popup. Selezionare **Avvia senza dati**, selezionare **Continua senza dati** e quindi selezionare **Conferma e avvia l'esplorazione**.
    1. Immettere **www.bing.com** nella barra degli indirizzi del browser e verificare di riuscire a connettersi al motore di ricerca.
    1. Dopo aver confermato che è possibile accedere a www.bing.com, chiudere la finestra del browser nella macchina virtuale, ma lasciare la macchina virtuale attiva.

1. Ridurre al minimo la macchina virtuale selezionando il carattere di sottolineatura **_** nella scheda blu che mostra l'indirizzo IP della macchina virtuale. Si tornerà alla pagina SC900-WinVM | Connetti. 

1. Dal riquadro di spostamento sinistro selezionare **Rete**.

1. Mantenere aperta la scheda del browser perché verrà usata nell'attività successiva.

### <a name="task-4"></a>Attività 4

Nell'attività precedente è stata confermata la possibilità di stabilire una connessione RDP alla macchina virtuale. Dalla macchina virtuale è stata anche confermata la possibilità di stabilire una connessione in uscita a Internet.  Il traffico Internet in uscita era consentito perché le regole predefinite in uscita per il gruppo di sicurezza di rete consentono il traffico Internet in uscita.  In questa attività si seguirà il processo di creazione di una regola in uscita personalizzata per bloccare il traffico Internet in uscita e si testerà quella regola.

1. Dovrebbe essere visualizzata la pagina SC900-WinVM | Rete. Se in precedenza è stata chiusa la scheda del browser, selezionare la barra di ricerca blu nella parte superiore della pagina e selezionare Macchine virtuali, quindi selezionare la macchina virtuale **SC900-WinVM** e quindi selezionare **Rete**.

1. Selezionare la scheda **Regole porta in uscita**. Verranno visualizzate le regole in uscita predefinite.  Notare la regola predefinita "AllowInternetOutBound". Questa regola consente tutto il traffico Internet in uscita. Non è possibile rimuovere la regola predefinita, ma è possibile sostituirla creando una regola con priorità più alta. Dal lato destro della pagina, selezionare **Aggiungi regola porta in uscita**.

1. Nella pagina Aggiungi regola porta in uscita, specificare le seguenti impostazioni:
    1. Origine:  **Qualsiasi**
    1. Intervalli di porte di origine: **\***
    1. Destinazione:  **Tag del servizio**
    1. Tag del servizio di destinazione:  **Internet**
    1. Servizio:  **Personalizzato** (lasciare l'impostazione predefinita)
    1. Intervalli di porte di destinazione: * (assicurarsi di inserire un asterisco nel campo degli intervalli di porte di destinazione)
    1. Protocollo: **Qualsiasi**
    1. Azione: **Nega**
    1. Priorità: **1000**
    1. Nome: lasciare il nome predefinito o creare un nome descrittivo personalizzato.
    1. Selezionare **Aggiungi**

1. Una volta eseguito il provisioning della regola, questa verrà visualizzata nell'elenco delle regole in uscita.  Sebbene compaia nell'elenco, occorreranno alcuni minuti perché diventi efficace (attendere alcuni minuti mentre si procede ai passaggi successivi).  

1. Tornare alla macchina virtuale. L'icona per la macchina virtuale dovrebbe essere visualizzata sulla barra delle applicazioni nella parte inferiore della pagina.

1. Aprire il browser Edge nella propria macchina virtuale e immettere **www.bing.com**. La pagina non dovrebbe essere visualizzata.  Nota: se si riesce a connettersi a Internet e si è verificata la corretta impostazione di tutti i parametri della regola in uscita, è possibile che ciò avvenga perché la regola impiega alcuni minuti per diventare attiva.  Chiudere il browser, attendere alcuni minuti e riprovare.  Nota: le sottoscrizioni di Azure nell'ambiente lab potrebbero riscontrare ritardi più lunghi del normale.

1. Chiudere la connessione al desktop remoto selezionando la **X** in alto al centro della pagina dove viene mostrato l'indirizzo IP.  Viene visualizzata una finestra popup che indica che la sessione remota verrà disconnessa. Selezionare **OK**.

1. Chiudere tutte le schede del browser aperte.

### <a name="review"></a>Verifica

In questo lab sono stati illustrati i processi di configurazione di un gruppo di sicurezza di rete (NSG), di associazione del gruppo di sicurezza di rete all'interfaccia di rete di una macchina virtuale e di aggiunta di nuove regole al gruppo di sicurezza di rete per consentire il traffico RDP in ingresso e bloccare il traffico Internet in uscita.
