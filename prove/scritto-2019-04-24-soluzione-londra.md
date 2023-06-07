# Soluzione dello scritto del 24 aprile 2019

Questo scritto è di quando Zanasi era tutor all'University College London. Molte
delle domande di allora sono state riproposte tali e quali da Zanasi qui a
Bologna. Queste soluzioni sono state scritte da uno studente, e come tali
potrebbero contenere imprecisioni.

## Esercizio 1

### 1.a

#### 1.a.i

Un linguaggio si dice decibille quando esiste almeno una macchina di Turing che
lo decide, e cioè che accetta tutte le stringhe che ne fanno parte e rigetta
tutte quelle che non ne fanno parte.

Un linguaggio si dice riconoscibile quando esiste almeno una macchina di Turing
che lo riconosce, e cioè che termina su tutte e sole le stringhe appartenenti
al linguaggio.

#### 1.a.ii

$$(\{0, 1, \textvisiblespace\}, \{q_0, Y, N\}, q_0, \{Y, N\}, \delta)$$

$$\delta(q_0, 0) = (q_0, 0, \rightarrow)$$
$$\delta(q_0, 1) = (Y, 1, \rightarrow)$$
$$\delta(q_0, \textvisiblespace) = (N, \textvisiblespace, \rightarrow)$$

#### 1.a.iii

$$(\{0, 1, \textvisiblespace\}, \{q_0, q_1\}, q_0, \{q_1\}, \delta)$$

$$\delta(q_0, 0) = (q_0, 0, \rightarrow)$$
$$\delta(q_0, 1) = (q_1, 1, \rightarrow)$$
$$\delta(q_0, \textvisiblespace) = (q_0, \textvisiblespace, \rightarrow)$$

### 1.b

1. Non riconoscibile (potremmo provarlo riducendo $ETH^-$ a esso). Il teorema di
   Rice non si applica, perché non è una proprietà di linguaggio. Potremmo
   provarlo scegliendo come $M_1$ una macchina di $n$ stati che riconosce le
   macchine che hanno strettamente meno di $m$ stati, dove $m > n$, e come $M_2$
   una macchina ottenuta aggiungendo a $M_1$ stati inutili fino ad arrivare a
   $m$;
2. riconoscibile (si consideri la macchina che simula la macchina codificata dai
   dati in ingresso su tutti i possibili input in parallelo ma scaglionati, e si
   ferma quando almeno una simulazione ferma) ma non decidibile, perché vi si
   applica il teorema di Rice. Potremmo dimostrare che il teorema di Rice vi
   si applica considerando la macchina che riconosce l'insieme vuoto e quella
   che riconosce $\Sigma^*$;
3. riconoscibile (basta simulare la macchina su $0$ e fermarsi quando la
   simulazione si ferma), ma non decidibile per il teorema di Rice. Potremmo
   dimostrare che il teorema di Rice vi si applica considerando la macchina che
   riconosce l'insieme vuoto e quella che riconosce $\Sigma^*$;
4. decidibile (basta studiare la codifica, cominciare a contare gli stati e
   fermarsi se e solo se il quinto è anche l'ultimo). Il teorema di Rice non si
   applica (o non sarebbe decidibile);
5. né decidibile né riconoscibile (lo si può dimostrare riducendo FL a questo
   linguaggio), e il teorema di Rice si applica. Lo si può dimostrare
   considerando la macchina che riconosce l'insieme vuoto e quella che riconosce
   $\Sigma^*$.

### 1.c

- si consideri la funzione che mappa le $(y, x)$ la cui $y$ non è codifica di
  nessuna macchina in $y$, e le $(y, x)$ la cui $y$ codifica una qualche
  macchina $M_y$ nella codifica della corrispettiva macchina $M_y^'$. Tale
  macchina prima cancella il proprio nastro, poi vi scrive $x$ e infine simula
  su tale sequenza $M_y$. Questa funzione è banalmente computabile da una
  macchina di Turing, e inoltre è evidente che rispetti $(y, x) \in HALT
  \leftrightarrow f((y, x)) \in L$. Se infatti $y$ non è codifica di alcuna
  macchina, entrambi i membri dell'equivalenza logica sono falsi, mentre se $y$
  codifica una qualche macchina $M_y$ allora è ovvio per costruzione che $M_y$
  converga su $x$ se e solo se $M_y^'$ converge sulla propria codifica;
- ne concludiamo che $L$ non sia decidibile;
- siccome deve valere che $HALT^-$ sia mapping-riducibile a $L^-$, allora anche
  $L^-$, come $HALT^-$ deve essere non riconoscibile.

## Esercizio 2

### 2.a

Sia $G$ un grafo non direzionato con pesi 1 o 2. $HCP$ si chiede se $G$
contenga almeno un cammino di costo complessivo pari al numero dei nodi che
parte da un qualche nodo e vi ritorna passando per ogni nodo del grafo
esattamente una volta.

### 2.b

1. $6 = 2 + 0 + 1 + 3$ (ciclo 0-1-3-2)
2. $9 = 2 + 1 + 4 + 2$ (ciclo 0-1-2-3)

### 2.c

Avrò bisogno di memorizzare un intero per il numero dei nodi ($|X|$), $|X|^2$
interi di lunghezza al più $m$ per i pesi e un ultimo intero per $k$. Siccome
uso codifica binaria, il costo complessivo è
$\Omicron(|X|^2 log(m) + log(k))$.

### 2.d

Siano $L$ p-time riducibile in $L'$ e $L'$ p-time riducibile in $L''$. Quindi
esistono una funzione $f$ che riduce $L$ in $L'$ in tempo polinomiale e una
funzione $g$ che riduce $L'$ in $L''$ in tempo polinomiale. Considero la
funzione composta di $g$ e $f$ che prima applica $f$ e poi $g$. Essa mappa
$L$ in $L''$ e inoltre il suo costo temporale è polinomiale (una somma di
polinomi è un polinomio). Quindi $L$ è p-time riducibile in $L''$.

### 2.e

Che è MCP? Maximum Clique Problem? Ha una formulazione come problema di
decisione? Sul Sipser non si trova.

### 2.f

Vedi sopra.

### 2.g

Posso concludere che è anche MCP sia NP-completo.
