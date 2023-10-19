<!---
---
Lab: Titolo: 'Esplorare i gruppi di sicurezza di rete di Azure (NSG)' Percorso di apprendimento/Modulo/Unità: 'Percorso di apprendimento: Descrivere le funzionalità delle soluzioni di sicurezza Microsoft; Modulo 1: Descrivere le funzionalità di sicurezza di base in Azure; Unità 6: Descrivere i gruppi di sicurezza di rete di Azure'
---
--->

# Laboratorio: Esplorazione dei gruppi di sicurezza di rete di Azure (NSG)

Questo lab corrisponde al contenuto di Learn seguente:

- Percorso di apprendimento: Descrivere le funzionalità delle soluzioni di sicurezza Microsoft
- Modulo: Descrivere le funzionalità di sicurezza di base in Azure
- Unità: Descrivere i gruppi di sicurezza di rete di Azure

## Scenario del lab

In questo lab, si esplorerà la funzione dei gruppi di sicurezza di rete in Azure.  A tale scopo, si creerà un gruppo di sicurezza di rete (NSG) e si assegnerà il gruppo di sicurezza di rete all'interfaccia di una macchina virtuale preesistente.  Dopo la configurazione, si osserveranno le regole predefinite in ingresso e in uscita, si creeranno nuove regole e infine si testeranno queste regole.  In questo lab, la macchina virtuale che verrà usata con il gruppo di sicurezza di rete viene creata automaticamente, quindi verranno visualizzate prima di tutto alcune delle informazioni associate alla macchina virtuale.
  
**Tempo stimato**: 30-45 minuti

### Attività 1

In questa attività verranno visualizzati alcuni parametri associati alla macchina virtuale creata per l'uso con questo lab.

1. Aprire Microsoft Edge.  Nella barra degli indirizzi immettere **https://portal.azure.com**.

1. Accedere con le credenziali di amministratore.
    1. Nella finestra Accedi immettere il nome utente fornito dal provider di hosting del lab e quindi selezionare **Avanti**.
    1. Immettere la password di amministratore, che dovrebbe essere fornita dal proprio provider di hosting del lab. Fare clic su **Accedi**.
    1. Se viene richiesto se si desidera rimanere connessi, selezionare **Sì**.

1. Nella parte superiore della pagina, sotto alla dicitura Servizi di Azure, selezionare **Macchine virtuali**.  Se questa opzione non è disponibile, nella casella di ricerca, nella barra blu nella parte superiore della pagina accanto a Microsoft Azure, immettere **Macchine virtuali** e quindi selezionare **Macchine virtuali** dai risultati della ricerca.

1. Dalla pagina Macchine virtuali selezionare la macchina virtuale elencata **SC900-WinVM**.

1. Ora ci si trova nella pagina SC900-WinVM.  Si notino alcune delle informazioni di base sulla macchina virtuale.

1. Nella parte superiore della pagina selezionare **Connetti**.  Selezionare l'opzione **Controlla l'accesso**, elencata nell'indirizzo IP.  Questo controllo verrà eseguito usando la porta 3389, ovvero la porta per la connettività RDP.  Verrà visualizzato il messaggio "Impossibile verificare".  Nella casella RDP nativa fare clic su **Seleziona**.  Nella finestra visualizzata, in "1 Configurare i prerequisiti per Native RDP", verrà visualizzato "Azure deve configurare alcune funzionalità per connettersi alla macchina virtuale".  Nell'attività successiva verrà configurato un gruppo di sicurezza di rete per consentire in modo esplicito la connessione RDP.


1. Dal riquadro di spostamento sinistro selezionare **Rete**.  
    1. La visualizzazione predefinita è per le regole della porta in ingresso.  Si noti che non ci sono gruppi di sicurezza di rete configurati per questa macchina virtuale.  Lo stesso vale se si selezionano regole di porta in uscita.
    1. Selezionare **Regole di sicurezza valide** accanto a Interfaccia di rete.  Notare il messaggio "All'interfaccia di rete non sono associati gruppi di sicurezza di rete o gruppi di sicurezza delle applicazioni".

