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

### Abilitare il log di controllo e il monitoraggio dei file di Microsoft 365

In questa attività di installazione si abiliteranno le funzionalità di monitoraggio dei log di controllo e dei file in Microsoft 365.

1. Aprire Microsoft Edge. Nella barra degli indirizzi immettere **https://admin.microsoft.com**.

1. Accedere con le credenziali di amministrazione del tenant Microsoft 365 fornite dall'ALH (provider di servizi di hosting per i lab autorizzato).

1. Dal riquadro di spostamento a sinistra dell'interfaccia di amministrazione di Microsoft 365, selezionare **Mostra tutto**.

1. In Interfacce di amministrazione selezionare **Sicurezza**.  Verrà visualizzata una nuova pagina del browser nella pagina iniziale di Microsoft Defender.  

1. Dal riquadro di spostamento sinistro del portale di conformità di Microsoft Purview selezionare **Mostra tutto**.

1. Nel pannello di spostamento sinistro scorrere verso il basso ed espandere **Sistema**.  Nell'elenco espanso selezionare **Controlla**.  Nota: la funzionalità di controllo è accessibile anche tramite il portale di Microsoft Purview.

1. Una volta atterrato nella pagina Controllo, attendere 1-2 minuti.  Se il controllo NON è abilitato, verrà visualizzata una barra blu nella parte superiore della pagina con l'indicazione di avviare la registrazione delle attività di utenti e amministratori.  Selezionare **Avvia la registrazione delle attività di utenti e amministratori**.  Una volta abilitato il controllo, la barra blu scompare.

1. Nel pannello di spostamento a sinistra, in Sistema, selezionare **Impostazioni**.

1. Nella pagina delle impostazioni selezionare **App cloud**.   Scorrere verso il basso, quindi in Information Protection selezionare **File**.

1. Se non è già abilitato, selezionare la casella accanto a dove è indicato **Abilita monitoraggio** file e quindi selezionare **Salva**.  

### Configurare il ruolo amministratore di conformità

In questa attività di configurazione, si aggiungerà se stessi, come amministratore MOD, al gruppo di ruoli Amministratore conformità.

1. Aprire una nuova scheda del browser Microsoft Edge. Nella barra degli indirizzi immettere **https://purview.microsoft.com**. Per accedere al nuovo portale di Microsoft Purview, selezionare la casella accanto alla posizione in cui è indicato, **accetto le condizioni per la divulgazione del flusso di dati e le informative** sulla privacy, quindi selezionare **Inizia**.  
1. Nel pannello di spostamento a sinistra selezionare **Impostazioni**.
1. Nel pannello di spostamento visualizzato selezionare **Ruoli e con ambito** per espandere l'opzione e quindi selezionare **Gruppi di ruoli**.
1. Nella casella di ricerca sul lato destro della schermata cercare il termine **Conformità**.  Selezionare **Amministratore** conformità.
    1. Seleziona **Modifica**
    1. Selezionare **Scegli utenti**.
    1. Cercare Amministratore MOD, selezionare la casella accanto a **Amministratore MOD** e quindi selezionare il **pulsante Seleziona** nella parte inferiore della pagina.
    1. Selezionare Avanti e quindi Salva** e infine Fine****.** ****
1. In questo modo si conclude la configurazione per il tenant di Microsoft 365, è possibile chiudere le schede del browser.

## Configurazione preliminare della sottoscrizione di Azure

Per questa configurazione si usa l'ambiente Azure separato dal tenant di Microsoft 365 fornito. Disconnettersi dal tenant di Microsoft 365 e accedere usando le credenziali di Azure.

### Macchina virtuale di Azure

Verificare che la macchina virtuale sia già stata creata. In caso contrario, configurarla ora. La macchina virtuale verrà utilizzata come parte della demo NSG.

