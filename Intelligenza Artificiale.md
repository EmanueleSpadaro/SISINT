L'intelligenza artificiale deriva dall'unione di due parole:
1. Intelligenza: complesso di facoltà psichiche e mentali che consentono all’uomo di pensare, comprendere o spiegare i fatti o le azioni, elaborare modelli astratti della realtà, intendere e farsi intendere dagli altri, giudicare, e lo rendono insieme capace di adattarsi a situazioni nuove e di modificare la situazione stessa quando questa presenta ostacoli all’adattamento;
2. Artificiale: **ottenuto in maniera non naturale, con procedimenti tecnici**
## Automazione o Intelligenza?
E' bene distinguere la differenza che intercorre tra automazione e intelligenza.
L'automazione deriva dalla scrittura di programmi che **tutto prevedono e tutto gestiscono**: trattano un "ambiente chiuso" nel quale possono capitare solo alcuni eventi, gestibili in maniera totalmente sequenziale. Basti pensare ai [DFA](https://en.wikipedia.org/wiki/Deterministic_finite_automaton).
1. Lavatrice intelligente: non ci verrebbe mai in mente di considerare una lavatrice intelligente realmente tale. Questo perché la lavatrice fa ricadere tutti gli eventi possibili in un particolare caso gestito, come potrebbe essere lo sportello aperto oppure un carico eccessivo.
2. Rover di Marte: ha una capacità aggiuntiva rispetto alla lavatrice, cioè quella di avere un minimo di "**autonomia**". Il segnale tra il Rover e la base terrestre ha una latenza di 20 minuti, non si può pensare ad un semplice radiocomando, il Rover deve essere capace di gestire autonomamente casi come terreno scosceso o presenza di ostacoli nel percorso stabilito.
3. Assistenti virtuali e ChatGPT: sono multipurpose, riescono a gestire eventi in maniera non hardcodata e prevista dal programmatore. Sono scritti in maniera sostanzialmente differente rispetto ai programmi tradizionali.

###### Come stabilire se qualcosa è intelligente?
1. **Test di Turing**: la macchina deve riuscire a produrre gli output attesi.
   Vi è un intervistatore e dall'altra parte una entità sconosciuta (non sa se è umano o una macchina), e l'intervistatore dovrà decretare dopo avergli fatto arbitrarie domande, se quest'ultima sia umano o macchina. Se l'entità sconosciuta è una macchina e l'intervistatore dice "umano", allora la macchina ha superato il test di Turing.
   Il progresso tecnologico ha portato a considerare il test di Turing eccessivamente limitato per poter conferire il titolo di intelligenza ad una macchina in quanto non considera l'**[[Intenzionalità]]**.
