E' una proprietà rispetto al [[Grafo dei Vincoli]] che riguarda due variabili adiacenti, ed è utilizzata anche come [[Intelligenza Artificiale#Modalità di Inferenza|Modalità di Inferenza]].
E' utilizzata nell'ambito del [[Pre-processing dei CSP]] nell'algoritmo [[AC-3]].

L'Arc Consistency è una proprietà che valuta i vincoli tra due nodi $X$ e $Y$ in entrambe le direzioni:
![[Pasted image 20230613174405.png]]

## Definizione di Arco Consistente
Un arco $X\rightarrow Y$ è detto ***Arc-Consistent*** se e solo se
$$\forall v \in D_x\  \exists v'\in D_y $$
che rende consistente l'assegnamento.

N.B. $D_x$: dominio consistente della variabile x

### Esempio

![[Pasted image 20230613175015.png]]

- $\text{WA}\rightarrow\text{SA}$ non è consistente. 
  $\forall v \in D_\text{WA}\  \exists v'\in D_\text{SA}$ non è vera perché dato $v = R \Rightarrow \nexists v'\in  D_\text{SA}$.
  $\text{SA}$ rimarrebbe senza valori consistenti
- $\text{SA}\rightarrow \text{WA}$ è consistente.
- $\forall v \in D_\text{SA}\  \exists v'\in D_\text{WA}$ è vera perché l'unico valore in $D_\text{SA}$ è $R$.
  $\text{WA}$ avrebbe come valore consistente rimanente $G$.
