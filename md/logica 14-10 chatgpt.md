## 1. Problema di partenza: il modello canonico e i suoi limiti

Quando rappresentiamo il mondo con una tabella di database o con un modello grafico canonico, quello che compare nella rappresentazione è **esattamente** quello che sappiamo --- **né più né meno**. Ogni riga di una tabella, ogni fatto nel database corrisponde a un'informazione che possediamo, ma tutto ciò che non è scritto lì **non viene conosciuto** dal sistema.

Se il mondo reale contiene più informazioni di quelle che abbiamo inserito nella tabella, il database non ce lo dirà: semplicemente non lo conosce. L'unica "soluzione" immediata sarebbe arricchire manualmente il database con più dati --- cosa spesso impossibile o infeasibile su larga scala.

Questo è il motivo per cui i modelli canonici sono utili (sappiamo con precisione cosa rappresentano), ma sono limitati: non contengono la conoscenza implicita che noi, esseri umani, diamo per scontata.

------------------------------------------------------------------------

## 2. Perché ci serve la logica: andare oltre il dato esplicito

Le **logiche** servono a superare questo limite. Esse prendono in input un modello di riferimento (uno dei tipi che abbiamo visto) e, grazie a regole di ragionamento, permettono di **dedurre** nuove affermazioni che non sono esplicitamente scritte nel database ma che sono implicite nel modello mentale o nel background knowledge.

In altre parole: la logica ci consente di trasformare un insieme di fatti espliciti (quelli nel modello) in una **teoria** --- un insieme più ricco di asserzioni che possiamo considerare vere rispetto a quel modello.

------------------------------------------------------------------------

## 3. World entailment: il mapping da modello a teoria

Formalmente, esiste una funzione --- possiamo chiamarla **world entailment** --- che, dato un modello del mondo, costruisce una teoria: cioè genera affermazioni (asserzioni) che si deducono da quello che è implicito nel modello.

Ricordiamo:

- Un **modello** è un insieme di fatti.

- Una **teoria** è un insieme di asserzioni (formule).

Nei modelli canonici precedenti c'era essenzialmente una corrispondenza uno-a-uno tra ciò che si diceva e ciò che esisteva nel modello. Con la logica vogliamo usare il modello come base per generare **nuove** asserzioni che non sono espresse esplicitamente ma sono giustificate dal background knowledge.

------------------------------------------------------------------------

## 4. Esempio intuitivo: il Duomo e le chiese

Prendiamo un esempio semplice per chiarire il punto. Io so che "il Duomo è una chiesa". Dal mio background culturale (istruzione, esperienza, conoscenza comune) so anche che **tutte le chiese** hanno tipicamente una certa struttura --- ad esempio una torre campanaria. Questa è una conoscenza generalizzata (un universale): non la percepisco direttamente nel Duomo, ma la so.

Quindi, anche se nel mio database ho solo la relazione `Duomo` → `è una chiesa`, la logica con il mio background knowledge mi permette di dedurre che `Duomo` è anche una costruzione fisica con una torre. Questo non è "inventare" informazioni: è sfruttare conoscenze pregresse per dedurre ciò che è implicito.

Se vogliamo che un sistema automatico faccia lo stesso senza errore, dobbiamo esplicitare queste regole e fornire al sistema il background knowledge: altrimenti la macchina non sa *quando* e *perché* dedurre certe affermazioni.

------------------------------------------------------------------------

## 5. Teorie incomplete e conversione in completezza tramite inferenza

Una teoria può essere formalmente **incompleta** rispetto a un modello: non contiene tutte le formule vere nel modello. Tuttavia, grazie a un motore inferenziale (la logica), la teoria può essere **estesa** producendo nuove affermazioni vere nel modello, cioè possiamo "colmare" l'incompletezza tramite regole di ragionamento.

Questo è il ruolo pratico della logica: accettare che la rappresentazione è incompleta, ma fornire regole per derivare le informazioni mancanti, in modo sistematico e controllabile.

------------------------------------------------------------------------

## 6. Connettivi logici e loro ruolo rappresentativo

Per costruire descrizioni più ricche abbiamo bisogno di costrutti logici fondamentali. Tra i principali:

- **Congiunzione (AND)**: consente di affermare che due cose sono vere insieme.

- **Disgiunzione (OR)**: rappresenta alternative o incertezza (es.: "una persona è uomo o donna" quando non sappiamo quale dei due casi sia vero). L'OR è particolarmente importante perché permette di esprimere non conoscenza o scelta fra alternative.

- **Negazione (NOT)**: consente di affermare che una proprietà non vale (es.: "una donna non è un uomo").

Questi connettivi sono gli strumenti sintattici che, insieme alla semantica, permettono di esprimere e manipolare le conoscenze implicite nel modello.

