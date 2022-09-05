---
Demo:
  title: Gruppi di sicurezza di rete (NSG) di Azure
  module: 'Module 3 Lesson 1: Describe the capabilities of Microsoft security solutions: Describe basic security capabilities in Azure.'
ms.openlocfilehash: 34a08ed5a6edd845087e4ed4b5d94d4f06bc8f89
ms.sourcegitcommit: 07d6d5b9df44c747453e21a65bca524afbaf85ae
ms.translationtype: HT
ms.contentlocale: it-IT
ms.lasthandoff: 08/27/2022
ms.locfileid: "147695306"
---
# <a name="demo-azure-network-security-groups-nsgs"></a>Dimostrazione: Gruppi di sicurezza di rete (NSG) di Azure

## <a name="demo-scenario"></a>Scenario demo

Questa demo illustrerà le funzionalità di un gruppo di sicurezza di rete (NSG) in Azure.  Per farlo, verrà innanzitutto creata una macchina virtuale (VM) senza alcun NSG come parte della configurazione pre-demo. Verrà anche creato un NSG senza alcuna interfaccia o subnet associata.  Come parte della demo, verranno anche mostrare le regole in ingresso e in uscita predefinite per il NSG. Si esaminerà quindi il processo di assegnazione dell'interfaccia della VM al NSG.  Al termine della configurazione, si testerà la connessione alla VM usando le regole del NSG predefinite e anche le regole create.
  
### <a name="pre-demo-setup-part-1"></a>Configurazione pre-demo parte 1

 Si raccomanda agli istruttori di farlo **PRIMA** della lezione poiché la creazione di una VM può richiedere diversi minuti. In questa configurazione verrà creata una macchina virtuale di Windows 10.

1. Aprire la scheda **Home – Microsoft Azure** nel browser.  Se la scheda era stata chiusa in precedenza, aprire una pagina del browser e nella barra degli indirizzi inserire portal.azure.com e accedere di nuovo.

1. Nella casella di ricerca, nella barra blu nella parte superiore della pagina accanto a Microsoft Azure, inserire **Macchine virtuali** quindi selezionare **Macchine virtuali** dai risultati della ricerca.  

1. Dalla parte superiore sinistra della pagina selezionare **+Aggiungi**, quindi selezionare **+Macchina virtuale**.

1. Dalla scheda generale, compilare le seguenti informazioni (per eventuali voci non elencate, lasciare le impostazioni predefinite):
    1. **Sottoscrizione**: verificare che l'impostazione predefinita sia Azure Pass – Sponsorizzazione.
    1. **Gruppo di risorse**: selezionare **Crea nuovo** quindi nel campo Nome inserire **LabsSC900-RG**, poi selezionare **OK**.
    1. **Nome macchine virtuali**: immettere **SC900-WinVM**.
    1. **Area**: lasciare il valore predefinito.
    1. **Opzioni di disponibilità**: assicurarsi di selezionare **La ridondanza dell'infrastruttura non è richiesta**.  NOTA: è molto importante che le opzioni di disponibilità siano impostate su La ridondanza dell'infrastruttura non è richiesta, altrimenti la demo non funzionerà come previsto.  Avere un'opzione di disponibilità richiede un NSG e la macchina virtuale viene intenzionalmente creata senza un NSG.
    1. **Immagine**: selezionare **Windows 10 Pro, Versione 21H2 – Gen 2** nell'elenco a discesa.
    1. **Dimensioni**: selezionare **vedi tutte le dimensioni** nell'elenco a discesa e selezionare **B2s**, quindi fare clic su **Seleziona** nella parte inferiore della pagina.
    1. **Nome utente**:  immettere il nome utente desiderato.  Prenderne nota, perché sarà necessario per accedere alla macchina virtuale.
    1. **Password**:  immettere una password di propria scelta.  Prenderne nota, perché sarà necessario per accedere alla macchina virtuale.
    1. **Porte in ingresso pubbliche**: lasciare l'impostazione predefinita **Consenti porte selezionate**.
    1. **Selezionare le porte in ingresso**: lasciare l'impostazione predefinita **RDP 3389**
    1. **Licenze**: selezionare **I confirm I have an eligible Windows 10 license with multi-tenant hosting rights** (Confermo di avere una licenza idonea di Windows 10 con diritti di hosting multi-tenant), in modo che nella casella compaia un segno di spunta.
    1. Selezionare **Avanti: Dischi**.

