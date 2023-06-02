E' una [[Intelligenza Artificiale#Strategie di Ricerca Informate|Strategia di Ricerca Informata]] che come funzione di valutazione utilizza una
$$f(n) = h(n)$$
e cioè che **si fa guidare esclusivamente dalla stima dei costi minimi per raggiungere i nodi target, non curandosi del costo di partenza dallo stato iniziale**.

La descrizione della *Ricerca Greedy* termina qua, ma andiamo a capire invece perché **questo approccio non va bene**.

## Esempio di Euristica
Immaginiamo di voler ottenere la strada più breve da Torino a Genova.
Si presentano degli scenari differenti sulla base di come vogliamo stimare la distanza.
- **Distanza in Linea d'Aria**: è estremamente semplice stimare la distanza in linea d'aria da un punto *x* ad un punto *y*, ma in un contesto reale la strada potrebbe presentare diversi ostacoli e curve che incrementano notevolmente la distanza rispetto a quella in linea d'aria.
![[greedy-search.png]]