### Recursive Best-First Search
E' una [[Intelligenza Artificiale#Strategie di Ricerca Informate|Strategia di Ricerca Informata]] ed è un'approssimazione di [[A-star|A*]].
Abbiamo determinato che [[A-star|A*]] sia ottimamente efficiente, e cioè che non esiste nessun altro algoritmo ottimo che garantisce di espandere meno nodi di [[A-star|A*]]: ma ha un problema.
Nonostante l'efficienza dell'algoritmo, **occupa tantissima memoria**.

**RBFS**, in quanto approssimazione, **usa meno memoria di** [[A-star|A*]] **basandosi sulla [[Ricerca in profondità]]**.

### Difficoltà nella determinazione delle complessità
Considerando che può esplorare nuovamente nodi precedentemente visitati e cancellati dalla memoria, risulta complicato andare a determinare la complessità dell'algoritmo.

## Funzionamento
Si procede con il visitare l'algoritmo con la seguente firma:
$$\text{RBFS}(n, F(n), B)$$ dove:
- $n$: nodo
- $F(n)$: funzione di valutazione
- $B$: **upper bound**, cioè il limite di costo che tiene **traccia del secondo percorso migliore** al momento dell'esplorazione

RBFS procede con l'espandere il percorso con il costo minore, ma confronta ogni volta il costo con il successore del percorso espanso con quello del secondo percorso migliore.
Nel caso i successori del percorso offrano un costo maggiore rispetto al secondo, cancella dalla memoria il percorso attuale e continua con il secondo: aggiorna proceduralmente i costi sulla base delle informazioni che ottiene esplorando i nodi.
**Non è richiesto all'esame, ma ecco lo pseudocodice**.

### Implementazione
La chiamata iniziale sarà: $\text{RBFS}(n_\text{radice}, f(n_\text{radice}), \infty)$.
Notare bene che come funzione di valutazione di passa la funzione statica f(n) per la prima chiamata.

```
IF f(N)>B, return f(N) // la fz. val. supera il limite superiore, cambia percorso
IF N is a goal, EXIT algorithm // successo!
IF N has no children, RETURN infinity // vicolo cieco, cambia percorso
FOR each child Ni of N, // inizializza F(.) per i successori di N
 IF f(N)<F(N), F[i] := MAX(F(N),f(Ni)) // N è il nodo padre, su cui siamo focalizzati
 ELSE F[i] := f(Ni)
sort Ni and F[i] in increasing order of F[i] // ordinamento per F crescenti, dopo
 // F[1] sarà l’F del figlio più promettente
IF only one child, F[2] := infinity
WHILE (F[1] <= B and F[1] < infinity) // discesa ricorsiva solo se upper bound rispettato
 F[1] := RBFS(N1, F[1], MIN(B, F[2])) // applico ricorsivamente RBFS
 insert N1 and F[1] in sorted order
return F[1] 
```


