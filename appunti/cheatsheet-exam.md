---
geometry: margin=2cm
output: pdf_document
---

# TM
TM $M$ definita come tupla

$$M = \langle \Sigma, Q, q_0, H, \delta \rangle$$

Dove $\delta$ è definita come un'insieme di funzioni $\Sigma \times Q \setminus H \mapsto \Sigma \times \{ \to, \gets\} \times Q$

# Decidibile e/o Riconoscibile
| Linguaggio | STATO | Esempio |
| - | - | - |
| _non_ si ferma su stringa $w$                 | non riconoscibile | $HALT^-, ETH^-$
| si ferma su _numero infinito di input_        | non riconoscibile | $FL$
| $M$ ferma su stesse stringhe di $M'$          | non riconoscibile | $EQ$
| _si ferma_ su stringa $w$                     | riconoscibile | $HALT, ETH$
| $M$ ha $N$ stati (o caratteristica statica)   | decidibile |

# Rice
> Se $P$ è language property non triviale, allora il problema "$M$ ha proprietà $P$" è indecidibile

Sì qundo la proprietà di linguaggio è relativa alle politiche del linguaggio e non all'implementazione

## Proprietà dei linguaggi
Funzione da un insieme di TM a $\{0, 1\}$, tale che $L_M = L_{M'} \Rightarrow P(M) = P(M')$

Una proprietà è NON TRIVIALE se esiste una TM $M$ tale che $P(M) = 1$ e una TM $M'$ tale che $P(M) = 0$

# Complessità $P$ vs $NP$
Nota: Fare attenzione se la domanda parla di macchine non deterministiche

Se è polinomiale è in $P$

Attenzione a proprietà di potenze e logaritmi

Ricorda che $\binom{n}{k} = O(n)$

# Linguaggio $P$, $NP$ o $PSPACE$
Ricorda che $P \subseteq NP \subseteq PSPACE$

| Problema | STATO |
| - | - |
| K-CLIQUE con K non fissato                                                                                | $NP$ |
| K-CLIQUE con K fissato                                                                                    | $P$ |
| --- | --- |
| Percorso da $s$ a $t$ in un grafo                                                                         | $P$ |
| Esiste un percorso in G (indiretto) che visita tutti i nodi esattamente una volta (problema dei ponti)    | $NP$ |
| _Non_ esiste un percorso in G (diretto) da $s$ a $t$                                                      | $P$ |
| --- | --- |
| F è un enunciato booleano _senza_ quantificatori soddisfacibile (SAT)                                     | $NP$ |
| F è un enunciato booleano _con_ quantificatori soddisfacibile (TBQF)                                      | $PSPACE$ |

# Problemi Aperti, Vero o Falso
| Problema | STATO | Note |
| - | - | - |
| $L \in NP \implies L^- \in NP$                        | Vero | Poichè basta invertire stati finali accettanti e stati finali rigettanti, e $P \subseteq NP$
| Sia $L \in P$. Se $SAT \leq_p L$, allora $P = NP$     | Vero |
| Sia $L \in P$. Se $3SAT \leq_p L$, allora $P = NP$    | Vero |
| Alcuni linguaggi decidibili non sono in $P$           | Vero | Vedi linguaggi in $EXP$
| P è chiuso per unione                                 | Vero |
| $SAT/3SAT \in P$                                      | APERTO | Poichè $P = NP$ aperto
| Se $L$ è in $NP$, allora $L \leq_p SAT$s              | Vero | Poichè $SAT$ è $NP$-completo

# Altre note
## Chiusure di Linguaggi
Linguaggi decidibili chiusi per:

- Unione
- Intersezione
- Differenza
- Complemento

Linguaggi riconoscibili chiusi per:

- Unione
- Intersezione
- Differenza

## PSPACE
- $P \subseteq NP \subseteq PSPACE$
- $PSPACE = NPSPACE$

## Mapping Riducibilità
- Dato $L$ decidibile, $\forall L', \ L \leq L'$
- $\forall L_1,\ L_2 \quad L_1 \leq L_2^- \implies L_1^- \leq L_2$
