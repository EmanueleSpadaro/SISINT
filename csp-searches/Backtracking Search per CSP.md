L'algoritmo di Backtracking Search per CSP è una [[Intelligenza Artificiale#Strategie di Ricerca per CSP|Strategia di Ricerca per CSP]] che sia basa sulla [[Intelligenza Artificiale#Strategie Blind|Strategia Blind]] della [[Ricerca in profondità]].

#### Considerazioni iniziali
E' possibile notare come i CSP, se visti come albero, abbiano:
- un **branching factor $b$ elevato**, pari al numero di mosse possibili
- **poca profondità $d$**, equivalente al numero di variabili

Con questa considerazione, possiamo calcolare il **Numero di Foglie di un CSP** con la seguente formula:
$$d!\ b^d$$
Nel caso del [[Problema dell'Australia]], per esempio, ci ritroveremo con $7!\ 3^7=11.022.480$ foglie.
![[Pasted image 20230613155836.png]]

Ricordando la [[Intelligenza Artificiale#Commutatività dei CSP|Commutatività dei CSP]], possiamo cambiare il nostro approccio all'assegnamento delle variabili **assegnando i valori una variabile alla volta**.

Così facendo, passiamo ad un numero di foglie nettamente inferiore: $b^d$.
Nel caso del [[Problema dell'Australia]], per esempio, ci ritroveremo con $3^7=2187$ foglie, molte meno rispetto a quelle iniziali!

## Funzionamento
Il funzionamento della Backtracking Search per CSP consiste nell'**assegnare un valore $v_i$ ad una variabile $x_i$ non assegnata per volta**, andando a **controllare il rispetto dei vincoli con tale assegnamento**.

## Pseudocodice
```
BACKTRACK_SEARCH(CSP, ASSIGNMENT)
if COMPLETE(ASSIGNMENT)
	=> return ASSIGNMENT
var <- SELECT_UNASSIGNED_VARIABLE(CSP)
foreach value in ORDER_DOMAIN_VALUES(VAR, ASSIGNMENT, CSP)
	if(value is consistent with assignment according to contraints of CSP)
		ADD {var, value} TO ASSIGNMENT
		result <- BACKTRACK_SEARCH(CSP, ASSIGNMENT)
		if(result != FAILURE)
			=> return result
		REMOVE {var, value} FROM ASSIGNMENT
```

Seppur teniamo conto della commutatività dei CSP e del fatto che la soluzione debba essere completa, nello Pseudocodice è possibile notare 3 punti fondamentali:
- **SELECT_UNASSIGNED_VARIABLE**: è il punto in cui l'algoritmo seleziona una variabile senza ancora alcun assegnamento.
  Possiamo implementarlo in modo che ritorni la variabile più critica in termini di assegnamento per raggiungere una soluzione
- **ORDER_DOMAIN_VALUES**: è il punto in cui, data una variabile, ritorniamo in maniera ordinata i valori che può assumere.
  Possiamo implementarlo in modo che ritorni in maniera ordinata i valori, da quello più probabile che porti alla soluzione a quello minormente probabile.
- **VALUE IS CONSISTENT WITH ASSIGNMENT ACCORDING TO CONSTRAINTS OF CSP:** è il punto in cui verifichiamo che il valore che stiamo cercando di aggiungere all'assegnamento non lo renda inconsistente con i vincoli del CSP.
  E' importante perché ci fa capire che si tratta ancora di un **Algoritmo Blind** in quanto **la conoscenza è usata solo per tagliare i percorsi**.

E' possibile per esempio, applicare in questi punti critici, le **[[Intelligenza Artificiale#Euristiche per CSP|Euristiche per CSP]]**.

   