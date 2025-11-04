# Memoria, livelli di conoscenza e grafi concettuali --- riscrittura integrale

## 1. Memoria umana e formalizzazione logica

La cognizione umana funziona spesso con due registri di memoria: una **long-term memory** (memoria a lungo termine) e una **short-term memory** (memoria a breve termine). Quando percepiamo qualcosa, lo confrontiamo con ciò che è già memorizzato: riconosciamo se «l'abbiamo già visto» oppure no. Per esempio, possiamo vedere una foto di Anthony Fauci con i capelli bianchi e capire che non è lo stesso con i capelli neri; tutta questa attività --- il confronto di percezioni, il riconoscimento e la generalizzazione --- può essere formalizzata e modellata con la logica.

La logica funge dunque da motore algoritmico del ragionamento: è un algoritmo parametrizzato dal tipo di dati che rappresentiamo. Diversi tipi di conoscenza richiedono algoritmi diversi, ma la struttura di base del ragionamento (confronto, deduzione, riconoscimento) trova nella logica una precisa formalizzazione.

------------------------------------------------------------------------

## 2. Tre tipi fondamentali di rappresentazione della conoscenza

Possiamo distinguere tre grandi livelli o tipi di conoscenza che vogliamo rappresentare:

1.  **Conoscenza linguistica** --- le parole e le etichette che usiamo per nominare concetti (es.: "uomo", "persona", "cane").

2.  **Type graphs** --- strutture che rappresentano la conoscenza come insiemi, tipi ed eredità (le ontologie di alto livello). Qui rientrano le generalizzazioni e le relazioni di inclusione fra categorie.

3.  **Conoscenza percettiva** --- ciò che percepiamo direttamente (immagini, suoni, sensazioni) e i modelli che associano tali percezioni a etichette linguistiche (es.: riconoscimento facciale, riconoscimento di oggetti).

Questi tre livelli sono complementari: le parole (livello linguistico) servono per descrivere i concetti che formalizziamo nei type graphs, mentre il collegamento fra percezione e linguaggio è ciò che il machine learning aiuta a ottenere (associare una label a un insieme di percezioni).

------------------------------------------------------------------------

## 3. Conoscenze universali e conoscenze contestuali

Alcune conoscenze sono **universali** o generalizzazioni (es.: "tutti gli uomini hanno due gambe", salvo eccezioni). Queste conoscenze si formalizzano bene in logica come enunciati universali. Altre conoscenze sono **episodiche** o contestuali: quando incontriamo una persona la prima volta registriamo un insieme di percezioni concrete (volto, capelli, abbigliamento) che poi vengono generalizzate o confrontate con la memoria.

La logica consente di rappresentare entrambi i tipi: generalizzazioni formali (quantificatori universali) e la pratica del riconoscimento di singoli oggetti/istanze.

------------------------------------------------------------------------

## 4. Scelta del linguaggio della conoscenza

Quando modelliamo la conoscenza assumiamo un linguaggio --- ovvero accettiamo che le parole che useremo abbiano precise interpretazioni e che i concetti corrispondano a certi insiemi di percezioni. Questo implica:

- formalizzare il significato delle parole;

- definire le entità (cosa chiamiamo "persona", "auto", ecc.);

- nominare le entità (fornire identificatori).

Queste attività sono in genere date per scontate, ma sono proprio quelle che la logica deve rendere esplicite quando sorgono problemi di qualità o di integrazione dei dati.

------------------------------------------------------------------------

## 5. Concetti, gerarchie e relazioni fondamentali

Un **concetto** è una rappresentazione linguistica di un tipo di percetto: es. "uomo", "persona", "cane", "sedia" sono concetti. I concetti sono organizzati in strutture gerarchiche (es.: l'insieme degli uomini è sottinsieme dell'insieme delle persone). Due relazioni fondamentali tra concetti sono:

1.  **Inclusione** (subset): es. `Uomini ⊆ Persone`.

2.  **Disgiunzione / separazione**: concetti che non condividono istanze.

