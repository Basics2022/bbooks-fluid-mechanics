**Esercizi per il corso di Fluidodinamica**

+:---------------------------------:+:---------------------------------:+
| Si consideri una corrente d'acqua |                                   |
| a pelo libero, laminare e         |                                   |
| stazionaria, che scorre su una    |                                   |
| parete verticale piana di         |                                   |
| lunghezza e apertura infinita. Si |                                   |
| ipotizzi che la pressione         |                                   |
| atmosferica che agisce sul pelo   |                                   |
| libero sia uniforme. Si ipotizzi  |                                   |
| inoltre che lo sforzo tangenziale |                                   |
| fra acqua e aria in               |                                   |
| corrispondenza del pelo libero    |                                   |
| sia nullo.                        |                                   |
|                                   |                                   |
| Assegnata la portata in massa per |                                   |
| unità di apertura                 |                                   |
| $\overline{Q}=0.5\ kg/(ms)$,      |                                   |
| determinare                       |                                   |
|                                   |                                   |
| 1.  lo spessore $h$ della         |                                   |
|     corrente d'acqua;             |                                   |
|                                   |                                   |
| 2.  lo sforzo tangenziale a       |                                   |
|     parete;                       |                                   |
|                                   |                                   |
| 3.  la velocità in corrispondenza |                                   |
|     del pelo libero;              |                                   |
|                                   |                                   |
| 4.  la velocità media e il numero |                                   |
|     di Reynolds basato su tale    |                                   |
|     velocità media e sullo        |                                   |
|     spessore della corrente.      |                                   |
|                                   |                                   |
| Si sostituisca poi al pelo libero |                                   |
| una parete solida. Si determini   |                                   |
| quale dovrebbe essere la velocità |                                   |
| di tale parete per ottenere una   |                                   |
| portata nulla.                    |                                   |
|                                   |                                   |
| Dati:                             |                                   |
| $\overline{\rho}= 999\ kg/m^3$,   |                                   |
| $\overline{\mu}= 1.15\ 10^{-3} kg |                                   |
| /(ms)$.                           |                                   |
|                                   |                                   |
| ($h=5.61\, 10^{-4}\  m$,          |                                   |
| $\tau = 5.494\ Pa$,               |                                   |
| $u(h)=1.339\ m/s$,                |                                   |
| $\overline{U}=0.893\  m/s$,       |                                   |
| $Re=434.8$, $U=-0.4464\ m/s$.)    |                                   |
+-----------------------------------+-----------------------------------+

### Soluzione {#soluzione .unnumbered}

     **Concetti.** Semplificazione delle equazioni di NS in casi
particolari. Soluzioni esatte in coordinate cartesiane.

**Svolgimento.** Si scelga un sistema di riferimento cartesiano con
l'asse x orientato lungo la parete verso il basso e l'asse y
perpendicolare ed uscente ad essa.

Sulla corrente di questo problema agisce la forza di volume dovuta alla
gravità.

L'ipotesi che la pressione sia uniforme sulla superficie di interfaccia
tra acqua e aria implica che la pressione è costante in tutto il fluido:
si vedrà che $\frac{\partial p}{\partial y}=0$; se sulla superficie
libera la pressione è costante e non varia nello spessore, allora la
pressione è costante in tutto il fluido.

-   Scrittura delle equazioni di NS in 2 dimensioni.

    $$\begin{cases}
      \frac{\partial u}{\partial t} + u \frac{\partial u}{\partial x}
      + v \frac{\partial u}{\partial y} - \nu \left( 
      \frac{\partial^2 u}{\partial x^2} +
      \frac{\partial^2 u}{\partial y^2} \right)
       + \frac{1}{\rho} \frac{\partial p}{\partial x} = f_x \\
      \frac{\partial v}{\partial t} + u \frac{\partial v}{\partial x}
      + v \frac{\partial v}{\partial y} - \nu \left( 
      \frac{\partial^2 v}{\partial x^2} +
      \frac{\partial^2 v}{\partial y^2} \right)
      + \frac{1}{\rho}  \frac{\partial p}{\partial y} = f_y \\
      \frac{\partial u}{\partial x} + \frac{\partial v}{\partial y} = 0
    \end{cases}$$

