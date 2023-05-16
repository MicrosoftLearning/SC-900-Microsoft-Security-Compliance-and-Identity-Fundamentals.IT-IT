---
demo:
  title: 'Gruppi di sicurezza di rete di Azure (NSG)'
  module: 'Modulo 1: Descrivere le funzionalità di sicurezza di base in Azure'
---


# <a name="demo-azure-network-security-groups-nsgs"></a>Dimostrazione: Gruppi di sicurezza di rete (NSG) di Azure

Questa demo corrisponde al contenuto di Learn seguente:

- Percorso di apprendimento: Descrivere le funzionalità delle soluzioni di sicurezza Microsoft
- Modulo: Descrivere le funzionalità di sicurezza di base in Azure
- Unità: Descrivere i gruppi di sicurezza di rete di Azure

## <a name="demo-scenario"></a>Scenario demo

In questa demo si esaminerà la funzione dei gruppi di sicurezza di rete in Azure e si applicherà un gruppo di sicurezza di rete a una macchina virtuale già creata. Si inizierà con una breve presentazione di informazioni sulla macchina virtuale che è stata creata in precedenza dal provider di servizi di hosting per i lab autorizzato. Verrà quindi illustrato il processo di creazione del gruppo di sicurezza di rete, poi verranno presentate le regole predefinite in ingresso e in uscita, quindi verrà creata e testata una nuova regola RDP per consentire la connessione alla macchina virtuale.

### <a name="demo-part-1"></a>Demo parte 1

In questa parte verranno visualizzati alcuni dei parametri associati alla macchina virtuale creata per l'uso con questo lab.

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

### <a name="demo-part-2"></a>Demo parte 2

In questa parte si creerà un gruppo di sicurezza di rete, si assegnerà l'interfaccia di rete della macchina virtuale a tale gruppo di sicurezza di rete e si creerà una nuova regola in ingresso per il traffico RDP.

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

1. Nella parte superiore della pagina, sotto a Informazioni di base, verranno visualizzate alcune informazioni di base sul gruppo di sicurezza di rete creato.  Due punti da notare sono che non sono presenti regole di sicurezza PERSONALIZZATE e non sono presenti subnet né interfacce di rete associate a questo gruppo di sicurezza di rete.  Anche se non sono presenti regole di sicurezza personalizzate, esistono regole predefinite in ingresso e in uscita incluse in ogni gruppo di sicurezza di rete, come illustrato nella pagina.  Esaminare sia le regole in ingresso che quelle in uscita. Le regole in ingresso predefinite negano tutto il traffico in ingresso che non proviene da una rete virtuale o da un servizio di bilanciamento del carico di Azure.  Le regole in uscita negano tutto il traffico in uscita, ad eccezione del traffico tra reti virtuali e del traffico in uscita verso Internet.

1. Dal riquadro di spostamento sinistro nella pagina NSG-SC900, selezionare **Interfacce di rete** in Impostazioni.
    1. Selezionare **Associa**.
    1. Nel campo per selezionare le associazioni di interfaccia di rete selezionare la **freccia a discesa**, selezionare **sc900-winvmXXX** e quindi selezionare **OK** nella parte inferiore della finestra. Una volta effettuata l'associazione dell'interfaccia al NSG, questa verrà visualizzata nell'elenco.

1. Dal riquadro di spostamento sinistro selezionare **Regole di sicurezza in ingresso**. Le regole in ingresso predefinite negano tutto il traffico in ingresso che non proviene da una rete virtuale o da un servizio di bilanciamento del carico di Azure, quindi è necessario configurare una regola per consentire il traffico RDP in ingresso (traffico sulla porta 3389). Tenere presente che non è possibile rimuovere le regole predefinite, ma è possibile sostituirle creando regole con priorità più alte.

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

1. Dopo aver effettuato il provisioning della regola, verrà visualizzata nell'elenco delle regole in ingresso (potrebbe essere necessario aggiornare la schermata). Nella regola appena aggiunta verrà visualizzato un simbolo di avviso.  Come indicato in precedenza, si usa RDP solo per scopi di test e per illustrare la funzionalità del gruppo di sicurezza di rete.

