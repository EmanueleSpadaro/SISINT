E' una [[Intelligenza Artificiale#Strategie Blind|strategia di ricerca Blind]] che parte dallo stato inziale $s_i$ , poi si espande verso i suoi successori, successivamente verso tutti i discendenti del secondo livello, etc...

![[breadth-first-search.png]]
## Funzionamento
Si parte creando il nodo dello stato iniziale, lo si visita, e verosimilmente non sarà uno stato obiettivo, quindi si aggiungono tutti i suoi figli alla frontiera.
Si visitano tutti i suoi figli, e per ognuno di questi si aggiungono i conseguenti figli alla frontiera.
Qualora non si abbia ancora trovato uno stato obiettivo, si visitano i conseguenti figli.
## Implementazione
**Frontiera**: si implementa come **CODA FIFO**, ogni volta che si esplora un nodo si aggiungono i relativi figli prima di passare al nodo successivo.

## Criteri di valutazione della strategia di ricerca
- **Completezza**: se il *branching factor* è $<+\infty$, e cioè *finito*.
- **Ottimalità**: in generale **NO**, ma **è ottimale solo se il costo del cammino è una funzione monotona crescente della profondità** (es. tutte le azioni hanno lo stesso costo).
- **Complessità temporale**: $O(b^{d+1})$ dove
  - $b$: branching factor
  - $d$: profondità minimale del goal
- **Complessità spaziale**: $O(b^{d+1})$ perché tutti i nodi della frontiera e tutti i loro antenati vanno mantenuti in memoria

E' un algoritmo con delle caratteristiche positive quali la semplicità di implementazione, ma all'atto pratico nel caso in cui la ricerca di debba estendere in profondità assume temporalmente e spazialmente valori inaccettabili.

Avendo $O(b^{d+1})$ come complessità temporale e complessità spaziale:
supponiamo che:
- il branching factor b=10
- che vengano generati 10.000 nodi/sec
- un nodo occupi 1000 byte
![[breadth-complexity-table.png]]



