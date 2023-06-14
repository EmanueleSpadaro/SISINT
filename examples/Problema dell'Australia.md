Il Problema dell'Australia è un problema introduttivo ai CSP ed è utilizzato per dimostrare come questi possano [[Intelligenza Artificiale#CSP come Problema di Ricerca in uno Spazio di Stati|essere visti come Problemi di Ricerca in uno Spazio di Stati]].
Prende il nome dal fatto che le sue origini risalgono a un puzzle di posizionamento delle nazioni su una mappa dell'Australia.

L'obiettivo è trovare un'assegnazione di colori che soddisfi la condizione di non avere regioni adiacenti con lo stesso colore.

E' contestualizzabile come CSP dove:
- **Insieme delle variabili**: $\{WA, NT, SA, Q, NSW, V, T\}$
- **Insieme dei vincoli**: $\{SA\neq WA, SA\neq NT, SA\neq Q, SA\neq NSW, SA\neq V, WA\neq NT, NT\neq Q, Q\neq NSW, NSW\neq V\}$
- **Dominio delle variabili**: $\forall x, x\in\{R,G,B\}$ *(Red, Green, Blue)*

E' facile notare come all'occhio umano risulti difficile prendere in considerazione un insieme di vincoli così "complesso".
Per questa esatta motivazione possiamo utilizzare un [[Grafo dei Vincoli]].

### Mappa dell'Australia
![[australia-csp.png]]