**Esercizi per il corso di Fluidodinamica**

Sia dato il campo di moto
$$\bm{u}(x,y,z) = 3y \bm{\hat{x}} - 3x \bm{\hat{y}} +t\bm{\hat{z}}$$
Calcolare l'equazione delle linee di corrente, delle traiettorie e delle
linee di fumo (curve di emissione) e disegnarle.

### Soluzione {#soluzione .unnumbered}

     **Concetti.** Definizione di linee di corrente, traiettorie, linee
di fumo, tracce. Soluzione di sistemi di equazioni differenziali.

**Svolgimento.**

-   Linee di corrente. $$\begin{cases}
      \frac{dX}{dp} = \lambda(p) 3Y \\
      \frac{dY}{dp} = -\lambda(p) 3X \\
      \frac{dZ}{dP} = \lambda(p) t
     \end{cases}
     \quad\Rightarrow\quad
     ...
     \quad\Rightarrow\quad
     \begin{cases}
      X(p) = R \cos(p) \\
      Y(p) = R \sin(p) \\
      Z(p) = Z_0 + t p
     \end{cases} \text{se $\lambda(p) = \frac{1}{3}$}$$

-   Traiettorie. $$\begin{cases}
      \frac{dx}{dt} = 3y \\
      \frac{dy}{dt} = -3x \\
      \frac{dz}{dt} = t \\
      x(0) = x_0 , \quad y(0) = y_0 , \quad z(0) = z_0
     \end{cases}
     \quad\Rightarrow\quad
     \begin{cases}
      \frac{dx}{dt} = 3y \\
      \frac{d^2y}{dt^2} + 9 y = 0 \\
      z(t) = \frac{t^2}{2} + C
     \end{cases}
     \quad\Rightarrow\quad
     \begin{cases}
      x(t) = A \cos(3t) + B \sin(3t) \\
      y(t) = - A \sin(3t) + B \cos(3t) \\
      z(t) = \frac{t^2}{2} + C
     \end{cases}$$ Inserendo le condizioni iniziali si ottiene
    $$\begin{cases}
      x(t) = x_0 \cos(3t) + y_0 \sin(3t) \\
      y(t) = - x_0 \sin(3t) + y_0 \cos(3t) \\
      z(t) = \frac{t^2}{2} + z_0
     \end{cases}$$

    *Osservazione.* Ottenere $y$ in funzione di $x$ e confrontare con le
    linee di corrente. Commentare\...

-   Linee di fumo. Inserendo nelle soluzioni generali trovate per le
    traiettoire, le condizioni $$\begin{cases}
      x(\tau) = x_0 \\ y(\tau) = y_0 \\ z(\tau) = z_0
     \end{cases}$$ si ottengono le linee di fumo $$\begin{cases}
      x(t) = x_0 \cos(3(t-\tau)) + y_0 \sin(3(t-\tau)) \\
      y(t) = - x_0 \sin(3(t-\tau)) + y_0 \cos(3(t-\tau)) \\
      z(t) = \frac{t^2-\tau^2}{2} + z_0
    \end{cases}$$
