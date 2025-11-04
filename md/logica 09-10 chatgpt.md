## **Parte 1 -- Introduzione e scopo della logica**

Ci siamo finalmente avvicinati alla logica. Dopo aver compiuto le prime "hackerate" sul mondo --- ossia i primi tentativi di comprendere come descriverlo e formalizzarlo --- possiamo ora intuire perché la logica è necessaria e come la utilizzeremo.

Nella parte introduttiva del corso abbiamo definito alcuni concetti fondamentali:

- **Il modello**: inteso come una rappresentazione del mondo, costruita in termini di insiemi e relazioni.

- **La teoria**: intesa come un insieme di asserzioni o proposizioni, scritte secondo una grammatica definita, che esprimono conoscenze su quel modello.

Ora, in questa ultima parte dedicata al ragionamento logico, vogliamo dotarci di uno strumento matematico che ci permetta di **collegare ciò che diciamo** (il linguaggio) a **ciò che abbiamo in mente ma non possiamo direttamente comunicare** (la nostra rappresentazione mentale del mondo).

Il punto centrale è dunque formalizzare la **corrispondenza tra linguaggio e realtà**, o, più precisamente, tra **teorie e modelli**.  
Quando parliamo, partiamo da un modello del mondo che condividiamo implicitamente: se uso la parola "casa", voglio che chi mi ascolta interpreti la stessa entità che io ho in mente quando dico "casa".

Non stiamo ancora discutendo se un'affermazione sia **vera o falsa**; ci stiamo semplicemente assicurando che il **significato** delle parole e delle proposizioni sia condiviso.  
Solo dopo aver formalizzato questa corrispondenza tra linguaggio e significato potremo affrontare le nozioni di **verità**, **falsità**, **teoria** e infine **ragionamento**.

------------------------------------------------------------------------

### **Che cos'è un modello formale del mondo**

Un modello formale del mondo è una **tripla** composta da:

1.  **Un dominio di interpretazione** (che formalizzeremo tramite la teoria degli insiemi).

2.  **Un linguaggio assiomatico** (che modelleremo con una certa grammatica formale, ad esempio di tipo 1, 2 o 3 nella gerarchia di Chomsky).

3.  **Una funzione di interpretazione**, che mappa ogni elemento del linguaggio su un elemento del dominio, cioè su ciò che intendiamo nel modello.

Questa funzione di interpretazione deve essere costruita in modo che ad ogni espressione linguistica corrisponda univocamente il suo significato nel modello.

A questo punto abbiamo tutto:

- **Il linguaggio**, cioè l'insieme delle stringhe o espressioni che possiamo formulare.

- **Il modello**, cioè l'insieme dei "percetti" o fatti che descrivono la realtà.

È importante sottolineare che non stiamo inventando nulla di nuovo. Questi meccanismi esistono da sempre: fin da bambini, quando qualcuno ci mostrava il disegno di un libro e diceva "libro", stavamo già costruendo un modello del mondo e un mapping linguistico, seppure in modo del tutto informale.

------------------------------------------------------------------------

### **Linguaggi naturali, modelli informali e modelli formali**

Nel linguaggio naturale il collegamento tra parole e oggetti avviene **in modo informale**: si indica un oggetto con un gesto o un contesto, e l'interpretazione è affidata all'intuizione comune.  
Questo tipo di rappresentazione si chiama **modello semi-informale**.

Nei **modelli formali**, invece, sia l'insieme delle espressioni del linguaggio sia il dominio (cioè l'insieme degli oggetti a cui il linguaggio si riferisce) sono **definiti formalmente**, cioè secondo regole matematiche precise.

Esistono anche **modelli semi-formali**, che sono quelli che abbiamo usato fino a questo punto del corso: una sintassi in parte definita formalmente e in parte descritta in linguaggio naturale, per esempio quando rappresentiamo graficamente concetti con schemi o diagrammi.  
Ora, però, passiamo ai **modelli pienamente formali**, perché abbiamo finalmente gli strumenti matematici per farlo.

------------------------------------------------------------------------

### **Indipendenza dal linguaggio**

Tutto ciò che stiamo dicendo è **indipendente dal linguaggio specifico** che usiamo.  
Qualunque linguaggio --- purché dotato di regole sintattiche e semantiche --- può generare asserzioni che saranno poi considerate vere o false nel proprio modello.

