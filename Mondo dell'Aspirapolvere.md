Ci ritroviamo in una casa composta semplicemente da 2 stanze che possono essere *sporche* o *pulite*.

Abbiamo un'aspirapolvere che può essere in una delle due stanza e può eseguire le seguenti azioni:
- Vai a destra
- Vai a sinistra
- Aspira

Applicando la definizione di istanza di un problema di Intelligenza Artificiale al mondo dell'aspirapolvere, possiamo avere le seguenti:
- **Stato iniziale**: è quello in cui si trova l'aspirapolvere. Può essere uno stato qualsiasi dei possibili.
- **Funzione successore**: restituisce come valore lo stato successivo in base a quello attuale e l'azione che viene effettuata dall'aspirapolvere (tra le possibili 3 sopracitate).
- **Test obiettivo**: verifica se le due stanze sono pulite
- **Funzione costo**: ogni azione costa 1, oppure ogni movimento costa 1 e l'aspirazione costa 2.

![[vacuum-world.png]]
Per più info https://web.ntnu.edu.tw/~tcchiang/ai/Vacuum%20Cleaner%20World.htm.
E' stato utilizzato come ambiente introduttivo all'[[Intelligenza Artificiale#Istanza di un problema|Istanza di un problema per Intelligenza Artificiale]].

