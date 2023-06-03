<a name="---"></a><!---
---
Demo: Titolo: 'Criteri di Azure' Percorso di apprendimento/Modulo/Unità: 'Percorso di apprendimento: Descrivere le funzionalità di conformità Microsoft; Modulo 6: Descrivere le funzionalità di governance delle risorse in Azure; Unità 2: Descrivere Criteri di Azure'
---
--->

# <a name="demo-azure-policy"></a>Dimostrazione: Criteri di Azure

Questa demo corrisponde al contenuto di Learn seguente:

- Percorso di apprendimento: Descrivere le funzionalità di conformità Microsoft
- Modulo: Descrivere le funzionalità di governance delle risorse in Azure
- Unità: Descrivere Criteri di Azure

## <a name="demo-scenario"></a>Scenario demo

Questa demo illustra il processo di configurazione di un criterio di Azure e l'impatto di tale criterio.

### <a name="demo-part-1"></a>Demo parte 1

Creare un criterio per richiedere un tag su un gruppo di risorse (mostra la procedura per creare un criterio da un modello)

1. Aprire Microsoft Edge. Nella barra degli indirizzi immettere **portal.azure.com**.  L'accesso dovrebbe già essere stato effettuato, altrimenti è possibile accedere con le credenziali di amministratore.

1. Nella casella di ricerca, nella barra blu nella parte superiore della pagina accanto a Microsoft Azure, inserire **criteri**, quindi selezionare **Criteri** dai risultati della ricerca.

1. Compare una panoramica della pagina Criteri. Notare le informazioni disponibili nel dashboard.

1. Dal riquadro di spostamento sinistro, in Creazione, selezionare **Assegnazioni**.  Si noterà che è già presente un'assegnazione di criteri, selezionare **ASC Default**.  Esaminare il campo della descrizione. NOTA: il campo della descrizione fa riferimento a Centro sicurezza di Azure che è stato ridenominato Microsoft Defender per il cloud.  Tornare alla pagina Assegnazioni di criteri selezionando la **X** nell'angolo in alto a destra dello schermo.

1. Dalla parte superiore della pagina selezionare **Assegna criterio**. Si apre la procedura guidata di assegnazione dei criteri per guidare l'amministratore nel processo di assegnazione di un criterio.

1. Si inizia nella scheda Generale.
    1. Per Ambito lasciare l'impostazione predefinita. In questo caso, l'ambito dei criteri è la sottoscrizione di Azure fornita dal provider di servizi di hosting per i lab autorizzato.
    1. In Definizione criteri selezionare i **puntini di sospensione**.  Viene fornito un elenco delle definizioni dei criteri disponibili.  Nella barra di ricerca immettere **Richiedi un tag**. Dai risultati della ricerca, selezionare **Richiedi un tag su gruppo di risorse** (potrebbe essere necessario scorrere verso il basso), quindi premere **Seleziona**.  Nota: l'effetto di questo criterio è negare la creazione di qualunque gruppo di risorse che non soddisfa il requisito.  
    1. Si noti il nome di assegnazione predefinito.  Mantenere il nome così com'è.
    1. Assicurarsi che l'opzione Applicazione dei criteri sia impostata su **Abilitata** e selezionare **Avanti**.

1. Si è ora nella scheda Parametri. Nel campo Nome tag immettere **Ambiente** e quindi selezionare **Avanti**.

1. Nella scheda Correzione non modificare le impostazioni predefinite e quindi selezionare **Avanti**.

1. Si è ora nella scheda Messaggi di non conformità. Nel campo Messaggio di non conformità immettere **È obbligatorio un tag di ambiente** e quindi selezionare **Avanti**. Nota: questo messaggio apparirà come motivo di non conformità per i gruppi di risorse che sono stati creati prima dell'assegnazione del criterio e non hanno un tag Ambiente.  

1. Rivedere l'assegnazione dei criteri e quindi selezionare **Crea**.  Se non si vede immediatamente il criterio, selezionare **Aggiorna**. Nota: l'applicazione dei criteri potrebbe richiedere fino a 30 minuti, ma in genere avviene più rapidamente.

1. Uscire dalla pagina di assegnazione dei criteri selezionando la **X** nell'angolo in alto a destra dello schermo.

1. Ora ci si trova nella home page dei servizi di Azure.  Tenere questa pagina aperta, servirà per l'attività successiva.

### <a name="demo-part-2"></a>Demo parte 2

In questa attività si vedrà l'impatto dell'assegnazione dei criteri di Azure tentando di creare un gruppo di risorse in Azure senza un tag.

1. Nel browser, aprire la scheda Home – Microsoft Azure.

1. In alto sulla pagina, sotto la dicitura Servizi di Azure, selezionare **Gruppi di risorse**.

1. Dall'angolo superiore sinistro della pagina, selezionare **+ Crea**.

1. Nella scheda Generale di Crea un gruppo di risorse lasciare il campo Sottoscrizione così come è.

1. Nel campo Gruppo di risorse immettere **SC900-Labs**.

1. Lasciare l'impostazione Area geografica sul valore predefinito e quindi selezionare **Avanti: Tag**.

1. Lasciare vuoto il campo Nome e Valore del tag.  NON POPOLARE, quindi selezionare **Verifica + Crea**.

1. Verrà visualizzato un messaggio che indica che la convalida è riuscita (il nome e il valore del tag non sono campi obbligatori nella procedura guidata), quindi selezionare **Crea**.

1. Verrà visualizzato un messaggio di errore nella parte superiore dello schermo, "Non è stato possibile creare il gruppo di risorse. Selezionare **Visualizza dettagli errore**". La condizione che fa parte dei criteri di Azure non è stata soddisfatta, quindi la creazione del gruppo di risorse è stata bloccata per non conformità. Nota: se non viene visualizzato il messaggio di errore e il gruppo di risorse viene creato, significa che l'applicazione del criterio non è ancora avvenuta.  Passare alla pagina Criteri per i criteri creati nell'attività precedente e quando i criteri diventano effettivi si vedrà che la risorsa non è conforme.  La pagina dei dettagli includerà il messaggio di non conformità.

1. Il riepilogo dell'errore mostra il seguente tipo di errore, "La risorsa 'SC900-Labs' non è consentita dal criterio".  Chiudere questa finestra selezionando la **X** nell'angolo in alto a sinistra dello schermo.

1. Nella finestra Crea un gruppo di risorse selezionare **Precedente**.

1. Si ritorna alla pagina Tag per la creazione di un gruppo di risorse.  Nel campo Nome immettere Ambiente e nel campo Valore immettere **SC900-Labs**, quindi selezionare **Avanti: Rivedi e crea >** .

1. Verificare il tag e selezionare **Crea**.

1. Nel campo Nome immettere **Ambiente** e nel campo Valore immettere **Lab** (questo valore potrebbe essere qualsiasi cosa, il criterio richiede semplicemente un valore di tag), quindi selezionare **Avanti: Rivedi e crea >** e infine selezionare **Crea**.

1. Verrà elencato il gruppo di risorse.  

1. Far notare agli studenti che se fosse stato creato un gruppo di risorse prima dei criteri, il gruppo di risorse verrebbe ora visualizzato come non conforme a questa assegnazione di criteri e dovrebbe essere corretto applicando il tag Ambiente.  È presente un gruppo di risorse preesistenti con etichetta ResourceGroup1 non conforme e che può essere corretto, ma il tempo per l'aggiornamento dello stato, dopo la correzione, è più lungo del normale per l'ambiente lab.

### <a name="review"></a>Verifica

Questa demo ha illustrato il processo di configurazione di un criterio di Azure e l'impatto di tale criterio.
