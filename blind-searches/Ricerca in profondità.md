E' una [[Intelligenza Artificiale#Strategie Blind|Strategia Blind]] che ha un approccio opposto a quello della [[Ricerca in ampiezza]].
Visita lo stato inziale $s_i$ , poi **si espande nei** **nodi più profondi**, e cioè quelli **più distanti dalla radice**.
Esplora fino a quando si raggiunge un nodo foglia, quindi senza successori, e "torna indietro" per esplorare le eventuali alternative.

Esiste in due alternative:
- **Senza backtracking**: i nodi vengono creati *in memoria* subito, ma esplorati solo quando sono senza figli.
  Nell'esempio sottostante quindi, si visita S e si aggiungono A, B, C ad una vera e propria struttura dati di tipo *stack*.
- **Con backtracking**: i nodi vengono creati *in memoria* solo quando necessario.
  Anziché avere una struttura dati di tipo *stack*, si utilizzano delle *funzioni ricorsive*, andando quindi a sfruttare lo *stack delle funzioni*.
  E' più efficiente per quanto riguarda la memoria perché crea i nodi solo quando necessario, e a ritroso.

## Implementazione
**Frontiera**: si implementa come **CODA LIFO**.
Ogni volta che si esplora un nodo si aggiungono i relativi figli, se ne ha, prima di passare al nodo successivo nella coda.

![[depth-first-search-no-backtrack.png]]

## Criteri di valutazione della strategia di ricerca
- **Completezza**: se persistono le seguenti condizioni
  - $b$, il *branching factor*, è $<+\infty$, e cioè *finito*.
  - $m$, la *profondità massima dell'albero di ricerca*, è $<+\infty$, e cioè *finita*.
- **Ottimalità**: **NO**, non ha alcun meccanismo di orientamento per i costi, cerca esclusivamente una soluzione.
- **Complessità temporale**: $O(b^m)$, in quanto esplorerà tutto l'albero nel caso peggiore.
- **Complessità spaziale**: 
  - **senza Backtracking**: $O(b*m)$, perché occorre mantenere in memoria tutti i nodi del cammino esplorato ed i loro fratelli.
  - **con Backtracking**: $O(m)$, perché mantiene in memoria strettamente i nodi in concomitanza dell'accesso in profondità.

### Variante con limite artificiale
Per evitare che la ricerca entri in percorsi infiniti dovuti alla profondità dell'albero di ricerca, si introduce in maniera artificiosa un limite $l$ tale per cui:
- Un nodo $n$ viene espanso nei suoi successori solo se la sua profondità $p_n < l$
- Altrimenti viene trattato come un nodo foglia, quindi esplorato
Questa variante **riduce però la *Completezza*** in quanto la profondità $p_g$ dell'obiettivo non è nota a priori, e potrebbe trovarsi ad una profondità maggiore del limite impostato.
Se invece il limite $l >> p_g$, allora **si perde efficienza**.
Questa variante rappresenta il punto di transizione tra la [[Ricerca in profondità]] e l'[[Iterative Deepening]].