1. Lasciare aperta la scheda del browser.


### Attività 2

In questa attività si creerà un gruppo di sicurezza di rete, si assegnerà l'interfaccia di rete della macchina virtuale a tale gruppo di sicurezza di rete e si creerà una nuova regola in ingresso per il traffico RDP.

1. Nella scheda Apri gruppo di sicurezza di rete *fare clic con il pulsante destro del mouse* sul collegamento **Home** nella parte superiore della pagina e selezionare **Apri collegamento nella nuova scheda** per aprire un'altra pagina ai servizi di Azure.

1. Nella barra di ricerca blu nella parte superiore della pagina immettere gruppi di **sicurezza di rete** e, dai risultati, selezionare **Gruppi di sicurezza di rete**. Non selezionare *Gruppi di sicurezza di rete (versione classica).*

1. Dalla parte superiore della pagina Gruppi di sicurezza di rete, selezionare **+ Crea**.

1. Nella scheda Generale della pagina Crea gruppo di sicurezza di rete specificare le impostazioni seguenti:
    1. Sottoscrizione: lasciare il valore predefinito (si tratta della sottoscrizione di Azure fornita dal provider di servizi di hosting per i lab autorizzato)
    1. Gruppo di risorse:  **LabsSC900**
    1. Nome:  **NSG-SC900**
    1. Area: lasciare il valore predefinito.
    1. Selezionare **Verifica + Crea**, quindi **Crea**.

1. Una volta completata la distribuzione, selezionare **Vai alla risorsa**.

1. Nella parte superiore della pagina, sotto a Informazioni di base, verranno visualizzate alcune informazioni di base sul gruppo di sicurezza di rete creato.  Due punti da notare sono che non sono presenti regole di sicurezza personalizzate e non sono presenti subnet né interfacce di rete associate a questo gruppo di sicurezza di rete.  Anche se non sono presenti regole di sicurezza personalizzate, esistono regole predefinite in ingresso e in uscita incluse in ogni gruppo di sicurezza di rete, come illustrato nella pagina.  Esaminare sia le regole in ingresso che quelle in uscita. Le regole in ingresso predefinite negano tutto il traffico in ingresso che non proviene da una rete virtuale o da un servizio di bilanciamento del carico di Azure.  Le regole in uscita negano tutto il traffico in uscita, ad eccezione del traffico tra reti virtuali e traffico in uscita a Internet.

1. Dal riquadro di spostamento a sinistra nella pagina NSG-SC900, selezionare **Interfacce di rete** sotto Impostazioni.
    1. Selezionare **Associa**.
    2. Nel campo per le associazioni di interfaccia di rete selezionare la freccia giù, selezionare **sc900-winvmXXX**, quindi selezionare **OK** nella parte inferiore della finestra.**** Una volta effettuata l'associazione dell'interfaccia al NSG, questa verrà visualizzata nell'elenco.

1. Dal riquadro di spostamento sinistro selezionare **Regole di sicurezza in ingresso**.

1. Le regole in ingresso predefinite negano tutto il traffico in ingresso che non proviene da una rete virtuale o da un servizio di bilanciamento del carico di Azure, quindi è necessario configurare una regola per consentire il traffico RDP in ingresso (traffico sulla porta 3389). Tenere presente che non è possibile rimuovere le regole predefinite, ma è possibile sostituirle creando regole con priorità più alte.

