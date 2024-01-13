<!---
---
Demo: Titolo: 'Gruppi di sicurezza di rete di Azure (NSG)' Percorso di apprendimento/Modulo/Unità: 'Percorso di apprendimento: Descrivere le funzionalità delle soluzioni di sicurezza Microsoft; Modulo 1: Descrivere le funzionalità di sicurezza di base in Azure; Unità 6: Descrivere i gruppi di sicurezza di rete di Azure'
---
--->

# Demo: Gruppi di sicurezza di rete (NSG) di Azure

Questa demo corrisponde al contenuto di Learn seguente:

- Percorso di apprendimento: Descrivere le funzionalità delle soluzioni di sicurezza Microsoft
- Modulo: Descrivere le funzionalità di sicurezza di base in Azure
- Unità: Descrivere i gruppi di sicurezza di rete di Azure

## Scenario dimostrativo

In questa demo si esaminerà la funzione dei gruppi di sicurezza di rete in Azure e si applicherà un gruppo di sicurezza di rete a una macchina virtuale già creata. Si inizierà con una breve presentazione di informazioni sulla macchina virtuale che è stata creata in precedenza dal provider di servizi di hosting per i lab autorizzato. Quindi, usando un NSG che è stato configurato come parte della configurazione pre-demo, verranno visualizzati i parametri essenziali di un NSG e le regole predefinite in ingresso e in uscita. Verrà assegnata un'interfaccia della macchina virtuale a NSG, creata una nuova regola RDP per consentire la connessione alla macchina virtuale e infine si verrà eseguito il test.

### Demo parte 1

In questa parte, verranno visualizzati alcuni dei parametri associati alla macchina virtuale creata come parte della demo di configurazione (DEMO_00_pre_demo_setup.md).

1. Aprire Microsoft Edge.  Nella barra degli indirizzi, inserire **https://portal.azure.com** e accedere con le credenziali di Azure fornite dal provider di servizi di hosting per i lab autorizzato (ALH).  In questo modo si verrà indirizzati alla home page dei servizi di Azure.

1. Nella casella di ricerca di colore blu nella parte superiore della pagina, immettere **Macchine virtuali** e selezionare **Macchine virtuali** dai risultati di ricerca.

1. Dalla pagina Macchine virtuali selezionare la macchina virtuale elencata **SC900-WinVM**.  Questa macchina virtuale dovrebbe essere stata creata come parte della configurazione pre-demo.  Se non è presente nell'elenco, crearla ora.

1. Ora ci si trova nella pagina SC900-WinVM.  Notare alcune informazioni di base sulla macchina virtuale.

1. Dal riquadro di spostamento sinistro selezionare **Rete**.  
    1. La visualizzazione predefinita è per le regole della porta in ingresso.  Si noti che non ci sono gruppi di sicurezza di rete configurati per questa macchina virtuale.  Lo stesso vale se si selezionano regole di porta in uscita.
    1. Selezionare **Regole di sicurezza valide** accanto a Interfaccia di rete.  Notare il messaggio "All'interfaccia di rete non sono associati gruppi di sicurezza di rete o gruppi di sicurezza delle applicazioni".

1. Nota per il relatore: se si tenta di verificare lo stato della porta nella pagina di connessione, viene visualizzato il messaggio "Impossibile verificare".  Ciò non significa necessariamente che le porte non siano esposte.  Come si può notare, quando si esegue la stessa azione con NSG assegnato, viene visualizzato il messaggio "Non accessibile", indicando che il traffico su tale porta è bloccato.


1. Lasciare aperta la scheda del browser.

### Demo parte 2

In questa parte, verrà assegnerà un'interfaccia a NSG, verranno trattate le regole predefinite in ingresso e in uscita, illustrandone il funzionamento.  Come parte della configurazione pre-demo, una macchina virtuale dovrebbe assegnare l'interfaccia di rete della macchina virtuale a tale NSG e creare una nuova regola in ingresso per il traffico RDP.