In un modello del mondo semplificato (un "concept graph") queste relazioni sono rappresentate come nodi e archi: gli archi ISA (is a) vanno dal più specifico al più generale.

------------------------------------------------------------------------

## 6. Persistenza spazio-temporale e identità

I concetti hanno anche aspetti temporali e spaziali: una entità (una persona) persiste nel tempo con proprietà che possono cambiare (colore degli occhi, posizione nello spazio, stato di vita). Per riconoscere e tracciare entità nel tempo usiamo attributi robusti che rendono riconoscibile la stessa istanza (per es., il volto piuttosto che il colore della maglietta). Questa persistenza e la capacità di individuare istanze coerenti nel tempo sono parte importante del grafo concettuale.

------------------------------------------------------------------------

## 7. Come si rappresenta matematicamente un grafo di concetti

Matematicamente, il grafo dei concetti è spesso una gerarchia (diretta, con radice) in cui:

- ogni nodo è un concetto (un insieme di percezioni o istanze);

- archi ISA collegano concetti più specifici a concetti più generali;

- si possono rappresentare anche relazioni di parte-tutto (meronymy) per artefatti composti (es.: portiera è parte di auto).

Nel linguaggio di modellazione questo si traduce in **entity type graphs** o **ontologie top-level**.

------------------------------------------------------------------------

## 8. Istanza vs. tipo: esempi pratici

Esempio pratico: il concetto "chitarra" (tipo) ha sotto-classi (chitarra acustica, chitarra elettrica) e attributi (colore, peso). Le singole chitarre (istanze) vengono descritte da valori per questi attributi: "questa chitarra è bianca", "questa pesa 3 kg".

Quando costruisci un dominio ristretto (es.: un negozio di chitarre), cambi la radice del grafo concettuale e lavori su un sottoinsieme del dominio globale: il principio di funzionamento del grafo resta lo stesso, ma il contesto e il vocabolario si restringono.

------------------------------------------------------------------------

## 9. Proprietà (Data Properties) e relazioni (Object Properties)

Nel modellare entità occorre distinguere due tipi di collegamenti:

- **Data Properties** (proprietà di dato): collegano un'entità a un valore atomico o a un data type (es.: altezza = 175 cm, nome = "Paolo").

- **Object Properties** (proprietà oggetto): collegano un'entità a un'altra entità (es.: `amicoDi(Paolo, Maria)`).

Questa distinzione è fondamentale: altezza, peso, codice fiscale sono data properties; relazioni come "essere padre di", "possedere" sono object properties.

------------------------------------------------------------------------

## 10. Uguaglianza, riconoscimento e classificazione

Due operatori concettuali ricorrono frequentemente:

- **Uguaglianza**: verifica che due descrizioni corrispondano alla stessa entità (es.: autenticazione tramite confronto dei dati). Chi lavora in logica parla di uguaglianza; chi fa machine learning parla di classification (assegnare una label a una percezione).

- **Equivalenza di percezione**: machine learning impara a costruire classi di equivalenza di percezioni che corrispondono a una label ("persona", "Fiat 500", ecc.).

La logica e il machine learning cooperano: la logica dà la struttura, il ML associa percezioni alle etichette.

------------------------------------------------------------------------

## 11. Scale lessicali: quanti concetti servono?

Un essere umano mediamente usa \~15.000 parole; i sistemi di NLP/AI usano spesso vocabolari molto più ampi (order di grandezza: 100.000--120.000 parole) collegate in reti semantiche. Codificare tutte queste relazioni a mano è impossibile: sono migliaia, centinaia di migliaia di asserzioni. La logica aiuta a definire schemi e regole che permettono di non dover enumerare tutto esplicitamente.

------------------------------------------------------------------------

## 12. Grafi di concetti e "language models" (concettuali)

I grafi che descrivono concetti, relazioni e proprietà sono talvolta chiamati **modelli del linguaggio** (non confondere con gli LLM --- large language models). Sono strutture logiche/ontologiche: se prendi il concetto "persona" e raccolgi tutte le foto associate a "persona", puoi addestrare un algoritmo di visione artificiale a riconoscere nuovi esempi come appartenenti a quella classe.

