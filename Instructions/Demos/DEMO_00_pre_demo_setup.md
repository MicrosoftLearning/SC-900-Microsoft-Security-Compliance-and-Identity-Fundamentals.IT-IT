<!---
---
Configurazione pre-demo: Titolo: 'Configurazione della demo'
---
--->

## Tenant WWL: condizioni per l'utilizzo
Se, nell'ambito di una consegna di un corso con istruttore, viene fornito un tenant, tenere presente che il tenant viene messo a disposizione per supportare i lab pratici di tale corso.

I tenant non devono essere condivisi o usati per scopi diversi dai lab pratici. Il tenant utilizzato in questo corso è un tenant di valutazione e non può essere utilizzato o reso accessibile dopo il termine della lezione e non è idoneo per l'estensione.

I tenant non devono essere convertiti in un abbonamento a pagamento. I tenant ottenuti nell'ambito di questo corso rimangono di proprietà di Microsoft Corporation, che si riserva il diritto di accedervi e di recuperarli in qualsiasi momento.

## Configurazione pre-demo del tenant Microsoft 365

### Abilitare log di controllo di Microsoft 365

In questa attività di configurazione si abiliterà la funzionalità Log di controllo in Microsoft 365.  Sebbene la documentazione indichi che il log di controllo è attivato per impostazione predefinita, questa funzionalità non è abilitata per la maggior parte dei tenant dei lab e la sua attivazione potrebbe richiedere parecchie ore.  È vantaggioso abilitare questa funzionalità, poiché Microsoft 365 usa i log di controllo per informazioni dettagliate e attività degli utenti identificate nei criteri e nelle informazioni dettagliate di analisi.

1. Aprire Microsoft Edge. Nella barra degli indirizzi immettere **https://admin.microsoft.com**.

1. Accedere con le credenziali di amministrazione del tenant Microsoft 365 fornite dall'ALH (provider di servizi di hosting per i lab autorizzato).

1. Dal riquadro di spostamento a sinistra dell'interfaccia di amministrazione di Microsoft 365, selezionare **Mostra tutto**.

1. In Interfacce di amministrazione selezionare **Conformità**.  Si apre una nuova pagina del browser alla pagina di benvenuto del portale di conformità di Microsoft Purview.  

1. Dal riquadro di spostamento sinistro del portale di conformità di Microsoft Purview selezionare **Mostra tutto**.

1. Nel riquadro di spostamento a sinistra, sotto Soluzioni, selezionare **Controllo**.  Nota: la funzionalità di controllo è accessibile anche tramite la home page di Microsoft 365 Defender.

1. Verificare che la scheda **Ricerca** sia selezionata (sottolineata).

1. Una volta visualizzata la pagina Controllo, attendere 2-3 minuti.  Se il controllo NON è abilitato, verrà visualizzata una barra blu nella parte superiore della pagina con l'indicazione di avviare la registrazione delle attività di utenti e amministratori.  Selezionare **Avvia la registrazione delle attività di utenti e amministratori**.  Una volta abilitato il controllo, la barra blu scompare.  Se la barra blu non è presente, il controllo è già abilitato e non sono richieste ulteriori azioni.

1. Tornare alla home page del portale di conformità di Microsoft Purview selezionando **Home** dal riquadro di spostamento sinistro.

### Monitoraggio file di Microsoft Defender for Cloud Apps

In questa attività di configurazione, sarà abilitato il monitoraggio dei file in Microsoft Defender for Cloud Apps.

1. Aprire la scheda del browser con l'interfaccia di amministrazione di Microsoft 365.  Se è stata chiusa in precedenza, aprire una nuova scheda del browser, nella barra degli indirizzi digitare **https://admin.microsoft.com** e dal riquadro di spostamento a sinistra dell'interfaccia di amministrazione di Microsoft 365 selezionare **Mostra tutto**.

1. In Interfacce di amministrazione selezionare **Sicurezza**.  Viene visualizzata una nuova pagina del browser con la pagina di benvenuto del portale Microsoft 365 Defender.  

1. Nel riquadro di spostamento a sinistra, selezionare **File**, elencato tra le app cloud.

1. Se non già abilitato, è necessario selezionare **Abilita il monitoraggio dei file** e la casella accanto alla dicitura **Abilita il monitoraggio dei file**, quindi selezionare **Salva**.  

