---
ms.openlocfilehash: d2377516343cb85c279c1a2d6347c59f573d73c7
ms.sourcegitcommit: 15658ca1c7bae8a4dbaa33ab6f897070bde521b9
ms.translationtype: HT
ms.contentlocale: it-IT
ms.lasthandoff: 09/12/2022
ms.locfileid: "147892198"
---
<a name="---"></a><!---
---
Lab: Titolo: 'Esplorare i gruppi di sicurezza di rete di Azure (NSG)' Percorso di apprendimento/Modulo/Unità: 'Percorso di apprendimento: Descrivere le funzionalità delle soluzioni di sicurezza Microsoft; Modulo 1: Descrivere le funzionalità di sicurezza di base in Azure; Unità 6: Descrivere i gruppi di sicurezza di rete di Azure'
---
--->

# <a name="lab-explore-azure-network-security-groups-nsgs"></a>Laboratorio: Esplorazione dei gruppi di sicurezza di rete di Azure (NSG)

Questo lab corrisponde al contenuto di Learn seguente:

- Percorso di apprendimento: Descrivere le funzionalità delle soluzioni di sicurezza Microsoft
- Modulo: Descrivere le funzionalità di sicurezza di base in Azure
- Unità: Descrivere i gruppi di sicurezza di rete di Azure

## <a name="lab-scenario"></a>Scenario del lab

In questo lab, si esplorerà la funzione dei Gruppi di sicurezza di rete in Azure.  Questo avverrà attraverso la creazione della macchina virtuale (VM) senza alcun gruppo di sicurezza di rete. Si seguirà quindi il processo di creazione di un NSG e di assegnazione dell'interfaccia della VM a quel NSG.  Dopo la configurazione, si osserveranno le regole predefinite in ingresso e in uscita e si creeranno nuove regole.
  
**Tempo stimato**: 15-20 minuti

### <a name="task-1"></a>Attività 1

In questa attività verrà creata una macchina virtuale di Windows 10.

1. Aprire Microsoft Edge.  Nella barra degli indirizzi immettere **portal.azure.com**.

