E' un [[Intelligenza Artificiale#CSP - Problemi di Soddisfacimento di Vincoli|CSP]] utilizzato all'interno del corso per dimostrare l'efficienza delle varie [[Intelligenza Artificiale#Strategie di Ricerca per CSP|Strategie di Ricerca per CSP]].

Il problema è ambientato in una scacchiera $8\times8$ dove **si vogliono piazzare *8 Regine* in modo che nessuna risulti sotto attacco**. 

Il Problema delle 8 Regine è formulato, come CSP, nel seguente modo:
- **Insieme delle Variabili**: $\{Q_1=v_1, Q_2=v_2, ..., Q_8=v_8\}$ dove $v_i$ indica la posizione nella scacchiera della regina $Q_i$.
- **Insieme dei Valori**:
  - *Strategia 1* $\{1, 2, 3,...,64\}$ dove $v$ è la posizione nella scacchiera della regina $Q_i$
  - *Strategia 2* $\{1,2,3,4,5,6,7,8\}$ dove $v_i$ è la riga dove è piazzata la regina $Q_i$ 
Questo problema ha **92 soluzioni** che si riducono a 12 senza considerare le simmetrie.

La formulazione dei valori gioca un ruolo cruciale per rendere la computazione più leggera.

### Analisi delle Strategie per l'Insieme dei Valori
- **Strategia 1**: il caso più semplice e immediato, mappiamo la posizione nella scacchiera $8\times8$ vi sono $64^8=28.100.000.000.000$ possibili assegnamenti
- **Strategia 2**: vi sono $8^8=16.777.216$ possibili assegnamenti, è estremamente meno complicato.

Nella realtà dei fatti, alla **Strategia 2** vi sono complessivamente 3 vincoli:
- **Colonna diversa**: è direttamente implementato partendo dal concetto di variabile, dicendo che $v_i$ è la riga della regina $Q_i$, è implicito che $Q_1$ sarà alla colonna $1$, $Q_2$ sarà alla colonna $2$, $\text{etc}...$
- **Riga diversa**: $i\ne j \Rightarrow Q_i \ne Q_j$, le regine non possono essere nella stessa riga se non devono essere sotto attacco tra di loro
- **Diagonale diversa**: $i\ne j \Rightarrow |i-j|\ne Q_i \ne Q_j$, le regine non possono essere nella stessa diagonale se non devono essere sotto attacco tra di loro