E' una proprietà rispetto al [[Grafo dei Vincoli]] che **riguarda triplette di variabili**, ed è utilizzata anche come [[Intelligenza Artificiale#Modalità di Inferenza|Modalità di Inferenza]].
E' utilizzata nell'ambito del [[Pre-processing dei CSP]] con l'algoritmo [[PC-2]].

![[australia-3-consistency-example.svg]]

## Definizione di Path Consistency
Un Path è Path-Consistente se
$$\forall \{x_i=v_i,\ x_j = v_j\}\in \text{ASSEGNAMENTO}\ \exists v_k\in D_k\mid \{x_k=v_k, x_i=v_i, x_j=v_j\} \text{ sia consistente} $$
N.B. Nel corso è stata formulata dicendo
$$\forall \{x_i=v_i,\ x_j = v_j\}\in \text{ASSEGNAMENTO}\ \exists v_k\in D_k\mid \{x_k=v_k, x_i=v_i\} \text{ e }\{x_k=v_k, x_j=v_i\} \text{ siano consistenti} $$