1. Accedere con le credenziali di amministratore.
    1. Nella finestra Accedi immettere **admin@WWLxZZZZZZ.onmicrosoft.com** (dove ZZZZZZ è l'ID tenant univoco fornito dal proprio provider di hosting del lab) e quindi selezionare **Avanti**.

    1. Immettere la password di amministratore, che dovrebbe essere fornita dal proprio provider di hosting del lab. Fare clic su **Accedi**.
    1. Quando compare la domanda se rimanere connessi, selezionare **Sì**.
1. Nell'angolo in alto a sinistra della schermata, accanto alla dicitura Microsoft Azure, selezionare l'icona Mostra menu Portale (le tre linee orizzontali, chiamata anche icona hamburger), quindi selezionare **Tutti i servizi**.  
1. Nella finestra principale, sotto In primo piano, selezionare Macchine virtuali.  Se non vi sono macchine virtuali elencate, immetterla nella barra di ricerca, quindi selezionarla dai risultati della ricerca.
1. Nella parte superiore sinistra della pagina selezionare **+Crea**, quindi selezionare **Macchina virtuale di Azure**.
1. Dalla scheda generale, compilare le seguenti informazioni (per eventuali voci non elencate, lasciare le impostazioni predefinite):
    1. Sottoscrizione: verificare che l'impostazione predefinita sia Azure Pass – Sponsorizzazione.

    1. Gruppo di risorse: selezionare **Crea nuovo**, quindi nel campo Nome immettere **LabsSC900-RG** e infine selezionare **OK**.
    1. Nome macchine virtuali: immettere **SC900-WinVM**.
    1. Area: se questo campo non è precompilato, selezionare l'area più vicina alla propria posizione.
    1. Immagine: selezionare **Windows 10 Pro, Versione 21H2 – Gen 2** nell'elenco a discesa.
    1. Dimensioni: selezionare **vedi tutte le dimensioni** nell'elenco a discesa e selezionare **B2s**, quindi fare clic su **Seleziona** nella parte inferiore della pagina.
    1. Nome utente:  immettere il nome utente desiderato.  Prenderne nota, perché sarà necessario per accedere alla macchina virtuale.
    1. Password:  immettere una password di propria scelta.  Prenderne nota, perché sarà necessario per accedere alla macchina virtuale.
    1. Porte in ingresso pubbliche: lasciare l'impostazione predefinita **Consenti porte selezionate**.
    1. Selezionare le porte in ingresso: lasciare l'impostazione predefinita **RDP 3389**.
    1. Licenze: selezionare **I confirm I have an eligible Windows 10 license with multi-tenant hosting rights** (Confermo di avere una licenza idonea di Windows 10 con diritti di hosting multi-tenant), in modo che nella casella compaia un segno di spunta.
    1. Selezionare **Avanti: Dischi**.
1. Ora ci si trova nella scheda Dischi per la configurazione della macchina virtuale  Lasciare tutte le impostazioni sul valore predefinito, quindi selezionare **Avanti: Rete >** .
1. Ora ci si trova nella scheda Rete per la configurazione della macchina virtuale.  Per l'opzione Gruppo di sicurezza di rete della scheda di interfaccia di rete selezionare **Nessuno**. Lasciare il valore predefinito per tutte le altre impostazioni.  Nota: lo scopo della selezione di Nessuno in questo passaggio è quello di seguire i passaggi per la creazione di un gruppo di sicurezza di rete da zero nell'attività successiva.
1. Nella parte inferiore della pagina selezionare **Avanti: Rivedi e crea>** quindi, dopo aver superato la convalida, selezionare **Crea**. Il completamento della distribuzione della macchina virtuale può richiedere diversi minuti.
1. Una volta completata la distribuzione della VM, selezionare **Vai alla risorsa**.
1. Ora ci si trova nella pagina SC900-WinVM.
1. Dalla parte superiore della pagina selezionare **Connetti**, quindi selezionare **RDP** dall'elenco a discesa.
1. Si noti che il prerequisito della porta non è soddisfatto.  Per soddisfare il prerequisito, è necessario configurare una regola di sicurezza di rete in ingresso con la porta di destinazione 3389, usata da RDP.  Questa operazione verrà eseguita nell'attività successiva, quando si crea un gruppo di sicurezza di rete.
1. Lasciare aperta la scheda del browser.

### <a name="task-2"></a>Attività 2

Creare un gruppo di sicurezza di rete, assegnare l'interfaccia di rete della macchina virtuale a tale gruppo di sicurezza di rete e creare una nuova regola in ingresso per il traffico RDP.

1. Aprire la scheda SC900-WinVM – Microsoft Azure nel browser.

1. Dall'angolo in alto a sinistra della pagina, accanto alla dicitura Microsoft Azure, selezionare l'icona Mostra menu Portale (le tre linee orizzontali, chiamata anche icona hamburger), quindi selezionare **Tutti i servizi**.
1. Nella casella Filtra servizi accanto alla dicitura Tutti i servizi, immettere **Gruppi di sicurezza di rete**, quindi selezionare **Gruppi di sicurezza di rete** dai risultati (non selezionare Gruppi di sicurezza di rete (versione classica)).
1. Dalla parte superiore della pagina Gruppi di sicurezza di rete, selezionare **+ Crea**.
1. Nella scheda Generale della pagina Crea gruppo di sicurezza di rete specificare le impostazioni seguenti:
    1. Sottoscrizione:  Azure Pass – Sponsorizzazione

    1. Gruppo di risorse:  **LabsSC900**
    1. Nome:  **NSG-SC900**
    1. Area: lasciare il valore predefinito.
    1. Selezionare **Verifica + Crea**, quindi **Crea**.
1. Una volta completata la distribuzione, selezionare **Vai alla risorsa**.
1. Notare le regole in ingresso e in uscita predefinite nel NSG.  Sebbene sia stato creato il NSG e ci siano regole predefinite per filtrare il traffico, nessuna interfaccia è stata associata al NSG.
1. Dal riquadro di spostamento a sinistra nella pagina NSG-SC900, selezionare **Interfacce di rete** sotto Impostazioni.
1. Selezionare l'opzione **+ Associa** sopra la casella di ricerca.
1. Sul lato destro della pagina è presente un campo per selezionare l'interfaccia di rete da associare al gruppo di sicurezza di rete. Selezionare la freccia a discesa, quindi selezionare **sc900-winvmXXX** (XXX sarà specifico per l'interfaccia di rete della macchina virtuale), quindi selezionare **OK** nella parte inferiore della finestra.
1. Una volta effettuata l'associazione dell'interfaccia al NSG, questa verrà visualizzata nell'elenco.
1. Dal riquadro di spostamento sinistro selezionare **Regole di sicurezza in ingresso**.
1. Le regole in ingresso predefinite negano tutto il traffico in ingresso che non proviene da una rete virtuale o da un servizio di bilanciamento del carico di Azure, quindi è necessario configurare una regola per consentire il traffico RDP in ingresso (traffico sulla porta 3389). Tenere presente che non è possibile rimuovere le regole predefinite, ma è possibile sostituirle creando regole con priorità più alte.
1. Nella parte superiore della pagina selezionare **Aggiungi**:
1. Nella finestra Aggiungi regola di sicurezza in ingresso specificare le impostazioni seguenti:
    1. Origine:  **Qualsiasi**

    1. Intervalli di porte di origine: **\***
    1. Destinazione:  **Qualsiasi**
    1. Servizio:  **RDP**
    1. Azione:  **Consenti**
    1. Priorità:  **300**; Nota: le regole con i numeri più bassi hanno una priorità più alta e vengono elaborate per prime.
    1. Nome:  **AllowRDP**