Domani vedremo che, indipendentemente dalla sintassi adottata (che sia quella degli alberi, dei diagrammi o di altre notazioni), **esistono solo sette tipi fondamentali di modelli del mondo**, ciascuno corrispondente a un diverso modo di organizzare la conoscenza.

Per ciascuno di questi sette tipi di modelli costruiremo un diverso **modello di inferenza**, ossia una diversa logica del ragionamento.  
In altre parole, tutti i tipi di ragionamento che utilizziamo si possono ricondurre a una delle sette forme fondamentali di modelli del mondo.

## **Parte 2 -- Funzione di interpretazione, modelli e linguaggi**

Abbiamo definito che un **modello formale** è una **tripla (L, D, I)**, dove:

- **L** è il linguaggio, cioè l'insieme delle stringhe o formule che possiamo costruire.

- **D** è il dominio di interpretazione, ovvero l'insieme dei "fatti" o entità del mondo a cui il linguaggio si riferisce.

- **I** è la funzione di interpretazione, che associa a ogni espressione linguistica il suo significato nel dominio.

La funzione di interpretazione III è il cuore del modello, perché stabilisce la corrispondenza tra ciò che diciamo e ciò che intendiamo.

------------------------------------------------------------------------

### **Esempi intuitivi di interpretazione**

Riprendiamo alcuni esempi semplici, che abbiamo già incontrato:

- "Sofia è bionda" → nel modello significa che **Sofia appartiene all'insieme delle persone bionde**.

- "Sofia è amica di Paolo" → la coppia (Sofia, Paolo) appartiene alla relazione "essere amici".

- "Rocky è il cane di Sofia" → "Rocky" appartiene all'insieme dei cani, e la coppia (Sofia, Rocky) appartiene alla relazione "possedere".

- "Sofia è vicino a Paolo" → (Sofia, Paolo) appartiene alla relazione "essere vicini".

- "Paolo è un uomo" → Paolo appartiene all'insieme degli uomini.

- "Sofia è una persona" → Sofia appartiene all'insieme delle persone.

Queste frasi, che usiamo naturalmente, corrispondono già a interpretazioni di un linguaggio strutturato secondo la **tripla soggetto-verbo-oggetto**.  
È proprio una **tripla** (entità, relazione, entità), che possiamo rappresentare in forma di **knowledge graph** --- una rete di conoscenze che riflette il modo in cui gli esseri umani organizzano mentalmente i concetti.

------------------------------------------------------------------------

### **Dal linguaggio naturale al linguaggio formale**

Tuttavia, queste frasi non costituiscono ancora un **linguaggio formale**.  
Nel linguaggio naturale, una singola frase come "Rocky è il cane di Sofia" in realtà contiene **due asserzioni distinte**:

1.  Rocky è un cane.

2.  Rocky appartiene a Sofia (cioè Sofia possiede Rocky).

Il linguaggio naturale è ambiguo perché **un'unica espressione** può avere **più significati** contemporaneamente.  
In un linguaggio formale, questo non è possibile: ogni espressione deve essere **non ambigua** e avere **una sola interpretazione**.

Per questo motivo la formalizzazione è più difficile: richiede di scomporre le frasi in unità atomiche prive di ambiguità, e di specificare esattamente il significato di ogni simbolo.

------------------------------------------------------------------------

### **Struttura e formalizzazione**

In un linguaggio naturale, la struttura sintattica è implicita.  
Per esempio:

- "Ho visto il cane che abbaiava."

- "Ho visto la casa che bruciava."

- "Ho visto la persona che ho incontrato ieri."

In ciascuna frase, il "che" introduce funzioni grammaticali differenti: soggetto, complemento oggetto, ecc.  
Questo dimostra che il linguaggio naturale è **pervasivamente ambiguo** e contestuale.

Un linguaggio formale, invece, esplicita tutte le relazioni e non lascia margine di interpretazione.  
Ogni frase deve poter essere analizzata e verificata matematicamente.

------------------------------------------------------------------------

### **Tipi di modelli e logiche del mondo**

Nella **teoria dei modelli**, distinguiamo diversi tipi di elementi fondamentali:

- **Entità** (gli oggetti del dominio).

- **Tipi di entità** (categorie o classi di oggetti).

- **Relazioni** (associazioni tra entità).

