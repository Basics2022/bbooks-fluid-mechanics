**Esercizi per il corso di Fluidodinamica**

+:---------------------------------------------------------------------:+
| Si consideri la corrente a potenziale piana e stazionaria descritta   |
| in un sistema di riferimento Cartesiano $(x,y)$ dalla funzione        |
| potenziale cinetico $\phi(x,y)$: $$\phi(x,y) = 5(x^2-y^2) + 2x-4y.$$  |
| Si richiede di:                                                       |
|                                                                       |
| -   derivare l'espressione analitica delle componenti in $x$ e in $y$ |
|     del campo di velocità;                                            |
|                                                                       |
| -   verificare che la corrente sia incomprimibile e irrotazionale;    |
|                                                                       |
| -   derivare l'espressione analitica della funzione di corrente       |
|     $\psi(x,y)$;                                                      |
|                                                                       |
| -   calcolare la portata volumetrica per unità di apertura $q$ che    |
|     scorre attraverso il segmento congiungente l'origine del piano    |
|     con il punto di coordinate $(1,1)$;                               |
|                                                                       |
| ($u_x=10x+2$, $u_y=-10y-4$, $\psi(x,y)=10xy+2y+4x + const.$, $q=16$)  |
+-----------------------------------------------------------------------+

### Soluzione {#soluzione .unnumbered}

     **Concetti.** Legame tra potenziale e velocità. Funzione di
corrente per problemi 2D incomprimibili.
$$\bm{u} = \bm{\nabla} \phi \quad
  \begin{cases}
  \begin{aligned}
   & u_x  =  \frac{\partial \phi}{\partial x}  = \frac{\partial \psi}{\partial y} \\
   & u_y  =  \frac{\partial \phi}{\partial y}  = - \frac{\partial \psi}{\partial x}
  \end{aligned}
  \end{cases}$$

**Svolgimento.**

-   Calcolo delle componenti della velocità. $$\begin{cases}
        u_x = \frac{\partial \phi}{\partial x} = 10 x + 2 \\
        u_y = \frac{\partial \phi}{\partial y} = -10 y - 4
      \end{cases}$$

-   Verificare che la corrente sia incomprimibile e irrotazionale.

    -   Irrotazionalità ($\nabla \times \bm{u} = 0$). Verifica tramite
        l'identità vettoriale $\nabla \times \nabla \phi = 0$, oppure
        con il calcolo diretto. $$\begin{aligned}
              & \nabla \times \bm{u} = \nabla \times (\nabla \phi) = 0 \\
              & \nabla \times \bm{u} = \nabla \times ( (10x+2)\hat{\bm{x}} + (-10y-4)\hat{\bm{y}} ) = 
              \displaystyle \left(\frac{\partial u_y}{\partial x} - \frac{\partial u_x}{\partial y} \right)\hat{\bm{z}} = 0
            \end{aligned}$$

    -   Incomprimibilità ($\nabla \cdot \bm{u} = 0$). Dal calcolo
        diretto
        $\partial^2 \phi /\partial x^2 + \partial^2 \phi /\partial y^2=10-10=0$.

-   La corrente è incomprimibile, quindi si può definire la funzione di
    corrente. Usando la definizione della funzione di corrente,
    integrando, si ottiene:

    $$\begin{aligned}
        &\frac{\partial \psi}{\partial y} = u_x   &\quad \Rightarrow \quad \psi = 10xy+2y+f(x)\\
        &\frac{\partial \psi}{\partial x} = -u_y  &\quad \Rightarrow \quad \psi = 10xy+4x+g(y)
      \end{aligned}$$

    $$\psi = 10 xy + 2y + 4x + c$$

-   Calcolo della portata.
    $$Q = \int_{\gamma} \bm{u} \cdot \hat{\bm{n}} = \int_{\gamma} (u_x n_x + u_y n_y) = 
        \int_{\gamma} (u_x t_y - u_y t_x) = 
        \int_{\gamma} \displaystyle\left(\frac{\partial \psi}{\partial x} t_x + \frac{\partial \psi}{\partial y} t_y\right) = 
        \psi(1,1) - \psi(0,0) = 16$$