1. Aprire una nuova scheda del browser per accedere al portale di Azure (portal.azure.com) e nella barra di ricerca di colore blu nella parte superiore della pagina, immettere **Gruppi di sicurezza di rete**. Nei risultati selezionare **Gruppi di sicurezza di rete** (non selezionare Gruppi di sicurezza di rete classici).

1. Selezionare l'NSG creato come parte della configurazione pre-demo. Se non lo si è creato in precedenza, è possibile farlo ora. Selezionare **Crea gruppo di sicurezza di rete** e specificare le seguenti impostazioni:
    1. Sottoscrizione: lasciare il valore predefinito (si tratta della sottoscrizione di Azure fornita dal provider di servizi di hosting per i lab autorizzato)
    1. Gruppo di risorse:  **LabsSC900** (lo stesso gruppo di risorse utilizzato dalla macchina virtuale).
    1. Nome: **NSG-SC900**
    1. Area: lasciare il valore predefinito.
    1. Selezionare **Rivedi e crea** e quindi **Crea**.
    1. Una volta completata la distribuzione (che avviene molto rapidamente), selezionare **Vai alla risorsa**.

1. Nella parte superiore della pagina, sotto a Informazioni di base, verranno visualizzate alcune informazioni di base sul gruppo di sicurezza di rete creato.  Due punti da notare sono che non sono presenti regole di sicurezza PERSONALIZZATE e non sono presenti subnet né interfacce di rete associate a questo gruppo di sicurezza di rete.  Anche se non sono presenti regole di sicurezza personalizzate, esistono regole predefinite in ingresso e in uscita incluse in ogni gruppo di sicurezza di rete, come illustrato nella pagina.  Esaminare sia le regole in ingresso che quelle in uscita. Le regole in ingresso predefinite negano tutto il traffico in ingresso che non proviene da una rete virtuale o da un servizio di bilanciamento del carico di Azure.  Le regole in uscita negano tutto il traffico in uscita, ad eccezione del traffico tra reti virtuali e del traffico in uscita verso Internet.

1. Dal riquadro di spostamento sinistro nella pagina NSG-SC900, selezionare **Interfacce di rete** in Impostazioni.
    1. Selezionare **Associa**.
    1. Nel campo per selezionare le associazioni di interfaccia di rete selezionare la **freccia a discesa**, selezionare **sc900-winvmXXX** e quindi selezionare **OK** nella parte inferiore della finestra. Una volta che l'interfaccia è associata al NSG, verrà visualizzata nell'elenco.

1. Tornare alla macchina virtuale selezionando la scheda del browser relativa alla macchina virtuale.  Dovrebbe essere visualizzato un NSG collegato all'interfaccia della macchina virtuale.  Viene visualizzata la tabella delle regole della porta in ingresso. Le regole in ingresso predefinite negano tutto il traffico in ingresso che non proviene da una rete virtuale o da un servizio di bilanciamento del carico di Azure.  Per effettuare il test, verificare lo stato della porta RDP 3389.
    1. Nella parte superiore della pagina, selezionare **Connetti**, quindi selezionare **Verifica accesso** per la porta 3389 (RDP); verrà visualizzato "Non accessibile".  
    1. Anche se il test viene eseguito solo sulla porta 3389 (RDP), tutto il traffico di rete in ingresso che non proviene da un'altra rete virtuale o da un bilanciamento del carico viene bloccato.  

1. Ora è necessario creare una regola per consentire il traffico in ingresso sulla porta RDP.  Dal riquadro di spostamento a sinistra, selezionare **Rete**. Dovrebbe essere visualizzata la tabella delle regole della porta in ingresso (la scheda Regole della porta in ingresso è sottolineata).  Dalla parte destra della pagina, selezionare **Aggiungi regola porta in ingresso**. Un aspetto importante da illustrare è che non è possibile rimuovere le regole predefinite, ma è possibile eseguirne l'override creando regole con priorità più alta. Nella finestra Aggiungi regola di sicurezza in ingresso specificare le impostazioni seguenti:
    1. Origine: **qualsiasi**
    1. Intervalli di porte di origine: **\***
    1. Destinazione: **qualsiasi**
    1. Servizio: **RDP**
    1. Azione: **Consenti**
    1. Priorità: **1000**. Nota: le regole con i numeri più bassi hanno una priorità più alta e vengono elaborate per prime.
    1. Nome: lasciare il nome predefinito o creare un nome descrittivo personalizzato.
    1. Notare il simbolo di avviso nella parte inferiore della pagina.  Si usa RDP solo per scopi di test e per illustrare la funzionalità del gruppo di sicurezza di rete.
    1. Seleziona **Aggiungi**

