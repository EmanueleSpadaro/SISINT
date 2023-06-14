E' un [[Intelligenza Artificiale#Modalità di Inferenza|approccio alla propagazione delle informazioni]] dopo l'assegnamento di un valore ad una variabile.

Il forward checking consiste nell'**aggiornare** la tabella di **valori possibili dei nodi adiacenti a quello appena assegnato** nel **[[Grafo dei Vincoli]]**.

Ritorna come risultato **fallimento** quando una o più variabili rimangono senza valori disponibili per mantenere la consistenza con i vincoli.

![[Pasted image 20230613172732.png]]

### Short-Sightedness
Il Forward Checking si limita a ridurre i valori possibili delle variabili adiacenti dopo un assegnamento, e non si accorge, come nel caso sottostante, che dopo aver fatto inferenza, si è ritrovato in un caso che forza inconsistenza con i vincoli del problema.
![[Pasted image 20230613173205.png]]
Nel [[Problema dell'Australia]] $\text{NT}\ne\text{SA}$, ma Forward Checking non si accorge che già il percorso è fallimentare perché l'unica soluzione per $NT$ e $SA$ è $B$.  