-   Semplificazione delle equazioni di NS per il problema da affrontare.

    Ipotesi:

    -   problema stazionario: $\frac{\partial}{\partial t} = 0$;

    -   direzione x omogenea (canale infinito in direzione x):
        $\frac{\partial u}{\partial x} = \frac{\partial v}{\partial x} = 0$;
        la pressione nelle equazioni di NS incomprimibili è un
        moltiplicatore di Lagrange per imporre il vincolo di
        incomprimibilità; inoltre non appare mai, se non nelle
        condizioni al contorno, come $p$ ma solo con le sue derivate
        spaziali: quindi non è corretto imporre
        $= \frac{\partial v}{\partial x} = 0$, nonostante la direzione
        $x$ sia omogenea;

    -   $\frac{\partial u}{\partial x} = 0$ inserito nel vincolo di
        incomprimibilità
        ($\frac{\partial u}{\partial x}+\frac{\partial v}{\partial y}=0$)
        implica $\frac{\partial v}{\partial y}=0$; poichè
        $\frac{\partial v}{\partial x}=\frac{\partial v}{\partial y}=0$
        e $v = 0$ a parete per la condizione al contorno di adesione,
        segue che $v = \text{cost} = 0$;

    -   forze di volume solo in direzione verticale: per come sono stati
        orientati gli assi, $\bm{f} = g \hat{\bm{x}}$.

    $$\begin{cases}
      - \mu \frac{\partial^2 u}{\partial y^2} = - \frac{\partial p}{\partial x} + \rho g\\
      \frac{\partial p}{\partial y} = 0  
    \end{cases}$$

    Dalla seconda segue che la pressione può essere funzione solo di
    $x$. Come già detto in precedenza, la pressione sulla superficie
    libera è costante e uguale alla pressione ambiente $P_a$: se la
    pressione non può variare nello spessore, allora è costante ovunque.
    La derivata parziale $\frac{\partial p}
     {\partial x}=0$, il suo gradiente è nullo e quindi la pressione è
    costante in tutta la corrente di acqua.

    Nella prima, il termine a sinistra dell'uguale è funzione solo di
    $y$; quello di destra è costante e uguale a $\rho g$. Le condizioni
    al contorno sono di adesione a parete e di sforzo di taglio nullo
    all'interfaccia tra aria ed acqua:
    $0=\tau(H)=\mu \frac{\partial u}{\partial y}(H)=\mu u'(H)$, dove la
    derivata parziale in $y$ è stata sostituita da quella ordinaria,
    poichè la velocità è solo funzione di $y$.

    $$\begin{cases}
        - \mu u''(y) = \rho g \ , \ y \in[0,H] \\
        u(0) = 0  \\ u'(H) = 0
      \end{cases}$$

-   Soluzione dell'equazione differenziale (semplice) con dati al
    contorno.

    Risulta:
    $$\Rightarrow u(y) = - \frac{\rho g}{2 \mu} y^2 + \frac{\rho g}{\mu} H y$$

-   Calcolo della portata come integrale della velocità; si trova così
    la relazione tra Q ed H.

    $$Q = \int_{0}^{H} \rho u(y) dy = \frac{1}{3}\frac{\rho^2 g}{\mu} H^3$$
    E quindi
    $$H = \left( \frac{3 Q \mu}{\rho^2 g} \right) ^ {\frac{1}{3}}
         \quad \Rightarrow \quad H = 5.61 \cdot 10^{-4} m$$

-   Calcolo dello sforzo a parete
    $$\tau = \mu u'|_{y=0} = \rho g H \quad \Rightarrow \quad \tau = 5.494 Pa$$
    *Osservazione.* Equilibrio con la forza di gravità (problema
    stazionario).

-   Calcolo di $u(H)$. $$u(H) = \frac{1}{2}\frac{\rho g}{\mu} H^2 
        \quad \Rightarrow \quad u(H) = 1.342 m/s$$

-   Calcolo velocità media e numero di Reynolds.
    $$\bar{U} = \frac{1}{H}\int_{0}^{H} u(y) dy = \frac{Q}{\rho H}
        \quad \Rightarrow \quad \bar{U} = \frac{Q}{\rho H}
                                        = \frac{2}{3}u(H) = 0.895 m/s$$

    $$Re = \frac{\rho \bar{U} H}{\mu}
        \quad \Rightarrow \quad Re = 434.8$$

L'ultima parte del problema chiede di sostiutire alla superficie libera,
una parete infinita. L'equazione trovata in precedenza è ancora valida;
è necessario però sostituire la condizione di sforzo tangenziale nullo
con adesione su una parete mobile con velocità costante $U$.

$$\begin{cases}
    - \mu u''(y) = \rho g \ , \ y \in[0,H] \\
    u(0) = 0  \\ u(H) = U
  \end{cases}$$

Il profilo di velocità è:
$$u(y) = \dfrac{\rho g}{2 \mu}(-y^2 + yH) +\dfrac{U}{H}y$$ dove la
velocità $U$ è ancora incognita. Per trovarne il valore, si calcola la
portata e la si pone uguale a zero. La portata è uguale a
$$Q = \int_0^H u(y) dy = \dots = \dfrac{1}{12}\dfrac{\rho g H^3}{\mu}
 + \dfrac{1}{2}UH$$ Imponendo $Q=0$,
$$U = - \dfrac{\rho g H^2}{6 \mu} \quad \Rightarrow \quad
 U = - 0.4474\ m/s$$