1. Selezionare **Aggiungi**
1. Dopo aver effettuato il provisioning della regola, verrà visualizzata nell'elenco delle regole in ingresso (potrebbe essere necessario aggiornare la schermata).
1. Verificare ora se sia possibile connettersi alla VM tramite RDP.  Selezionare il campo di ricerca nella parte superiore della pagina, accanto a dove è indicato Microsoft Azure, per visualizzare i servizi recenti.  Selezionare **Macchine virtuali**.
1. Selezionare la macchina virtuale **SC900-WinVM**.
1. Dalla parte superiore della pagina selezionare **Connetti**, quindi selezionare **RDP** dall'elenco a discesa.
1. Verificare che l'indirizzo IP sia impostato su Indirizzo IP pubblico, lasciare il numero di porta predefinito e selezionare **Scarica file DRP**.
1. Aprire il file scaricato e selezionare **Connetti**.
1. Verrà chiesto di inserire le credenziali.  Immettere il nome utente e la password usati al momento della creazione della macchina virtuale.
1. Si apre una finestra di connessione al Desktop remoto con l'avviso "The identity of the remote computer cannot be verified.  Do you wish to connect anyway?" (Non è possibile verificare l'identità del computer remoto. Connettersi comunque?)  Selezionare **Sì**.
1. Ora la connessione alla VM è stata stabilita. In questo caso, è stato possibile connettersi alla VM perché la regola del traffico in ingresso creata consente il traffico in ingresso alla VM tramite RDP.
1. Tenere aperta la VM, poiché verrà usata nell'attività successiva.

### <a name="task-3"></a>Attività 3

Le regola in uscita predefinite per il gruppo di sicurezza di rete consentono il traffico Internet in uscita, quindi si confermerà la possibilità di connettersi a Internet.  Quindi si seguirà il processo di creazione di una regola in uscita personalizzata per bloccare il traffico Internet in uscita e si testerà quella regola.

