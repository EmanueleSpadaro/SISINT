## Euristica Ammissibile
Una funzione euristica $h$ è detta **ammissibile** quando
$$\forall n, h(n)\leq h^{star}$$
dove
- $h^{star}$: costo minimo reale per raggiungere il nodo goal a partire dal nodo $n$
Intuitivamente un'euristica è ammissibile quando non fa mai stime per eccesso, e quindi quando è una **stima ottimistica**
*E.G.: La distanza in linea d'aria è un'euristica ammissibile rispetto alla distanza su strada*