1. Nella parte superiore della pagina selezionare **Aggiungi**. Nella finestra Aggiungi regola di sicurezza in ingresso specificare le impostazioni seguenti:
    1. Origine:  **Qualsiasi**
    1. Intervalli di porte di origine: **\***
    1. Destinazione:  **Qualsiasi**
    1. Servizio:  **RDP**
    1. Azione:  **Consenti**
    1. Priorità: **1000**. Le regole con numeri inferiori hanno priorità maggiore e vengono elaborate prima.
    1. Nome: lasciare il nome predefinito o creare un nome descrittivo personalizzato.
    1. Notare il simbolo di avviso nella parte inferiore della pagina.  Si usa RDP solo per scopi di test e per illustrare la funzionalità del gruppo di sicurezza di rete.
    1. Selezionare **Aggiungi**

1. Dopo aver effettuato il provisioning della regola, verrà visualizzata nell'elenco delle regole in ingresso (potrebbe essere necessario aggiornare la schermata).

1. Lasciare aperta la scheda del browser.  

### Attività 3

In questa attività si testerà la regola del gruppo di sicurezza di rete in ingresso appena creata per verificare che sia possibile stabilire una connessione Desktop remoto (RDP) alla macchina virtuale.  Una volta all'interno della macchina virtuale, si verificherà la connettività in uscita a Internet dalla macchina virtuale.

1. Aprire la scheda SC900-WinVM – Microsoft Azure nel browser. Se in precedenza è stata chiusa la scheda del browser, aprire una nuova scheda del browser, immettere **https://portal.azure.com**e selezionare **Macchine** virtuali, quindi selezionare la macchina virtuale **, SC900-WinVM**.

1. Selezionare **Connetti** nel riquadro di spostamento a sinistra.

1. Selezionare **check access** (verificare che la porta sia impostata su 3389).  Lo stato deve essere visualizzato come "Accessibile".

1. Connettersi direttamente alla macchina virtuale facendo clic su **Seleziona** nella casella che indica Native RDP.
   
    1. Nella finestra **RdP nativa visualizzata selezionare Scarica file RDP**.
    1. Se viene visualizzato un avviso di download, selezionare **Mantieni**, quindi nella finestra popup visualizzata selezionare **Apri file**.
    1. Verrà visualizzata una finestra Connessione Desktop remoto; selezionare **Connetti**.
    1. Verranno chieste le credenziali.  Immettere nome utente e password per la macchina virtuale (vedere la scheda risorse nel pannello delle istruzioni del lab).
    1. Verrà visualizzata una finestra di connessione Desktop remoto che indica: *non è possibile verificare l'identità del computer remoto.  Si vuole connettersi comunque?*  Selezionare **Sì**.

1. La connessione alla VM è stata ora stabilita. In questo caso, è stato possibile connettersi alla VM perché la regola del traffico in ingresso creata consente il traffico in ingresso alla VM tramite RDP.  Dopo alcuni secondi nella schermata iniziale è possibile che venga visualizzata una finestra in Scegliere le impostazioni di privacy per il dispositivo, selezionare **Accetta**.  Se viene visualizzata la finestra Reti, selezionare **No**.

1. Con la macchina virtuale nella sessione RDP in esecuzione, testare la connettività in uscita a Internet dalla macchina virtuale.
    1. Nella macchina virtuale aperta selezionare **Microsoft Edge** per aprire il browser.  Trattandosi della prima volta che si apre Microsoft Edge, è possibile che venga visualizzata una finestra popup. Selezionare **Avvia senza dati**, selezionare **Continua senza dati** e quindi selezionare **Conferma e avvia l'esplorazione**.
    1. Immettere **www.bing.com** nella barra degli indirizzi del browser e verificare di riuscire a connettersi al motore di ricerca.
    1. Dopo aver confermato che è possibile accedere a www.bing.com, chiudere la finestra del browser nella macchina virtuale, ma lasciare la macchina virtuale attiva.

1. Ridurre al minimo la macchina virtuale selezionando il carattere di sottolineatura **_** nella scheda blu che mostra l'indirizzo IP della macchina virtuale. Verrà visualizzata nuovamente la pagina SC900-WinVM \| Connetti.

1. Mantenere aperta la scheda del browser; verrà usata l'attività successiva.

