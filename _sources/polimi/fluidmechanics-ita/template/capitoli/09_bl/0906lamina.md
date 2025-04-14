**Esercizi per il corso di Fluidodinamica**

Nella figura accanto una lastra piana di corda $c=30\ cm$, apertura
$b=75\ cm$ e spessore trascurabile è investita da una corrente esterna
d'aria ($\rho=1.225\ kg/ m^3$, $\mu=1.76\times10^{-5}\ kg/(ms)$)
uniforme in corda e variabile in apertura secondo la legge
$$\bm{U}_e(z) = U_e(z) \mathbf{\hat{\bm{x}}} = \overline{U} \left( \frac{z}{b} \right)^{2/3} \mathbf{\hat{\bm{x}}}$$
con $\overline{U}=5\ m/s$. Assumendo la corrente laminare, stazionaria e
bidimensionale su ciascuna sezione $z$ in apertura, e potendone
approssimare lo strato limite attraverso la soluzione di Blasius, si
richiede di:

-   calcolare la resistenza $D$ della lastra ed il corrispondente
    momento all'incastro $M_y$;

-   calcolare lo spessore di spostamento $\delta^*(x,z)$ e di quantità
    di moto $\theta(x,z)$ dello strato limite sulla superficie della
    lamina;

![image](./fig/sheet){width="100%"}

### Soluzione {#soluzione .unnumbered}

     **Concetti.** Soluzione di Blasius dello strato limite. Spessori di
strato limite.

**Svolgimento.** Assumendo valido il modello 2D di Blasius per lo strato
limite *quasi-3D* del problema, lo spessore convenzionale dello strato
limite vale $$\delta(x,z) = \sqrt{ \dfrac{x \nu}{ U_e(z)} } \ ,$$ e lo
sforzo viscoso a parete in direzione $x$ vale
$$\tau_w(x,z) = \mu \dfrac{\partial u}{\partial y}\Bigg|_{y=0} = 
     \mu \, g''(0) \dfrac{U_e(z)}{\delta(x,z)} = 
     g''(0) \mu \dfrac{U_e^{3/2}(z)}{\sqrt{\nu x}}  \ .
     = g''(0) \sqrt{ \mu \rho } \dfrac{U_e^{3/2}(z)}{\sqrt{x}}  \ .$$
Utilizzando il profilo di velocità fornito dal problema,
$$\delta(x,z) = \sqrt{\dfrac{x \nu b^{1/3}}{ \overline{U} z^{1/3} }} \qquad , \qquad
     \tau_w(x,z) = g''(0) \sqrt{ \mu \rho } \, \dfrac{\overline{U}^{3/2}}{b} \dfrac{z}{\sqrt{x}}  \ .$$

-   Per il calcolo della resistenza e del momento alla radice è
    necessario calcolare lo sforzo a parete sulla lamina piana
    $\tau_w (x,z)$. La resistenza è l'integrale di $\tau_w$ sulla
    superficie; il momento $M_y$ è l'integrale di $z \tau_w (x,z)$
    esteso alla superficie,
    $$D = \int_{x=0}^{c} \int_{z=0}^b \tau_w(x,z) dx \, dz = 
        g''(0) \sqrt{ \mu \rho } \, \overline{U}^{3/2} \, b \, \sqrt{c} \ ,$$
    $$M_y = \int_{x=0}^{c} \int_{z=0}^b z \tau_w(x,z) dx \, dz = 
        \dfrac{2}{3} g''(0) \sqrt{ \mu \rho } \, \overline{U}^{3/2} \, b^2 \, \sqrt{c} \ .$$

-   Nel modello *quasi-3D* dello strato limite, gli spessori integrali
    sono funzione di $(x,z)$,
    $$\delta^*(x,z) = \int_0^\infty \displaystyle\left[ 1 - \frac{u(x,y,z)}{U_e(x,z)} \right] dy ,\qquad
       \theta(x,z) = \int_0^\infty \frac{u(x,y,z)}{U_e(x,z)} \displaystyle\left[ 1 - \frac{u(x,y,z)}{U_e(x,z)} \right] dy \ ,$$
    e utilizzando le relazioni dello strato limite di Blasius
    $$\delta^*(x,z) = 1.721 \, \delta(x,z) \qquad , \qquad
           \theta(x,z) = 0.644 \, \delta(x,z) \ .$$