### <a name="demo-part-3"></a>Demo parte 3

Con il gruppo di sicurezza di rete creato e associato alla macchina virtuale e alla regola RDP creata, si mostrerà l'impatto del gruppo di sicurezza di rete testando la connettività RDP alla macchina virtuale.

1. Aprire la scheda SC900-WinVM – Microsoft Azure nel browser. Se in precedenza è stata chiusa la scheda del browser, selezionare la barra di ricerca blu nella parte superiore della pagina e selezionare Macchine virtuali, quindi selezionare la macchina virtuale **SC900-WinVM**.

1. Testare la regola in ingresso verificando che è possibile connettersi alla VM tramite RDP.
    1. Selezionare **Connetti** nel riquadro di spostamento a sinistra.
    1. Verificare che l'indirizzo IP sia impostato su Indirizzo IP pubblico, lasciare il numero di porta predefinito e selezionare **Scarica file DRP**.
    1. **Aprire** il file scaricato e selezionare **Connetti**.
    1. Verranno chieste le credenziali. Immettere il nome utente e la password usati al momento della creazione della macchina virtuale.  Se la finestra di richiesta di inserimento delle credenziali richiede un PIN, selezionare **Altre opzioni**, quindi selezionare **Usa un altro account**.
    1. Si apre una finestra di connessione al Desktop remoto con l'avviso "The identity of the remote computer cannot be verified. Do you wish to connect anyway?" (Non è possibile verificare l'identità del computer remoto. Connettersi comunque?) Selezionare **Sì**.
    1. La connessione alla VM è stata ora stabilita. Sottolineare allo studente che in questo caso è stato possibile connettersi alla macchina virtuale perché la regola del traffico in ingresso creata consente il traffico in ingresso alla macchina virtuale tramite RDP.

1. Trovandosi già all'interno della macchina virtuale, è possibile mostrare la connettività in uscita a Internet, abilitata da una delle regole predefinite in uscita.
    1. Dalla macchina virtuale selezionare **Microsoft Edge** per aprire il browser.  Trattandosi della prima volta che si apre Microsoft Edge, è possibile che venga visualizzata una finestra popup. Selezionare **Avvia senza dati**, selezionare **Continua senza dati** e quindi selezionare **Conferma e avvia l'esplorazione**.
    1. Immettere **www.bing.com** nella barra degli indirizzi del browser e verificare di riuscire a connettersi al motore di ricerca.
    1. Dopo aver confermato che è possibile accedere a www.bing.com, chiudere la finestra del browser nella macchina virtuale, ma lasciare la macchina virtuale attiva.

1. Ridurre al minimo la macchina virtuale selezionando il carattere di sottolineatura **_** nella scheda blu che mostra l'indirizzo IP della macchina virtuale. Si tornerà alla pagina SC900-WinVM | Connetti.  

### <a name="optional-demo-part-4"></a>FACOLTATIVO Demo parte 4

Se il tempo disponibile per la lezione lo consente, è possibile creare una regola del gruppo di sicurezza di rete in uscita per bloccare il traffico Internet in uscita dalla macchina virtuale.

1. Dal riquadro di spostamento sinistro selezionare **Rete**. Dovrebbe essere visualizzata la pagina SC900-WinVM | Rete.

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

1. Come procedura consigliata generale, è utile arrestare o rimuovere la macchina virtuale per evitare di sostenere costi, se viene usata solo per scopi di demo o test. In questo caso, tuttavia, NON rimuovere la macchina virtuale, perché consentirà di alimentare i dati per la gestione della postura di sicurezza cloud durante la demo di Microsoft Defender per il cloud.  La macchina virtuale verrà rimossa quando il lab viene annullato.

#### <a name="review"></a>Verifica

In questa demo sono state presentate le informazioni e le impostazioni associate a un gruppo di sicurezza di rete, incluso il processo di associazione di un'interfaccia al gruppo di sicurezza di rete, sono state illustrate le e regole in ingresso e in uscita predefinite e infine sono stati descritti i passaggi per creare una nuova regola.