1. Dalla VM, selezionare **Edge** per aprire il browser.  
1. Immettere **www.bing.com** nella barra degli indirizzi del browser e confermare di riuscire a connettersi al motore di ricerca.
1. Chiudere il browser nella propria VM, ma lasciare la VM aperta poiché verrà usata nei passaggi successivi.
1. Tornare al portale di Azure, aprire la scheda SC900-WinVM – Microsoft Azure nel browser.
1. Dal riquadro di spostamento sinistro, in Impostazioni selezionare **Rete**.
1. Selezionare la scheda **Regole porta in uscita**.  Verranno visualizzate le regole in uscita predefinite.  Notare la regola predefinita "AllowInternetOutBound". Questa regola consente tutto il traffico Internet in uscita. Non è possibile rimuovere la regola predefinita, ma è possibile sostituirla creando una regola con priorità più alta. Dal lato destro della pagina, selezionare **Aggiungi regola porta in uscita**.
1. Nella pagina Aggiungi regola porta in uscita, specificare le seguenti impostazioni:
    1. Origine:  **Qualsiasi**

    1. Intervalli di porte di origine: **\***
    1. Destinazione:  **Tag del servizio**
    1. Tag del servizio di destinazione:  **Internet**
    1. Servizio:  **Personalizzato** (lasciare l'impostazione predefinita)
    1. Intervalli di porte di destinazione: * (assicurarsi di inserire un asterisco nel campo degli intervalli di porte di destinazione)
    1. Protocollo: **Qualsiasi**
    1. Azione: **Nega**
    1. Priorità:  **4000**
    1. Nome:  **DenyInternet**
1. Selezionare **Aggiungi**
1. Una volta eseguito il provisioning della regola, questa verrà visualizzata nell'elenco delle regole in uscita.  Sebbene compaia nell'elenco, occorreranno alcuni minuti perché diventi efficace (attendere alcuni minuti mentre si procede ai passaggi successivi).  
1. Tornare alla propria VM.
1. Aprire il browser Edge nella propria macchina virtuale e immettere **www.bing.com**. La pagina non dovrebbe essere visualizzata.  Nota: se si riesce a connettersi a Internet e si è verificata la corretta impostazione di tutti i parametri della regola in uscita, è possibile che ciò avvenga perché la regola impiega alcuni minuti per diventare efficace.  Chiudere il browser, attendere alcuni minuti e riprovare.
1. Chiudere la connessione al desktop remoto selezionando la **X** in alto al centro della pagina dove viene mostrato l'indirizzo IP.  Una finestra pop-up indicherà "La sessione remota verrà disconnessa". Selezionare **OK**.
1. In questa attività si è configurata una regola in uscita nel gruppo di sicurezza di rete per bloccare il traffico Internet in uscita.

### <a name="tear-down"></a>Eliminazione

La macchina virtuale è una risorsa fatturabile e, anche se il costo di esecuzione delle macchine virtuali in questa demo è minimo, è consigliabile eliminare il gruppo di risorse contenente la macchina virtuale e le risorse associate alla fine del corso.

1. Aprire la scheda SC900-WinVM – Microsoft Azure nel browser.

1. Dall'angolo superiore sinistro della pagina, selezionare **Tutti i servizi**.
1. Nella casella Filtra servizi accanto alla dicitura Tutti i servizi, immettere **Gruppi di risorse**, quindi dai risultati selezionare **Gruppi di risorse**.
1. Selezionare **LabsSC900**.
1. Dalla parte superiore centrale della pagina LabsSC900, selezionare **Elimina gruppo di risorse**.
1. Nella finestra che si apre, immettere il nome del gruppo di risorse, **LabsSC900**, per confermare l'eliminazione del gruppo di risorse e di tutte le relative risorse, quindi selezionare **Elimina** in fondo alla pagina.
1. L'eliminazione di tutte le risorse e del gruppo di risorse può richiedere alcuni minuti.
1. Chiudere tutte le schede del browser aperte.

### <a name="review"></a>Verifica

In questo lab è stato illustrato il processo di configurazione di un gruppo di sicurezza di rete (NSG), associando il gruppo di sicurezza di rete all'interfaccia di rete di una macchina virtuale e aggiungendo nuove regole al gruppo di sicurezza di rete per consentire il traffico RDP in ingresso e bloccare il traffico Internet in uscita.
