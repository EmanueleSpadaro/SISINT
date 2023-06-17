Il backjumping è un **[[Backtracking Search per CSP|backtracking]] di tipo non cronologico** ed è una [[Intelligenza Artificiale#Strategie di Ricerca per CSP|Strategia di Ricerca per CSP]] che sfrutta il **[[Conflict Set]]**.

Il backjumping, non essendo cronologico, **permette di tornare indietro**, non in maniera ricorsiva con lo stack delle chiamate alla variabile assegnata immediatamente prima, ma bensì di fare backtracking **a una variabile che potrebbe risolvere il problema**.

![[Conflict Set]]


## Funzionamento
- Sia $X_j$ la variabile corrente
- Se $\forall x_j \in D_{X_j}$ l'assegnamento diventerebbe inconsistente, si fa backjump all'ultima variabile $X_i$ aggiunta a $\text{conf}(\text{WT})$
- Quando si fa backjumping a $X_i$, si aggiorna $\text{conf}(X_i)$ con
  $$\text{conf}(X_i) \leftarrow \text{conf}(X_i)\ \cup\ \text{conf}(X_j) - X_i$$ 