------------------------------------------------------------------------

## 7. Molti modelli → molte teorie: il rapporto modello-teoria è molti-a-molti

Diversi linguaggi o diverse assunzioni sul modello portano a **diverse teorie**: lo stesso modello del mondo può dare origine a molte teorie a seconda del linguaggio e delle regole di inferenza usate. Pertanto non c'è più la corrispondenza uno-a-uno che avevamo coi modelli canonici: ora si ha frequentemente un rapporto **molti-a-molti** tra modelli e teorie.

Questo è intrinseco al problema: ad esempio, l'affermazione "una persona è un uomo o una donna" corrisponde a diversi possibili modelli (tutti uomini, tutte donne, individui distinti) finché non imponiamo vincoli aggiuntivi.

------------------------------------------------------------------------

## 8. Linguaggio, dominio e funzioni di interpretazione

Per formalizzare tutto questo abbiamo bisogno di distinguere chiaramente:

- la **sintassi** (il linguaggio, l'insieme delle formule che possiamo scrivere);

- la **semantica** (il dominio, l'insieme dei fatti che il modello può rappresentare);

- la **funzione di interpretazione** che mappa formule del linguaggio su elementi o insiemi nel dominio.

La teoria è un sottoinsieme del linguaggio; il modello è un sottoinsieme del dominio. La funzione di interpretazione connette i due mondi: ci dice cosa ogni formula *significa* nel dominio.

------------------------------------------------------------------------

## 9. Dal modello mentale alla verifica: cosa significa che una formula è vera?

Dire che una formula α`\alphaα `{=tex}è **vera** in un modello MMM significa che, secondo la funzione di interpretazione e le regole del modello, l'enunciato α`\alphaα `{=tex}corrisponde a un fatto che effettivamente appartiene a MMM.

Verificare se α`\alphaα `{=tex}è vera in MMM è quindi una forma di *question answering*: date le regole e i dati di MMM, posso stabilire se α`\alphaα `{=tex}è soddisfatta o meno. Un errore comune è pensare che il fatto di non poter provare α`\alphaα `{=tex}equivalga a dimostrare ¬α`\lnot `{=tex}`\alpha`{=tex}¬α --- non è così: se non possiamo dedurre α`\alphaα`{=tex}, semplicemente **non sappiamo** se sia vera o falsa.

------------------------------------------------------------------------

## 10. Implicazioni per l'intelligenza artificiale

Gran parte dei problemi attuali dell'AI derivano dal fatto che i sistemi non hanno accesso a un modello del mondo sufficientemente esplicito o non sanno quando *non sanno*. I sistemi basati soltanto su pattern (ad esempio molti modelli di machine learning) possono essere molto efficaci nel classificare, ma non hanno un meccanismo intrinseco per verificare la verità di una proposizione rispetto a un modello del mondo.

Quando forniamo al sistema un sensore (es.: una telecamera) e un modello del mondo, esso può cominciare a verificare affermazioni; ma senza un modello e senza regole di verifica il sistema non sa distinguere tra verità e falsità in senso logico.

------------------------------------------------------------------------

## 11. Memoria, teoria e modello: la teoria come memoria del mondo

Possiamo pensare alla **teoria** come a una forma organizzata di memoria del mondo: ciò che riteniamo vero in un certo modello nasce dalla nostra esperienza, dalla scuola, dalla cultura. La logica è la matematica che formalizza il processo di passaggio dalla memoria (fatti memorizzati) alla derivazione di nuove asserzioni.

------------------------------------------------------------------------

## 12. Logical entailment: l'operazione fondamentale della logica

Formalmente introdurremo il concetto di **entailment** (conseguenza logica): diremo che una teoria TTT **entails** (deriva) una formula α`\alphaα `{=tex}se e solo se, per ogni modello MMM che rende vere tutte le formule di TTT, la formula α`\alphaα `{=tex}è vera in MMM. In simboli: T⊨αT `\models `{=tex}`\alphaT`{=tex}⊨α.

Questa relazione è il fulcro della logica: ci consente di definire operativamente che cosa significa "derivare" una nuova conoscenza a partire da una base di conoscenza.

------------------------------------------------------------------------

## 13. Regole di ragionamento, correttezza e completezza

Per poter usare le regole di inferenza in modo affidabile vogliamo garanzie formali:

- **Correttezza (soundness)**: tutto ciò che il motore inferenziale deriva è effettivamente vero nel modello di riferimento.

- **Completezza (completeness)**: tutto ciò che è vero nel modello può essere derivato dal motore inferenziale.

Queste proprietà sono fondamentali per costruire sistemi affidabili: nei prossimi incontri vedremo quali logiche soddisfano quali proprietà e come questo influenza l'efficacia e la complessità computazionale delle inferenze.
\# Minimi richiami su entailment, modelli e logiche --- testo riorganizzato

## 1. Il problema fondamentale: modelli vs. teorie (rapporto molti-a-molti)

Un punto cruciale è che **la relazione tra modelli e teorie non è uno-a-uno**. Uno stesso modello può essere compatibile con molte teorie, e una stessa teoria può essere soddisfatta da molti modelli. In termini matematici possiamo dire che il rapporto è **molti-a-molti**.

Questo significa due cose pratiche:

- non basta dire "una formula è vera": bisogna specificare **in quali modelli** la si intende;

- quando affermiamo che una teoria TTT **conseguentemente logico** implica T′T'T′ (cioè T⊨T′T `\models `{=tex}T'T⊨T′), stiamo dicendo: per **tutti** i modelli MMM che abbiamo scelto di considerare, se MMM soddisfa TTT allora MMM soddisfa anche T′T'T′.

Questa scelta dei modelli di riferimento è essenziale: due persone che discutono possono entrambi ragionare correttamente, ma rispetto a modelli mentali diversi, perciò arrivano a conclusioni apparentemente incompatibili. La logica esplicita questo meccanismo: scegli il linguaggio, scegli i modelli di riferimento, e allora le regole di ragionamento definiscono cosa significa derivare correttamente.

------------------------------------------------------------------------

## 2. Scelta dei modelli e implicazioni algoritmiche

Dal punto di vista operativo, la scelta dei modelli cambia completamente il problema computazionale:

- se devi verificare l'entailment rispetto a **un singolo modello**, l'algoritmo deve controllare solo quel modello;

- se devi verificare l'entailment rispetto a **insiemi di modelli** (ad esempio cinque modelli), l'algoritmo deve considerare tutti quei modelli --- il costo aumenta;

- la scelta dei modelli può essere fatta anche con criteri ottimizzativi (scegliere i modelli "meno costosi" da esplorare), che è formalmente simile a tecniche di branch-and-bound usate in problemi NP-hard come il TSP.

In sintesi: prima scegli il linguaggio (di cosa vogliamo parlare), poi si scelgono i modelli di riferimento; da queste scelte dipendono sia la correttezza semantica sia la complessità del ragionamento.

------------------------------------------------------------------------

## 3. Machine learning vs. logica: differenze formali

Dal punto di vista metodologico c'è una distinzione profonda tra:

- apprendimento induttivo (machine learning): generalizzare dal particolare al generale;

- inferenza logica (deduttiva): ricavare nuove formule da formule già date.

Entrambi i paradigmi sono utili e spesso complementari: il ML costruisce modelli empirici, la logica consente di ragionare su ciò che è formalizzato e di ottenere garanzie formali. In applicazioni pratiche devi decidere quale combinazione utilizzare: a volte si codifica tutto manualmente (costoso ma sicuro), a volte si lascia molto al ML (più veloce ma meno verificabile).

------------------------------------------------------------------------

## 4. Proprietà desiderate per una logica

Quando si progetta una logica (cioè la triplice scelta: modello del mondo, linguaggio, regole di ragionamento) si richiedono alcune proprietà fondamentali. Le più importanti sono:

- **Riflessività**: se una cosa è nelle ipotesi, allora si può derivare. In pratica consente di trattare gli assiomi come veri punti di partenza.

- **Transitività** (o chiusura per concatenazione): se da AAA ottengo BBB e da BBB ottengo CCC, allora da AAA ottengo CCC. Questa proprietà è alla base della composizione delle dimostrazioni e del planning.

- **Compattezza**: se una teoria TTT implica una formula φφφ, allora esiste un sottoinsieme finito T0⊆TT_0 `\subseteq `{=tex}TT0​⊆T che già implica φφφ. Questo riflette la nostra abilità pratica di isolare il sottoinsieme di conoscenze rilevante per risolvere un problema concreto (resilienza cognitiva).

- **Monotonicità**: aggiungendo conoscenza non si dovrebbe perdere ciò che era già derivabile. Le logiche monotone soddisfano questa proprietà: informazioni aggiunte non annullano inferenze precedenti.

- **Non-monotonicità**: in molti casi reali nuove informazioni invalidano deduzioni precedenti (es.: "gli uccelli volano" vs. "i pinguini non volano"). Le logiche non-monotone modellano questo comportamento e introducono meccanismi di revisione delle teorie.

Queste proprietà sono concetti chiave: in base alle scelte su quali proprietà garantire otterremo logiche con caratteristiche diverse (più semplici, più potenti, più costose da calcolare).

------------------------------------------------------------------------

## 5. Decidibilità, semi-decidibilità e limiti fondamentali

Due questioni fondamentali emergono in teoria della computabilità:

- **Decidibilità**: esiste un algoritmo che, in tempo finito, risponde sì/no al problema di interesse per **tutte** le istanze?

- **Semi-decidibilità**: esiste un algoritmo che, se la risposta è "sì", termina confermando "sì", ma se la risposta è "no" può non terminare (rimane in loop)?

Il risultato di Gödel (e il lavoro successivo di Church e Turing) mostrano che, per linguaggi abbastanza espressivi (per esempio quelli che catturano l'aritmetica dei numeri naturali con somma e prodotto), ci sono affermazioni vere ma non dimostrabili: esistono limiti intrinseci. Questo introduce la nozione di **incompletezza**: non esiste una procedura che provi tutte le verità aritmetiche.

Praticamente: se scegli una logica molto espressiva, puoi esprimere molte proprietà utili, ma potresti perdere la decidibilità o incorrere in complessità inaccettabili.

------------------------------------------------------------------------

## 6. Trade-off espressività vs. complessità

C'è una tensione ingegneristica fondamentale:

- logiche **semplici** → algoritmi decisionali più efficienti (magari decidibili e con buona complessità), ma minor potere espressivo;

- logiche **ricche** → puoi esprimere più concetti, ma paghi un prezzo in termini di decidibilità e/o complessità computazionale.

Per questo motivo nel corso esploreremo più logiche: partiremo da logiche semplici e via via aumenteremo l'espressività, controllando le conseguenze computazionali.

------------------------------------------------------------------------

## 7. Famiglie di logiche del mondo (World Logics)

Nel corso adotteremo una visione **familiare** delle logiche: per ciascuno dei modelli del mondo che abbiamo visto (i sette modelli base/composti), esiste una famiglia di logiche associate. In particolare:

- La famiglia base riguarda la **logica dell'entity graph** (vicina alla semantica degli schemi e dei database). È la logica "più vicina" ai database relazionali / ER.

- Poi si sale di livello: logiche dei concetti (ontologie), logiche per le proprietà e per le descrizioni più complesse, fino a logiche più ricche che combinano tutti gli elementi.

Ogni passo di estensione del linguaggio aggiunge costrutti che consentono di esprimere nuovi tipi di asserzioni e nuovi problemi di reasoning. La buona notizia è che **la semantica è composizionale**: l'estensione si costruisce in modo modulare, portando con sé i teoremi e le proprietà già dimostrate nelle fasi precedenti quando possibile.

------------------------------------------------------------------------

## 8. Reasoning problem e procedure di decisione

Per ogni logica associamo un **reasoning problem** (la domanda che vogliamo risolvere): ad esempio, "T⊨φT `\models `{=tex}φT⊨φ?", "esiste un modello per TTT?", "φφφ e ψψψ sono equivalenti?". Per ciascun problema cerchiamo una **procedura decisionale**: un algoritmo che risponde correttamente in tempo finito (se possibile). Alcuni problemi sono decidibili, altri solo semi-decidibili, altri ancora sono indecidibili.

Nella pratica ingegneristica si prende la logica adatta al problema: per check di schema in fase di design (design-time) si usano logiche diverse da quelle usate in tempo reale (run-time) per controlli operativi.

------------------------------------------------------------------------

## 9. Composizionalità e metodo ingegneristico

Un grande punto di forza delle logiche che adotteremo è la **composizionalità**: costruendo il linguaggio per livelli, posso affrontare problemi complessi passo dopo passo. Di fatto:

- definisco una logica semplice che risolve un insieme di problemi pratici;

- se ho bisogno di più espressività, estendo il linguaggio con nuovi costrutti;

- ogni estensione comporta nuovi algoritmi e nuove classi di problemi, ma il processo è sistematico.

Questo approccio è analogo a come in matematica si estende il linguaggio e le tecniche: prima si studia la teoria base, poi si aggiungono operatori e si studiano le loro conseguenze.

------------------------------------------------------------------------

## 10. Piano operativo del corso

Nel prosieguo del corso:

- cominceremo con la **logica delle entità** (logica vicina ai database / entity graphs);

- poi introdurremo logiche per i **concetti** (ontologie), per le **proprietà** e per le **descrizioni**;

- costruiremo poi logiche composte che mappano sui sette modelli base/composti discussi in precedenza;

- per ciascuna logica studieremo: sintassi, semantica, problematica di reasoning, decision procedure, correttezza e completezza, e complessità computazionale.

------------------------------------------------------------------------

## 11. Messaggio pratico per l'ingegnere

Da un punto di vista pratico: non esiste "la logica migliore" in assoluto. Esiste **la logica giusta per il problema**. Scegliere una logica troppo espressiva può rendere il problema indecidibile o intrattabile; scegliere una logica troppo povera può impedire di esprimere i vincoli importanti. Il buon ingegnere deve bilanciare espressività, correttezza e complessità.