A seconda di cosa rappresentiamo, otteniamo modelli differenti.  
Per esempio:

- Nei **modelli ER (Entity-Relationship)**, le tabelle rappresentano entità e relazioni in modo esplicito.

- Nel **modello relazionale** (come nei database), le entità vengono rappresentate implicitamente tramite insiemi di tuple.

Per esempio, una tabella:

| Name | Age | Friend |
|------|-----|--------|
| 1    | 27  | 2      |

rappresenta due entità (Name, Friend), un valore numerico (Age) e insiemi di possibili valori per ciascun attributo.

A seconda del tipo di modello, useremo una logica diversa:

- le logiche "delle entità" ragionano su oggetti individuali,

- le logiche "degli insiemi" ragionano su collezioni e proprietà globali.

------------------------------------------------------------------------

### **Proprietà della funzione di interpretazione**

Una funzione di interpretazione III deve possedere alcune proprietà fondamentali:

1.  **Non ambiguità** -- ogni asserzione deve corrispondere a un solo fatto nel dominio.

    - Non può accadere che una stessa espressione denoti due fatti diversi.

    - Questa è la differenza principale con il linguaggio naturale, che invece è **polisemico** (una parola può avere più significati).

2.  **Sinonimia ammessa** -- è possibile che **più espressioni diverse** indichino **lo stesso fatto**.

    - Esempio: "auto" e "macchina" possono riferirsi allo stesso oggetto.

    - Nei database, tuttavia, spesso si evita la sinonimia per ragioni di efficienza, adottando la **unique name assumption** (ogni nome denota un solo oggetto).

3.  **Totalità e soggettività** -- la funzione di interpretazione può essere:

    - **Totale**, se a ogni espressione linguistica corrisponde un significato nel dominio.

    - **Soggettiva (o parziale)**, se esistono elementi del linguaggio che non hanno ancora un significato definito (per esempio, concetti non ancora osservati o non rilevanti nel dominio).

Nella pratica, spesso accettiamo funzioni di interpretazione parziali, perché **definire tutto** può essere troppo costoso o inutile.  
L'importante è che la funzione sia **corretta**: cioè ogni espressione interpretata corrisponda effettivamente a qualcosa di reale nel dominio.

------------------------------------------------------------------------

### **Correttezza e competenza della funzione di interpretazione**

Possiamo definire formalmente due proprietà ulteriori:

- **Correttezza**: per ogni espressione α∈L`\alpha `{=tex}`\in `{=tex}Lα∈L, la sua interpretazione I(α)I(`\alpha`{=tex})I(α) appartiene al dominio DDD.  
  (Tutto ciò che il linguaggio dice ha senso nel dominio del modello.)

- **Competenza**: per ogni elemento d∈Dd `\in `{=tex}Dd∈D, esiste almeno una espressione α∈L`\alpha `{=tex}`\in `{=tex}Lα∈L tale che I(α)=dI(`\alpha`{=tex}) = dI(α)=d.  
  (Ogni elemento del dominio è nominabile nel linguaggio.)

Nella realtà, non sempre possiamo avere entrambe le proprietà:  
a volte la **competenza** è sacrificata perché rappresentare ogni possibile elemento del dominio sarebbe troppo costoso o inutile.

Un esempio:  
in passato, in un'università non si conoscevano i nomi di tutti i visitatori che entravano negli edifici.  
Non era un problema fino a quando non è diventato necessario per motivi assicurativi: a quel punto si è reso obbligatorio registrare i visitatori, introducendo una funzione di mappatura più completa.  
La **correttezza** era sempre garantita (ogni nome corrispondeva a una persona reale), ma la **competenza** era inizialmente assente e poi completata per necessità.

------------------------------------------------------------------------

### **Conclusione della Parte 2**

Abbiamo ora una definizione chiara di **funzione di interpretazione** e delle sue proprietà:

- deve essere **corretta**,

- può essere **totale o parziale**,

- può ammettere **sinonimia ma non ambiguità**,

- E definisce la corrispondenza tra linguaggio e mondo.

## **Parte 3 -- Rappresentazione del mondo e teoria del mondo**

A questo punto possiamo distinguere due concetti centrali e complementari:

