
La CNF ha una grammatica molto più semplificata rispetto a quella della [[Intelligenza Artificiale#Logica Proposizionale|Logica Proposizionale]].

Una base di conoscenza $\text{KB}_{CNF}$ in *Conjunctive Normal Form* è una congiunzione di clausole
$$\text{KB}_{CNF}\rightarrow \text{CLAUSE}\ \lor\ ...\ \lor \text{CLAUSE}$$
dove
$$ \text{CLAUSE} \rightarrow \text{literal}\ \lor\ ...\ \lor \text{literal} $$

In *Conjunctive Normal Form* gli unici operatori sono:
- $\land$
- $\lor$
- $\lnot$

e quindi vengono a mancare gli operatori $\Rightarrow$ e $\iff$.

E' possibile passare da una knowledge base in [[Intelligenza Artificiale#Logica Proposizionale|Logica Proposizionale]] ad una in *Conjunctive Normal Form* attraverso queste semplici [[Regola di Inferenza|regole di inferenza]].

1. Eliminare $\iff$:  $\alpha \iff \beta \equiv (\alpha \Rightarrow \beta) \land (\beta \Rightarrow \alpha)$
2. Eliminare $\Rightarrow$:  $\alpha\Rightarrow \beta \equiv \lnot \alpha \lor \beta$
3. De Morgan su $\lnot$
4. Distribuzione di $\lor$ sull'$\land$