---
lab:
  title: 'Esplorare Criteri di Azure'
  module: 'Modulo 6: Descrivere le funzionalità di governance delle risorse in Azure'
---


# <a name="lab-explore-azure-policy"></a>Laboratorio: Esplorare Criteri di Azure

Questo lab corrisponde al contenuto di Learn seguente:

- Percorso di apprendimento: Descrivere le funzionalità di conformità Microsoft
- Modulo: Descrivere le funzionalità di governance delle risorse in Azure
- Unità: Descrivere Criteri di Azure

## <a name="lab-scenario"></a>Scenario del lab

Criteri di Azure è un servizio che consente di applicare gli standard aziendali e di valutare la conformità su larga scala. Criteri di Azure valuta le risorse in Azure confrontando le proprietà di tali risorse con le regole business. In questo lab si creerà un criterio e si vedrà l'impatto di tale criterio.  Verranno anche esaminate le informazioni sulla conformità e la correzione disponibili nella pagina dei criteri.

**Tempo stimato**: 15-20 minuti

### <a name="task-1"></a>Attività 1

In questa attività verrà creata un'assegnazione di criteri di base per richiedere un tag per un gruppo di risorse.
1.  Aprire Microsoft Edge. Nella barra degli indirizzi immettere **portal.azure.com**.

