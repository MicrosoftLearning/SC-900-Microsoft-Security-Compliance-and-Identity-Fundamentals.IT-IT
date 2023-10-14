<!---
---
Demo: Titolo: 'Gruppi di sicurezza di rete di Azure (NSG)' Percorso di apprendimento/Modulo/Unità: 'Percorso di apprendimento: Descrivere le funzionalità delle soluzioni di sicurezza Microsoft; Modulo 1: Descrivere le funzionalità di sicurezza di base in Azure; Unità 6: Descrivere i gruppi di sicurezza di rete di Azure'
---
--->

# Dimostrazione: Gruppi di sicurezza di rete (NSG) di Azure

Questa demo corrisponde al contenuto di Learn seguente:

- Percorso di apprendimento: Descrivere le funzionalità delle soluzioni di sicurezza Microsoft
- Modulo: Descrivere le funzionalità di sicurezza di base in Azure
- Unità: Descrivere i gruppi di sicurezza di rete di Azure

## Scenario demo

In questa demo si esaminerà la funzione dei gruppi di sicurezza di rete in Azure e si applicherà un gruppo di sicurezza di rete a una macchina virtuale già creata. Si inizierà con una breve presentazione di informazioni sulla macchina virtuale che è stata creata in precedenza dal provider di servizi di hosting per i lab autorizzato. Quindi, usando un gruppo di sicurezza di rete configurato come parte della configurazione pre-demo, verranno visualizzati i parametri essenziali di un gruppo di sicurezza di rete e le regole predefinite in ingresso e in uscita. Si assegna un'interfaccia vm al gruppo di sicurezza di rete, si creerà una nuova regola RDP per consentire la connessione alla macchina virtuale e infine si eseguirà il test.

### Demo parte 1

In questa parte verranno visualizzati alcuni dei parametri associati alla macchina virtuale creata come parte della demo di installazione (DEMO_00_pre_demo_setup.md).

1. Aprire Microsoft Edge.  Nella barra degli indirizzi immettere e accedere **https://portal.azure.com** con le credenziali di Azure fornite dall'host del lab autorizzato (ALH).  Verrà visualizzata la home page dei servizi di Azure.

1. Nella casella di ricerca blu nella parte superiore della pagina immettere **Macchine virtuali** quindi selezionare **Macchine virtuali** dai risultati della ricerca.

1. Dalla pagina Macchine virtuali selezionare la macchina virtuale elencata **SC900-WinVM**.  Questa macchina virtuale deve essere stata creata come parte della configurazione pre-demo.  Se non è elencato, crearlo ora.

1. Ora ci si trova nella pagina SC900-WinVM.  Si notino alcune delle informazioni di base sulla macchina virtuale.

1. Dal riquadro di spostamento sinistro selezionare **Rete**.  
    1. La visualizzazione predefinita è per le regole della porta in ingresso.  Si noti che non ci sono gruppi di sicurezza di rete configurati per questa macchina virtuale.  Lo stesso vale se si selezionano regole di porta in uscita.
    1. Selezionare **Regole di sicurezza valide** accanto a Interfaccia di rete.  Notare il messaggio "All'interfaccia di rete non sono associati gruppi di sicurezza di rete o gruppi di sicurezza delle applicazioni".

1. Nota per il relatore, se si prova a controllare lo stato della porta nella pagina di connessione, viene visualizzato il messaggio "Impossibile verificare".  Ciò non significa necessariamente che le porte non siano esposte.  Come si noterà quando si esegue la stessa azione con NSG assegnato si ottiene "Non accessibile" che indica che il traffico su tale porta è bloccato.


1. Lasciare aperta la scheda del browser.

### Demo parte 2

In questa parte si assegna un'interfaccia al gruppo di sicurezza di rete, si parlerà delle regole in ingresso e in uscita predefinite che illustrano il funzionamento delle regole.  Come parte della configurazione pre-demo, una macchina virtuale deve assegnare l'interfaccia di rete della macchina virtuale a tale gruppo di sicurezza di rete e creare una nuova regola in ingresso per il traffico RDP.

1. Aprire una nuova scheda del browser alla portale di Azure (portal.azure.com) e nella barra di ricerca blu nella parte superiore della pagina immettere **gruppi di sicurezza di rete**. Nei risultati selezionare **Gruppi di sicurezza di rete** (non selezionare Gruppi di sicurezza di rete classici).