2. **[[Intenzionalità#Esperimento della Stanza Cinese |Esperimento della Stanza Cinese]]**: proposto da [John Searle](https://en.wikipedia.org/wiki/John_Searle), aggiunge un livello di complessità aggiuntivo basato sull'[[Intenzionalità]].
   "Il fatto che di fronte agli stessi input un uomo e un computer producano lo stesso output significa che entrambi capiscono cosa stanno facendo"?

Una curiosità è che quotidianamente siamo sottoposti al **Test di Turing inverso** attraverso i **C.A.P.T.C.H.A.** *(Completely Automated Public Turing-test to tell Computers and Humans Apart)*.

## Strong e Weak AI
L'intervento di [John Searle](https://en.wikipedia.org/wiki/John_Searle) ha spaccato la comunità dell'Intelligenza Artificiale in due branchie:
- **Strong AI**: si pone la questione di ottenere la riproducibilità dell'intelligenza umana in quanto tale. Si è sviluppata molto al di fuori del semplice contesto matematico e informatico, andando a coinvolgere discipline quali sociologia, psicologia, ..., andando a configurarsi come una disciplina a parte come **Scienze Cognitive**.
- **Weak AI**: si pone la questione di risolvere problemi che, se risolti dagli esseri umani, richiederebbero intelligenza. E' detta **task-oriented**, e si concentra nello studio del pensiero e del **comportamento razionale** che l'uomo assume di fronte alla soluzione di uno specifico problema.

## Agenti e Ambienti
Gli agenti e gli ambienti sono dei concetti fondamentali per poter studiare approfonditamente la disciplina dell'Intelligenza Artificiale e sono un binomio *<Agente, Ambiente>*.
Perché sono un binomio imprescindibile? Perché un agente può essere particolarmente adatto per un determinato ambiente rispetto ad un altro.
### Agente
Un agente è astrattamente composto da 3 componenti principali:
- **Sensori**: permettono di percepire segnali dall'ambiente in cui si trova. Un esempio software è quello di percepire dati, ambiente in questo caso virtuale.
- **Funzione deliberativa**: sulla base delle informazioni ottenute grazie ai sensori, decide cosa fare.
- **Attuatori**: permettono di agire all'interno dell'ambiente in cui si trova. Un esempio possono essere i freni di un'auto intelligente.
Un agente esegue costantemente un ciclo sequenziale come il seguente:
 1. Percepisco
 2. Delibero
 3. Agisco
### Ambiente
Un ambiente è astrattamente composto da 3 caratteristiche principali:
1. **Osservabilità**:
   - **Completamente osservabile**: i sensori hanno accesso a tutti gli aspetti dell'ambiente per deliberare quale azione eseguire
   - **Parzialmente osservabile**: i sensori danno accesso solo a parte delle informazioni rilevanti per poter deliberare un'azione (imprecisione dei sensori o impossibilità di reperire queste info)
2. **Determinismo**:
   - **Deterministico**: lo stato successivo è determinato dallo stato corrente e dall'azione eseguita, come nei [DFA](https://en.wikipedia.org/wiki/Deterministic_finite_automaton).
   - **Stocastico**: lo stato successivo può differire pur avendo lo stesso stato ed eseguendo la medesima azione. E' detto **strategico** se l'ambiente è stocastico solo sulla base delle azioni eseguite da altri agenti all'interno dell'ambiente.
3. **Staticità**:
   - **Statico**: l'ambiente non cambia mentre l'agente sta deliberando quale azione eseguire
   - **Dinamico**: l'ambiente può cambiare mentre l'agente sta deliberando quale azione eseguire
4. **Numero degli agenti**:
   - **Singolo agente**: viene modellato come singolo agente una sola entità
   - **Multiagente**: vengo modellate entità multiple come agente
 
Un esempio di ambiente sarebbe quello di una strada con attraversamento pedonale.
Un esempio di agente sarebbe un uomo che cerca di attraversare la strada.
L'uomo in questo contesto deve effettuare moltissime valutazioni:
- Identificare il passaggio pedonale
- Rilevare possibili ostacoli
- Rilevare oggetti in movimento
- Rilevare segnali significativi come la luce semaforica
- Costruire un piano di azione, quali attraversare, magari fermarsi un attimo perché una macchina non dà la precedenza
L'ambiente è:
- Complesso (moltissimi altri attori presenti, auto, bici, altri pedoni, ...)
- Parzialmente previdibile (è possibile prevedere la velocità delle macchine, il tempo rimanente della luce verde, ...)
- Parzialmente collaborativo (vige il Codice della Strada, ma non è detto che tutti lo rispettino sempre e questo richiede prudenza aggiuntiva)

## Approccio al Design di Intelligenza Artificiale
L'approccio tradizionale alla programmazione, imperativo e a oggetti, non è adatto alla scrittura di software: è adatto a svolgere un singolo compito e ruota attorno al **come adempierlo in una sequenza di passi**.
```c++
list ins_ord(list L, int dato) {
 if (!L) return(crea_nodo(dato));
 else if (L->d < dato) {
 L->next =
 ins_ord(L->next, dato);
 return L;
 }
 else {
 list tmp = crea_nodo(dato);
 tmp->next = L;
 return(tmp);
 }
}
```

L'approccio adatto all'AI software è quello del **paradigma dichiarativo** e ruota attorno al **cosa so per poter deliberare come agire a riguardo**.
Lo stesso programma quindi è utilizzabile in molteplici situazioni differenti e la percezione è integrata con la base di conoscenze di quest'ultimo.
**E' potente perché l'algoritmo può essere lo stesso, ma la conoscenza può essere totalmente diverso anche in termini di dominio**. (Per esempio, l'algoritmo del [[Mondo Giocattolo]] potrebbe essere tranquillamente utilizzabile anche per decidere la strada per andare da Torino a Catania).

```mermaid
graph TD
	1[Modulo deliberativo]
	2[Knowledge base]
	3[Perception]
	1 --> |Queries| 2
	1 --> |Uses| 3
```
   
Un agente percepisce la situazione iniziale e resta in attesa, non facendo nulla, di ricevere un **goal** (obiettivo) da raggiungere.
Una volta ricevuto il goal, costruisce i passi con i quali andare dalla situazione iniziale a quella desiderata.
Attraverso la **Knowledge Base**, viene a conoscenza delle azioni che può effettuare e di come queste alterino l'ambiente all'interno del quale si trova.
Le azioni sono descritte sulla base di **quando sono applicabili** e **gli effetti sull'ambiente**.

La ricerca del percorso per raggiungere la situazione desiderata richiede la capacità di **ragionamento**, cioè quella di scegliere l'azione utile, tra quelle applicabili, per avvicinarsi all'obiettivo.
**Problema dell'Ottimalità**: noi non vogliamo una soluzione utile, ma la vogliamo in tempi rapidi e che sia efficiente! Questo problema è estremamente non banale.
### Da automazione ad autonomia
- **Automazione**: ormai è standard in molteplici attività, impone che si debba programmare il device a fare ogni passo e gestire ogni caso, ed è applicabile in domini fortemente ripetitivi.
- **Autonomia**: un agente artificiale riceve dei compiti e/o goal ad alto livello, l'utente demanda quindi all'agente la risoluzione.

---
# Risoluzione Automatica dei Problemi
La risoluzione automatica dei problemi coinvolge diverse discipline:
- Ricerca nello spazio degli stati
- Problemi con avversario
- Problemi di soddisfacimento di vincoli
- Inferenza Logica
**La realtà che si vuole trattare con tecniche di risoluzione automatiche di problemi deve poter essere astratta in stati tra i quali transire**.

- **Stato**: condizione corrente
- **Transazione**: passaggio di stato da uno corrente al successivo attraverso un'azione.
  Se esiste uno stato dal quale una stessa azione porta a stati differenti, si parla di *non determinismo*.
- **Obiettivo**: stato che si vuole raggiungere. Ogni stato obiettivo è equivalente a tutti gli altri. Opzionalmente è possibile introdurre anche un valore di prestazione o costo per ottenere una soluzione ottimale.
  L'**Insieme degli Stati Obiettivo** è composto da tutti gli stati che godono della proprietà di essere obiettivo.
- **Percorso**: sequenza di transizione da uno stato iniziale ad uno stato obiettivo.
- **Funzione Costo**: valore associato ad ogni possibile transizione che ci permette di ordinare le soluzioni. E' utilizzata per determinare il percorso minimo, ovvero quello più efficiente tra i possibili percorsi.

E' bene non confondere la soluzione con il goal: se il goal fosse che da Torino si vuole raggiungere una località di mare, Genova fa parte degli stati obiettivo, ma la soluzione non è Genova, bensì il percorso da Torino a Genova.

## Istanza di un problema
Un problema è definito come la seguente n-upla:
$$ <s_i, f_s, t_o, f_c> $$ dove:
- $s_i$ rappresenta lo **stato iniziale**
- $f_s$ rappresenta la **funzione successore** $f_s(s,a) = s'$, dove $s$ stato e $a$ azione.
- $t_o$ rappresenta il **test obiettivo**, funzione che ci informa se uno stato è obiettivo.
- $f_c$ rappresenta la **funzione costo** $f_c(s,a) = c$
Un esempio di problema utile per consolidare il concetto di istanza di un problema è quello del [[Mondo dell'Aspirapolvere]].
Nel corso tratteremo solo ambienti statici e deterministici.

## Algoritmi e Strutture Dati di Ricerca di una Soluzione
Gli algoritmi di ricerca di una soluzione sono suddivisi in due categorie:
- **Algoritmi Blind**: l'unica informazione della quale dispongono è la descrizione del problema, lo stato iniziale.
- **Algoritmi Informati**: hanno una piccolissima conoscenza in più rispetto agli algoritmi blind, ma sono estremamente più performanti e veloci grazie a quest'ultima.
Le **strutture dati per la ricerca** sono:
- **Alberi di ricerca**
- **Grafi di ricerca**
### Albero / Grafo di Ricerca
E' stato utilizzato come mondo di riferimento quello del [[Gioco del 9]].
Data una particolare configurazione della scacchiera di gioco, per esempio quella iniziale del problema, è logico dire quindi che questo sia uno **stato**.
**Uno stato del problema NON corrisponde ad un nodo della struttura di ricerca**.
Uno **stato** mantiene esclusivamente le informazioni relative alla logica di gioco.
Un **nodo** ha più informazioni rispetto ad uno stato:
- Stato al quale si riferisce
- Costo successori
- Riferimento ai "nodi genitori"
- Riferimento ai nodi successivi

![[search-tree.drawio.png]]

```mermaid
---
title: Grafo di ricerca
---
graph TD
	1((i))
	2((s' a' c'))
	3((s'' a'' c''))
	4((Stato goal))

	1 --> |c'| 2
	1 --> |c''| 3
	2 --> |c'''| 4
	3 --> |c''''| 4
```

Il grafo di ricerca è una struttura più generica, e può dare vita a più sequenze di soluzione per raggiungere un determinato nodo target.
**Soluzione ottima**: sequenza di azioni che portano dallo stato iniziale ad uno stato goal con il costo minimo.
N.B. **Soluzione ottima non significa necessariamente percorso minimo**:
si può avere una soluzione ottima con tanti passi di costo basso rispetto ad una soluzione con pochi passi di costo maggiore complessivamente.

### Definizione di Grafo
$$ G = (\{n_i\}, \{e_{ij}\})$$
dove:
- $n_i$ : nodo generico
- $e_{ij}$ : arco 

```mermaid
flowchart TB
	subgraph one["n_{i}"]
	id1((Nodo i))
	end
	subgraph two["n_{j}"]
	id2((Nodo j))
	end
	one --> |"e_{ij}"| two
```
Ogni arco $e_{ij}$ ha associato un costo $c_{ij}$.
Inoltre, gli archi sono diretti e quindi l'esistenza di un arco da A verso B non implica che ve ne sia uno da B verso A.
$$ \exists e_{l_m} \in \{e_{ij}\} \neg\Rightarrow \exists e_{ml} \in e_{ij}$$
All'interno di un grafo di ricerca vi sono diversi **stati di nodi**:
- **Nodo creato**: nodo che il nostro algoritmo ha creato in memoria, ma non ha ancora visitato
- **Nodo esplorato**: nodo che il nostro algoritmo ha già valutato

L'insieme dei nodi non esplorati visitabili da quelli che abbiamo esplorato è detto **frontiera**.

## Strategie di ricerca di una soluzione
Le strategie di ricerca sono degli approcci con i quali possiamo andare a ricercare delle soluzioni.
### Schemi di strategia di ricerca
Si parla di schemi di strategia in quanto forniscono delle strategie ad altissimo livello, i quali passi possono essere implementati in maniera estremamente variegata.
- **Ricerca-Albero *(problema)***: ritorna come valore una soluzione, oppure fallimento se non ne esistono.
  ```
  LOOP DO
	  IF (frontiera vuota) THEN RETURN fallimento
	  SCEGLI NODO DALLA FRONTIERA
	  IF (nodo contiene stato obiettivo) THEN RETURN soluzione
	  ESPANDI IL NODO SCELTO
	  AGGIUNGI I NODI SUCCESSORI DI QUELLO SCELTO ALLA FRONTIERA
  ENDLOOP
  ```
  La scelta del nodo scritta in modo così generico ci dà l'idea che possiamo implementare come più ci aggrada questa operazione.

### Confronto di strategie
Questi sono i criteri con i quali le strategie di ricerca di una soluzione vengono valutati.
- **Completezza**: riesce, SEMPRE, a trovare una soluzione qualora ve ne .fossero
- **Ottimalità**: riesce a dare, SEMPRE, una soluzione ottima
- **Complessità spaziale** in termini di memoria
- **Complessità temporale** in termini di tempo di esecuzione

Le strategia di ricerca sono suddivise inoltre in due tipologie:
1.  **Blind**: l'unica informazione è la descrizione del problema $<s_i, f_s, t_o, f_c>$ 
2. **Approcci informati**: utilizzano la descrizione del problema + **ulteriore conoscenza per guidare la ricerca *(euristica)*** e possono essere:
   - **Monoagente**: ad agente singolo
   - **Multiagente** o **con avversario**
   - **CSP**: **C**onstraint **S**atisfaction **P**roblem

La scrittura della strategia di ricerca può essere effettuata tramite la tradizionale programmazione imperativa, in quanto, per esempio, si tratta semplicemente di realizzare un algoritmo che esplora in ampiezza un albero, come vedremo.
La conoscenza rappresenta, nella forma base, la rappresentazione di un problema nella forma $<s_i, f_s, t_o, f_c>$. 
Una volta sviluppata la strategia di ricerca, possiamo riutilizzarla per i più disparati problemi a patto che riusciamo a tradurli in un modello di conoscenza nella forma $<s_i, f_s, t_o, f_c>$ , dove ci si aspetta di trovare una sequenza di passi per raggiungere l'obiettivo.


## Strategie Blind
Le strategie blind principali sono le seguenti:
- **[[Ricerca in ampiezza]]**
- **[[Ricerca a costo uniforme]]**
- **[[Ricerca in profondità]]** *con o senza Backtracking*
- **[[Iterative Deepening]]**
- **[[Ricerca bidirezionale]]**
## Strategie di Ricerca Informate
Sono delle strategie di ricerca che ambiscono ad ottenere **soluzioni ottime in modo efficiente**, e hanno a disposizione la seguente conoscenza:
- **Istanza del problema**: $<s_i, f_s, t_o, f_c>$
- **Euristica**: funzione $h(n, t) = v$, da *heuristics*, dalla quale otteniamo $h(n) = v$, dove
  -  $n$ è un nodo qualsiasi dell'albero/grafo di ricerca
  - $t$ è un nodo target
  - $v$ è una stima del costo per andare da $n\rightarrow t$

```mermaid
graph TB
1((Stato iniziale))
2((n))
3((t_1))
4((t_2))
5((t_k))
1 --> 2
2 --> |"h(n, t_1)"| 3
2 --> |"h(n, t_2)"| 4
2 --> |"h(n, t_k)"| 5
```
$$h(n)=min_i\text{ } h(n,t_i)$$
Sono detti **nodi preferiti di $n$** quei nodi target $t$ per cui il costo stimato è minimo.
Grazie all'*Euristica* avremo quindi una guida per raggiungere in modo efficiente delle soluzioni ottime.

E' detta strategia di ricerca informata una strategia di ricerca che **applica ai nodi della frontiera una funzione di valutazione** $f(n)$. *(La quale può utilizzare internamente anche l'euristica)*

Ne esistono di diverse, noi tratteremo:
- [[Ricerca Greedy]]
- [[A-star]]
- [[RBFS]]
### Funzioni Euristiche
Le funzioni euristiche possono essere:
- [[Euristica Ammissibile|Ammissibili]]: ottimistiche rispetto al costo reale
- **Informative**: per esempio $h(n)=0$ per la definizione di [[Euristica Ammissibile|Ammissibilità]] è ammissibile, ma **NON E' INFORMATIVA**: permetterebbe di valutare solo il costo del percorso fatto per raggiungere il nodo $n$.
- **Consistenti o Monotone**: rispettano la Disuguaglianza Triangolare $\forall n, n', \text{  }h(n)\leq c(n,n',a) + h(n')$


Le funzioni euristiche possono essere più adatte rispetto ad altre in termini di efficienza.

Un esempio potrebbe essere quello del Gioco dell'8.
Proponiamo due euristiche, entrambe [[Euristica Ammissibile|ammissibili]] per risolvere il problema:
- $h_1$: numero di tessere fuori posto rispetto al goal
- $h_2$: distanza di Manhattan, e cioè il numero di spostamenti che la tessera deve fare verticalmente e orizzontalmente per raggiungere la sua posizione desiderata all'interno del goal

e le compariamo in termini di *nodi generati* con l'[[Iterative Deepening]].

| d   | id      | $A* \ h_1$ | $A* \ h_2$ |
| --- | ------- | ---------- | ---------- |
| 2   | 10      | 6          | 6          |
| 4   | 112     | 13         | 12         |
| 6   | 680     | 20         | 18         |
| 8   | ...     | ...        | ...        |
| 10  | ...     | ...        | ...        |
| 12  | 3644025 | 227        | 73         |
| ... | ...     | ...        | ...        |
| 22  | ...     | 18094      | 1219       |
| 24  | ...     | 39135      | 1641       |

E' detta **funzione euristica dominante rispetto ad un'altra** quella *funzione euristica* $h_2$ rispetto ad $h_1$ per cui vale
$$\forall n\ h_1(n)\leq h_2(n)$$
Una funzione dominante è anche detta **più informativa** rispetto ad altre.

Se non si vuole dimostrare in maniera così estensiva, andando a comparare i dati in maniera tabellare tra le funzioni euristiche, è possibile andare a reperire semplicemente la funzione dominante in un insieme di funzioni euristiche in questo modo.

Siano $h_1, h_2,...,h_k$ euristiche ammissibili per un certo problema se:
$$\forall n\ h(n)=\text{MAX}\{h_1(n), h_2(n), ..., h_k(n)\}$$
$h(n)$ è l'**euristica dominante** su $h_1, h_2,...,h_k$

La ricerca di un'euristica valida per un problema può essere ardua, è possibile quindi trovare un'euristica per una **versione rilassata di un problema**: una versione dove i vincoli del problema sono attenuati o rimossi (E.G.: nel gioco dell'8 i movimenti delle tessere sono limitati dallo spazio libero).
Una soluzione ottima di un problema rilassato è ammissibile anche per il problema con i vincoli. 
### Branching Factor effettivo
Supponiamo di avere eseguito A* generando $N$ nodi, e avendo  
Supponiamo di avere eseguito A* su un certo problema, siano:
- $N$: numero di nodi generati a partire da un nodo iniziale
- $d$: profondità della soluzione trovata

$b$* è  il **branching factor di un albero uniforme di profondità d che contiene N+1 nodi**.

E' utilizzato per valutare la bontà di una *funzione euristica*, è un numero reale che più si avvicina a 1, più indica che l'*euristica* è indicata per risolvere il problema.
Avere un branching factor pari a 1 indicherebbe che abbiamo un albero che costituisce un'unica sequenza di passi da effettuare.

# Ricerca con Avversario
La Ricerca con Avversario ci sposta in un **contesto multiagente**: quest'ultimo potrebbe essere *collaborativo*, ma noi studiamo il caso in cui vi sono **2 agenti con obiettivi conflittuali**.
Questi problemi sono talvolta chiamati **giochi**: noi affronteremo il caso di **giochi a turni**.

I giochi a turni sono i più semplici da affrontare in quanto non si deve affrontare un problema dove lo stato dell'ambiente può mutare in tempo reale: è il caso del gioco del Tris.

Le Strategia di Ricerca con Avversario introducono una **Funzione di Utilità**:
**valuta gli stati terminali** di ogni azione mappandolo con un valore talvolta intero che, se positivo rappresenta un "premio", se negativo una situazione di perdita.

Cosa si intende per "stati terminali"?
Il contesto multiagente impone che, per esempio nel tris, dopo la nostra azione, lo stato successivo non sarà più determinato da noi, ma bensì dall'agente avversario: sarà quindi necessario per le Strategia di Ricerca con Avversario andare a valutare tutti i possibili stati che potrebbe causare l'avversario dopo una scelta.

## Giochi
I giochi sono quindi **contesti multiagente** dove gli agenti hanno goal conflittuali.
Sono classificabili secondo le seguenti proprietà:
- **A informazione perfetta / imperfetta**: caratteristica per la quale gli agenti sono in possesso di tutte le informazioni utili a poter effettuare una decisione all'interno dell'ambiente
- **Effetti della scelta deterministici / stocastici**: caratteristica per la quale la scelta intrapresa da un agente porta ad un solo stato oppure può portare a diversi stati

|  | Informazione Perfetta | Informazione Imperfetta |
|---|---|---|
| **Deterministico** | Scacchi | Master Mind |
| **Stocastico** | Monopoli | Poker |


### Teoria delle Decisione nell'ambito dei Giochi a Somma Zero
**Giochi a Somma Zero**: sono giochi dove il guadagno di un agente è compensato dalla perdita di altri.
E.G.: se c'è una torta e due agenti, se uno dei due mangia metà torta, questo avrà guadagnato quella metà, e il suo guadagno è compensato dalla perdita di metà torta dell'avversario.

La teoria della decisione studia **gli approcci alla decisione**:
- **Appoccio Maximax**: è un approccio **ottimistico**, sceglie sempre il **massimo guadagno** per scelta possibile
- **Approccio Minimax**: è un approccio **pessimistico**, sceglie sempre la **minima perdita** per scelta possibile
- **Minimax Regret**: è un approccio di **pentimento minimo**, calcola il **Best Regret**:
  $$\text{Best Regret}= \text{Best Payoff} - \text{Real Payoff}$$
  e computa una **tabella dei pentimenti**.
  Una volta computata, sceglie il **pentimento massimo minimo**.
  Massimo rispetto ai pentimenti possibili dopo le azioni degli altri agenti data un'azione, minimo rispetto agli altri pentimenti massimi derivanti dalle altre azioni.
  
Durante la trattazione della teoria delle decisioni nell'ambito dei Giochi a Somma Zero, ci utilizzeremo i seguenti termini per indicare con:
- **MAX**: il giocatore che vogliamo aiutare a scegliere la mossa
- **MIN**: il giocatore contro il quale gioca MAX, lo consideriamo un **avversario perfetto** durante la valutazione delle decisioni, e cioè per ogni suo nodo scegliamo come suo successore quello che mette *MAX* nella situazione peggiore
- **Nodo terminale**: nodo in cui è possibile calcolare una **funzione di utilità per MAX**.

**Funzione di utilità**: è una funzione applicabile solo ed esclusivamente ai nodi terminali, e deve esplicitare valori che rendano l'idea della condizione di vittoria rispetto a quella di sconfitta.
Un esempio può essere il seguente:

$$f_\text{utilità}(n_\text{terminale})= \begin{cases} 1 & \text{se rappresenta una vittoria di MAX } \\ 0 & \text{se rappresenta un pareggio} \\ -1 & \text{se rappresenta una sconfitta per MAX} \end{cases} $$
Gli algoritmi di Ricerca con Avversario sono strani perché **non ci danno una soluzione**, ma bensì **solo la mossa successiva da fare**.
Perché? Perché non possono sapere la mossa che farà l'avversario, non è detto che faccia la mossa che peggiora più di tutte la condizione di vittoria di MAX.

Se per i *nodi terminali* utilizziamo la *funzione di utilità* per capire quale siano i nodi terminali da prediligere, d'altro canto ci è necessario poter valutare i nodi intermedi di MAX e MIN.
Viene introdotta infatti una **funzione di valutazione dei nodi intermedi**:
$$\text{valore-minimax}(n)= \begin{cases} f_\text{utilità}(n) & \text{se } n \text{ è terminale} \\ \text{MAX}_{S\in\text{SUCC}(n)}(\text{valore-minimax}(S))  & \text{se è un nodo di MAX} \\ \text{MIN}_{S\in\text{SUCC}(n)}(\text{valore-minimax}(S))  & \text{se è un nodo di MIN} \end{cases} $$
E' facile notare che la considerazione di *MIN* come *avversario perfetto* è ben esplicitata in quanto, nel caso di un nodo di *MIN*, viene considerato come valore il minimo tra i valori della *funzione di utilità* per *MAX*.

Grazie alla funzione di utilità è possibile introdurre l'**Algoritmo Minimax**.

## Algoritmo Minimax
L'algoritmo Minimax è un algoritmo di ricerca con avversario che visita l'albero delle possibilità in profondità, da qui deriva l'estrema efficienza in termini di spazio.
E' facilmente implementabile grazie delle seguenti funzioni
```
function MINIMAX-DECISION(state) returns ACTION {
	v <- MAX_VALUE(state)
	return ACTION IN SUCCESSORS(state) WITH value v
}

function MAX_VALUE(state) returns UTILITY_VALUE {
	if(isTerminalState(state)) => return UTILITY_VALUE(state)
	v <- -∞
	for(a,s) IN SUCCESSORS(state)
		v <- MAX(v, MIN_VALUE(state))
	return v
}

function MIN_VALUE(state) returns UTILITY_VALUE {
	if(isTerminalState(state)) => return UTILITY_VALUE(state)
	v <- +∞
	for(a,s) IN SUCCESSORS(state)
		v <- MIN(v, MAX_VALUE(state))
	return v
}
//mappata in modo adatto al gioco di riferimento
function UTILITY_VALUE(state)
```

### Valutazione delle complessità di Minimax

- **Complessità temporale**: $O(b^m)$, perché **costruisce per intero l'albero** dove
  - $b$: branching factor *medio*
  - $m$: profondità massima dell'albero
- **Complessità spaziale**: 
  - $O(b*m)$ se *senza backtracking*
  - $O(m)$, se *con backtracking*

La complessità temporale ci impone di andare a cercare un'ottimizzazione dell'algoritmo.

## Algoritmo Minimax con Potatura Alfa-Beta
Osserviamo che durante la visita dell'albero **non vogliamo osservare tutti i percorsi di gioco**, ma bensì solo quelli **migliori nel caso sia una scelta di *MAX***, e quelli **peggiori nel caso sia una scelta di *MIN***.
Per raggiungere tale comportamento viene introdotto un **intervallo alfa-beta**:
$$\alpha|--------\text{ }|\beta$$
dove:
- $\alpha$: **minimo guadagno di *MAX***, detto anche **massimo lower bound**, è il valore che *MAX* ha tutto l'interesse di aumentare
- $\beta$: **massimo guadagno di *MIN***, detto anche **minimo upper bound**, è il valore che *MIN* ha tutto l'interesse di diminuire

Le firme dell' [[#Algoritmo Minimax]] diventano quindi le seguenti:
```
function ALPHA-BETA-DECISION(state, alpha, beta) returns ACTION {
	v <- MAX_VALUE(state)
	return ACTION IN SUCCESSORS(state) WITH value v
}

function MAX_VALUE(state, alpha, beta) returns UTILITY_VALUE {
	if(isTerminalState(state)) => return UTILITY_VALUE(state)
	v <- -∞
	for(a,s) IN SUCCESSORS(state)
		v <- MAX(v, MIN_VALUE(state, alpha, beta))
		if(v >= beta) => return v
		alpha = MAX(alpha, v)
	return v
}

function MIN_VALUE(state, alpha, beta) returns UTILITY_VALUE {
	if(isTerminalState(state)) => return UTILITY_VALUE(state)
	v <- +∞
	for(a,s) IN SUCCESSORS(state)
		v <- MIN(v, MAX_VALUE(state, alpha, beta))
		if(v <= alpha) => return v
		beta = MIN(beta, v)
	return v
}
//mappata in modo adatto al gioco di riferimento
function UTILITY_VALUE(state)
```
E' bene comprendere che quindi si aggiungo 2 ulteriori funzioni ai cicli di scorrimento dei successori:
- **Controllo del range**: se $v$ risulta rispettivamente *maggiore o uguale* oppure *minore o uguale* del limite opposto, allora abbiamo trovato una ramificazione che **non vale la pena esplorare**
- **Aggiustamento del range**: se $v$ risulta rispettivamente *maggiore* oppure *minore* rispetto al limite analogo, lo aggiorniamo

### Valutazione delle complessità di Minimax con Potatura Alfa-Beta
- **Complessità temporale**: 
  - $O(b^{3/4m})$ nel **caso peggiore**
  - $O(b^{m/2})$ nel **caso medio**, grazie alle *Killer Moves*
- **Complessità spaziale**: 
  - $O(b*m)$ se *senza backtracking*
  - $O(m)$, se *con backtracking*

Le *Killer Moves* sono mosse precedentemente identificate come forti e che hanno portato a una potatura efficace durante la ricerca in alberi di gioco.

**Nonostante il miglioramento della complessità spaziale**,  *soprattutto nel caso medio*, anche questo algoritmo **non è sufficientemente veloce per i** **Giochi in Tempo Reale**.


## Giochi in Tempo Reale
I giochi in tempo reale sono dei giochi che impongono un limite di tempo per eseguire la mossa successiva, e gli algoritmi fino ad ora affrontati sono troppo lenti per farlo quando il nodo terminale è situato a grande profondità.
Introduciamo quindi una **funzione di valutazione per nodi intermedi** che entra in gioco **allo scadere del limite di tempo**, andando ad evitare di dover arrivare fino in fondo.

Esistono diversi approcci per affrontare i giochi in tempo reale:
1. **Strategia 1 - Tecniche di Apprendimento Automatico per la Sintetizzare la Funzione di Utilità**: consiste nell'etichettare tutti gli stati possibili di gioco, e salvarne l'etichettatura in una base di dati, con una **funzione costruita per approssimare l'obiettivo.**
2. **Strategia 2 - Identificazione delle caratteristiche rilevanti**: questo approccio richiede il coinvolgimento di un esperto del settore per andare a
   - **Identificare le caratteristiche misurabili rilevanti degli stati**, $f_i$
   - **Attribuire un peso alle caratteristiche misurabili**, $w_i$
   - **Formulare la combinazione lineare:** $$\text{EVAL}(S)=\sum_{i=1}^{n} (f_i \cdot w_i)$$
dove $n$ è il numero delle caratteristiche rilevate.

Implementare queste strategie come adattamento per i giochi in tempo reale comporta la modifica del codice dell'algoritmo Minimax, che non dovrà più controllare se il nodo sia terminale, ma dovrà effettuare un $\text{TEST-TAGLIO}(\text{stato}, ...)$  sulla base della profondità, tempo passato, ...

**Entrambe le funzioni di valutazione** rispondono con il valore della funzione di utilità più probabile, si tratta di una **misura probabilistica**: l'algoritmo **costruisce l'albero finché ha tempo**, e poi restituisce l'approssimazione da adottare.

L'aspetto probabilistico è problematico perché introduce al **Problema dell'Orizzonte**.
Un nodo è detto:
- **Quiescente**: quando, se promettente o negativo, scendere al sottoalbero non comporta uno stravolgimento della situazione
- **Non Quiescente**: quando, se promettente o negativo, scendere al sottoalbero con le immediate mosse successive comporta uno stravolgimento della situazione

Il **Problema dell'Orizzonte** consiste nel fatto che l'algori


### Tabelle di Trasposizione
Le tabelle di trasposizione tengono traccia delle sequenze di mosse che portano da uno stato $S$ ad $S'$ per efficientare la ricerca nello spazio degli stati, evitando di rivalutare un percorso.
*E.G. Dati* $S \rightarrow (ABC) \rightarrow S'$ e $S \rightarrow (BCA) \rightarrow S'$, $ABC$ e $BCA$ *sono dette trasposizioni*.


# CSP - Problemi di Soddisfacimento di Vincoli
I CSP, *Constraint Satisfaction Problems* sono dei problemi di ricerca nello spazio degli stati composti dai seguenti elementi:
1. **Insieme di variabili**
2. **Insieme di vincoli**
3. **Dominio delle variabili**

E' possibile riformulare la composizione dei CSP dicendo che è formato da 2 elementi tra i quali un **Insieme di variabili con ognuna il proprio dominio**.

I CSP consistono nel trovare un **assegnamento $\{x_1=v_1, x_2=v_2, ..., x_n=v_n\}$ di tutte le variabili che soddisfa i vincoli**.
Un assegnamento è detto:
- **Assegnamento vuoto**: $\{\ \}$, se non ha assegnato alcun valore ad alcuna variabile
- **Assegnamento Completo:** $\{x_1=v_1, x_2, ..., x_n=v_n\}$, se ha assegnato un valore a tutte le variabili
- **Assegnamento Consistente**: $\{x_1 = v_1, x_2=v_2\}$, se ha assegnato dei valori alle variabili che rispettano i vincoli
- **Soluzione**:  $\{x_1=v_1, x_2, ..., x_n=v_n\}$, se ha assegnato a tutte le variabile un valore che rispetta i vincoli, e cioè **se è Completo e Consistente**.

N.B. $Completo \nRightarrow Consistente \land Consistente \nRightarrow Completo$ !

I CSP sono problemi nella quale siamo coinvolti quotidianamente:
- *Gestione degli Orari*: dai semplici *Orari Scolastici* alla gestione degli *Equipaggi delle Linee Aeree*...
- *Logistica*: gestione dei vincoli di tempo per la consegna e  i vincoli fisici imposti dal voler sfruttare al massimo lo spazio nei mezzi di trasporti
- *Gestione Produttiva*: per efficientare l'utilizzo delle risorse di produzione come la *Stoffa in Sartoria* oppure la *[produzione di segnali stradali](https://youtu.be/_Gu1_S1SIeg?t=686)*.

Un esempio di CSP introduttivo è il [[Problema dell'Australia]].

#### CSP come Problema di Ricerca in uno Spazio di Stati 
Potrebbe risultare controintuitivo considerare i CSP come dei problemi di ricerca nello spazio di stati, ma è in realtà se riprendiamo la forma di [[#Istanza di un problema]]
$$ <s_i, f_s, t_o, f_c> $$
dove
- $s_i$: $\{\ \}$, è sempre l'*Assegnamento Vuoto*
- $f_s$: assegnamento di un valore ad una variabile
- $t_o$: controllo che l'assegnamento sia *Completo* e *Consistente*
- $f_c$: è inutilizzata in questo caso, l'assegnamento di un valore ad una variabile ha costo costante, solitamente si dice $f_c=1$ 

Notiamo sin da subito che i CSP hanno un **forma estremamente standardizzata** e che
 - La **profondità massima $m$** è sempre il **numero di variabili**
 - L'**ordinamento degli assegnamenti è ininfluente**

L'ininfluenza degli assegnamenti è una diretta conseguenza della **proprietà commutativa dei CSP**.
Dati $A_i = \{x_1=v_1, x_2=v_2\}, A_j=\{x_2=v_2,x_1=v_1\}$, allora $A_i$ e $A_j$ sono lo stesso assegnamento. 

#### Domini delle Variabili di un CSP
E' opportuno, durante la formulazione di un CSP, andare a verificare il dominio delle sue variabili, che può essere:
- **Dominio Booleano**: solo 2 valori, $True\ False$ oppure $0\ 1$
- **Valori Discreti con Dominio Finito**: come nelle *Enumerazioni di Costanti*
- **Valori Discreti con Dominio Infinito**: per esempio $\forall x \in \mathbb{Z}$ 
- **Valori Continui**: per esempio $\forall x \in \mathbb{R}$

Si può notare come ognuno dei dominio sia sottoinsieme dell'altro.

L'importanza della definizione del dominio delle variabili deriva dal fatto che ogni dominio abbia un proprio linguaggio di specifica.
Prendendo in esempio i **Valori Discreti con Dominio Infinito**, potrebbe per esempio modellare i valori interi al numero dei giorni e formulare con
$$ Task_1 + 5 < Task_2$$
che $Task_2$ debba essere schedulata 5 giorni dopo $Task_1$. 

#### Vincoli e Criteri di Preferenza
I vincoli sono classificati sulla base del numero di variabili che coinvolgono:
- **Unari**: $Età \geq 18$, coinvolgono una sola variabile
- **Binari**: $WA\neq NT$, coinvolgono due variabili
- **Con 3 o più variabili**: non li affrontiamo perché è dimostrabile che ogni vincolo di 3 o più variabili possa essere ricondotto ad un sistema di vincoli unari e binari, ma sono molto comuni per esempio nella *Cripto-aritmetica*.

E' bene distinguere i vincoli dai criteri di preferenza:
- **Vincolo**: condizione **obbligatoria**, una soluzione deve rispettarla per essere tale
- **Criterio di preferenza**: condizione **morbida**, può essere utilizzata per effettuare un ranking delle soluzioni, ma **può essere violato**.

I vincoli sono talvolta visualizzabili e gestibili attraverso il [[Grafo dei Vincoli]].

### Strategie di Ricerca per CSP
Durante il corso utilizzeremo il [[Problema delle 8 Regine]] come esempio per comparare le diverse strategie di ricerca per CSP, che sono:
- [[Generate & Test]], che genera casualmente gli assegnamenti
- [[Backtracking Search per CSP]], che sfrutta la proprietà di commutatività dei CSP
- [[Backtracking Search per CSP con Inferenza]]

#### Euristiche per CSP
Le Euristiche per CSP sono utili per efficientare la ricerca nello spazio degli stati, e sono usate nel seguente ordine:
1. **Minimum Remaining Values (Fail First)**: seleziona la variabile con il minor numero di valori rimanenti nel suo dominio. 
   Questa euristica permette di andare a verificare più velocemente se il percorso che si sta ricercando sia fallimentare. [[Esempio Minimum Remaining Values - Fail First|Esempio]].
2. **Euristica di Grado**: seleziona la variabile coinvolta in un numero massimo di vincoli con altre variabili non ancora assegnate.
   Questa euristica punta a ridurre le interazioni tra variabili non ancora assegnate, considerando le variabili con più vincoli come più problematiche. [[Esempio Euristica di Grado per CSP|Esempio]].
3. **Euristica del Valore Meno Vincolante**: seleziona il valore che viola meno vincoli per la variabile attuale.
   Questa euristica si pone come obiettivo quello di voler lasciare quanti più valori disponibili alle restanti variabili non assegnate, dopo l'assegnamento del valore scelto. [[Esempio Euristica valore meno vincolante|Esempio]].

### Modalità di Inferenza
L'Inferenza è un modo per propagare attraverso i vincoli e le proprietà dei CSP le informazioni attualmente in possesso, andando a ridurre lo spazio di ricerca attraverso delle deduzioni logiche che ne conseguono.

Le proprietà utilizzate come modalità per fare inferenza sono:
- **[[Forward Checking]]**, *più un approccio che una proprietà*, relativo ai nodi adiacenti 
- **[[Node Consistency]]**, relativo ai vincoli unari
- **[[Arc Consistency]]**, relativo ai vincoli binari
- **Path Consistency**