Matematicamente questo processo definisce classi di equivalenza: tutte le percezioni che vengono etichettate come "persona" appartengono alla stessa classe.

------------------------------------------------------------------------

## 13. Ontologie e "top-level ontologies"

Il termine **ontologia** è stato ripreso dall'informatica per definire insiemi di concetti e relazioni in un dominio. Le ontologie top-level definiscono concetti generali (entità, evento, agente, luogo) e servono come radici per ontologie di dominio (sanità, sport, commercio...). Le ontologie consentono di documentare il significato delle parole e facilitare l'integrazione dei dati eterogenei.

------------------------------------------------------------------------

## 14. ISA, inheritance e part-of

Le relazioni più usate nelle ontologie sono:

- **ISA (is a)**: relazioni di tipo "è un": collega il più specifico al più generale (ereditarietà di proprietà).

- **Part-of**: relazioni di parte-totale (una portiera è parte di un'auto).

L'ISA permette di ereditare proprietà dal genitore al figlio; la relazione part-of definisce composizione strutturale. Entrambe sono rilevanti per la modellazione, ma il corso si concentra primariamente su ISA come principale mecanismo di generalizzazione.

------------------------------------------------------------------------

## 15. Definizione vs. separazione: come si dà significato a una parola

Per definire "persona" (o qualsiasi concetto) si procede per **inclusione** (cosa è) e **separazione** (cosa non è). In pratica:

- si elencano le proprietà generali che caratterizzano il concetto;

- si dichiarano disgiunzioni rispetto ad altre categorie dove necessario.

Questo è il modo in cui si costruisce il significato formale di una parola in una ontologia.

------------------------------------------------------------------------

## 16. Eccezioni: regole e pratiche sociali

Molti tratti che riteniamo "ovvi" sono in realtà regole sociali o convenzioni culturali: es. "un uomo ha due gambe" è vero nella generalità dei casi ma ammette eccezioni (persone con amputazioni). Il modello formale deve poter rappresentare sia la regola generale sia le eccezioni. A volte la scelta di considerare un'eccezione come "ancora uomo" o come "non uomo" dipende da una definizione culturale o applicativa.

------------------------------------------------------------------------

## 17. Diversità linguistica e culturale (esempi)

I linguaggi e le culture organizzano il mondo in modi differenti. Alcuni esempi citati:

- Alcune lingue non distinguono certe categorie che per noi sono distinte (es.: "seaport" in certe lingue può non esistere).

- La differenza maschio/femmina può essere marcata solo per adulti in certe culture.

- Il concetto di "riso" può essere distinto in "riso crudo" e "riso cotto" in alcune lingue, mentre in altre no.

Queste differenze mostrano che la costruzione di ontologie e vocabolari non è neutrale: dipende da scelte culturali e pragmatiche. Chi "stabilisce" il significato (es.: grandi servizi che fanno traduzioni automatiche) influenza in pratica l'uso corrente della lingua.

------------------------------------------------------------------------

## 18. Reference concept, E-types e Data types

Nel design dei modelli pratici troviamo concetti ricorrenti:

- **Reference concept**: il concetto radice che usi per descrivere un dominio (es.: `Persona` per dati anagrafici).

- **E-types (entity types)**: tipologie di entità definite per il dominio (studente, corso, docente).

- **Data types**: tipi di dato predefiniti (stringhe, numeri, date, geometrie) con insieme di valori noti a priori; utili per proprietà (data properties).

Gli E-types e i data types aiutano a standardizzare la rappresentazione e rendono possibile il mapping fra schemi diversi.

------------------------------------------------------------------------

## 19. E-type graphs e Knowledge Models

Gli **E-type graphs** (o knowledge models) sono grafi che descrivono, dato un reference concept, quali proprietà e relazioni sono rilevanti per quel concetto. Un E-type graph specifica:

- gli attributi (data properties) pertinenti;

- le relazioni con altri E-types (object properties);

- quali E-types sono disgiunti o in relazione ISA.

Questi modelli vengono usati in progettazione dei database, in data engineering e nelle specifiche di sistemi informativi (es.: S3).

------------------------------------------------------------------------

## 20. Collegamento con i sistemi reali (es.: S3, matricole)

Nei sistemi reali la funzione di interpretazione spesso è implementata tramite identificatori concreti: matricola universitaria, codice fiscale, passaporto ecc. Questi identificatori sono pratici ma non perfetti (problemi con cambi di nome, stranieri, duplicazioni). La progettazione del mapping (dare un'identità univoca alle istanze) è un'attività critica e costosa.

------------------------------------------------------------------------

## 21. Sintesi finale --- perché tutto questo è importante

- La logica fornisce lo schema per rappresentare parole, concetti, relazioni e regole; il machine learning si occupa di associare percezioni a etichette.

- Le ontologie e i grafi concettuali formalizzano il significato delle parole e la struttura della conoscenza.

- Le scelte progettuali (cosa modellare, quali identificatori usare, quali eccezioni accettare) sono compromessi di costo e scopo: non si tratta di negligenza, ma di scelte pratiche.

- Comprendere queste scelte e formalizzarle previene errori di integrazione, ambiguità e perdita informativa.
  \# Dalla percezione ai grafi di concetti: E-type graphs, teleontologie e ragionamento

## 1. Dalla percezione alla costruzione delle relazioni

Partiamo da ciò che facciamo naturalmente: osserviamo il mondo, separiamo gli elementi percepiti, li raggruppiamo e cominciamo a costruire relazioni tra di essi.  
Nella pratica didattica l'abbiamo fatto con le foto: prima estraiamo ciò che vediamo, poi definiamo insiemi di percezioni (percetti) e infine introduciamo relazioni. Alcuni di quei concetti li decidiamo di trasformare in **entity types** (E-type): dichiariamo "questo concetto lo voglio trattare come un E-type" e quindi definiamo le relazioni che lo collegano ad altri concetti.

Le relazioni che usiamo possono essere:

- **n-arie** (relazioni con più argomenti),

- **object properties** (collegano entità tra loro),

- **data properties** (collegano entità a valori atomici, es. numeri o stringhe).

Questa organizzazione ci permette, per esempio, di distinguere «la persona che sono io oggi» da «la persona che ero ieri»: due istanze/descrizioni diverse dello stesso concetto.

------------------------------------------------------------------------

## 2. E-type graph plurali e gerarchie

Un singolo E-type graph tipicamente contiene più concetti.  
Esempio: nel concept/E-type graph di S3 troveremo `Persona`, `Studente`, `Docente` (professore), ecc. Possiamo rappresentarli nello stesso grafo a patto di mantenere coerenza gerarchica: ad esempio, se definiamo `Uomo` come sottotipo di `Persona`, la relazione deve essere consistente. Se in una parte del grafo si afferma che `Uomo ⊆ Persona` ma in un'altra si afferma il contrario, abbiamo una contraddizione definizionale.

Nel linguaggio naturale usiamo queste categorie in modo flessibile --- "ho visto un uomo che camminava" --- e il contesto ci permette di non specificare se stiamo parlando del concetto astratto o di un'istanza particolare con proprietà aggiuntive ("uomo alto", "uomo con una gamba", ecc.). Ma nella modellazione formale questa distinzione va esplicitata.

------------------------------------------------------------------------

## 3. Che forma ha un E-type graph (ETG) --- teleontologia e nesting

Un ETG spesso è pensato come una **teleontologia** o come un modello simile allo schema YARN che avete visto: una struttura a nidificazione (nesting) con ereditarietà di proprietà.

Caratteristiche tipiche:

- radice/concetti generali (top-level);

- nodi sottostanti più specifici (sottotipi);

- propagazione delle proprietà dai padri ai figli (inheritance);

- possibilità di rappresentare parti e composizioni (part-of) oltre a ISA.

Un E-type può descrivere oggetti curiosi (es.: "veicolo che è anche barca") --- tecnicamente un E-type esiste, ma non sempre ha senso trattarlo come concetto principale: se diventasse un concetto primario, saremmo costretti a definire molte proprietà atipiche. Per questo distinguiamo tra ciò che è concetto (ontologico) e ciò che è mera combinazione di attributi.

------------------------------------------------------------------------

## 4. Concept graph vs. livello delle proprietà

Il **concept graph** serve principalmente a dire *cosa esiste* e *come il mondo è spartito in categorie non confondibili* (es.: `Persona`, `Luogo`, `Organismo`). Non è il livello dove si dichiarano tutti i dettagli proprietà-by-property.  
Quando vogliamo ragionare su verità/falsità o eseguire inferenze, abbiamo bisogno anche delle proprietà (livello inferenziale), e lì entra in gioco la propagazione di informazioni dall'alto verso il basso nel grafo (espansione).

Un esempio pratico: se `Persona` ha la proprietà "due gambe" a livello alto, non è necessario ripeterla su `Uomo` o `Donna`; la proprietà viene ereditata. Questo è comodo perché evita ripetizioni e consente ai motori inferenziali di dedurre proprietà sulle istanze.

------------------------------------------------------------------------

## 5. Tassonomie e teleontologie applicative

Alcune strutture simili a ontologie sono le **tassonomie** statistiche --- ad esempio: età 0--20, 20--40, 40--60. Queste sono utili per categorizzare popolazioni ma non sono concetti ontologici di per sé: sono classificazioni applicative utili per un certo scopo.

In una modellazione reale si sceglie un dominio, si restringe la radice del grafo (es.: dominio "sport", o "sanità") e si costruisce la teleontologia specifica per quell'ambito. Questo è ciò che si intende per **language teleontology** o ontologia di dominio: un grafo con obiettivo funzionale.

------------------------------------------------------------------------

## 6. Ereditarietà delle proprietà e motori inferenziali

Il processo tipico è: definisco il linguaggio (concetti), definisco le proprietà sui concetti più generali, e poi uso un motore inferenziale per *camminare* sul grafo ed espandere o verificare affermazioni.  
Esempio: se il grafo dice che "Persona → haDueGambe" e io incontro un'istanza etichettata `Uomo`, il motore inferenziale, conoscendo che `Uomo ⊆ Persona`, può dedurre che l'istanza haDueGambe (salvo eccezioni specificate).

Le eccezioni sono cruciali: in applicazioni safety-critical (es.: controllo dei treni, avionica) una singola eccezione non prevista può causare disastri; per questo è fondamentale un metodo sistematico per modellare eccezioni e garantire copertura.

------------------------------------------------------------------------

## 7. Identificatori (CID, IID) e integrazione dati

Nei grafi reali, ogni concetto e ogni istanza ha identificatori espliciti:

- **CID** --- concept ID (identifica un concetto nel concept graph);

- **IID** --- instance ID (identifica un'istanza/entità concreta).

Questi ID sono essenziali per l'integrazione dei dati: due dataset in lingue diverse possono avere etichette diverse ma condividere lo stesso CID, permettendo il mapping e la data integration. Gli ID risolvono problemi pratici di ambiguità lessicale nelle integrazioni su larga scala.

------------------------------------------------------------------------

## 8. Specializzazioni pratiche: es. piazza quadrata vs piazza rotonda

Spesso abbiamo concetti che condividono la stessa categoria generale ma richiedono proprietà diverse. Esempio: `PiazzaQuadrata` e `PiazzaRotonda` sono entrambe `Piazza` (stesso E-type), ma per computare la superficie la piazza quadrata richiede il lato, la piazza rotonda richiede il raggio. Di conseguenza, a livello di implementazione del knowledge graph o del database, servono proprietà (attributi) diverse per istanziare correttamente la misura che ci interessa.

Questo illustra la necessità di avere sia un *concetto unico* che *descrizioni specializzate* per casi d'uso specifici.

------------------------------------------------------------------------

## 9. Schema, implementazione e propagazione dell'informazione

Uno **schema** è la specifica che dice quali proprietà (ereditate o locali) sono disponibili per un concetto.  
Dal punto di vista implementativo:

- si costruisce il concept graph / E-type graph;

- si definiscono gli schemi (quali proprietà provengono dalla radice e quali sono locali);

- si implementano ID e mapping ai dataset reali.

Una volta definito lo schema, algoritmi di espansione cammineranno sul grafo e permetteranno a motori inferenziali di rispondere a domande del tipo "questa entità ha nome/indirizzo?" anche se il dato non è esplicitamente presente sull'istanza, ma è ereditato dalla struttura concettuale.

------------------------------------------------------------------------

## 10. Knowledge graphs, ER models e semi-formalità

Le rappresentazioni diffuse nello engineering sono spesso **semi-formali**:

- ER models, tabelle di database e knowledge graphs sono rappresentazioni pratiche e canoniche, ma spesso non contengono tutta la conoscenza implicita del mondo.

- La sintassi è formalizzata (es.: schemi, tipi), ma la semantica completa (tutte le implicazioni) non è sempre esplicitata.

Questo è accettabile per molte applicazioni: i costi di esprimere tutto formalmente sono enormi. Tuttavia, laddove serve correttezza e copertura completa, bisogna adottare modelli più rigorosi e motori inferenziali che espandano automaticamente la conoscenza implicita.

------------------------------------------------------------------------

## 11. Lessici, WordNet e standardizzazione

Per rendere interoperabili i dataset si usano lessici e risorse lessicali (es.: WordNet) o standard di dominio (ISO, comitati tecnici). Queste risorse formalizzano significati, sensi e relazioni lessicali e sono fondamentali per l'integrazione dei dati eterogenei (es.: durante la pandemia, è stato necessario armonizzare informazioni tra stati e agenzie).

Nel mondo reale, chi sviluppa database spesso non ha bisogno di tutta questa ontologia globale; ma per integrazione su larga scala (sanità, pubblica amministrazione, ecc.) la standardizzazione è cruciale.

------------------------------------------------------------------------

## 12. Dal grafo concettuale al mondo reale: grande scala e complessità

I grafi di concetti reali sono enormi: per la sanità si possono avere milioni di nodi e centinaia di milioni di link. Il problema non è solo modellare, ma anche progettare algoritmi scalabili che, dato un world model canonico e una domanda, sappiano dedurre le informazioni mancanti (entailment).

La sfida che affronteremo dopo è: dato un input teorico (world model) e una domanda, come usare regole di ragionamento (entailment) per produrre le conclusioni non esplicitate? Questo richiede teorie logiche, algoritmi efficienti e attenzione alla complessità computazionale.

------------------------------------------------------------------------

## 13. Espansione, inferenza e qualità delle risposte

L'operazione di **espansione** (propagare proprietà lungo il grafo) è ciò che rende possibile rispondere a query anche quando i dati espliciti sono incompleti. Ma l'efficacia dipende dalla qualità del world model, dalla completezza degli schemi e dalla gestione delle eccezioni.

Nel prossimo incontro introdurremo la prima nozione di logica operativa per questi modelli --- la logica che ci permette di ragionare sui primi tre tipi di modelli (knowledge graph, database relazionale, ecc.), discutendo inoltre teoremi di correttezza e completezza e gli aspetti computazionali (esistenza di algoritmi, complessità).

------------------------------------------------------------------------

## 14. Conclusione: perché tutto questo conta

- Costruire concept graph ed E-type graphs non è solo un esercizio teorico: è la base pratica per sistemi che devono integrare dati, fare inferenza e garantire qualità in contesti critici.

- La differenza tra modelli semiformali e modelli formali si risolve definendo procedure e algoritmi per espandere e verificare la conoscenza implicita.

- La logica, insieme alle strutture ontologiche, è lo strumento che ci permette di trasformare rappresentazioni sparpagliate in sistemi coesi, rispondendo a domande complesse e coprendo eccezioni quando serve.