- Il **modello del mondo**: rappresenta **tutto ciò che esiste o potrebbe esistere**. È l'insieme completo di fatti, relazioni e oggetti che costituiscono la realtà (o una sua porzione).

- La **rappresentazione del mondo**: rappresenta **ciò che noi conosciamo** del mondo, ossia l'insieme delle asserzioni che abbiamo effettivamente espresso nel linguaggio.

La rappresentazione del mondo è quindi sempre **una parte** del modello del mondo.  
In termini logici, essa costituisce una **teoria**: un insieme di proposizioni che descrivono, con una certa fedeltà, la realtà modellata.

------------------------------------------------------------------------

### **Dalla conoscenza al linguaggio**

Possiamo dire che la teoria (la rappresentazione) è una **vista parziale** del modello, definita dal linguaggio.  
Non possiamo dire tutto del mondo, ma solo ciò che è esprimibile con le risorse linguistiche e concettuali che abbiamo.

Questo è il motivo per cui ogni teoria è **limitata dal suo linguaggio**:  
un linguaggio più povero genera teorie meno dettagliate, mentre un linguaggio più ricco consente rappresentazioni più precise.

Formalmente, possiamo pensare che ogni teoria TTT sia un sottoinsieme del linguaggio LLL, ossia T⊆LT `\subseteq `{=tex}LT⊆L, composto dalle formule che consideriamo **vere** rispetto a un certo modello MMM.

------------------------------------------------------------------------

### **La relazione tra teoria e modello**

Il collegamento tra teoria e modello è mediato dalla **funzione di interpretazione III**:  
per ogni formula α∈T`\alpha `{=tex}`\in `{=tex}Tα∈T, I(α)I(`\alpha`{=tex})I(α) è un fatto che appartiene al modello MMM.

Quando tutte le formule della teoria sono vere nel modello, diciamo che il modello **soddisfa** la teoria, e scriviamo:

M⊨TM `\models `{=tex}TM⊨T

In modo simmetrico, possiamo dire che la teoria **descrive** il modello se contiene tutte e sole le formule vere in quel modello.

------------------------------------------------------------------------

### **Esempio: il mondo delle persone**

Supponiamo di modellare il mondo delle persone con queste asserzioni:

- Sofia è una persona.

- Paolo è una persona.

- Sofia è amica di Paolo.

Questa teoria descrive un mondo molto piccolo.  
Potremmo espanderlo aggiungendo altre proposizioni ("Paolo è nato a Roma", "Sofia ha un cane", ecc.), ma resta comunque **una rappresentazione parziale** del mondo reale.

Il mondo vero è infinitamente più complesso; la teoria seleziona e organizza solo le informazioni rilevanti per il nostro scopo.

------------------------------------------------------------------------

### **Correttezza e completezza del linguaggio rispetto al modello**

Possiamo ora introdurre due nozioni fondamentali della teoria dei modelli:

1.  **Correttezza (soundness)**:  
    Tutto ciò che è deducibile nel linguaggio è vero nel modello.

    Se T⊢α, allora M⊨α`\text{Se }`{=tex} T `\vdash `{=tex}`\alpha`{=tex}, `\text{ allora }`{=tex} M `\models `{=tex}`\alphaSe`{=tex} T⊢α, allora M⊨α

    Significa che il linguaggio non genera errori: non possiamo derivare una proposizione falsa rispetto al modello.

2.  **Completezza (completeness)**:  
    Tutto ciò che è vero nel modello è anche deducibile nel linguaggio.

    Se M⊨α, allora T⊢α`\text{Se }`{=tex} M `\models `{=tex}`\alpha`{=tex}, `\text{ allora }`{=tex} T `\vdash `{=tex}`\alphaSe`{=tex} M⊨α, allora T⊢α

    Significa che il linguaggio è abbastanza potente da esprimere tutto ciò che è vero nel mondo.

In pratica, un sistema logico ideale sarebbe **corretto e completo**: direbbe solo verità, e direbbe **tutte** le verità.  
Tuttavia, nella maggior parte dei casi reali, dobbiamo accontentarci di sistemi **corretti ma incompleti**:  
preferiamo non dire qualcosa di vero piuttosto che affermare qualcosa di falso.

------------------------------------------------------------------------

## **Parte 4 -- I sette tipi di modelli del mondo**

