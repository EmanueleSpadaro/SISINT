>Sia $A$ un assegnamento parziale consistente, sia $X$ una variabile non ancora assegnata.
>Se $\forall x \in D_x\ ,\ A \cup \{X=x\}$ è inconsistente, $A$ è detto **Conflict Set** di $X$.

E' possibile calcolare il **Conflict Set** attraverso il [[Forward Checking]].

![[Pasted image 20230614175913.png]]

Supponiamo di aver effettuato l'assegnamento nel seguente modo, con il relativo *Conflict Set* calcolato progressivamente sulla base degli assegnamenti precedenti:
1. WA = R, $\text{conf}(\text{WA}) = \ \{\ \}$
2. NSW = R, $\text{conf}(\text{NSW}) = \ \{\ \}$
3. T = B, $\text{conf}(\text{T}) = \ \{\ \}$
4. NT = B, $\text{conf}(\text{NT}) = \ \{\text{ WA }\}$
5. Q = G, $\text{conf}(\text{NT}) = \ \{\text{ NSW, NT }\}$
6. SA = ?, $\text{conf}(\text{NT}) = \ \{\text{ WA, NSW, NT, Q }\}$

Avendo scelto di assegnare il valore a SA, ci ritroviamo a non trovare alcun valore valido affinché si possa mantenere consistente l'assegnamento.

