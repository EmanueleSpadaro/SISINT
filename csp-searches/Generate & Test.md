Generate & Test è una [[Intelligenza Artificiale#Strategie di Ricerca per CSP|Strategia di Ricerca per CSP]] molto banale, genera casualmente degli assegnamenti nella speranza che siano corretti.

### Funzionamento
Il funzionamento consiste nel **generare casualmente un assegnamento** completo, finché ve ne sono altri non valutati, **e verificare se sia consistente**.

E' **estremamente inefficiente**: basti pensare che il [[Problema delle 8 Regine]], nella versione in cui le variabili informano della casella in cui una regina è posta, prevede $64^{8}=28.100.000.000.000$ possibili assegnazioni, tra le quali solo $92$ sono soluzioni.

Generate & Test è estremamente semplice da implementare, ed il suo utilizzo è giustificabile nel caso in cui gli assegnamenti possibili del CSP non siano grandi in modo devastante e nel caso in cui le performance non siano rilevanti.

### Pseudocodice
```
WHILE (NOT ALL ASSIGNMENTS HAVE BEEN GENERATED)
	ass <- GENERATE_COMPLETE_ASSIGNMENT_NOT_YET_GENERATED
	if isConsistent(ass) => return solution(ass)
```