+:---------------------------------------------------------------------:+
| Una corrente piana con velocità asintotica $U_\infty=10\ m/s$ investe |
| un profilo circolare di raggio $a=0.1\ m$. Determinare il valore di   |
| circolazione $\Gamma$ affinché nel punto sulla superficie del         |
| cilindro posto a $\theta=\pi/3$ la velocità aumenti fino al valore    |
| $2U_\infty$ in modulo.                                                |
|                                                                       |
| ($\Gamma = -1.68\ m^2 / s$, 23.45$\ m^2 / s$)                         |
+-----------------------------------------------------------------------+

### Soluzione {#soluzione-1 .unnumbered}

     **Concetti.** Flusso non viscoso 2D, incomprimibile e irrotazionale
attorno al cilindro. Circolazione

**Svolgimento.** Una volta scritte (come si ricavano?) le componenti
della velocità nel campo di moto, si impongono le condizioni richieste
dal problema per determinare il valore di circolazione necessario.

$$\begin{cases}
  u_r (r,\theta) = U_\infty \displaystyle \left(1 - \frac{a^2}{r^2}\right)\cos{\theta} \\
  u_\theta (r,\theta) = - U_\infty \displaystyle \left(1 + \frac{a^2}{r^2}\right)\sin{\theta} + \frac{\Gamma}{2\pi r}
\end{cases}$$

Si impongono ora le condizioni del problema. Sulla superficie del
cilindro la componente radiale è nulla (condizioni al contorno). Quindi:

$$|\bm{u}(a,\theta)| = |u_\theta(a,\theta)| = \Big| - 2 U_\infty \sin{\theta} + \frac{\Gamma}{2 \pi a} \Big|$$

E quindi $$\begin{aligned}
  2 U_\infty & = \Big| - 2 U_\infty \sin{\frac{\pi}{3}} + \frac{\Gamma}{2 \pi a} \Big| \\
  \pm 2 U_\infty & = - 2 U_\infty \frac{\sqrt{3}}{2} + \frac{\Gamma}{2 \pi a} \\
  \\
  \Rightarrow \Gamma  & = 2 \pi a U_\infty (\sqrt{3} \pm 2)
\end{aligned}$$

