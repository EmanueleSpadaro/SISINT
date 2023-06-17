> *Non è richiesto e non è stato spiegato durante il Corso, per fini di completezza abbiamo ricercato e trovato queste informazioni per i più curiosi.
> Disclaimer: è stato generato con ChatGPT in quanto non abbiamo trovato risorse da altre fonti.*

L'algoritmo di Mackworth, noto anche come algoritmo per la [[Path Consistency]], è un metodo utilizzato nella teoria dei vincoli ([[Intelligenza Artificiale#CSP - Problemi di Soddisfacimento di Vincoli|CSP]]) per risolvere problemi di soddisfacimento di vincoli. Questo algoritmo è stato sviluppato da R. Mackworth nel 1977 ed è particolarmente utile per ridurre lo spazio di ricerca quando si lavora con un gran numero di vincoli.

L'obiettivo dell'algoritmo di Mackworth è di rendere consistente un insieme di vincoli, in particolare la consistenza del cammino (path consistency). Questo significa che, per ogni variabile coinvolta in un vincolo, l'algoritmo garantisce che qualsiasi valore assegnato a quella variabile sia compatibile con tutti gli altri vincoli che coinvolgono quella variabile.

L'algoritmo di Mackworth funziona nel seguente modo:

1. Inizializzazione: Vengono create due liste, una per i vincoli binari e l'altra per i vincoli n-ari. I vincoli binari collegano due variabili, mentre i vincoli n-ari collegano più di due variabili. Entrambe le liste vengono inizializzate con tutti i vincoli presenti nel problema.

2. Iterazione: L'algoritmo itera finché entrambe le liste non sono vuote. Durante ogni iterazione, vengono considerati i vincoli presenti nelle liste.

3. Vincoli binari: Per ogni vincolo binario, viene verificata la consistenza tra le due variabili coinvolte. Se un valore viene rimosso da una delle variabili, viene controllato se ciò comporta la rimozione di altri valori dalle variabili coinvolte in altri vincoli. Se ciò accade, questi vincoli vengono aggiunti alla lista dei vincoli da considerare.

4. Vincoli n-ari: Per ogni vincolo n-ario, viene verificata la consistenza tra tutte le variabili coinvolte. Se un valore viene rimosso da una delle variabili, viene controllato se ciò comporta la rimozione di altri valori dalle variabili coinvolte in altri vincoli. Se ciò accade, questi vincoli vengono aggiunti alla lista dei vincoli da considerare.

5. Rimozione dei vincoli: Una volta che tutti i vincoli sono stati considerati, vengono rimossi dalla lista corrispondente.

L'algoritmo di Mackworth continua a iterare fino a quando entrambe le liste dei vincoli sono vuote. Quando ciò accade, si raggiunge la Path Consistency, ossia la consistenza del cammino, che garantisce che ogni valore assegnato a una variabile sia compatibile con tutti i vincoli che coinvolgono quella variabile.

In breve, l'algoritmo di Mackworth per la Path Consistency è un metodo per garantire la consistenza dei vincoli in un problema di soddisfacimento dei vincoli, riducendo così lo spazio di ricerca e rendendo più efficiente la risoluzione del problema.