### Attività 4

Nell'attività precedente è stata confermata la possibilità di stabilire una connessione RDP alla macchina virtuale. Una volta nella macchina virtuale è stato confermato anche che è possibile stabilire una connessione in uscita a Internet.  Il traffico Internet in uscita è stato consentito perché le regole predefinite in uscita per il gruppo di sicurezza di rete consentono il traffico Internet in uscita.  In questa attività verrà illustrato il processo di creazione di una regola in uscita personalizzata per bloccare il traffico Internet in uscita e testare tale regola.

1. Dovrebbe trovarsi nella pagina SC900-WinVM \| Connetti. Dal riquadro di spostamento sinistro selezionare **Rete**. Se in precedenza è stata chiusa la scheda del browser, selezionare la barra di ricerca blu nella parte superiore della pagina e selezionare Macchine virtuali, quindi selezionare la macchina virtuale **SC900-WinVM** e quindi selezionare **Rete**.

1. Selezionare la scheda **Regole porta in uscita**. Verranno visualizzate le regole in uscita predefinite.  Notare la regola predefinita "AllowInternetOutBound". Questa regola consente tutto il traffico Internet in uscita. Non è possibile rimuovere la regola predefinita, ma è possibile sostituirla creando una regola con priorità più alta. Dal lato destro della pagina, selezionare **Aggiungi regola porta in uscita**.

1. Nella pagina Aggiungi regola porta in uscita, specificare le seguenti impostazioni:
    1. Origine:  **Qualsiasi**
    1. Intervalli di porte di origine: **\***
    1. Destinazione:  **Tag del servizio**
    1. Tag del servizio di destinazione:  **Internet**
    1. Servizio:  **Personalizzato** (lasciare l'impostazione predefinita)
    1. Intervalli di porte di destinazione:  **\*** (assicurarsi di inserire un asterisco nel campo intervalli di porte di destinazione)
    1. Protocollo: **Qualsiasi**
    1. Azione: **Nega**
    1. Priorità: **1000**
    1. Nome: lasciare il nome predefinito o creare un nome descrittivo personalizzato.
    1. Selezionare **Aggiungi**

1. Una volta eseguito il provisioning della regola, questa verrà visualizzata nell'elenco delle regole in uscita.  Sebbene compaia nell'elenco, occorreranno alcuni minuti perché diventi efficace (attendere alcuni minuti mentre si procede ai passaggi successivi).  


1. Tornare alla macchina virtuale (l'icona RDP per la macchina virtuale deve essere visualizzata sulla barra delle applicazioni nella parte inferiore della pagina).

1. Aprire il browser Edge nella propria macchina virtuale e immettere **www.bing.com**. La pagina non dovrebbe essere visualizzata. Se si è in grado di connettersi a Internet e si è verificato che tutti i parametri per la regola in uscita sono stati impostati correttamente, è probabile che siano necessari alcuni minuti per rendere effettiva la regola.  Chiudere il browser, attendere alcuni minuti e riprovare. Le sottoscrizioni di Azure nell'ambiente lab possono riscontrare ritardi più lunghi dei normali.


1. Chiudere la connessione al desktop remoto selezionando la **X** in alto al centro della pagina dove viene mostrato l'indirizzo IP.  Viene visualizzata una finestra popup che indica che la sessione remota verrà disconnessa. Selezionare **OK**.

1. Nell'angolo superiore sinistro della finestra, appena sotto la barra blu in cui è indicato Microsoft Azure, selezionare **Home** per tornare alla home page dei servizi di Azure.

1. Mantenere aperta la scheda Azure nel browser.

### Verifica

In questo lab è stato illustrato il processo di configurazione di un gruppo di sicurezza di rete (NSG), associandolo all'interfaccia di rete di una macchina virtuale e aggiungendo nuove regole al gruppo di sicurezza di rete per consentire il traffico RDP in ingresso e bloccare il traffico Internet in uscita.