1. Selezionare il gruppo di sicurezza di rete creato come parte della configurazione pre-demo. Se non è stato creato in precedenza, farlo ora. Selezionare **Crea gruppo di sicurezza di rete** e specificare le impostazioni seguenti:
    1. Sottoscrizione: lasciare il valore predefinito (si tratta della sottoscrizione di Azure fornita dal provider di servizi di hosting per i lab autorizzato)
    1. Gruppo di risorse:  **LabsSC900** (lo stesso gruppo di risorse usato dalla macchina virtuale).
    1. Nome:  **NSG-SC900**
    1. Area: lasciare il valore predefinito.
    1. Selezionare **Verifica + Crea**, quindi **Crea**.
    1. Al termine della distribuzione (questo avviene molto rapidamente), selezionare **Vai alla risorsa**.

1. Nella parte superiore della pagina, sotto a Informazioni di base, verranno visualizzate alcune informazioni di base sul gruppo di sicurezza di rete creato.  Due punti da notare sono che non sono presenti regole di sicurezza PERSONALIZZATE e non sono presenti subnet né interfacce di rete associate a questo gruppo di sicurezza di rete.  Anche se non sono presenti regole di sicurezza personalizzate, esistono regole predefinite in ingresso e in uscita incluse in ogni gruppo di sicurezza di rete, come illustrato nella pagina.  Esaminare sia le regole in ingresso che quelle in uscita. Le regole in ingresso predefinite negano tutto il traffico in ingresso che non proviene da una rete virtuale o da un servizio di bilanciamento del carico di Azure.  Le regole in uscita negano tutto il traffico in uscita, ad eccezione del traffico tra reti virtuali e del traffico in uscita verso Internet.

1. Dal riquadro di spostamento sinistro nella pagina NSG-SC900, selezionare **Interfacce di rete** in Impostazioni.
    1. Selezionare **Associa**.
    1. Nel campo per selezionare le associazioni di interfaccia di rete selezionare la **freccia a discesa**, selezionare **sc900-winvmXXX** e quindi selezionare **OK** nella parte inferiore della finestra. Una volta effettuata l'associazione dell'interfaccia al NSG, questa verrà visualizzata nell'elenco.

1. Restituire la macchina virtuale selezionando la scheda del browser per la macchina virtuale.  Si noterà che è ora presente un gruppo di sicurezza di rete collegato all'interfaccia della macchina virtuale.  Viene visualizzata la tabella delle regole delle porte in ingresso. Le regole in ingresso predefinite negano tutto il traffico in ingresso che non proviene da una rete virtuale o da un servizio di bilanciamento del carico di Azure.  Per testare questo problema, si verificherà lo stato nella porta RDP 3389.
    1. Nella parte superiore della pagina selezionare **Connetti** e quindi selezionare **Controlla l'accesso** per la porta 3389 (RDP), verrà visualizzato "Non accessibile".  
    1. Anche se si esegue solo il test sulla porta RDP 3389, tutto il traffico di rete in ingresso non proveniente da un'altra rete virtuale o il servizio di bilanciamento del carico è bloccato.  

1. Verrà ora creata una regola per consentire il traffico in ingresso sulla porta RDP.  Nel riquadro di spostamento a sinistra selezionare **Rete**. La tabella Regole porta in ingresso deve essere visualizzata (viene sottolineata la scheda Regole porta in ingresso).  Dal lato destro della pagina selezionare **Aggiungi regola porta in ingresso**. Un punto importante da chiamare è che non è possibile rimuovere le regole predefinite, ma è possibile eseguirne l'override creando regole con priorità più elevate. Nella finestra Aggiungi regola di sicurezza in ingresso specificare le impostazioni seguenti:
    1. Origine:  **Qualsiasi**
    1. Intervalli di porte di origine: **\***
    1. Destinazione:  **Qualsiasi**
    1. Servizio:  **RDP**
    1. Azione:  **Consenti**
    1. Priorità: **1000**. Nota: le regole con i numeri più bassi hanno una priorità più alta e vengono elaborate per prime.
    1. Nome: lasciare il nome predefinito o creare un nome descrittivo personalizzato.
    1. Notare il simbolo di avviso nella parte inferiore della pagina.  Si usa RDP solo per scopi di test e per illustrare la funzionalità del gruppo di sicurezza di rete.
    1. Selezionare **Aggiungi**

1. Dopo aver effettuato il provisioning della regola, verrà visualizzata nell'elenco delle regole in ingresso (potrebbe essere necessario aggiornare la schermata).

### Demo parte 3

Con il gruppo di sicurezza di rete associato alla macchina virtuale e alla regola RDP creata, si mostrerà l'impatto del gruppo di sicurezza di rete testando la connettività RDP alla macchina virtuale.

1. Aprire la scheda SC900-WinVM – Microsoft Azure nel browser. 

