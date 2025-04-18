Ricavare le equazioni di Prandtl dello strato limite laminare (hp\...).
Ricavare poi l'equazione di Blasius per lo strato limite laminare
(hp\...). Ricavare la soluzione con un metodo numerico: in particolare,
ricavare il valore di $\frac{d^2 g}{d\eta^2}\big|_{\eta=0}$ da inserire
nella formula dello sforzo viscoso a parete (Shooting method ed
iterazioni di Newton).

($g''(0) = 0.332$)

Equazioni di Prandtl. Equazione di Blasius. Soluzione in similitudine.
Shooting method.

Le equazioni di Prandtl dello strato limite possono essere ricavate
tramite ragionamenti sugli ordini di grandezza delle grandezze fisiche.

$$\begin{cases}
    u\frac{\partial u}{\partial x} + v\frac{\partial u}{\partial y} - \nu \frac{\partial^2 u}{\partial y^2} = - \frac{1}{\rho}P(x) \\
    \frac{\partial u}{\partial x} + \frac{\partial x}{\partial y} = 0
  \end{cases}$$

Sfruttando la definizione di funzione di corrente, l'ipotesi che $U(x)$
sia costante, si cerca una soluzione in similitudine delle equazioni di
Prandtl. Siano $\eta = y/\delta(x)$ e $\psi = U(x) \delta(x) g(\eta)$,
si ricava l'andamento dello spessore dello strato limite
$\delta(x) = \sqrt{\frac{\nu x}{U}}$ e l'equazione di Blasius
$$g''' + \frac{1}{2} g g'' = 0$$ con le condizioni al contorno
$$\begin{cases}
 g(0) = 0 \\
 g'(0) = 0 \\
 \lim_{\eta\to \infty}
 g'(\eta) = 1
 \end{cases}$$

La formula per lo sforzo viscoso a parete è:
$$\tau_w = \mu \frac{\partial u}{\partial y}\big|_{y=0} = \mu \frac{\partial^2 \psi}{\partial y^2}\big|_{\eta=0} = 
  \mu \frac{U}{\delta(x)} g''(0)$$

Per risolvere l'equazione di Blasius con metodi numerici, si può
incontrare qualche difficoltà nell'imporre la condizione al contorno per
$\eta \to \infty$. Tramite uno *shooting method* si può risolvere il
problema ai valori al contorno, tramite la soluzione di problemi ai
valori iniziali insieme a un metodo per trovare gli zeri di una funzione
(es. Newton). Il dominio semi-infinito viene troncato. Il dominio
numerico è quindi $[0,\bar{\eta}]$. L'equazione scalare di terzo ordine,
viene scritta come sistema del primo ordine. Invece di imporre la
condizione all'infinito, viene imposto il valore di $g''(0)=\alpha$. Si
risolve l'equazione. Si trova il valore di $g'_n$in $\bar{\eta}$. Si
itera fino a quando il valore assoluto di
$F(\alpha) = g'_n(\bar{\eta};\alpha) - \lim_{\eta\to \infty} g'(\eta)$
non è inferiore a una tolleranza stabilita.

Per esempio, partendo da $\alpha=0.1$, con una tolleranza $tol = 1E-09$:

    nIter    g"(0)    res 
      1     0.1000  5.508e-01 
      2     0.2836  9.975e-02 
      3     0.3308  2.575e-03 
      4     0.3320  1.660e-06 
      5     0.3320  1.804e-12