$$\Rightarrow \Gamma = 
  \begin{cases}
    -1.684 \ m^2/s \\
    23,449 \ m^2/s
  \end{cases}$$

  --------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------
   Una corrente piana con velocità asintotica orizzontale (parallela all'asse x) $U_\infty=1$ viene perturbata introducendo nell'origine del piano un vortice in modo tale da accelerare la corrente nel semipiano superiore e rallentarla in quello inferiore per valori positivi di $\Gamma$. Determinare la circolazione necessaria ad ottenere una differenza di componente x della velocità pari a 1 tra i due punti di coordinate (polari) $R=1$ e $\theta=\pm\pi/2$. ($\Gamma = -\pi$)
  --------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------

### Soluzione {#soluzione-2 .unnumbered}

     **Concetti.** Flusso non viscoso 2D, incomprimibile e
irrotazionale. Circolazione. Corrente indisturbata. Vortice.
Sovrapposizione delle cause e degli effetti.

**Svolgimento.** Una volta scritte (come si ricavano?) le componenti
della velocità nel campo di moto, si impongono le condizioni richieste
dal problema per determinare il valore di circolazione necessario.

$$\begin{cases}
  u_r (r,\theta) = U_\infty \cos{\theta} \\
  u_\theta (r,\theta) = - U_\infty \sin{\theta} + \frac{\Gamma}{2\pi r}
\end{cases}$$

Si impongono ora le condizioni del problema. Per $\theta_1 = \pi/2$ e
$\theta_2 = -\pi/2$, la componente radiale è nulla.

$$\begin{cases}
    u_{\theta}(R,\theta_1) = -U_\infty + \frac{\Gamma}{2\pi R} \\
    u_{\theta}(R,\theta_2) = U_\infty + \frac{\Gamma}{2\pi R}
  \end{cases}$$

Si vuole determinare la differenza delle componenti in direzione x
$u_x(R,\theta_1) - u_x(R,\theta_2)$; questa è uguale a
$-(u_\theta(R,\theta_1) + u_\theta(R,\theta_2))$. Quindi, per $R=1$:

$$-\frac{\Gamma}{\pi} = 1 \quad \Rightarrow \quad \Gamma = -\pi$$

+:---------------------------------------------------------------------:+
| Si consideri la copertura rigida di un campo da calcio avente sezione |
| semicircolare di raggio $\bar{R}=50\ m$ rappresentata schematicamente |
| in figura. Sulla struttura soffia un vento uniforme                   |
| ($\rho=1.225\,kg/m^3$, $P_\infty=101325\ Pa$) in direzione            |
| orizzontale con velocità $U_\infty=15\,km/h$. Assumendo di poter      |
| approssimare la corrente esterna come stazionaria, bidimensionale e a |
| potenziale, si richiede di determinare:                               |
|                                                                       |
| -   la distribuzione della pressione esterna sulla sezione della      |
|     struttura;                                                        |
|                                                                       |
| -   la risultante per unità di apertura delle forze agenti sulla      |
|     struttura, ipotizzando che la pressione interna $P_i$ sia pari a  |
|     $P_\infty$.                                                       |
|                                                                       |
| ($P(\theta) = P_\infty+\frac{1}{2}\rho U_\infty^2(1-4\sin^2\!\theta)$ |
| ,                                                                     |
| $\bm{F} = 425.35\mathbf{\hat{\bm{y}}}\ N/m$)                          |
|                                                                       |
| ![image](./fig/Cyl.png){width="150%"}                                 |
+-----------------------------------------------------------------------+

### Soluzione {#soluzione-3 .unnumbered}

     **Concetti.** Flusso non viscoso 2D, incomprimibile e irrotazionale
attorno al cilindro. Circolazione.

**Svolgimento.** Una volta scritte (come si ricavano?) le componenti
della velocità nel campo di moto, tramite il teorema di Bernoulli (nel
caso incomprimibile, stazionario, inviscido, irrotazionale,\...) si
calcola la pressione agente sulla superficie del cilindro. Integrando
gli sforzi di pressione (interna ed esterna al cilindro) sul contorno,
si ottiene la risultante.

-   Campo di moto nel dominio esterno alla metà cilindro
    ($(r,\theta) \in [0,\infty)\times[0,\pi])$.

    $$\begin{cases}
      u_r (r,\theta) = U_\infty \displaystyle \left(1 - \frac{a^2}{r^2}\right)\cos{\theta} \\
      u_\theta (r,\theta) = - U_\infty \displaystyle \left(1 + \frac{a^2}{r^2}\right)\sin{\theta}
    \end{cases}$$

-   Grazie al teorema di Bernoulli (ipotesi\...) si ottiene la pressione
    esterna sulla superficie della metà di cilindro. Sulla superficie
    del cilindro la componente radiale è nulla, quindi il modulo della
    velocità coincide con il valore assoluto della componente radiale.
    $$\begin{aligned}
      P(\theta) & = P_\infty + \frac{1}{2}\rho U_\infty^2 - \frac{1}{2}\rho u_\theta(a,\theta)^2 = \\
                & = P_\infty + \frac{1}{2}\rho U_\infty^2 - \frac{1}{2}\rho (2 U_\infty \sin{\theta})^2 = \\
                & = P_\infty + \frac{1}{2}\rho U_\infty^2 (1 - 4 \sin^2{\theta})
    \end{aligned}$$

-   Integrale sulla superficie (interna ed esterna) degli sforzi di
    pressione per ottenere la risultante. Con $\hat{\bm{b}}$ si indica
    la normale diretta verso il centro del cilindro.

    $$\begin{aligned}
      \bm{F} & = \int_{0}^{\pi} (P(\theta)-P_\infty) \hat{\bm{b}} a d\theta = \\
          & = \int_{0}^{\pi} (\frac{1}{2}\rho U_\infty^2 (1 - 4 \sin^2{\theta}) (-\cos{\theta}\hat{\bm{x}} - \sin{\theta}\hat{\bm{y}}) a d\theta = \\
    \end{aligned}$$

    Usando i risultati (integrare!!) $$\begin{aligned}
     & \int_{0}^{\pi} \sin{\theta} d\theta  = 2 \\
     & \int_{0}^{\pi} \cos{\theta} d\theta  = 0 \\
     & \int_{0}^{\pi} \sin^3{\theta} d\theta  = \frac{4}{3} \\
     & \int_{0}^{\pi} \cos{\theta}\sin^2{\theta} d\theta  = 0 
    \end{aligned}$$

    si ottiene: $$\begin{aligned}
      \bm{F} & = \int_{0}^{\pi} (P(\theta)-P_\infty) \hat{\bm{b}} a d\theta = \\
          & = - \frac{1}{2}\rho a U_\infty^2 \int_{0}^{\pi}  (1 - 4 \sin^2{\theta}) \sin{\theta}\hat{\bm{y}} d\theta = \\
          & = - \frac{1}{2}\rho a U_\infty^2 \displaystyle\left( 2 - \frac{16}{3}\right)\hat{\bm{y}} \\ \\
      \bm{F} & = \frac{5}{3}\rho a U_\infty^2 \hat{\bm{y}} \quad \Rightarrow \quad \bm{F} = 425.35 \hat{\bm{y}} N/m
    \end{aligned}$$

Condizione necessaria di incipiente separazione
-----------------------------------------------

Un punto di incipiente separazione viene identificato dall'anullarsi
della derivata in direzione perpendicolare a parete della componente di
velocità parallela ad essa, con derivata seconda positiva. Si consideri
il problema bidimensionale su una superficie piana: viene scelto di
usare un sistema di riferimento cartesiano con l'asse $x$ parallelo alla
parete e diretto nel verso della corrente asintotica
$\bm{U} = U \bm{x}$, l'asse $y$ uscente dalla parete. La componente $x$
dell'equazione della quantità di moto è
$$u \dfrac{\partial u}{\partial x} +
  v \dfrac{\partial u}{\partial y} -
  \dfrac{1}{Re}\left[ \dfrac{\partial^2 u}{\partial x^2} +
                      \dfrac{\partial^2 u}{\partial y^2} \right] +
  \dfrac{\partial P}{\partial x} = 0$$ A parete i termini non lineari
sono nulli poichè la velocità è nulla per la condizione di adesione. La
derivata seconda in direzione $x$ è nulla poichè a parete la velocità è
sempre zero per ogni valore della coordinata $x$. Rimane quindi
$$\dfrac{\partial P}{\partial x} =
    \dfrac{1}{Re}\dfrac{\partial^2 u}{\partial y^2} > 0$$

  ------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------
   Si assuma che il profilo di velocità $u(x,y)$ dello strato limite sulla superficie di un corpo sia approssimabile con la seguente legge $$u = \frac{(1-x)y}{1+y} + \frac{xy^2}{1+y^2},$$ dove $u$ è la velocità adimensionalizzata rispetto alla velocità esterna, $x$ è la coordinata adimensionale di parete localmente rettilinea e $y$ la coordinata adimensionale in direzione normale alla parete stessa. Determinare la coordinata $x_s$ del punto di separazione dello strato limite in questione.
  ------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------

### Soluzione {#soluzione-4 .unnumbered}

     **Concetti.** Separazione.

**Svolgimento.**

$$\begin{aligned}
  \frac{\partial u}{\partial y} & = \frac{\partial}{\partial y} \displaystyle \left[
  \frac{(1-x)y}{1+y} + \frac{xy^2}{1+y^2} \right] = \\
  & = (1-x)\frac{1}{(1+y)^2} + x \frac{2y}{(1+y^2)^2}
\end{aligned}$$

Quando si impone la condizione di separazione
$\frac{\partial u}{\partial y}\big|_{y=0} = 0$, si ottiene $x_s = 1$.

![Linee di corrente e modulo della
velocità.](./fig/Ese75contour.eps){width="90%"}

![Campo di velocità e modulo della
velocità.](./fig/Ese75quiver.eps){width="90%"}

![Andamento della componente orizzontale $u(y)$ in diverse stazioni
x.](./fig/Ese75u.eps){width="90%"}

Se si ipotizza che il moto del fluido sia governato dalle equazioni di
Navier-Stokes per fluido incomprimibile (così facendo, si abbandonano le
ipotesi di non viscosità del fluido e irrotazionalità della corrente,
proprie dell'Aerodinamica; in realtà questo è già stato fatto nel testo
del problema, imponendo un profilo di velocità che soddisfa la
condizione di adesione a parete\...) è possibile ricostruire il campo di
velocità e di pressione. Utilizzando il vincolo di incomprimibilità e le
condizioni al contorno a parete ($y=0$), si può calcolare la componente
di velocità $v(x,y)$ perpendicolare alla parete
$$v(x,y) = - ln | 1 + y | + atan \ y$$ Utilizzando le equazioni
stazionarie di Navier-Stokes è possibile determinare il campo di
pressione $P(x,y)$. La pressione (a meno di costanti di integrazione) e
la derivata in direzione $x$ valutate a parete valgono $$\begin{cases}
  P(x,0) & = \dfrac{1}{Re} ( 2 x^2 - 2 x ) \\
  \dfrac{\partial P}{\partial x}(x,0) & = \dfrac{1}{Re} ( 4 x - 2 )
 \end{cases}$$ Si noti che nel punto di separazione $x_s=1$, la derivata
$\partial P/
 \partial x (x_s,0) = 2 / Re$ è positiva (come era logico attendersi,
per la condizione necessaria di incipiente separazione).

+:---------------------------------------------------------------------:+
| Si assuma che il profilo di velocità $u(x,y)$ dello strato limite     |
| sulla superficie di un corpo sia approssimabile con la seguente legge |
| $$u = 1-e^{-y/\sqrt{x}},$$ dove $u$ è la velocità adimensionalizzata  |
| rispetto alla velocità esterna, $x$ è la coordinata adimensionale di  |
| parete localmente rettilinea e $y$ la coordinata adimensionale in     |
| direzione normale alla parete stessa. Determinare l'andamento dello   |
| spessore di spostamento $\delta$ in funzione della coordinata $x$     |
| lungo la parete. Lo strato limite in questione separa? Se si per      |
| quale valore di $x$?                                                  |
|                                                                       |
| ($\delta(x)=\sqrt{x}$, lo strato limite non separa mai se non nel     |
| limite di $x\rightarrow\infty$)                                       |
+-----------------------------------------------------------------------+

### Soluzione {#soluzione-5 .unnumbered}

     **Concetti.** Separazione. Spessori di strato limite.

$$\delta(x) = \int_{0}^{\infty} \left( 1 - \frac{u(y)}{U_e} \right) dy$$

**Svolgimento.**

-   Spessore di spostamento. Il profilo di velocità è già
    adimensionalizzato sulla \"velocità esterna\". Utilizzando la
    definizione di spessore di spostamento, si ottiene:
    $$\begin{aligned}
      \delta(x) & = \int_{0}^{\infty} \left( 1 - u(y) \right) dy = \\
      & = \int_{0}^{\infty} (1 - (1-e^{-y/\sqrt{x}}))dy  = \\
      & = \int_{0}^{\infty} e^{-y/\sqrt{x}} dy = \\
      & = -\sqrt{x} [e^{-y/\sqrt{x}}]\big|_{y=0}^{\infty}
    \end{aligned}$$

    E quindi: $\delta(x) = \sqrt{x}$.

-   Separazione. La condizione di separazione è
    $\frac{\partial u}{\partial y}\big|_{y=0} = 0$.

    $$\begin{aligned}
      \frac{\partial u}{\partial y}  = 
      \frac{\partial}{\partial y} \displaystyle \left[   1-e^{-y x^{-1/2}} \right] = 
       x^{-1/2} e^{-y x^{-1/2}}
    \end{aligned}$$

    Si osserva che $\frac{\partial u}{\partial y}\big|_{y=0}$ non si
    annulla mai:
    $$\displaystyle\frac{\partial u}{\partial y}\displaystyle\Big|_{y=0} = \frac{1}{\sqrt{x}}$$

  ------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------
   Trovare il campo di moto generato da una doppietta. Sovrapporre ad esso una corente uniforme con lìvelocità asintotica lungo x, per trovare la corrente attorno al cilindro: stabilire il legame tra l'intensità della doppietta, la velocità asintotica e il raggio del cilindro.
  ------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------

### Soluzione {#soluzione-6 .unnumbered}

     **Concetti.** Soluzioni elementari dell'equazione di Laplace.
Sovrapposizione di soluzioni elementari. Doppietta. Corrente attorno al
cilindro.

**Svolgimento.** Dopo aver ricordato la definizione di doppietta, si
calcolano il campo di moto e il potenziale cinetico da essa generato.
Fatto questo, si sommano gli effetti della corrente indisturbata e si
trovano le condizioni in cui esiste un raggio $a$ (il raggio del
cilindro) per il quale si annulla la velocità normale per ogni
$\theta \in [0, 2\pi]$.

-   Definizione di doppietta ed equazioni. Per $d$ finito:

    $$\begin{aligned}
        \phi & = \phi^+ + \phi^- = \\
        & = \frac{q}{2\pi}\ln{\sqrt{\displaystyle\left( x - \frac{d}{2} \right)^2 + y^2}} - 
        \frac{q}{2\pi}\ln{\sqrt{\displaystyle\left( x + \frac{d}{2} \right)^2 + y^2}} = \\
        & = \frac{q}{4\pi}\ln{\frac{( x - d/2 )^2 + y^2}{( x + d/2 )^2 + y^2}}
      \end{aligned}$$ Facendo tendere $d \to 0$ in modo tale che
    $qd = \mu$ sia finito e diverso da zero, sfruttando $\ln(1+x)\sim x$
    per $x \to 0$:
    $$\frac{q}{4\pi}\ln{\frac{( x - d/2 )^2 + y^2}{( x + d/2 )^2 + y^2}} = 
      \frac{q}{4\pi}\ln\displaystyle\left[1- \frac{2xd}{( x + d/2 )^2 + y^2}\right] \sim
      -\frac{qd}{2\pi}\frac{x}{(x^2 + y^2)}$$ Quindi, il potenziale
    cinetico della doppietta espresso in coordinate cartesiane e
    cilindriche è:
    $$\phi = -\frac{\mu}{2\pi}\frac{x}{(x^2 + y^2)} = -\frac{\mu}{2\pi r}\cos \theta$$
    Le componenti cartesiane della velocità sono: $$\begin{cases}
      u = \frac{\partial \phi}{\partial x} = \frac{\mu}{2\pi}\frac{x^2 - y^2}{(x^2 + y^2)^2} =  \frac{\mu}{2\pi}\frac{\cos^2 \theta - \sin^2 \theta}{r^2} = \frac{\mu}{2\pi}\frac{\cos(2\theta)}{r^2} \\
      v = \frac{\partial \phi}{\partial y} = \frac{\mu}{2\pi}\frac{2xy}{(x^2 + y^2)^2} =  \frac{\mu}{2\pi}\frac{2\cos \theta \sin \theta}{r^2} = \frac{\mu}{2\pi}\frac{\sin(2\theta)}{r^2} \\
     \end{cases}$$ Quelle cilindriche: $$\begin{cases}
      u_r = u \cos\theta + v \sin\theta = 
      \frac{\mu}{2\pi r^2}[\cos(2\theta)\cos\theta + 
      \sin(2\theta)\sin\theta ] = 
      \frac{\mu}{2\pi r^2} \cos\theta\\
      u_\theta = -u \sin\theta + v \cos\theta = 
      \frac{\mu}{2\pi r^2}[- \cos(2\theta)\sin\theta + 
      \sin(2\theta)\cos\theta] = 
      \frac{\mu}{2\pi r^2} \sin\theta\\
     \end{cases}$$

-   Si svovrappone alla soluzione appena trovata, quella della corrente
    uniforme

    $$\begin{cases}
        u_r = \displaystyle\left( U_\infty + \frac{\mu}{2\pi r^2} \right)\cos\theta \\
        u_\theta = \displaystyle\left( - U_\infty + \frac{\mu}{2\pi r^2} \right)\sin\theta \\
      \end{cases}$$

-   Si impongono le condizioni al contorno
    $u_r(a,\theta) = 0, \theta \in [0, 2\pi]$, per trovare il legame tra
    il raggio del cilindro $a$, la velocità asintotica $U_\infty$ e
    l'intensità della doppietta $\mu$.
    $$0 = u_r(a,\theta) =  \displaystyle\left( U_\infty + \frac{\mu}{2\pi a^2} \right)\cos\theta
      \Rightarrow \frac{\mu}{2\pi} = - a^2 U_\infty$$

-   Si ricostruisce infine la soluzione (alla quale è immediato sommare
    un eventuale vortice nel centro del cilindro) del flusso potenziale
    all'esterno del cilindro:

    $$\begin{cases}
        u_r = U_\infty \displaystyle\left(1 - \frac{a^2}{r^2}  \right)\cos\theta \\
        u_\theta = - U_\infty \displaystyle\left(1 + \frac{a^2}{r^2}  \right)\sin\theta \\
      \end{cases}$$

Il metodo di Pistolesi è un primo metodo rudimentale per la modellazione
di profili bidimensionali nell'ambito della teoria a potenziale. Il
profilo viene approssimato con una lamina piana. L'effetto del profilo
viene modellato tramite la sovrapposizione a una corrente asintotica di
un vortice posto a un quarto di corda (corrispondente all'incirca con la
posizione del centro aerodinamico - def\...). Il valore della
circolazione (e quindi della portanza) viene ricavato imponendo le
condizioni al contorno in un punto di controllo sul profilo.

Assumendo sia valida l'approssimazione per piccoli angoli
$\sin \alpha \sim \alpha$, confrontando la formula della portanza
$l = \frac{1}{2} \rho U^2 c c_L$ con quella ottenuta dal teorema di
Kutta-Joukowski, ipotizzando un valore di $c_{L_\alpha} = 2\pi$, si
trovi il punto di controllo nel quale deve essere imposta la condizione
al contorno.

Quale condizione al contorno va imposta e perchè?

### Soluzione {#soluzione-7 .unnumbered}

     **Concetti.** Metodi a pannelli. Metodo di Pistolesi. Aerodinamica
potenziale.

**Svolgimento.** La condizione da imporre è quella di tangenza: la
velocità nel punto di controllo deve essere tangente alla lamina piana.

Definita $b$ la distanza del punto di controllo dal centro aerodinamico,
si impone la condizione al contorno in tale punto: deve essere nulla la
componente normale alla lamina della velocità ottenuta come
sovrapposizione della corrente asintotica e della corrente indotta dal
vortice.

$$0 = \frac{\Gamma}{2\pi b} + U_\infty \sin \alpha \qquad \Rightarrow \qquad 
  \Gamma = - 2\pi b U_\infty \alpha$$

Inserita nel teorema di Kutta-Joukowski
$l = -\rho \Gamma U_\infty = \rho U_\infty^2 b 2\pi \alpha$ e
confrontata alla formula della portanza
$l = \frac{1}{2} \rho U^2 c c_L$, si ottiene

$$b = \frac{c}{2}$$

Quindi nel metodo di Pistolesi, il centro aerodinamico è posizionato
$\frac{1}{4}$ di corda, mentre il punto di controllo è posizionato a
$\frac{3}{4}$ di corda.

*Osservazioni.*

-   É possibile simulare l'interazione tra più profili. Con metodi a
    pannelli un po' più raffinati (Hess Smith, Morino,\...) è possibile
    simulare l'interazione tra corpi aerodinamici di forma qualsiasi,
    ricordandosi che le informazioni ottenute sono valide sotto le
    ipotesi dell'aerodinamica a potenziale: non devono verificarsi
    grandi separazioni, la vorticità deve essere confinata in una
    regione sottile (numero di Reynolds elevato).

-   Quale può essere un metodo per simulare l'effetto di una superficie
    piana infinita (effetto suolo)?

Usare il metodo di Pistolesi per ottenere delle informazioni qualitative
sul coefficiente di portanza

-   di un profilo in effetto suolo

-   di due profili, in funzione della posizione reciproca

#### Confronto con i risultati ottenuti con il metodo di Hess Smith: effetto suolo.

Con il metodo delle immagini è possibile calcolare l'effetto che ha la
presenza di una parete orizzontale (parallela alla velocità asintotica)
sul coefficiente di portanza di un profilo NACA2412 con incidenza
$\theta = 2\degree$. Il coefficiente di portanza in "aria libera" è
$c_{L0} = 0.481$. La distanza del profilo dalla parete è
adimensionalizzata sulla corda.

+:---------------------------------:+::+
|       h/c      cL     DcL/cL0     |  |
|     ----------------------------- |  |
|      0.500   0.680     0.261      |  |
|      1.000   0.536     0.112      |  |
|      1.500   0.508     0.054      |  |
|      2.000   0.498     0.033      |  |
|      2.500   0.493     0.022      |  |
|      3.000   0.490     0.016      |  |
|      3.500   0.488     0.012      |  |
+-----------------------------------+--+

#### Confronto con i risultati ottenuti con il metodo di Hess Smith: due profili.

Quando due profili sono investiti da una corrente, ognuno di essi
influenza l'altro. Come primo esempio vengono usati due profili
NACA0012, con la stessa corda. Il secondo profilo viene messo in scia al
primo a distanza di 3 corde. La prima prova consiste nel mantenere il
secondo profilo a incidenza nulla rispetto alla velocità asintotica,
aumentando l'incidenza del primo. Il primo profilo genera una portanza
inferiore a un profilo in aria libera, mentre il secondo è deportante:
il primo profilo induce una velocità verso il basso sul profilo in coda,
che quindi vede un'incidenza non nulla, ma negativa.

     theta2 = 0.0\degree
    -------------------------------
     theta1    cL1     cL2    cL10 
    -------------------------------
       2.5°  0.286  -0.045   0.297 
       5.0°  0.571  -0.089   0.594 

La seconda prova consiste nel mantenere il primo profilo a incidenza
nulla rispetto alla velocità asintotica e aumentare l'incidenza del
profilo in scia. Il secondo profilo ha un coefficiente di portanza
minore rispetto a quello di un profilo in aria libera; il primo profilo
è anch'esso portante: il profilo in scia induce una velocità verso
l'alto sul primo profilo che quindi vede un'indicenza positiva.

     theta1 = 0.0°
    -------------------------------
     theta2    cL1     cL2    cL20 
    -------------------------------
       2.5°  0.064   0.287   0.297 
       5.0°  0.128   0.573   0.594 

La portanza risultante è maggiore a quella che si otterrebbe
considerando la somma della portanza generata singolarmente dai due
profili. Per esempio, per $\theta = 2.5°$: $$\begin{aligned}
 c_{L1} + c_{L2} & > c_{L01} + c_{L02} \\
  0.064 + 0.287  & >  0.000  +  0.297  \\
          0.351  & >  0.297
\end{aligned}$$ Lo stesso effetto viene osservato con due profili più
vicini tra loro. La corda del profilo secondario è la metà di quella del
profilo principale. Il profilo principale ha incidenza
$\theta_1 = -0.5°$ rispetto alla velocità asintotica, quello secondario
$\theta_2 = 12°$. La presenza del secondo profilo fa aumentare
significativamente la portanza del profilo principale.

+:----------------------------------+:----------------------------------+
|               +------------------ | ![image](./fig/Aileron.pdf){width |
| ------                            | ="95%"}                           |
|               | theta  |   cL  |  |                                   |
|  cL0                              |                                   |
|     ----------+--------+-------+- |                                   |
| ------                            |                                   |
|     airfoil 1 |  -0.5° | 1.099 |  |                                   |
| 0.184                             |                                   |
|     airfoil 2 |  12.0° | 0.975 |  |                                   |
| 1.656                             |                                   |
|     ----------+--------+-------+- |                                   |
| ------                            |                                   |
|                                   |                                   |
| La colonna $\mathtt{cL}$ contiene |                                   |
| i coefficienti di portanza dei    |                                   |
| profili disposti come in figura.  |                                   |
| La colonna $\mathtt{cL0}$         |                                   |
| contiene i coefficienti di        |                                   |
| portanza dei profili presi        |                                   |
| singolarmente, senza influenza    |                                   |
| reciproca, alla stessa incidenza. |                                   |
+-----------------------------------+-----------------------------------+

Come ultimo esempio si considerano due profili NACA0012 uguali
sovrapposti, con angolo di incidenza $\theta=5.0°$, separati da una
distanza adimensionalizzata $y/c$ compresa tra 1 e 15. Il coefficiente
di portanza del singolo profilo è $c_L = 0.594$.

![image](./fig/vanes.pdf){width="60%"}

Esistono alcuni esempi \"esotici\": ekranoplano sovietico\...; esempi
meno esotici:\...