1. Dopo aver effettuato il provisioning della regola, verrà visualizzata nell'elenco delle regole in ingresso (potrebbe essere necessario aggiornare la schermata).

### Demo parte 3

Con NSG associati alla macchina virtuale e alla regola RDP creata, è possibile visualizzare l'effetto di NSG testando la connettività RDP alla macchina virtuale.

1. Aprire la scheda SC900-WinVM – Microsoft Azure nel browser. 

1. Dal riquadro di spostamento a sinistra, selezionare **Connetti**.
    1. È possibile selezionare **Verifica accesso**.  Lo stato dovrebbe essere "Accessibile". In alternativa, è possibile collegarsi alla macchina virtuale aprendo un'istanza di Connessione Desktop remoto su Windows.  Con questa opzione verrà visualizzata la macchina virtuale dopo averla collegata correttamente.  Di seguito sono elencati i passaggi:
        1. Nella barra di ricerca di Windows, digitare **Connessione Desktop remoto** e selezionare **Apri**.
        1. Nel campo accanto alla dicitura **Computer**, inserire l'indirizzo IP pubblico della macchina virtuale.
        1. Dopo aver immesso l'indirizzo IP, il nome utente dovrebbe apparire sotto il campo in cui è stato inserito l'indirizzo IP. In caso contrario, espandere **Mostra opzioni** e inserire il nome utente della macchina virtuale, quindi selezionare **Connetti**.
        1. Verrà visualizzata una finestra di Connessione Desktop Remoto che indica: L'identità del computer remoto non può essere verificata. Connettersi comunque? Selezionare **Sì**.
        1. La connessione alla VM è stata ora stabilita. Sottolineare allo studente che in questo caso è stato possibile connettersi alla macchina virtuale perché la regola del traffico in ingresso creata consente il traffico in ingresso alla macchina virtuale tramite RDP.
        1. Ridurre al minimo la macchina virtuale selezionando il carattere di sottolineatura **_** nella scheda blu che mostra l'indirizzo IP della macchina virtuale. Si tornerà alla pagina SC900-WinVM | Connetti.

1. Nel pannello di spostamento a sinistra, selezionare **Rete** e quindi, dalla finestra principale, selezionare **Regole porta in uscita**.  Consultare le regole predefinite relative alla porta in uscita. Le regole predefinite consentono sia il traffico di rete virtuale in uscita da una qualsiasi rete virtuale a un'altra sia il traffico Internet in uscita. Tutto il traffico in uscita di altro tipo viene rifiutato.  Non è possibile rimuovere la regola predefinita, ma è possibile eseguirne l'override creando una regola con priorità più alta nello stesso modo in cui è stata creata una regola in ingresso.

1. Se il tempo lo consente e si desidera mostrare passaggi simili relativi al traffico in uscita, visualizzare la parte demo facoltativa elencata di seguito.  In caso contrario, uscire dalla macchina virtuale, ma mantenere aperta la scheda di Azure nel browser per visualizzare la demo successiva.

### FACOLTATIVO Demo parte 4

In questa parte verranno mostrate le regole correnti del gruppo di sicurezza di rete in uscita, che consentono il traffico Internet in uscita dalla macchina virtuale.  Verrà creata quindi una regola per bloccare il traffico Internet in uscita dalla macchina virtuale. Infine, sarà mostrato l'effetto della regola appena creata, tentando di accedere a Internet dalla macchina virtuale.