1. Aprire Microsoft Edge.  Nella barra degli indirizzi, inserire **https://portal.azure.com** e accedere con le credenziali di Azure fornite dal provider di servizi di hosting per i lab autorizzato (ALH).  In questo modo si verrà indirizzati alla home page dei servizi di Azure.

1. Nella casella di ricerca di colore blu nella parte superiore della pagina, immettere **Macchine virtuali** e selezionare **Macchine virtuali** dai risultati di ricerca.

1. Se una macchina virtuale è già presente nell'elenco, saltare i passaggi successivi, altrimenti sarà necessario crearne una.  Selezionare **Crea**, quindi, dal menu a discesa, selezionare **Macchina virtuale di Azure**. Configurare i seguenti parametri (se un parametro non è elencato, lasciare il valore predefinito).
    1. Gruppo di risorse: selezionare **Crea nuovo** e immettere **LabsSC900**, quindi selezionare **OK**.
    1. Nome macchina virtuale: immettere **SC900-WinVM**.
    1. Opzioni di disponibilità: nell'elenco a discesa, selezionare **La ridondanza dell'infrastruttura non è richiesta**.
    1. Tipo di sicurezza: nell'elenco a discesa selezionare **Standard**.
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

Configurare un'area di lavoro Log Analytics e, una volta creata, creare un'istanza di Microsoft Sentinel e aggiungervi l'area di lavoro Log Analytics.

1. Aprire la scheda Home-Microsoft Azure nel browser.

1. Nella casella di ricerca blu nella parte superiore della pagina immettere **Log Analytics** e selezionarlo nei risultati della ricerca.
1. Seleziona **+ Crea**.
1. Nella scheda Informazioni di base dell'area di lavoro Crea Log Analytics, immettere quanto segue:
    1. Sottoscrizione: lasciare l'impostazione predefinita, ovvero la sottoscrizione di Azure fornita dal provider di servizi di hosting per i lab autorizzato.
    1. Gruppo di risorse: selezionare **SC900-Sentinel-RG**. Se questo gruppo di risorse non è elencato, crearlo selezionando **Crea nuovo**, immettere **SC900-Sentinel-RG**, quindi selezionare **OK**.
    1. Nome: **SC900-Sentinel-workspace**.
    1. Area geografica: **Stati Uniti orientali** (è possibile selezionare un'area geografica predefinita diversa in base alla posizione)
    1. Selezionare **Rivedi e crea** (non verranno configurati tag).
    1. Verificare le informazioni immesse in precedenza e quindi selezionare **Crea**.
    1. La creazione della nuova area di lavoro potrebbe richiedere un minuto o due.
    1. Dopo la creazione, selezionare Vai alla risorsa** per visualizzare **le informazioni sull'area di lavoro.
1. A questo punto, l'istanza di Microsoft Sentinel non è ancora stata creata. Per creare un'istanza di Sentinel, è necessario passare alla pagina di Microsoft Sentinel. Usare la barra di ricerca blu nella parte superiore della pagina per cercare **Microsoft Sentinel** e selezionarla nel risultato della ricerca.
1. Per aggiungere l'area di lavoro a Microsoft Sentinel, è necessario passare alla pagina di Microsoft Sentinel. Usare la barra di ricerca blu nella parte superiore della pagina per cercare **Microsoft Sentinel**
    1. Nella pagina Microsoft Sentinel selezionare **+ Crea**.
    1. È ora possibile aggiungere l'area di lavoro appena creata. Selezionare **SC900-Sentinel-workspace**, quindi selezionare **Aggiungi**.  L'attivazione della versione di valutazione gratuita di Microsoft Sentinel potrebbe richiedere alcuni minuti.  Dopo l'attivazione, selezionare **OK**.

### Revisione

In questa configurazione è stata abilitata la funzionalità del log di controllo nel tenant di Microsoft 365 e si è anche verificato che una macchina virtuale è stata preconfigurata nell'ambiente Azure. È stato anche preparato l'ambiente Defender per il cloud e Microsoft Sentinel.
