**Esercizi per il corso di Fluidodinamica**

Dato il profilo di velocità, determinare il rapporto di forma $H$.
$$\frac{u(x,y)}{U(x)} = 
  \begin{cases}
    \displaystyle\left( \frac{y}{\delta(x)} \right)^{\frac{1}{7}} &  \qquad y \le \delta(x) \\
    1 &  \qquad y > \delta(x)
  \end{cases}$$

($H = 9/7$)

### Soluzione {#soluzione .unnumbered}

     **Concetti.** Spessori di strato limite. Rapporto di forma
$H = \delta_1 / \delta_2$.

$$\begin{aligned}
   \delta_1(x) & = \int_{0}^\infty \displaystyle \left( 1 - \frac{u(x,y)}{U(x)} \right) dy \\
   \delta_2(x) & = \int_{0}^\infty \frac{u(x,y)}{U(x)} \displaystyle \left( 1 - \frac{u(x,y)}{U(x)} \right) dy
\end{aligned}$$

**Svolgimento.** L'esercizio viene risolto calcolando prima gli
integrali nelle definizioni degli spessori di strato limite e poi il
loro rapporto.

Lo spessore di spostamento: $$\begin{aligned}
  \delta_1 & = \int_{0}^\infty \displaystyle \left( 1 - \frac{u(x,y)}{U(x)} \right) dy  = \\
           & = \int_{0}^{\delta(x)} \displaystyle \left( 1 - \frac{u(x,y)}{U(x)} \right) dy +
           \underbrace{\int_{\delta(x)}^\infty \displaystyle \left( 1 - \frac{u(x,y)}{U(x)} \right) dy}_{=0}  =\\
           & = \frac{1}{8}\delta(x)
\end{aligned}$$

Lo spessore di quantità di moto: $$\begin{aligned}
  \delta_2 & = \int_{0}^\infty \frac{u(x,y)}{U(x)} \displaystyle \left( 1 - \frac{u(x,y)}{U(x)} \right) dy \\
           & = \int_{0}^{\delta(x)} \frac{u(x,y)}{U(x)}\displaystyle \left( 1 - \frac{u(x,y)}{U(x)} \right) dy +
           \underbrace{\int_{\delta(x)}^\infty \frac{u(x,y)}{U(x)}\displaystyle \left( 1 - \frac{u(x,y)}{U(x)} \right) dy}_{=0}  =\\
           & = \frac{7}{72}\delta(x)
\end{aligned}$$

Il rapporto di forma vale quindi $H = 9/7$.

*Osservazione.* Questo profilo di velocità viene usato come
approssimazione del profilo di strato limite turbolento. Questo profilo
ha $\frac{\partial u}{\partial y}\big|_{y=0}$ infinita, che implica
sforzo a parete infinito. Una formula per lo sforzo di parete, associata
a questo profilo di velocità è:
$$\tau_w = 0.0225 \rho U^2 \displaystyle \left( \frac{\nu}{U \delta} \right) ^ {\frac{1}{4}}$$