Il professore sottolinea che **esistono solo sette tipi fondamentali di modelli del mondo**, ognuno dei quali corrisponde a un diverso modo di organizzare la conoscenza e a una diversa forma di logica.  
Questi modelli si distinguono in base a **come rappresentano le relazioni e i significati**.

1.  **Modelli insiemistici (set-based)**  
    Il mondo è visto come un insieme di elementi con certe proprietà.  
    È il paradigma della **logica del primo ordine** e della **teoria degli insiemi**.  
    Tutto è riducibile a appartenenza e inclusione.

2.  **Modelli relazionali**  
    Gli oggetti sono collegati da relazioni binarie o n-arie.  
    Tipico dei database e dei grafi relazionali: rappresentano "chi è amico di chi", "chi lavora con chi".

3.  **Modelli funzionali**  
    Gli oggetti sono descritti in termini di funzioni che producono risultati.  
    È la base della logica funzionale e dei linguaggi di programmazione funzionali.

4.  **Modelli procedurali**  
    Il mondo è rappresentato come un insieme di azioni e trasformazioni di stato.  
    È la logica delle macchine di stato, dei sistemi dinamici e dell'informatica operazionale.

5.  **Modelli dichiarativi o proposizionali**  
    La conoscenza è espressa come un insieme di proposizioni vere o false.  
    È il modello più semplice: adatto alla logica proposizionale e ai sistemi esperti classici.

6.  **Modelli semantici**  
    Le relazioni non sono solo formali ma portano significato; il mondo è visto come una rete di concetti.  
    È la logica dei sistemi ontologici, delle reti semantiche, e delle ontologie del web semantico.

7.  **Modelli pragmatici o contestuali**  
    Il significato delle proposizioni dipende dal contesto, dall'intenzione e dalla situazione d'uso.  
    È la logica dei linguaggi naturali, della comunicazione e dell'intelligenza situata.

Questi sette tipi di modelli costituiscono la base di **tutte le forme di ragionamento umano e artificiale**.  
Ogni tipo di modello determina quale logica usiamo, quali inferenze sono valide e quale concetto di verità possiamo adottare.

------------------------------------------------------------------------

## **Parte 5 -- Dalla teoria alla verità: logica come strumento di interpretazione**

Ora possiamo finalmente comprendere **che cos'è la logica** nel senso più rigoroso.

La logica è lo **strumento matematico che formalizza la relazione tra linguaggio e mondo**.  
Essa definisce in modo preciso:

1.  **La sintassi**, cioè le regole che stabiliscono quali stringhe del linguaggio sono ben formate (le formule).

2.  **La semantica**, cioè la funzione di interpretazione che attribuisce significato a quelle formule.

3.  **La relazione di verità**, che stabilisce quando una formula è vera o falsa rispetto a un modello.

4.  **Le regole di inferenza**, che stabiliscono come dedurre nuove formule vere a partire da quelle già accettate come tali.

------------------------------------------------------------------------

### **Inferenza e significato**

L'atto del "ragionare" consiste nel muoversi all'interno del linguaggio secondo regole che **preservano la verità**.  
Un sistema di inferenza è **corretto** se non produce mai falsità da premesse vere.

Quando diciamo che un sistema logico è "potente", intendiamo che è **completo** o **abbastanza competente** da esprimere tutte le verità del dominio.  
Tuttavia, come abbiamo visto, la completezza assoluta è spesso impossibile.

------------------------------------------------------------------------

### **Verità, validità e soddisfazione**

- Una **formula è vera in un modello** se la sua interpretazione corrisponde a un fatto del modello.

- Una **formula è valida** se è vera in tutti i modelli possibili.

- Una **formula è soddisfacibile** se è vera almeno in un modello.

Queste distinzioni sono fondamentali in logica:  
la **validità** riguarda la forma del ragionamento, mentre la **verità** riguarda il contenuto.  
Un ragionamento valido non può portare da premesse vere a conclusioni false, indipendentemente da cosa significhino i simboli.

------------------------------------------------------------------------

### **Dalla logica al linguaggio naturale**

Quando comunichiamo, facciamo implicitamente logica.  
Ogni volta che diciamo "Se piove, prendo l'ombrello" stiamo costruendo una proposizione condizionale che ha lo stesso schema formale della logica proposizionale.