1. Ora ci si trova nella scheda Dischi per la configurazione della macchina virtuale  Lasciare tutte le impostazioni sul valore predefinito, quindi selezionare **Avanti: Rete >** .
1. Ora ci si trova nella scheda Rete per la configurazione della macchina virtuale.  Per l'opzione Gruppo di sicurezza di rete della scheda di interfaccia di rete selezionare **Nessuno**. Lasciare il valore predefinito per tutte le altre impostazioni.
1. Nella parte inferiore della pagina selezionare **Avanti: Rivedi e crea>** quindi, dopo aver superato la convalida, selezionare **Crea**. Il completamento della distribuzione della macchina virtuale può richiedere diversi minuti.
1. Una volta completata la distribuzione della VM, selezionare **Vai alla risorsa**.
1. Ora ci si trova nella pagina SC900-WinVM.
1. Dalla parte superiore della pagina selezionare **Connetti**, quindi selezionare **RDP** dall'elenco a discesa.
1. Si noti che il prerequisito della porta non è soddisfatto.  Per consentire di soddisfare il prerequisito, è necessario configurare una regola di sicurezza di rete in ingresso con la porta di destinazione 3389, usata da RDP.  Questa operazione verrà eseguita nell'attività successiva, quando si crea un gruppo di sicurezza di rete.
1. Lasciare aperta la scheda del browser.


### <a name="pre-demo-setup-part-2"></a>Configurazione pre-demo parte 2

Creare un gruppo di sicurezza di rete ma NON assegnare l'interfaccia di rete della VM a quel NSG.  

1. Aprire la scheda SC900-WinVM – Microsoft Azure nel browser.

1. Nella casella di ricerca, nella barra blu nella parte superiore della pagina accanto a Microsoft Azure, inserire **gruppo di sicurezza di rete** quindi selezionare **Gruppi di sicurezza di rete** dai risultati della ricerca.  Non selezionare Gruppi di sicurezza di rete in versione classica.

1. Dalla parte superiore della pagina Gruppi di sicurezza di rete, selezionare **+ Crea**.

1. Nella scheda Generale della pagina Crea gruppo di sicurezza di rete specificare le impostazioni seguenti:
    1. Sottoscrizione:  Azure Pass – Sponsorizzazione
    1. Gruppo di risorse:  **LabsSC900-RG**
    1. Nome:  **NSG-SC900**
    1. Area: lasciare il valore predefinito
    1. Selezionare **Verifica + Crea**, quindi **Crea**.

1. Al termine della distribuzione, selezionare **Vai alla risorsa** e assicurarsi che tutte le impostazioni siano corrette.  Dovrebbero esserci 3 regole in ingresso predefinite, 3 regole in uscita predefinite e nessuna subnet e nessuna interfaccia associate al NSG.  Tornare alla pagina **Home** del portale di Azure.  

### <a name="demo"></a>Demo

Esaminare le impostazioni per un NSG.  In questo caso si esaminerà un NSG (quello creato nella configurazione precedente) che non è ancora stato assegnato a un'interfaccia della VM. Verrà quindi illustrato il processo di associazione di un'interfaccia al NSG e il processo di creazione di regole in ingresso e in uscita.

1. Aprire la scheda del browser, **Home-Microsoft Azure**.  Se la scheda era stata chiusa in precedenza, aprire una pagina del browser e nella barra degli indirizzi inserire portal.azure.com e accedere di nuovo.

1. Nella casella di ricerca, nella barra blu nella parte superiore della pagina accanto a Microsoft Azure, inserire **gruppo di sicurezza di rete** quindi selezionare **Gruppi di sicurezza di rete** dai risultati della ricerca.  Non selezionare Gruppi di sicurezza di rete in versione classica.

1. Dalla pagina del NSG, selezionare il NSG creato nella configurazione, **NSG-SC900**.

