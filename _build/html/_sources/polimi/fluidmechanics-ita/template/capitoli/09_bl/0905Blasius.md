**Esercizi per il corso di Fluidodinamica**

Una lamina piana molto sottile viene investita parallelamente su
entrambe le sue facce da una corrente di velocità uniforme $U$ di un
fluido di densità $\rho$ e viscosità dinamica $\mu$. Nell'ipotesi che il
problema possa essere approssimato con le equazioni bidimensionali dello
strato limite laminare con velocità asintotica costante (Blasius):

-   determinare l'espressione della resistenza di attrito della lamina
    rettangolare in funzione della sua lunghezza $\ell$ (lati paralleli
    alla velocità della corrente esterna) e della sua larghezza $b$;

-   determinare la forma della lamina rettangolare di area data
    $A = \ell \, b$ che ha resistenza minima.

### Soluzione {#soluzione .unnumbered}

     **Concetti.** Strato limite laminare. Equazione di Blasius.

**Svolgimento.** Nell'ipotesi in cui si possa utilizzare la soluzione di
Blasius, considerata omogenea in apertura, la resistenza di attrito
della lamina è $$\begin{aligned}
    D & = 2 b \int_0^{\ell} \tau_w(x) dx = & \displaystyle\left(\tau_w = \mu \frac{U}{\delta(x)} g''(0)\right)\\
    & = 2 g''(0) \mu b U \int_0^{\ell} \frac{1}{\delta(x)} dx = & \displaystyle\left(\delta(x) = \sqrt{\frac{\nu x}{U}}\right) \\
    & = 2 g''(0) \frac{\mu b U^{\frac{3}{2}} }{\sqrt{\nu}} \int_0^{\ell} \frac{1}{\sqrt{x}} dx = & \\
    & = 4 g''(0) \sqrt{\rho \mu}  U^{\frac{3}{2}}  \, b \sqrt{\ell} \ , 
\end{aligned}$$ o raccogliendo nel coefficiente $K$ tutti i parametri
costanti del problema, $D(\ell, \, b) = K \, b \sqrt{\ell}$.

#### Resistenza minima, ad area $A$ fissata.

Per trovare il valore minimo della resistenza di una lamina, si
inserisce il vincolo $A = \ell \, b$ all'interno dell'espressione della
resistenza per ottenere l'espressione in funzione di una sola variabile,
$$D_A(\ell) = K \, A \, \dfrac{1}{\sqrt{\ell}} = \tilde{K} \dfrac{1}{\sqrt{\ell}} \ .$$
Si osserva che la resistenza minima si ottiene per una lamina di
lunghezza $\ell$ infinita e di spessore $b$ infinitesimo,
$D_A(\ell \rightarrow \infty) \rightarrow 0$.

#### Commento.

Il problema considera un modello laminare dello strato limite su tutta
la lunghezza della lamina, senza considerare la transizione a un regime
di moto turbolento. In generale la transizione a un regime di moto
turbolento avviene a una determinata distanza dal bordo di attacco della
lamina. Se avviene la transizione a un regime di moto turbolento,
aumentando la lunghezza della lamina aumenta la sua superficie soggetta
a un regime turbolento, nel quale gli sforzi a parete sono generalmente
maggiori, rispetto a uno strato limite laminare.