Il linguaggio naturale, però, è ricco di ambiguità, presupposizioni e contesto:  
la logica formale cerca di **astrarre** da tutto ciò, per concentrarsi sulla struttura pura del ragionamento.  
È per questo che la logica è al tempo stesso **astratta e potentissima**: ci permette di studiare la forma del pensiero, indipendentemente dal contenuto.

------------------------------------------------------------------------

## **Parte 6 -- Considerazioni conclusive e prospettive**

A questo punto possiamo tirare le fila di tutto il percorso:

1.  Abbiamo definito un **modello del mondo** come rappresentazione matematica della realtà.

2.  Abbiamo introdotto la **teoria**, ossia la rappresentazione linguistica di ciò che sappiamo del mondo.

3.  Abbiamo definito la **funzione di interpretazione**, che collega linguaggio e mondo.

4.  Abbiamo studiato le proprietà di **correttezza**, **completezza** e **competenza**.

5.  Abbiamo visto che esistono **sette tipi fondamentali di modelli** e, di conseguenza, sette modi diversi di ragionare.

6.  Infine, abbiamo compreso che la **logica** è il ponte che unisce linguaggio, conoscenza e realtà.

------------------------------------------------------------------------

### **La logica come metastrumento**

La logica non serve solo a fare deduzioni:  
è uno **strumento di modellazione** del pensiero, della conoscenza e della comunicazione.  
Serve a capire come rappresentiamo il mondo, come costruiamo significati condivisi e come verifichiamo la coerenza di ciò che diciamo.

In questo senso, la logica è una **meta-disciplina**: studia i principi generali di ogni linguaggio e di ogni forma di conoscenza possibile.  
Ogni linguaggio, per essere significativo, deve ammettere un modello, e ogni modello, per essere interpretabile, deve essere esprimibile in un linguaggio.

------------------------------------------------------------------------

### **Conclusione generale**

Concludendo, possiamo dire che:

- La **teoria dei modelli** descrive **come** il linguaggio si collega al mondo.

- La **logica** descrive **come** possiamo derivare conoscenze vere a partire da ciò che già sappiamo.

- Il **ragionamento** è l'attività che, all'interno di un linguaggio, costruisce nuove verità mantenendo la coerenza con il modello.

In sintesi:

> **La logica è la scienza della corrispondenza tra linguaggio e realtà.**

E questa corrispondenza --- formale, precisa, ma fondata su un'antichissima esigenza umana di capire e condividere il mondo --- è ciò che rende la logica il fondamento di ogni conoscenza, naturale o artificiale.

# Modelli, diversità, canonicalità e problemi pratici nella rappresentazione del mondo

## 1. Diversità e impossibilità di eliminarla