1. Accedere con le credenziali di amministratore per la sottoscrizione di Azure. Queste credenziali di amministratore sono diverse dalle credenziali di amministratore di Microsoft 365.
    1. Nella finestra Accedi immettere **User1-XXXXXXXX@LODSPRODMSLEARNMCA.onmicrosoft.com** (dove XXXXXXXX è l'ID tenant univoco fornito dal proprio provider di hosting del lab) e quindi selezionare **Avanti**.

    1. Immettere la password di amministratore fornita dal proprio provider di hosting del lab. Fare clic su **Accedi**.
    1. Se viene richiesto se si desidera rimanere connessi, selezionare **Sì**.

1. Ci si trova ora nel portale di Azure.  Nella casella di ricerca, nella barra blu nella parte superiore della pagina accanto a Microsoft Azure, inserire **criteri**, quindi selezionare **Criteri** dai risultati della ricerca. Viene aperta la home page Criteri con una visualizzazione del dashboard.  L'ambito della visualizzazione Dashboard è la sottoscrizione di Azure fornita dal provider di servizi di hosting per i lab autorizzato. Verrà visualizzato un criterio creato dal provider di servizi di hosting per i lab autorizzato, per l'uso della sottoscrizione di Azure.

1. Dal riquadro di spostamento sinistro, sotto Creazione, selezionare **Assegnazioni**.

1. Dalla parte superiore della pagina selezionare **Assegna criterio**. Si apre la procedura guidata di assegnazione dei criteri per guidare l'amministratore nel processo di assegnazione di un criterio.

1. Si inizia nella scheda Generale.
    1. Per Ambito lasciare l'impostazione predefinita. In questo caso, l'ambito dei criteri è la sottoscrizione di Azure fornita dal provider di servizi di hosting per i lab autorizzato.
    1. In Definizione criteri selezionare i **puntini di sospensione**.  Viene fornito un elenco delle definizioni dei criteri disponibili.  Nella barra di ricerca immettere **Richiedi un tag**. Nei risultati della ricerca selezionare **Richiedi un tag nel gruppo di risorse** (potrebbe essere necessario scorrere verso il basso), quindi premere **Aggiungi**.  Nota: l'effetto di questo criterio è negare la creazione di qualunque gruppo di risorse che non soddisfa il requisito.  
    1. Si noti il nome di assegnazione predefinito.  Mantenere il nome così com'è.
    1. Assicurarsi che l'applicazione dei criteri sia **impostata su Abilitato**

1. Selezionare Avanti, quindi selezionare **Di** nuovo **avanti** per passare alla scheda Parametri (è anche possibile selezionare direttamente la scheda parametri).

1. Si è ora nella scheda Parametri. Nel campo Nome tag immettere **Ambiente** e quindi selezionare **Avanti**.

1. Nella scheda Correzione non modificare le impostazioni predefinite e quindi selezionare **Avanti**.

1. Si è ora nella scheda Messaggi di non conformità. Nel campo Messaggio di non conformità immettere **È obbligatorio un tag di ambiente** e quindi selezionare **Avanti**. Nota: questo messaggio apparirà come motivo di non conformità per i gruppi di risorse che sono stati creati prima dell'assegnazione del criterio e non hanno un tag Ambiente.

1. Rivedere l'assegnazione dei criteri e quindi selezionare **Crea**.  Se non si vede immediatamente il criterio, selezionare **Aggiorna**. Nota: l'applicazione dei criteri potrebbe richiedere fino a 30 minuti, ma in genere avviene più rapidamente.

1. Uscire dalla pagina di assegnazione dei criteri selezionando la **X** nell'angolo in alto a destra dello schermo.

1. Ora ci si trova nella home page dei servizi di Azure.  Tenere questa pagina aperta, servirà per l'attività successiva.

### <a name="task-2"></a>Attività 2

In questa attività si vedrà l'impatto dell'assegnazione dei criteri di Azure tentando di creare un gruppo di risorse in Azure senza un tag.

1. Nel browser, aprire la scheda Home – Microsoft Azure.

1. In alto sulla pagina, sotto la dicitura Servizi di Azure, selezionare **Gruppi di risorse**.

1. Dall'angolo superiore sinistro della pagina, selezionare **+ Crea**.

1. Nella scheda Generale di Crea un gruppo di risorse lasciare il campo Sottoscrizione così come è.

1. Nel campo Gruppo di risorse immettere **SC900-Labs**.

1. Lasciare l'impostazione Area geografica sul valore predefinito e quindi selezionare **Avanti: Tag**.

1. Lasciare vuoto il campo Nome e Valore del tag.  NON POPOLARE, quindi selezionare **Verifica + Crea**.

1. Verrà visualizzato un messaggio di convalida riuscita (il nome e il valore del tag non sono campi obbligatori nella procedura guidata), quindi selezionare **Crea**.

1. Verrà visualizzato un messaggio di errore nella parte superiore dello schermo, "Non è stato possibile creare il gruppo di risorse". Selezionare **Visualizza dettagli errore**. La condizione che fa parte dei criteri di Azure non è stata soddisfatta, quindi la creazione del gruppo di risorse è stata bloccata per non conformità. Nota: se non viene visualizzato il messaggio di errore e il gruppo di risorse viene creato, significa che l'applicazione del criterio non è ancora avvenuta.  Passare alla pagina Criteri per i criteri creati nell'attività precedente e quando i criteri diventano effettivi si vedrà che la risorsa non è conforme.  La pagina dei dettagli includerà il messaggio di non conformità.

1. Il riepilogo dell'errore mostra il seguente tipo di errore, "La risorsa 'SC900-Labs' non è consentita dal criterio".  Chiudere questa finestra selezionando la **X** nell'angolo in alto a sinistra dello schermo.

1. Nella finestra Crea un gruppo di risorse selezionare **Precedente**.

1. Si ritorna alla pagina Tag per la creazione di un gruppo di risorse.  Nel campo Nome immettere Ambiente e nel campo Valore immettere **SC900-Labs**, quindi selezionare **Avanti: Rivedi e crea >** .

1. Verificare il tag e selezionare **Crea**.

1. Nel campo Nome immettere **Ambiente** e nel campo Valore immettere **Lab** (questo valore potrebbe essere qualsiasi cosa, il criterio richiede semplicemente un valore di tag), quindi selezionare **Avanti: Rivedi e crea >** e infine selezionare **Crea**.

1. Verrà elencato il gruppo di risorse.  

1. Selezionare **Home** nel percorso di navigazione nella parte superiore della pagina per tornare alla home page di Azure.

1. Mantenere aperta la scheda del browser perché sarà necessaria per l'attività successiva.

### <a name="task-3-optional"></a>Attività 3 (facoltativa)

In questa attività verranno illustrati i passaggi per correggere un gruppo di risorse non conforme. NOTA: la sottoscrizione di Azure usata per il lab richiederà più tempo del normale per aggiornare lo stato di conformità di un gruppo di risorse corretto.

1. Nella home page di Azure selezionare **criteri**. Viene aperta la home page Criteri con una visualizzazione del dashboard.  L'ambito della visualizzazione Dashboard è la sottoscrizione di Azure fornita dal provider di servizi di hosting per i lab autorizzato.  

1. Verrà visualizzato il criterio creato in precedenza. Selezionarlo.

1. In alto sulla pagina, sotto Essentials, si possono vedere nome, descrizione e altre informazioni essenziali.  Si noti che il criterio viene visualizzato come non conforme.  Selezionare il criterio per visualizzare altre informazioni sul motivo per cui il criterio non è conforme. Qui è possibile notare che una risorsa elencata come resourcegroup1 non è conforme.  Si tratta di un esempio di un gruppo di risorse creato prima della creazione del criterio. Selezionare **Dettagli** per altre informazioni.  Qui è possibile visualizzare il messaggio di conformità che indica che è richiesto il tag ambiente.  Selezionare la **X** in alto a destra per chiudere la finestra.

1. Selezionare **resourcegroup1** e quindi nella parte superiore della pagina selezionare **Visualizza risorsa**.
    1. Accanto a Tag selezionare **modifica**
    1. Posizionare il puntatore del mouse nel campo Tag e selezionare **Ambiente**.
    1. Posizionare il puntatore del mouse nel campo Valore e selezionare **Lab**, quindi selezionare **Salva**.

1. Tornare ora alla pagina dei criteri.  Posizionare il puntatore del mouse nella casella di ricerca blu nella parte superiore della pagina e selezionare **Criteri**.

1. Dal riquadro di spostamento sinistro, selezionare **Conformità**.  Come per la pagina della panoramica, in questa pagina è possibile visualizzare lo stato dei criteri e/o delle iniziative elencati.  NOTA: anche se il tag è stato aggiunto al gruppo di risorse, l'aggiornamento dello stato richiederà tempo.  Le sottoscrizioni di Azure usate per i lab possono riscontrare ritardi più lunghi del normale. Se si vuole attendere che lo stato di conformità della risorsa venga aggiornato, non terminare il lab. A seconda dell'ambiente lab, l'aggiornamento può richiedere un'ora o più.  

### <a name="review"></a>Verifica

In questo lab è stato presentato il processo di creazione di un'assegnazione di criteri di Azure ed è stato possibile vedere l'impatto di tale criterio.
