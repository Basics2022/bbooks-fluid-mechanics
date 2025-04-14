Sia dato il campo di moto
$$\bm{u}(x,y,z) = 3y \bm{\hat{x}} - 3x \bm{\hat{y}} +t\bm{\hat{z}}$$
Calcolare l'equazione delle linee di corrente, delle traiettorie e delle
linee di fumo (curve di emissione) e disegnarle.

**Suggerimento.** Le componenti $x$ e $y$ del sistema sono accoppiate
tra di loro. Risolvendo il sistema per le **linee di corrente**,
$$\begin{cases}
  \dfrac{dX}{dp} =  \lambda(p) 3Y \\
  \dfrac{dY}{dp} = -\lambda(p) 3X \\
  \dfrac{dZ}{dp} =  \lambda(p) t \ ,
 \end{cases}
\quad \rightarrow \quad
 \begin{cases}
  X(p) \dfrac{dX}{dp} + Y(p) \dfrac{dY}{dp} = 0 \\
  \dfrac{dZ}{dP} = \lambda(p) t \ .
 \end{cases}$$ Integrando la prima, si ottiene l'equazione di una
criconferenza $X(p)^2 + Y(p)^2 = R^2$ (con $R^2 = X(p_0)^2 + Y(p_0)^2$,
descrivibile in forma paramterica come $$\begin{cases}
 X(p) = R \cos(p) \\
 Y(p) = R \sin(p) \ .
 \end{cases}$$ Con la parametrizzazione scelta, è possibile ricavare la
relazione $\lambda(p) = -1/3$ e integrare l'equazione per la componente
$Z$.

Per il calcolo dell'equazione che descrive le **triettorie** delle
particelle materiali e le **linee di fumo**, la soluzione del problema
di Cauchy $$\begin{cases}
  \dfrac{dx}{dt} =  3y(t) & x(t_0) = x_0 \\
  \dfrac{dy}{dt} = -3x(t) & y(t_0) = y_0 \\
  \dfrac{dz}{dt} = t  &     z(t_0) = z_0 \ ,
 \end{cases}$$ ha la forma $$\begin{cases}
  x(t,\bm{r_0},t_0) = A \sin(3t) - B \cos(3t) \\
  y(t,\bm{r_0},t_0) = A \cos(3t) + B \sin(3t) \\
  z(t,\bm{r_0},t_0) = z_0 + \dfrac{t^2 - t_0^2}{ 2 } \ .  \\
 \end{cases}$$ Le costanti di integrazione mancanti $A$, $B$ vengono
calcolate imponendo le condizioni iniziali,
$$A = y_0 \cos(3t_0) + x_0 \sin(3t_0) \quad , \quad
  B = y_0 \sin(3t_0) - x_0 \cos(3t_0) \ ,$$ e la soluzione del problema
in forma parametrica può essere riscritta come $$\begin{cases}
  x(t,\bm{r_0},t_0) = x_0 \cos(3(t-t_0)) + y_0 \sin(3(t-t_0)) \\
  y(t,\bm{r_0},t_0) =-x_0 \sin(3(t-t_0)) + y_0 \cos(3(t-t_0)) \\
  z(t,\bm{r_0},t_0) = z_0 + \dfrac{t^2 - t_0^2}{ 2 } \ .  \\
 \end{cases}$$
