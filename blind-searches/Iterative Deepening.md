E' una [[Intelligenza Artificiale#Strategie Blind|Strategia Blind]] che migliora la [[Ricerca in profondità]], e in particolare la sua [[Ricerca in profondità#Variante con limite artificiale|variante con limite artificiale]].
Il problema della [[Ricerca in profondità]] è quello in cui un ramo di un albero che sta visitando in profondità ha una profondità infinita: non cessa più di approfondire la ricerca, e se magari in quel ramo non vi sono test obiettivo, non restituirà mai un risultato.
L'Iterative Deepening ovvia ai problemi derivanti dal limite artificiale, e itera aumentando il limite artificiale ad ogni fallimento nella ricerca.

## Implementazione
```
ID_RICERCA(Problema) RETURNS Soluzione, Fallimento
{
	FOR(PROFONDITA' <- 0 TO +INFINITY) DO
		RISULTATO <- RICERCA_PROF_LIMITATA(Problema, PROFONDITA')
		IF(RISULTATO != TAGLIO)
			RETURN RISULTATO
}
```

## Criteri di valutazione della strategia di ricerca
- **Completezza**: se $b$, il *branching factor*, è $<+\infty$, e cioè *finito*.
- **Ottimalità**: **è ottimale solo se il costo del cammino è una funzione monotona crescente della profondità** (es. tutte le azioni hanno lo stesso costo).
- **Complessità temporale**: $O(b^d)$, in quanto esplorerà tutto l'albero nel caso peggiore, dove:
  - $b$: branching factor
  - $d$: profondità minimale del goal
- **Complessità spaziale**: 
  - **senza Backtracking**: $O(b*d)$, perché occorre mantenere in memoria tutti i nodi del cammino esplorato ed i loro fratelli.
  - **con Backtracking**: $O(d)$, perché mantiene in memoria strettamente i nodi in concomitanza dell'accesso in profondità.
Come possiamo notare, prende gli aspetti migliori dalla [[Ricerca in ampiezza]], quali la completezza maggiore, una migliore ottimalità, arrivando ad essere addirittura migliore nella complessità temporale perché arrivato alla profondità $d$, non genera anche i nodi alla profondità $d+1$ e li unisce all'estrema efficienza di memoria della [[Ricerca in profondità]].