1. Nel riquadro di spostamento a sinistra, sotto app cloud, selezionare **File** per tornare alla pagina dei file.  Se il monitoraggio dei file è stato attivato correttamente, le opzioni di filtro dovrebbero essere visualizzate nella parte superiore della pagina.  La visualizzazione dei file del tenant del lab preconfigurato potrebbe richiedere un determinato periodo di tempo.

## Configurazione pre-demo della sottoscrizione di Azure Cloud Slice

Per questa configurazione viene utilizzato l'ambiente Azure Cloud Slice, che è separato dal tenant Microsoft 365 fornito. Disconnettersi dal tenant di Microsoft 365 ed effettuare l'accesso utilizzando le credenziali di Azure Cloud Slice.

### Macchina virtuale di Azure

Verificare che la macchina virtuale sia già stata creata. In caso contrario, configurarla ora. La macchina virtuale verrà utilizzata come parte della demo NSG.

1. Aprire Microsoft Edge.  Nella barra degli indirizzi, inserire **https://portal.azure.com** e accedere con le credenziali di Azure fornite dal provider di servizi di hosting per i lab autorizzato (ALH).  In questo modo si verrà indirizzati alla home page dei servizi di Azure.

1. Nella casella di ricerca di colore blu nella parte superiore della pagina, immettere **Macchine virtuali** e selezionare **Macchine virtuali** dai risultati di ricerca.

1. Se una macchina virtuale è già presente nell'elenco, saltare i passaggi successivi, altrimenti sarà necessario crearne una.  Selezionare **Crea**, quindi, dal menu a discesa, selezionare **Macchina virtuale di Azure**. Configurare i seguenti parametri (se un parametro non è elencato, lasciare il valore predefinito).
    1. Gruppo di risorse: selezionare **Crea nuovo** e immettere **LabsSC900**, quindi selezionare **OK**.
    1. Nome macchina virtuale: immettere **SC900-WinVM**.
    1. Opzioni di disponibilità: nell'elenco a discesa, selezionare **La ridondanza dell'infrastruttura non è richiesta**.
    1. Immagine: nell'elenco a discesa, selezionare **Windows 11 Pro, versione 22H2 - x64 Gen2** (o qualsiasi immagine di Windows 10 o Window 11 elencata).
    1. Dimensione: selezionare **Visualizza tutte le dimensioni** e selezionare **Standard_B1s**, quindi selezionare **Seleziona** nella parte inferiore della pagina.
    1. Nome utente: immettere **SC900-VM-User**
    1. Password: immettere una password e annotarla, sarà necessaria in seguito.
    1. Confermare la password: inserire nuovamente la password.
    1. Porte in ingresso pubbliche: **nessuna**.
    1. Licenze: selezionare la voce "Confermo di possedere una licenza di Windows 10/11 con diritti di hosting multi-tenant".  Verrà visualizzato un segno di spunta.
    1. Selezionare **Avanti: dischi**.
    1. Tipo di disco del sistema operativo: dal menu a discesa, selezionare **SSD standard**.
    1. Selezionare **Avanti: rete**
    1. Gruppo di sicurezza di rete della scheda di interfaccia di rete: selezionare **Nessuno**.  Verrà creato un NSG come parte della demo, quindi non crearlo qui!
    1. Eliminare l'IP pubblico e NIC durate l'eliminazione della macchina virtuale: selezionare la casella in modo che venga visualizzato un segno di spunta.
    1. Selezionare **Rivedi e crea**, quindi, una volta completata la convalida, selezionare **Crea**.
    1. Quando la la distribuzione della macchina virtuale è stata completata, selezionare **Home** nella parte superiore della pagina.

1. Mantenere aperta la scheda del browser di Azure per continuare con l'impostazione pre-demo.

### Gruppo di sicurezza di rete

Verificare se è già stato creato un NSG. Se l'NSG non è ancora stato creato, è necessario configurarlo ora, ma senza associarvi alcuna interfaccia e senza creare alcuna regola. Questi passaggi saranno eseguiti nell'ambito della demo di NSG.

1. Nella barra di ricerca blu nella parte superiore della pagina immettere **Gruppi di sicurezza di rete**. Nei risultati selezionare **Gruppi di sicurezza di rete** (non selezionare Gruppi di sicurezza di rete classici).

