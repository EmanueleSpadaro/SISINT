L'algoritmo di Backtracking Search per CSP con **Inferenza** è una [[Intelligenza Artificiale#Strategie di Ricerca per CSP|Strategia di Ricerca per CSP]] che **aggiunge un layer di Inferenza** alla **[[Backtracking Search per CSP]]**.
In parole povere, seleziona una variabile usando *MVP (Fail First) e Euristica di Grado*, prova i relativi valori ordinandoli con l'*Euristica del Valore Meno Vincolante*, e non appena trova un valore consistente con i vincoli li propaga grazie all'inferenza. 

### Cos'è l'Inferenza?
L'inferenza è la propagazione delle informazioni ottenute dai vincoli in fase di valutazione di un assegnamento.
Immagina che tu abbia un puzzle davanti a te, con molti pezzi che devi mettere insieme per formare un'immagine. Ogni pezzo ha una forma e una posizione specifica in cui può essere collocato.

Quando inizi a risolvere il puzzle, puoi iniziare a fare alcune "**inferenze**" osservando i pezzi che sono già stati posizionati correttamente. Ad esempio, se vedi che un pezzo di un albero è già al posto giusto, puoi "inferire" che gli altri pezzi dell'albero non possono andare nella stessa posizione, altrimenti non si incastrerebbero correttamente.

Nel contesto della Backtracking Search per i CSP, l'**inferenza** funziona in modo simile. Quando proviamo a risolvere un problema di CSP, dobbiamo trovare valori che soddisfino le regole e i vincoli del problema. A volte, però, potrebbe non essere immediatamente evidente quale valore debba essere assegnato a una variabile.

Qui entra in gioco l'inferenza. **Utilizzando la conoscenza dei vincoli tra le variabili, possiamo fare deduzioni logiche per ridurre il numero di valori possibili per una variabile**. Ad esempio, se sappiamo che due variabili non possono avere lo stesso valore, possiamo eliminare dalla considerazione alcuni valori che violerebbero questa regola.

L'inferenza nella Backtracking Search per i CSP **ci aiuta a prendere decisioni più informate e a ridurre lo spazio di ricerca**. Ci permette di esplorare solo le soluzioni che rispettano le inferenze fatte finora, evitando di sprecare tempo a esaminare opzioni che sappiamo già essere incompatibili.

In conclusione, l'inferenza nella Backtracking Search per i CSP è come fare deduzioni logiche basate sui vincoli del problema, in modo da ridurre le possibilità e arrivare più velocemente a una soluzione corretta. È come mettere insieme i pezzi di un puzzle, osservando quelli che sono già al posto giusto per capire dove devono andare gli altri.

## Effetti sullo Pseudocodice
Lo pseudocodice della [[Backtracking Search per CSP]] subisce delle lievi modifiche per andare ad implementare l'inferenza al suo interno.

```
BACKTRACK_SEARCH_CON_INFERENZA(CSP, ASSEGNAMENTO)
if (ASSEGNAMENTO COMPLETO)
	return ASSEGNAMENTO
var <- SELEZIONA_VARIABILE_NON_ASSEGNATA(CSP) //MVP (Fail-First) + Grado
foreach value in ORDERED_DOMAIN_VALUES(var, csp, assignment) //Meno Vincolante
	if(value consistente con assegnamento & vincoli)
		AGGIUNGI {var = value} ALL'ASSEGNAMENTO
		inferenze <- INFERENZA(csp, var, valore)
		if inferenze != fallimento //se non portano ad una dead-end
			aggiungi inferenze ad assegnamento
			risultato <- BACKTRACKING_SEARCH_CON_INFERENZA(CSP, ASSEGNAMENTO)
			if(risultato != fallimento)
				 => return risultato
	rimuovi {var = valore} e inferenze da assegnamento
```