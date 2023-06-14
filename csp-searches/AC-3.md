AC-3 è un **algoritmo non-completo** che sfrutta la proprietà di [[Arc Consistency]] per fare [[Intelligenza Artificiale#Modalità di Inferenza|Inferenza]].

L'algoritmo AC-3 paga la sua semplicità con la **non-completezza**: esistono dei CSP inconsistenti, e cioè non risolvibili, che AC-3 non riesce a rilevare. Sostanzialmente **non riesce a capire durante il pre-processing che il problema non ha soluzione**.
![[ac-3-1.svg]]
Questo [[Grafo dei Vincoli]] è [[Arc Consistency|Arc-Consistent]], ma il CSP non è risolvibile!
### Pseudocodice

```
AC-3(CSP)
queue <- tutti gli archi del CSP in maniera direzionata
while(queue not empty)
	{x_i, x_j} <- pop_front arco direzionato da xi a xj in queue
	if(remove_inconsistent_values tra xi e xj)
		foreach(x_n in neighbours di x_i)
			aggiungo alla queue {x_n, x_i}

--

//ritorna true se rimuove qualcosa
remove_inconsistent_values(source, dest){
	removed <- false
	foreach x in domain(source)
		if(domain(dest) non avrebbe valori validi se source=x)
			delete x from domain(source)
			removed <- true
	return removed
}

```
