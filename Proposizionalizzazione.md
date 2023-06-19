E' un metodo di [[Intelligenza Artificiale#Ragionamento su FOL|Ragionamento su FOL]].

L'idea è quella di "trasformare in [[Intelligenza Artificiale#Logica Proposizionale|Logica Proposizionale]].
Si parte da una $\text{KB}_{FOL}$, base di conoscenza in [[Intelligenza Artificiale#Logica del Prim'Ordine (FOL)|FOL]], e ci chiediamo se non sia possibile passare da questa ad un'analoga $\text{KB}_{LP}$ *(LP=Logica Proposizionale)*.
La nostra ambizione sarebbe quella di poter utilizzare l'ottenuta $\text{KB}_{LP}$ per poter applicare metodi di ragionamento per Logica Proposizionale come il [[Intelligenza Artificiale#Forward Chaining|Forward Chaining]] e [[Intelligenza Artificiale#Backward Chaining|Backward Chaining]].


Sappiamo che le formule nella Logica del Prim'Ordine possono contenere simboli e costrutti che non sono presenti nella Logica Proposizionale.



### Regola di Istanziazione Universale
E' una [[Regola di Inferenza]] che opera per tradurre il quantificatore $\forall$ all'interno di un modello della [[Intelligenza Artificiale#Logica Proposizionale|Logica Proposizionale]].
$$\frac{\forall x\ \alpha}{\text{SUBST}(\{x/g\}, \alpha)}$$
dove $\alpha$ è una **qualunque formula ground** in Logica del Prim'Ordine.

### Regola di Istanziazione Esistenziale
E' una [[Regola di Inferenza]] che opera per tradurre il quantificatore $\exists$ all'interno di un modello della [[Intelligenza Artificiale#Logica Proposizionale|Logica Proposizionale]].
$$\frac{\exists x\ \alpha}{\text{SUBST}(\{x/k\}, \alpha)}$$
dove $\alpha$ è una **qualunque formula ground** in Logica del Prim'Ordine e
$k$ è **una costante nuova, cioè non ancora utilizzata nella KB**, perché potrebbe portare a una sovrapposizione di significato tra l'oggetto rappresentato dalla costante k precedente e l'oggetto istanziato tramite la regola di istanziazione esistenziale.

A causa di questa limitazione, l'inferenza si limita a dare un nome a questo elemento.
Possiamo inferire $Corona(C1) \land SullaTesta(C1, John)$ dove $C1$ è un nome di costante nuovo inventato appositamente tramite un processo detto **Skolemizzazione**. 

### Differenza tra UI e EI
*(UI = Universal Instantiation, EI = Universal Instantiation)*
- **UI**: le formule quantificate universalmente hanno tante istanze prodotte, e la $\text{KB}_{LP}$ ottenuta è **logicamente equivalente a quella originaria**
- **EI**: le formule quantificate esistenzialmente, purtroppo, **non produce una $\text{KB}_{LP}$ logicamente equivalente**.

## Inefficienza della Proposizionalizzazione
Se consideriamo la $\text{KB}$:
- $\forall x,  \text{Re}(x)\land \text{Avido}(x) \Rightarrow \text{Malvagio}(x)$
- $\text{Re}(\text{John})$
- $\text{Avido}(\text{John})$
- $\text{Fratello}(\text{John},\text{Richard})$

la proposizionalizzazione creerà:
- $\text{Re}(\text{Richard})\land \text{Avido}(\text{Richard}) \Rightarrow \text{Malvagio}(\text{Richard})$
- $\text{Re}(\text{John})\land \text{Avido}(\text{John}) \Rightarrow \text{Malvagio}(\text{John})$
- $\text{Re}(\text{John})$
- $\text{Avido}(\text{John})$

andando a **perdere tempo creando istanze dell'implicazione ininfluenti** come quella di Richard.


## Herbrand e Semidecidibilità
La proposizionalizzazione consiste nel:
1. Convertire una data $KB_{FOL}\rightarrow KB_{LP}$
2. Applicare all'ottenuta $KB_{LP}$ un qualsiasi algoritmo completo per la ricerca nella Logica Proposizionale, come per esempio il [[Intelligenza Artificiale#Model Checking|Model Checking]] oppure il [[Intelligenza Artificiale#Theorem Proving|Thereom Proving]].

Sorge spontanea una domanda: come possiamo affrontare la traduzione di **funzioni applicate ricorsivamente** in Logica Proposizionale?

**[Herbrand](https://it.wikipedia.org/wiki/Jacques_Herbrand)** ha dimostrato come, **se una formula è conseguenza logica della knowledge base originale (in FOL) allora è possibile dimostrare la sua verità in passi finiti**, costruendo i termini ground in ampiezza in questo modo:
1. Si procede provando a sostituire le variabili con le costanti, *esempio: *$\{x/Richard\}, \{x/John\}$
2. Senza successo, si provano le sostituzioni con termini ground che prevedono una sola applicazione delle funzioni, *esempio:* $\{x/fz(Richard)\}, \{x/fz(John)\}$
3. Senza successo, quelle con una chiamata ricorsiva, *per esempio:* $\{x/fz(fz(Richard))\}, \{x/fz(fz(John))\}$
4. *etc... etc...*


> **Enunciato di Herbrand**
> Se $KB_{FOL}\vDash F \Rightarrow KB_{LP}\vdash F$ in passi finiti 

Conseguenza con tale dimostrazione che la **FOL è semidecidibile**:
- **Completa**: se una formula consegue da $KB_{FOL}$
- **Incompleta**: **se non vale la consequenzialità**, allora la presenza di funzioni chiamate ricorsivamente porterà l'**inferenza su un percorso infinito**

In quanto semidecidibile, **non esiste quindi un algoritmo per dimostrare che una certa conseguenza in FOL non valga**.


