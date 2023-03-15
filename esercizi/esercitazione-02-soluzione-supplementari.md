# Soluzione degli esercizi supplementari dell'esercitazione 2

Non sappiamo se il professore Professore e la tutor rilasceranno soluzioni
supplementari. Queste sono state proposte dagli studenti.

## Problema 6

Considero una MdT a due nastri. Sul primo scrivo l'input. Il secondo funge da
contatore, inizialmente vuoto, a indicare che ho contato lo stesso numero di
simboli 0 e simboli 1 (0 occorrenze e 0 occorenze). Per indicare che ho
scansionato nell'input k occorrenze di 0 in più rispetto alle occorrenze di 1,
sul secondo nastro avrò una sequenza di k simboli 0 adiacenti. Per indicare che
ho scansionato nell'input k occorrenze di 1 in più rispetto alle occorrenze di
0, sul secondo nastro nastro avrò una sequenza di k simboli 1 adiacenti. Man
mano che la macchina scansiona l'input da sinistra a destra, aggiorna il nastro
contatore. Alla fine della scansione, viene controllato il nastro contatore. Se
è vuoto, si finisce nello stato accettente; altrimenti, nello stato rigettante.

## Problema 7

### Parte a

Siccome L- non è riconoscibile, L non è decidibile. Osservo che L è
mapping-riducibile a L', considerando come funzione di mapping quella che
aggiunge "0" come prefisso. Quindi, L' non può essere decidibile, o lo sarebbe
anche L. Osservo che L- è mapping riducibile a L', considerando come funzione di
mapping quella che aggiunge "1" come prefisso. Quindi, L' non può essere
riconoscibile, o lo sarebbe anche L-.

Perciò L' deve essere non-riconoscibile.

### Parte b

Se L' è non riconoscibile, L'- non è decidibile. Siccome ho mostrato (nella
parte a) che L è mapping-riducibile a L', allora L- è mapping-riducibile a L'-.
Quindi L'- non può essere riconoscibile, o lo sarebbe anche L-. Quindi anche L-
deve essere non riconoscibile.

## Problema 8

L è decidibile: se la stringa corretta non è una codifica corretta, mi fermo su
uno stato rigettante. Se lo è, simulo la macchina M su input x tenendo un
contatore dei passi:

- se la simulazione ferma prima di 100 passi, mi fermo su uno stato rigettante;
- se la simulazione ferma in 100 passi, mi fermo su uno stato accettante;
- se la simulazione giunge al passo 101, la abortisco e mi fermo su uno stato
  rigettante.

Siccome L è decidibile, è anche riconoscibile.

## Problema 9

### Parte a

È una proprietà di linguaggio: due qualsiasi macchine che riconoscono lo stesso
linguaggio o avranno entrambe un linguaggio finito complementare a quello
riconosciuto (lo stesso), o nessuna delle due avrà un linguaggio finito
complementare a quello riconosciuto (siccome il linguaggio riconosciuto è lo
stesso).

Non è una proprietà triviale: una macchina di Turing che riconosce il linguaggio
vuoto non ne gode, mentre una macchine di Turing che riconosce il linguaggio di
tutte le stringhe costruite sull'alfabeto ne gode.

### Parte b

È una proprietà di linguaggio: due qualsiasi macchine che riconoscono lo stesso
linguaggio fermano sugli stessi input, e quindi una fermerà su un qualche input
se e solo se vi si fermerà anche l'altra.

Non è una proprietà triviale: una macchina di Turing che riconosce il linguaggio
vuoto non ne gode, mentre una macchine di Turing che riconosce il linguaggio di
tutte le stringhe costruite sull'alfabeto ne gode.

### Parte c

Non è una proprietà di linguaggio: si consideri il linguaggio vuoto. Una
possibile implementazione di una macchina che lo riconosce prevede un singolo
stato iniziale e non finale, e tanti cappi che riportano sempre allo stesso
stato. Questa implementazione non gode della proprietà (se i cappi non fossero
ammessi nella definizione di tornare", basterebbe usare due soli stati,
entrambi non finali, e una funzione di transizione che obbliga a passeggiare da
uno all'altro). Una implementazione alternativa dello stesso linguaggio vuoto
può prevedere due soli stati, entrambi non finali. Il primo funge da stato
iniziale, che obbliga subito a spostarsi sul secondo. Il secondo funge da stato
pozzo, che non può mai essere lasciato. Questa implementazione gode della
proprietà.

Siccome la proprietà non è di linguaggio, non ha senso chiedersi se sia triviale
o meno.

### Parte d

È una proprietà di linguaggio: due qualsiasi macchine che riconoscono lo stesso
linguaggio o terminano entrambe su "ab", o nessuna delle due lo riconosce.

È una proprietà non triviale: una macchina che riconosce il linguaggio vuoto non
la soddisfa, ma una macchine che riconosce il linguaggio di tutte le stringhe
costruite sull'alfabeto la soddisfa.

### Parte e

È una proprietà di linguaggio: due qualsiasi macchine che riconoscono lo stesso
linguaggio riconoscono entrambe un linguaggio riconoscibile, e quindi entrambe
godono della proprietà.

È una proprietà triviale: ogni macchina di Turing riconosce un linguaggio
riconoscibile (per esempio, dalla macchina stessa).