1. La scheda **Panoramica** nel riquadro di spostamento sinistro è evidenziata.  Notare le regole in ingresso e in uscita predefinite nel NSG. Sebbene sia stato creato il NSG e ci siano regole predefinite per filtrare il traffico, nessuna interfaccia è stata associata al NSG. Si può vedere nella parte in alto a destra della pagina dove dice "Associato a: 0 subnet, 0 interfacce di rete".  Affinché un NSG funzioni correttamente, deve essere assegnato a qualcosa.  In questo caso verrà assegnato all'interfaccia di rete per la VM creata precedentemente.

1. Dal riquadro di spostamento a sinistra nella pagina NSG-SC900, selezionare **Interfacce di rete** sotto Impostazioni.

1. Selezionare **+ Associa**, sopra la casella di ricerca, poi dal menu a discesa selezionare **sc900-winvmXXX** (XXX sarà specifico per l'interfaccia di rete della VM) poi selezionare **Ok**. Mentre l'interfaccia viene associata si vedrà una casella di notifica nell'angolo in alto a destra dello schermo. Una volta effettuata l'associazione dell'interfaccia al NSG, questa verrà visualizzata nell'elenco.

1. Tornare alla scheda **Panoramica**.  Notare che nella parte in alto a destra della pagina comparirà "Associato a: 0 subnet, 1 interfacce di rete"; l'interfaccia è ora assegnata al NSG. Inoltre, illustrare agli studenti le regole predefinite. In ingresso, saranno consentiti solo il traffico da altre reti virtuali Azure e Azure Load Balancer. Tutto il restante traffico in ingresso alla VM verrà negato. Richiamare inoltre le regole in uscita predefinite.  È consentito solo il traffico in uscita verso altre reti virtuali e il traffico Internet in uscita.  Come parte della demo, si raccomanda di mostrare che il traffico in uscita viene negato.
    1. Nella barra di ricerca nella parte superiore della pagina, inserire e selezionare **Macchine virtuali**.
    1. Dalla pagina Macchine virtuali, selezionare **SC900-WinVM**.
    1. Dalla parte superiore della pagina SC900-WinVM, selezionare **Connetti**, quindi selezionare **RDP**.
    1. Si noti che il prerequisito della porta non è soddisfatto.  Per consentire di soddisfare il prerequisito, è necessario configurare una regola di sicurezza di rete in ingresso con la porta di destinazione 3389, usata da RDP.  

1. Ora sarà necessario creare una nuova regola per consentire il traffico RDP in ingresso.  Ricordare che non è possibile eliminare le regole predefinite esistenti, si possono solo creare altre regole con una priorità superiore. Dal riquadro di spostamento sinistro, in Impostazioni selezionare **Rete**.  Verrà visualizzata la pagina di rete della macchina virtuale.
1. Verificare che la scheda **Regole porta in ingresso** sia selezionata (sottolineata) e quindi selezionare **Aggiungi regola porta in ingresso** per creare la regola per consentire il traffico RDP in ingresso, con le impostazioni seguenti:
    1. Origine: **Qualsiasi**
    1. Intervalli di porte di origine: **\***
    1. Destinazione: **Qualsiasi**
    1. Servizio: **RDP**
    1. Azione: **Consenti**
    1. Priorità: **300**; Nota: le regole con i numeri più bassi hanno una priorità più alta e vengono elaborate per prime. Pertanto la priorità per questa nuova regola deve essere più alta della priorità della regola esistente che nega tutto il traffico in ingresso.
    1. Nome: **AllowRDP**
    1. Selezionare **Aggiungi**
    1. Una volta eseguito il provisioning della regola, questa verrà visualizzata nell'elenco delle regole in ingresso.

1. Selezionare ora la scheda **Regole porta in uscita** ed esaminare le regole predefinite.  Selezionare **Aggiungi regola porta in uscita** nella parte superiore della pagina e illustrare le varie impostazioni.  Si raccomanda di creare la regola. Le impostazioni seguenti creano una regola per negare il traffico Internet in uscita:
    1. Origine: **Qualsiasi**
    1. Intervalli di porte di origine: **\***
    1. Destinazione: **Tag del servizio**
    1. Tag del servizio di destinazione: **Internet**
    1. Servizio: **Personalizzato** (lasciare l'impostazione predefinita)
    1. Intervalli di porte di destinazione: **\*** (assicurarsi di inserire un asterisco nel campo degli intervalli di porte di destinazione).
    1. Protocollo: **Qualsiasi**
    1. Azione: **Nega**
    1. Priorità: **4000** (il punto da sottolineare è che la priorità deve essere superiore a quella della regola esistente che permette il traffico Internet in uscita)
    1. Nome: **DenyInternet**
    1. Selezionare **Aggiungi**
    1. Una volta eseguito il provisioning della regola, questa verrà visualizzata nell'elenco delle regole in uscita.

1. Tornare ora alla VM e testare le regole.  Nella parte superiore della pagina selezionare **SC900-VM**.

1. Testare la regola in ingresso verificando che è possibile connettersi alla VM tramite RDP.
    1. Selezionare **Connetti** nel riquadro di spostamento a sinistra.
    1. Verificare che l'indirizzo IP sia impostato su Indirizzo IP pubblico, lasciare il numero di porta predefinito e selezionare **Scarica file DRP**.
    1. **Aprire** il file scaricato e selezionare **Connetti**.
    1. Verrà chiesto di inserire le credenziali. Immettere il nome utente e la password usati al momento della creazione della macchina virtuale.  Se la finestra di richiesta di inserimento delle credenziali richiede un PIN, selezionare **Altre opzioni**, quindi selezionare **Usa un altro account**.
    1. Si apre una finestra di connessione al Desktop remoto con l'avviso "The identity of the remote computer cannot be verified. Do you wish to connect anyway?" (Non è possibile verificare l'identità del computer remoto. Connettersi comunque?) Selezionare **Sì**.
    1. Ora la connessione alla VM è stata stabilita. Sottolineare allo studente che in questo caso è stato possibile connettersi alla macchina virtuale perché la regola del traffico in ingresso creata consente il traffico in ingresso alla macchina virtuale tramite RDP.

1. Ora testare la regola del NSG in uscita
    1. Aprire il browser Edge nella VM.
    1. Immettere **www.bing.com**. La pagina non dovrebbe essere visualizzata. Nota: se si riesce a connettersi a Internet e si è verificata la corretta impostazione di tutti i parametri della regola in uscita, è possibile che ciò avvenga perché la regola impiega alcuni minuti per diventare efficace. Attendere alcuni minuti e riprovare.

1. Chiudere la connessione al desktop remoto selezionando la **X** in alto al centro della pagina dove viene mostrato l'indirizzo IP. Una finestra pop-up indicherà "La sessione remota verrà disconnessa". Selezionare **OK**.

1. Tornare alla Home page del portale Azure selezionando **Microsoft Azure** sulla barra blu sulla parte superiore della pagina.

### <a name="post-course-delivery-tear-down"></a>Cancellare i dati alla fine del corso

La macchina virtuale è una risorsa fatturabile e, anche se il costo di esecuzione delle macchine virtuali in questa demo è minimo, è consigliabile eliminare il gruppo di risorse contenente la macchina virtuale e le risorse associate alla fine del corso.

1. Aprire la scheda SC900-WinVM – Microsoft Azure nel browser.

1. Dall'angolo superiore sinistro della pagina, selezionare **Tutti i servizi**.

1. Nella casella Filtra servizi accanto alla dicitura Tutti i servizi, immettere **Gruppi di risorse**, quindi dai risultati selezionare **Gruppi di risorse**.

1. Selezionare **LabsSC900-RG**.

1. Dalla parte centrale superiore della pagina LabsSC900-RG, selezionare **Elimina gruppo di risorse**.

1. Nella finestra che si apre, inserire il nome del gruppo di risorse, **LabsSC900-RG**, per confermare l'eliminazione del gruppo di risorse e di tutte le sue risorse, quindi selezionare **Elimina** dal fondo della pagina.

1. L'eliminazione di tutte le risorse e del gruppo di risorse può richiedere alcuni minuti.

#### <a name="review"></a>Verifica

Questa demo ha illustrato le informazioni e le impostazioni associate a un NSG, incluso il processo di associazione di un'interfaccia al NSG, ha illustrato e regole in ingresso e in uscita predefinite e infine i passaggi per creare una nuova regola.
