> E' un teorema fondamentale per il [[Intelligenza Artificiale#Theorem Proving|Theorem Proving]] ed è utilizzato congiuntamente alla [[Regola di Risoluzione]].

Date due formule $R$ e $Q$
$$R \vDash Q \iff R \Rightarrow Q \text{ è valida}$$
e cioè che $R \Rightarrow Q$ è vera in tutti i modelli possibili.

Ricordiamo che una formula è detta valida se e solo la sua negazione è insoddisfacibile:
- $\alpha$ valida: vera in tutti i modelli
- $\lnot \alpha$ insoddisfacibile: falsa in tutti i modelli

Dimostrare che la negazione sia insoddisfacibile è più facile e ci permette di non enumerare tutti i modelli.

Partiamo da:
1. $\lnot(R\Rightarrow Q)$, e ci ricordiamo che $R\Rightarrow Q \equiv\ \lnot R \lor Q$
2. $\lnot(\lnot R \lor Q)$, e attraverso applichiamo le leggi di De Morgan
3. $R \land \lnot Q$, e questa deve essere insoddisfacibile

Posso immaginare $R$ come la mia base di conoscenza, e la assumo vera.
Supponiamo per assurdo che $\lnot Q$ sia vera e che in quanto tale la aggiungiamo alla nostra knowledge base.
Se troviamo anche una sola inconsistenza, allora la colpa è l'assunzione che $\lnot Q$ sia vera, perché $R$ fino a prima della sua aggiunta era vera.