1. Selezionare **Crea gruppo di sicurezza di rete**. Nella scheda Informazioni di base della pagina Crea gruppo di sicurezza di rete, specificare le impostazioni seguenti:
    1. Sottoscrizione: lasciare il valore predefinito (si tratta della sottoscrizione di Azure fornita dal provider di servizi di hosting per i lab autorizzato)
    1. Gruppo di risorse: **LabsSC900**
    1. Nome: **NSG-SC900**
    1. Area: lasciare il valore predefinito.
    1. Selezionare **Rivedi e crea** e quindi **Crea**.
    1. Una volta completata la distribuzione (che avviene molto rapidamente), selezionare **Vai alla risorsa**.

### Microsoft Defender for Cloud

L'obiettivo è semplicemente quello di accedere per la prima volta a Microsoft Defender per il cloud. È importante perché Defender per il cloud può impiegare fino a 24 ore per riflettere un punteggio di sicurezza iniziale.  

1. Aprire la scheda Home-Microsoft Azure nel browser.

1. Nella barra di ricerca blu immettere **Microsoft Defender per il cloud** e quindi nell'elenco dei risultati selezionare **Microsoft Defender per il cloud**.

1. Se questa è la prima volta che si accede a Microsoft Defender per il cloud con la propria sottoscrizione, potrebbe comparire la pagina introduttiva e potrebbe essere richiesto di eseguire l'aggiornamento.  Scorrere fino in fondo alla pagina e selezionare **Ignora**.  Verrà visualizzata la pagina Panoramica.

1. Per impostazione predefinita, tutte le sottoscrizioni dispongono di CSPM di base, che fornisce un punteggio di sicurezza, ma Defender per il cloud può impiegare fino a 24 ore per riflettere un punteggio di sicurezza iniziale.

1. Selezionare **Home** nella parte superiore della pagina.

1. Mantenere aperta la scheda del browser per continuare la configurazione pre-demo.

### Microsoft Sentinel

Verificare che sia già stata creata un'istanza di Microsoft Sentinel. In caso contrario, è necessario configurarla ora, poiché sarà necessaria nell'ambito della demo di Microsoft Sentinel.

1. Aprire la scheda Home-Microsoft Azure nel browser.

1. Nella casella di ricerca, nella barra blu nella parte superiore della pagina accanto a Microsoft Azure, immettere **Microsoft Sentinel** e quindi selezionare **Microsoft Sentinel** dai risultati della ricerca.

1. Nella pagina di Microsoft Sentinel selezionare **Crea Microsoft Sentinel**.

1. Nella pagina Aggiungi Microsoft Sentinel a un'area di lavoro selezionare **Crea una nuova area di lavoro**.

1. Nella scheda Informazioni di base dell'area di lavoro Crea Log Analytics, immettere quanto segue:
    1. Sottoscrizione: lasciare l'impostazione predefinita.
    1. Gruppo di risorse: selezionare **Crea nuovo**, quindi inserire il nome **SC900-Sentinel-RG** e selezionare **OK**.
    1. Nome: **Area di lavoro Log Analytics SC900**.
    1. Area geografica: **Stati Uniti orientali** (è possibile selezionare un'area geografica predefinita diversa in base alla posizione).
    1. Selezionare **Rivedi e crea** (non verranno configurati tag).
    1. Verificare le informazioni immesse in precedenza e quindi selezionare **Crea**.
    1. Elencare le aree di lavoro potrebbe richiedere qualche minuto. Se l'elenco non viene ancora visualizzato, selezionare **Aggiorna**, quindi selezionare **Aggiungi**.

1. Dopo aver aggiunto la nuova area di lavoro, verrà visualizzata la pagina Microsoft Sentinel | Novità e guide che indica che la versione di valutazione gratuita di Microsoft Sentinel è attivata.  Seleziona **OK**.

### Revisione

In questa configurazione è stata abilitata la funzionalità del log di controllo nel tenant di Microsoft 365 ed è stato anche verificato che una macchina virtuale è stata preconfigurata nell'ambiente Azure Cloud Slice. È stato anche preparato l'ambiente Defender per il cloud e Microsoft Sentinel.
