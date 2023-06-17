La Regola di Risoluzione è una [[Regola di Inferenza]], e cioè una manipolazione sintattica delle formule.

Attraverso un processo di ricerca, applichiamo il [[Teorema di Deduzione]].
Partiamo da uno stato iniziale $$\text{KB}\land \lnot Q$$

La risoluzione lavora su due formule dette **Clausole**, ovvero **disgiunzioni letterali**:
$$\frac{P_1\lor...\lor P_{i-1}\lor P_i\lor P_{i+1}\lor...\lor P_n\hspace{1em} Q_1\lor...\lor Q_{j-1}\lor Q_{j}\lor Q_{j+1}\lor...\lor Q_m }{P_1\lor...\lor P_{i-1}\lor P_{i+1}\lor...\lor P_n\hspace{1em} Q_1\lor...\lor Q_{j-1}\lor Q_{j+1}\lor...\lor Q_m }{}$$
dove $P_i\equiv \lnot Q_j$. Questo comporta l'annullamento di $P_i$ e $Q_j$.

**Se partendo da una knowledge base vera $KB$ applichiamo la Regola di Risoluzione e otteniamo una clausola vuota, allora abbiamo dimostrato che $\lnot Q$ non è vera**. 