1. Selezionare **Connetti** nel riquadro di spostamento a sinistra.
    1. È sufficiente selezionare **controlla l'accesso**.  Lo stato deve essere visualizzato come "Accessibile". In alternativa, se è possibile connettersi alla macchina virtuale aprendo un'istanza di Connessione Desktop remoto in Windows.  Questa opzione aprirà la macchina virtuale al termine della connessione.  Di seguito sono elencati i passaggi seguenti:
        1. Nella barra di ricerca di Windows immettere **Connessione desktop remoto** e quindi selezionare **Apri**.
        1. Nel campo accanto a dove si dice **Computer** immettere l'indirizzo IP pubblico della macchina virtuale.
        1. Dopo aver immesso l'indirizzo IP, il nome utente dovrebbe essere visualizzato sotto il campo in cui è stato immesso l'indirizzo IP. In caso contrario, espandere **Mostra opzioni** e immettere il nome utente per la macchina virtuale, quindi selezionare **Connetti**.
        1. Si apre una finestra di connessione al Desktop remoto con l'avviso "The identity of the remote computer cannot be verified. Do you wish to connect anyway?" (Non è possibile verificare l'identità del computer remoto. Connettersi comunque?) Selezionare **Sì**.
        1. La connessione alla VM è stata ora stabilita. Sottolineare allo studente che in questo caso è stato possibile connettersi alla macchina virtuale perché la regola del traffico in ingresso creata consente il traffico in ingresso alla macchina virtuale tramite RDP.
        1. Ridurre al minimo la macchina virtuale selezionando il carattere di sottolineatura **_** nella scheda blu che mostra l'indirizzo IP della macchina virtuale. Si tornerà alla pagina SC900-WinVM | Connetti.

1. Nel pannello di spostamento a sinistra selezionare **Rete** e quindi nella finestra principale selezionare **Regole porta in uscita**.  Parlare con le regole predefinite in uscita. Le regole predefinite consentono il traffico di rete virtuale in uscita da qualsiasi rete virtuale a qualsiasi altra rete virtuale e consente il traffico Internet in uscita. Viene negato qualsiasi altro tipo di traffico in uscita.  Non è possibile rimuovere la regola predefinita, ma è possibile eseguirne l'override creando una regola con priorità più alta nello stesso modo in cui è stata creata una regola in ingresso.

1. Se il timer consente e si desidera visualizzare passaggi simili per il traffico in uscita, passare attraverso la parte demo facoltativa elencata di seguito.  In caso contrario, uscire dalla macchina virtuale, ma mantenere aperta la scheda Azure nel browser per la demo successiva.

### FACOLTATIVO Demo parte 4

In questa parte verranno visualizzate le regole in uscita del gruppo di sicurezza di rete correnti che consentono il traffico Internet in uscita dalla macchina virtuale.  Verrà quindi creata una regola per bloccare il traffico Internet in uscita dalla macchina virtuale, infine si mostrerà l'impatto della regola appena creata tentando di accedere a Internet dalla macchina virtuale.

1. Aprire la macchina virtuale ridotta al minimo nel passaggio precedente. In questo caso verrà visualizzata la connettività Internet in uscita a Internet, abilitata da una delle regole predefinite in uscita. Dopo l'apertura della macchina virtuale e l'accesso come utente, selezionare **Microsoft Edge** per aprire il browser.  Trattandosi della prima volta che si apre Microsoft Edge, è possibile che venga visualizzata una finestra popup. Selezionare **Avvia senza dati**, selezionare **Continua senza dati** e quindi selezionare **Conferma e avvia l'esplorazione**.
    1. Immettere **www.bing.com** nella barra degli indirizzi del browser e verificare di riuscire a connettersi al motore di ricerca.
    1. Dopo aver confermato che è possibile accedere a www.bing.com, chiudere la finestra del browser nella macchina virtuale, ma lasciare la macchina virtuale attiva.

1. Ridurre al minimo la macchina virtuale selezionando il carattere di sottolineatura **_** nella scheda blu che mostra l'indirizzo IP della macchina virtuale. Si tornerà alla pagina SC900-WinVM | Connetti.  

1. Dal riquadro di spostamento sinistro selezionare **Rete**.

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

1. Mantenere aperta la scheda Azure nel browser per la demo di Azure successiva.

### Verifica

In questa demo sono state presentate le informazioni e le impostazioni associate a un gruppo di sicurezza di rete, incluso il processo di associazione di un'interfaccia al gruppo di sicurezza di rete, sono state illustrate le e regole in ingresso e in uscita predefinite e infine sono stati descritti i passaggi per creare una nuova regola.
