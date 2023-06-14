E' una [[Intelligenza Artificiale#Strategie Blind|Strategia Blind]] **aggiuntiva**, in quanto implementa due ricerche:
- Dallo stato iniziale al goal, detta **forward search**
- Dal goal allo stato iniziale **backward search**
La strategia termina quando le frontiere delle due ricerche si incontrano, e cioè $F_{fw}$ e $F_{bw}$, frontiere delle rispettive ricerche, abbiano intersezione vuota.
$$F_{fw}\cap F_{bw}\neq\varnothing$$
L'ambizione della ricerca bidirezionale sarebbe quella di far partire parallelamente la *forward search* e la *backward search*, per **dimezzare i tempi di ricerca** andando ad unire la sequenza ottenuta dalle due ricerche al momento di intersezione delle frontiere.
### La funzione successore inversa
L'implementazione dell'istanza di un problema, avente la solita struttura $<s_i, f_s, t_o, f_c>$, ha una funzione successore $f_s(s,a)=s'$ che ha una sua *direzionalità*: ci permette di capire che da uno stato $s$ attraverso l'azione $a$ è possibile raggiungere $s'$, ma non il contrario.
Questa caratteristica ci impone di introdurre una funzione inversa:
$$f'(s', a) = s$$
L'introduzione di tale funzione però introduce diversi problemi:
- **Introduzione di un nodo fittizio**: per implementare la ricerca al contrario, nel caso generale in cui $G$, insieme degli stati goal, abbia $|G| > 1$, e quindi più di uno stato obiettivo, **si introduce un  nodo fittizio che abbia una transizione verso tutti gli stati goal**.
- **Non determinismo**: se  $\exists s_1,s_2\text{ , stati, }| s_1\neq s_2 \wedge f(s_1,a)=f(s_2,a)=s'$, allora la nostra funzione inversa sarà non deterministica, in quanto con la stessa azione, tornando indietro, si possono raggiungere due o più stati differenti.
## Casi d'uso consigliati
Questa strategia è fortemente consigliata con [[Intelligenza Artificiale#Strategie Blind|Strategie Blind]] che non si focalizzano in profondità, ma bensì in ampiezza.
Il problema di avere una strategia fortemente direzionale è evidente nel caso in cui le ricerche parallele intraprendono percorsi che non avranno praticamente mai intersezione, andando effettivamente a rendere invano il punto di forza di lavorare in parallelo: è come se lavorassero da sole.

![[bidirectional-search-depth.drawio.svg]]

In caso di [[Ricerca in ampiezza]] o simili, invece, la ricerca assume un carattere differente come qui descritto:

![[bidirectional-search-breadth.drawio.svg]]
andando a trovare con molta più facilità un'intersezione.

## Criteri di valutazione della strategia di ricerca
- **Completezza**: se il *branching factor* è $<+\infty$, e cioè *finito*.
- **Ottimalità**: in generale **NO**, ma **è ottimale solo se il costo del cammino è una funzione monotona crescente della profondità** (es. tutte le azioni hanno lo stesso costo).
- **Complessità temporale**: $O(b^{d/2})$ dove
  - $b$: branching factor
  - $d$: profondità minimale del goal
- **Complessità spaziale**: $O(b^{d+1})$ perché tutti i nodi della frontiera e tutti i loro antenati vanno mantenuti in memoria