La diversità esiste e non è eliminabile: luoghi, persone e dati sono diversi per natura (la stazione di Trento è diversa da un'altra stazione, ecc.). Tuttavia, se riusciamo a rendere **trasparente** il processo che ci porta a dimenticare i dettagli non rilevanti, allora possiamo costruire un modello MMM per il quale riusciamo a ottenere proprietà desiderabili come **correttezza** e **completezza**.

In altre parole: la correttezza si può impostare e costruire formalmente, ma per farlo è necessario aver prima **formalizzato il modello**. Solo dopo aver fissato la formalizzazione possiamo costruire il mapping (la funzione di interpretazione) in modo tale da poter --- quando serve --- "buttare via" (o dimenticare) il modello originario senza perdere informazioni rilevanti per le inferenze che vogliamo fare.

## 2. Competenza sì / competenza no --- perché servono entrambi i punti di vista

Nel corso è stato detto che la competenza (cioè la proprietà secondo cui ogni elemento del dominio è denotato da qualche formula del linguaggio) non è sempre necessaria per usare la semantica. Però, nella pratica:

- Prima si **costruisce** la rappresentazione formale (e quindi si può non richiedere competenza completa).

- Poi si può "buttare via" il modello originario purché la costruzione sia fatta in modo tale che non si perda nulla dell'informazione necessaria.

Quindi la competenza non serve necessariamente per **utilizzare** la semantica, ma serve per **costruirla** in modo robusto, così che la si possa poi scartare senza danni.

## 3. Teorie massimali e problema della massimalità

Una teoria può essere incompleta rispetto a un modello MMM, ma al contempo essere teoria anche di modelli più grandi M′M'M′ che estendono MMM. Questo è importante perché, se non stiamo attenti, la nostra teoria potrebbe includere o escludere cose che non vogliamo: dobbiamo poter **definire formalmente la massimalità** di una teoria rispetto a un modello.

- **Teoria massimale rispetto a MMM**: è completa rispetto a MMM (non si può aggiungere una formula vera in MMM rimanendo all'interno della teoria senza contraddizione).

- La massimalità non è sempre obbligatoria, ma diventa critica quando vogliamo gestire sistematicamente l'**incompletezza** in un sistema.

### Esempio pratico (database universitario)

Se il database di un'università contiene solo le persone registrate ma manca una persona realmente presente in aula, una query al database restituirà "non c'è" mentre nel mondo reale quella persona esiste. Questo disallineamento tra rappresentazione del database e rappresentazione del mondo richiede attività aggiuntive di gestione (controlli, verifiche, procedura per aggiornare i dati). In alcune applicazioni (dove un errore è tollerabile) questo costo extra è accettabile; in applicazioni critiche (es. esami, controllo accessi, sicurezza) non lo è.

## 4. Incompletezza implicita nelle schematizzazioni (ER model, tabelle, ecc.)

Molte rappresentazioni pratiche (ER model, tabelle, archivi, ecc.) sono intrinsecamente **incomplete**: certi ruoli o relazioni non sono esplicitati. Per esempio nel database S3 (o in altri sistemi di gestione studenti) non è detto che "un professore possa essere anche un assistente" sia scritto esplicitamente: può risultare implicito o non modellato. Queste lacune sono la ragione per cui i sistemi reali non sono logiche complete e perfette.

Per questo motivo esistono convenzioni pratiche (come la **unique name assumption** nei database) e meccanismi di engineering (identificatori univoci, matricole) che cercano di ridurre ambiguità e confusione.

## 5. Canonicalità, teoria massimale e modello canonico

Quando parliamo di modellazione vogliamo spesso arrivare a una **rappresentazione canonica**: una forma in cui la teoria è **massimale** e **corretta** rispetto a un modello "inteso" (intended model). In breve:

- La **teoria massimale** è costruita in modo da non dimenticare niente di ciò che è rilevante per il modello canonico.

- Il **modello canonico** è la rappresentazione del modello "inteso" che guida la costruzione della funzione di interpretazione.

Se abbiamo fissato il modello canonico e la funzione di interpretazione, possiamo ricavare una teoria T che è corretta e --- se vogliamo --- massimale rispetto a quel modello. L'obiettivo è far sì che la teoria T rappresenti completamente MMM nel modo canonico deciso.

## 6. Trasformare il dominio in "oggetti linguistici" (quando il dominio diventa lingua)

Nella pratica della realizzazione di un sistema, spesso si arriva a "trascrivere" il dominio nei termini del linguaggio; il dominio finisce per diventare una collezione di simboli o record. Questo è ciò che accade quando:

- si progetta una specifica e si decide quali entità modellare;

- si definisce la sintassi e il vocabolario (nomi, attributi, relazioni).

Tuttavia, nel mondo reale questo processo può diventare impossibile da compiere in modo esauriente (es. il dominio dei numeri naturali è infinito; modellare tutto "ciò che è vero nel mondo" alla lettera è impraticabile). Perciò la modellazione richiede scelte: cosa includere, cosa escludere e quale livello di dettaglio adottare.

## 7. Perché la logica è utile nonostante i limiti pratici

La logica nasce perché, anche senza conoscere tutto in maniera esplicita, possiamo definire regole che ci permettono di **calcolare conseguenze** e **ragionare**. La logica dà strumenti per essere resilienti: sapere regole generali che permettono di ricostruire informazioni implicite e per derivare ciò che non è stato esplicitato.

Detto più pragmaticamente: nella modellazione e nello sviluppo software, non è realistico codificare tutto. La logica serve a definire gli schemi, le ipotesi e le regole sotto cui possiamo lavorare in sicurezza.

## 8. Il ruolo dei mapping pratici: identificatori e casi reali

Nei sistemi reali la funzione di interpretazione spesso è implementata tramite identificatori concreti:

- **Matricola** (numero identificativo dell'università) → puntatore a una scheda studente;

- **Codice fiscale** → identifica una persona in modo (quasi) univoco;

- Altri identificatori (passaporto, patente) usati in sistemi diversi.

Questi identificatori hanno pregi e limiti: a volte funzionano bene, altre volte introducono problemi (ad esempio la gestione di cambi di nome, stranieri, errori di trascrizione). La realtà mostra che la costruzione di mapping "puliti" è costosa e tutt'altro che banale: richiede pratiche amministrative, procedure e (spesso) un lavoro manuale di pulizia dei dati.

## 9. Costi, compromessi e decisioni progettuali

Le scelte che si fanno nel rappresentare il mondo --- quali entità modellare, quali attributi includere, quale livello di completezza perseguire --- sono **decisioni di costo**. Ottenere completezza e competenza totale costa (in progettazione, calcolo, memoria, manutenzione), quindi spesso si accettano compromessi:

- applicazioni dove un errore è tollerabile: si accettano rappresentazioni parziali e procedure ad hoc;

- applicazioni critiche (es. controllo treni, sicurezza, esami): si richiedono investimenti maggiori per garantire correttezza e completezza dove necessario.

## 10. Linguaggio, rappresentazione e livelli di modellazione

È utile distinguere più livelli:

1.  **Livello del linguaggio**: gli strumenti sintattici che usiamo (nomi, verbi, strutture).

2.  **Livello della conoscenza**: la teoria che esprime la nostra conoscenza (le asserzioni che formiamo).

3.  **Livello del mondo**: il dominio inteso e i fatti oggettivi.

La progettazione logica e informatica consiste nel decidere quale livello enfatizzare e come far corrispondere i tre livelli attraverso mapping e procedure di costruzione.

## 11. Entity Graph e rappresentazioni di base vs. composte

La lezione introduce l'idea di **Entity Graph** come una delle rappresentazioni principali (quelle "di base" utilizzate più frequentemente) che poi possono essere composte per ottenere modelli più complessi. Le rappresentazioni di base (es. modelli relazionali, knowledge graph) permettono di tracciare entità, attributi e relazioni e si mappano naturalmente sulle istanze concrete (es. gli studenti di S3).

Quando si vogliono evitare problemi di sinonimia o polisemia (parole con più significati) o si vuole parlare a diversi livelli (persone vs. insiemi), si usano modelli composti che definiscono con più cura il vocabolario, i tipi e le relazioni.

## 12. Vocabolario, definizioni e analisi: perché definire fa la differenza

Ogni analisi seria inizia con definizioni chiare: definire che cosa è un intero, un reale, cosa intendiamo per "studente", "professore", ecc. Questo vocabolario consente la costruzione di teorie con ipotesi chiare. Se il linguaggio di specifica è canonico e la conoscenza è coerente, allora le istanze (es. gli oltre 17.000 studenti in S3) si applicheranno correttamente alle regole della teoria.

Questa è la ragione per cui, prima di scrivere regole e algoritmi, si dedica tempo a definire il dominio e la sintassi: la qualità della modellazione dipende da lì.

## 13. Costruire sistemi resilienti: regole, ipotesi e "non dire tutto"

Nel mondo reale non si codifica tutto; si definiscono ipotesi e regole che consentono di inferire ciò che non è esplicitato. Questo è il lavoro della logica applicata: usare regole di comportamento (e regole di inferenza) che permettono agli umani e ai sistemi di essere resilienti anche con informazioni parziali.

Questa è la ragione per cui i sistemi operativi reali, i database e molte applicazioni pratiche adottano convenzioni (unique identifiers, regole di inferenza, strategie di fallback) per gestire ambiguità e mancanze.

## 14. Conclusione e richiamo alla lezione successiva

In sintesi:

- La diversità e l'incompletezza sono problemi reali ma gestibili con progettazione e formalizzazione.

- La canonicalità (teorie massimali, modelli canonici) è un ideale utile per capire come costruire rappresentazioni robuste, ma spesso impraticabile da realizzare pienamente nel mondo reale (per motivi di costo e scala).

- Le applicazioni pratiche richiedono compromessi: spesso si sceglie la soluzione che minimizza i costi pur garantendo le proprietà essenziali (correttezza laddove critica, procedure di fallback dove possibile).

- Nella prossima lezione si partirà dai modelli canonici di base e si vedrà come costruire i modelli composti e come queste scelte impattano l'ingegneria del software e il ragionamento automatico.