1. Aprire la macchina virtuale ridotta a icona nel passaggio precedente. Qui sarà possibile mostrare la connettività in uscita a Internet, abilitata da una delle regole predefinite in uscita. Dopo aver aperto la macchina virtuale e aver eseguito l'accesso come utente, selezionare **Microsoft Edge** per aprire il browser.  Trattandosi della prima volta che si apre Microsoft Edge, è possibile che venga visualizzata una finestra popup. Selezionare **Avvia senza dati**, selezionare **Continua senza dati** e quindi selezionare **Conferma e avvia l'esplorazione**.
    1. Immettere **www.bing.com** nella barra degli indirizzi del browser e verificare di riuscire a connettersi al motore di ricerca.
    1. Dopo aver confermato che è possibile accedere a www.bing.com, chiudere la finestra del browser nella macchina virtuale, ma lasciare la macchina virtuale attiva.

1. Ridurre al minimo la macchina virtuale selezionando il carattere di sottolineatura **_** nella scheda blu che mostra l'indirizzo IP della macchina virtuale. Si tornerà alla pagina SC900-WinVM | Connetti.  

1. Dal riquadro di spostamento sinistro selezionare **Rete**.

1. Selezionare la scheda **Regole porta in uscita**. Verranno visualizzate le regole in uscita predefinite.  Notare la regola predefinita "AllowInternetOutBound". Questa regola consente tutto il traffico Internet in uscita. Non è possibile rimuovere la regola predefinita, ma è possibile sostituirla creando una regola con priorità più alta. Nella parte destra della pagina, selezionare **Aggiungi regola porta in uscita**.

1. Nella pagina Aggiungi regola di sicurezza in uscita, specificare le seguenti impostazioni:
    1. Origine: **qualsiasi**
    1. Intervalli di porte di origine: **\***
    1. Destinazione: **tag del servizio**
    1. Tag del servizio di destinazione: **Internet**
    1. Servizio: **personalizzato** (lasciare l'impostazione predefinita)
    1. Intervalli di porte di destinazione: * (assicurarsi di inserire un asterisco nel campo degli intervalli di porte di destinazione)
    1. Protocollo: **tutti**
    1. Azione: **nega**
    1. Priorità: **1000**
    1. Nome: lasciare il nome predefinito o creare un nome descrittivo personalizzato.
    1. Seleziona **Aggiungi**

1. Una volta che è stato effettuato il provisioning della regola, questa verrà visualizzata nell'elenco delle regole in uscita.  Anche se viene visualizzata nell'elenco, ci vorranno alcuni minuti prima che la regola abbia effetto (aspettare qualche minuto prima di continuare con i passaggi successivi).  

1. Tornare alla macchina virtuale. L'icona per la macchina virtuale dovrebbe essere visualizzata sulla barra delle applicazioni nella parte inferiore della pagina.

1. Aprire il browser Edge nella propria macchina virtuale e immettere **www.bing.com**. La pagina non dovrà essere visualizzata.  Nota: se si riesce a connettersi a Internet e si è verificata la corretta impostazione di tutti i parametri della regola in uscita, è possibile che ciò avvenga perché la regola impiega alcuni minuti per diventare attiva.  Chiudere il browser, attendere qualche minuto e riprovare.  Nota: le sottoscrizioni di Azure nell'ambiente lab potrebbero riscontrare ritardi più lunghi del normale.

1. Chiudere Connessione Desktop remoto, selezionando la **X** in alto al centro della pagina dove è indicato l'indirizzo IP.  Viene visualizzata una finestra popup che indica che la sessione remota verrà disconnessa. Seleziona **OK**.

1. Mantenere aperta la scheda Azure nel browser per visualizzare la demo di Azure successiva.

### Revisione

In questa demo sono state presentate le informazioni e le impostazioni associate a un gruppo di sicurezza di rete, incluso il processo di associazione di un'interfaccia al gruppo di sicurezza di rete, sono state illustrate le e regole in ingresso e in uscita predefinite e infine sono stati descritti i passaggi per creare una nuova regola.
