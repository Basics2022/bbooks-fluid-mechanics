Equazioni di Boussinesq
=======================

Le equazioni di Boussinesq sono un modello approssimato delle equazioni
complete del moto dei fluidi, ricavato sotto le ipotesi che:

-   il contributo di dissipazione nell'equazione dell'energia sia
    trascurabile;

-   la densità dipenda linearmente dalla temperatura nel termine di
    forze di volume nell'equazione della quantità di moto.

La variazione della densità in funzione della densità diventa quindi
$$d \rho(P, T) = \left(\dfrac{\partial \rho}{\partial P} \right)_T dP +  \left(\dfrac{\partial \rho}{\partial T} \right)_P dT \approx \left(\dfrac{\partial \rho}{\partial T} \right)_P dT = - \rho_0 \, \alpha \, dT \$$
$$\rightarrow \rho = \rho_0 \left( 1 - \alpha \, (T-T_0) \right) \ ,$$
dove le derivate sono calcolate nello stato termodinamico di
riferimento, $(\rho_0, \ T_0)$, ed è stato introdotto il coefficiente di
dilatazione termica
$$\alpha = - \dfrac{1}{\rho_0} \left(\dfrac{\partial \rho}{\partial T} \right)_P \ .$$
Introducendo le approssimazioni elencate, l'espressione dell'energia
interna $e = c_v T$ e la legge di Fourier per il flusso di calore per
conduzione, $\bm{q} = -k \bm{\nabla} T$, nelle equazioni complete per
una corrente incomprimibile di un fluido newtoniano, $$\begin{cases}
      \rho \dfrac{\partial \bm{u}}{\partial t} + \rho
      \left( \bm{u} \cdot \bm{\nabla} \right) \bm{u} -
      \mu \nabla^2 \bm{u} + \bm{\nabla} P = \rho \bm{g} \\
      \bm{\nabla} \cdot \bm{u} = 0 \\
      \rho \dfrac{\partial e}{\partial t} + \rho \bm{u} \cdot 
      \bm{\nabla} e = 2 \mu \mathbb{D}:\mathbb{D} - \bm{\nabla} \cdot \bm{q} \ ,
    \end{cases}$$ si ottengono le equazioni di Boussinesq
$$\begin{cases}
      \dfrac{\partial \bm{u}}{\partial t} + 
      \left( \bm{u} \cdot \bm{\nabla} \right) \bm{u} -
      \nu \nabla^2 \bm{u} + \dfrac{1}{\rho_0}\bm{\nabla} P = \big( 1 - \alpha ( T-T_0 ) \big) \bm{g} \\
      \bm{\nabla} \cdot \bm{u} = 0 \\
      \dfrac{\partial T}{\partial t} + \bm{u} \cdot 
      \bm{\nabla} T =  D \nabla^2 T \ ,
    \end{cases}$$ avendo definito il coefficiente di diffusione termica
$D = \dfrac{k}{\rho_0 c_v}$.

Equazioni di Boussinesq: problema bidimensionale tra due superfici piane
------------------------------------------------------------------------

### Condizioni al contorno

Si considera ora la corrente che si sviluppa tra due superfici piane
orizzontali infinite, a distanza $h$ l'una dall'altra, mantenute a
temperatura costante: la temperatura vale $T_w$ sulla superficie
inferiore e $T_c$ sulla superficie superiore. Viene definita la
differenza di temperatura $\Delta T = T_w - T_c$. Se le due superfici
considerate sono superfici solide, la velocità su di esse è nulla. Se le
due superfici sono superfici "libere" (di simmetria, a sforzo nullo) si
annulla la derivata normale della velocità. Prendendo un sistema di assi
ortogonali, con l'origine in corrispondenza della superficie inferiore,
con l'asse $x$ parallelo e l'asse $z$ perpendicolare alla superficie, si
possono riassumere così le condizioni al contorno, $$\text{wall: }
    \begin{cases}
      T(x,z=0) = T_w \\ T(x,z=h) = T_c \\
      \bm{u}(x,z=0) = \bm{0} \\ \bm{u}(x,z=h) = \bm{0}
    \end{cases}  \hspace{0.5cm}
    \text{free: } \left\{
    \begin{aligned}
      T(x,z=0) = T_w \ & \ , \ \ T(x,z=h) = T_c \\
      \dfrac{\partial u}{\partial z}(x,z=0) = 0 \ & \ , \ \ \dfrac{\partial u}{\partial z}(x,z=h) = 0 \\
      w(x,z=0) = 0 \ & \  , \  \  w(x,z=h) = 0 \ .
    \end{aligned} \right.$$ Non ci sono condizioni al contorno in $x$,
poichè la direzione è omogenea. Considereremo qui solo il problema con
le condizioni al contorno "free".

### Soluzione stazionaria non convettiva

Esiste una soluzione stazionaria ($\partial / \partial t = 0$) del
problema con fluido in quiete ($\bm{u} = \bm{0}$). Il vincolo di
incomprimibilità è soddisfatto identicamente. Sfruttando l'omogeneità
della direzione $x$, la soluzione stazionaria indipendente dalla
coordinata $x$ soddisfa le equazioni $$\begin{cases}
        \dfrac{1}{\rho_0}\dfrac{d P}{d z} = \alpha g (T-T_0)  \vspace{0.2cm} \\
        \dfrac{d^2 T}{d z^2} = 0 \ ,
    \end{cases}$$ dotate delle opportune condizioni al contorno. La
soluzione stazionaria del problema è $$\begin{cases}
    \overline{T}(z) = T_w + (T_c-T_w) \dfrac{z}{h} =
    T_w - \Delta T \dfrac{z}{h} \\
    \overline{P}(z) = P_w + \alpha \rho_0 g \left[ (T_w-T_0) z
    - \dfrac{1}{2} \Delta T \dfrac{z^2}{h} \right] \ ,
\end{cases}$$ avendo indicato con $P_w$ il valore della pressione in
corrispondenza della superficie inferiore a $z = 0$.

### Equazione delle fluttuazioni

Viene definita la fluttuazione di temperatura $\tau(x,z)$,
$$\begin{aligned}
    \tau(x,z) = T(x,z) - \overline{T}(z) & = T(x,z) - T_w + \Delta T \dfrac{z}{h} \\
    \quad \rightarrow \quad T(x,z) - T_w & = \tau(x,z) - \Delta T \dfrac{z}{h} \ .
\end{aligned}$$ Scegliendo la superficie inferiore a $z = 0$ per
definire la condizione termodinamica di riferimento, $T_0 = T_w$. le
equazioni di Boussinesq diventano $$\begin{cases}
      \dfrac{\partial \bm{u}}{\partial t} + 
      \left( \bm{u} \cdot \bm{\nabla} \right) \bm{u} -
      \nu \nabla^2 \bm{u} + \dfrac{1}{\rho_0}\bm{\nabla} P = \left( 1 - \alpha \tau + \Delta T \dfrac{z}{h} \right) \bm{g} \\
      \bm{\nabla} \cdot \bm{u} = 0 \\
      \dfrac{\partial \tau}{\partial t} + \bm{u} \cdot 
      \bm{\nabla} \tau + w \dfrac{\partial \overline{T}}{\partial z}=  D \nabla^2 \tau \ .
    \end{cases}$$ Inoltre è possibile raccogliere il primo e il terzo
termine delle forze di galleggiamento sotto lo stesso operatore di
gradiente che opera sul campo di pressione. Infatti, è possibile
scrivere il termine di galleggiamento come $$\begin{aligned}
    \left( 1 - \alpha \tau + \Delta T \dfrac{z}{h} \right) \bm{g} & = \alpha \tau g \bm{\hat{z}} - \bm{\nabla} \left( gz + \Delta T \dfrac{z^2}{2 h} \right) \ .
\end{aligned}$$ Definendo una "pressione generalizzata" $P'$,
$$P' = P + \rho_0 g z + \rho_0 \Delta T \dfrac{z^2}{2 h} \ ,$$ le
equazioni di Boussinesq diventano $$\label{eqn:Bouss-tau}
    \begin{cases}
      \dfrac{\partial \bm{u}}{\partial t} + 
      \left( \bm{u} \cdot \bm{\nabla} \right) \bm{u} -
      \nu \nabla^2 \bm{u} + \dfrac{1}{\rho_0}\bm{\nabla} P' = \alpha  g \tau \bm{\hat{z}} \\
      \bm{\nabla} \cdot \bm{u} = 0 \\
      \dfrac{\partial \tau}{\partial t} + \bm{u} \cdot 
      \bm{\nabla} \tau -\dfrac{\Delta T}{h} w =  D \nabla^2 \tau \ ,
    \end{cases}$$ e le condizioni al contorno della temperatura vengono
espresse anch'esse in funzione di $\tau$, $$\label{eqn:Bouss-tau-bc}
    \tau(x,z=0) = \tau(x,z=h) = 0 \ .$$

Equazioni di Boussinesq in forma adimensionale
==============================================

Si ricava la forma adimensionale delle equazioni
([\[eqn:Bouss-tau\]](#eqn:Bouss-tau){reference-type="ref"
reference="eqn:Bouss-tau"}) e delle condizioni al contorno
([\[eqn:Bouss-tau-bc\]](#eqn:Bouss-tau-bc){reference-type="ref"
reference="eqn:Bouss-tau-bc"}) utilizzando il teorema $\pi$ di
Buckingham. Nel problema di Boussinesq compaiono 12 grandezze
dimensionali (13 se si volesse considerare la componente $w$ della
velocità $\bm{u}$ in maniera indipendente),
$$\underbrace{\bm{x}, t}_{\text{tar. indip.}}, 
    \underbrace{\bm{u}, \tau, P'}_{\text{campi } f(\bm{x},t)},
    \underbrace{\rho_0, \nu, D, \alpha, g}_{\substack{ \text{\footnotesize{propr. del fluido}} \\ \text{\footnotesize{e del problema}} } }, 
    \underbrace{h, \Delta T}_{\substack{ \text{\footnotesize{dominio e}} \\ \text{\footnotesize{ condizioni al contorno}} } } \ ,$$
e 4 grandezze fisiche fondamentali: massa $M$, lunghezza $L$, tempo $T$
e temperatura $\Theta$. Secondo il teorema di Buckingham, il problema
può quindi essere caratterizzato da 8 numeri adimensionali. Utilizzando
la stessa scala di lunghezze per adimensionalizzare $\bm{x}$ e $h$ e la
stessa scala di temperature per adimensionalizzare $\tau$ e $\Delta T$,
sono sufficienti 6 numeri adimensionali. É necessario scegliere 4
grandezze fisiche di riferimento indipendenti e, possibilmente,
rappresentative del problema con le quali adimensionalizzare le altre.
Il problema della convezione non forzata descritto dalle equazioni di
Boussinesq è caratterizzato dalla differenza di temperatura $\Delta T$ e
dalla distanza $h$ delle superfici, dal fluido considerato e
dall'intensità delle forze di volume. I campi di velocità $\bm{u}$, di
"temperatura" $\tau$ e di "pressione" $P'$ sono un risultato, una
conseguenza, delle condizioni al contorno e del fluido impiegato: non
esistono scale di velocità e pressione indipendenti, mentre il campo di
temperatura può essere scalato sulla differenza $\Delta T$. Non esiste
nemmeno una scala indipendente dei tempi, poiché l'evoluzione del
sistema è determinata dalle condizioni al contorno e dal fluido
utilizzato. Come grandezze dimensionali di riferimento indipendenti e
caratteristiche del problema vengono scelte la densità del fluido, il
coefficiente di diffusione termica, la distanza tra le superfici e la
loro differenza di temperatura:
$$\tilde{\rho}=\rho_0, \ \tilde{D} = D, \ \tilde{L} = h, \ \tilde{\Theta} = \Delta T \ .$$

              $\bm{x}$   $t$   $\bm{u}$   $\tau$   $P'$   $\rho_0$   $\nu$   $D$   $\alpha$   $g$   $h$   $\Delta T$
  ---------- ---------- ----- ---------- -------- ------ ---------- ------- ----- ---------- ----- ----- ------------
      M                                             1        1                                           
      L          1                1                 -1       -3        2      2                1     1   
      T                   1       -1                -2                -1     -1               -2         
   $\Theta$                                 1                                         -1                      1

  : Teorema di Buckingham. Grandezze dimensionali e unità
  fisiche.[]{label="tab:Bouss-pi-thm"}

Ora è possibile scrivere ogni grandezza dimensionale come prodotto di
una grandezza omogenea di riferimento (dimensionale) e del suo valore
adimensionale. Si può quindi scrivere, $$\label{eqn:var-adim}
\begin{aligned}
    \bm{x} = \tilde{L} \bm{x}^*  \quad & , \quad t = \tilde{T} t^* \\
    \bm{u} = \tilde{U} \bm{u}^* \quad , \quad \tau & = \tilde{\Theta} \tau^* \quad , \quad P' = \tilde{P} P^{*'} \\
    \rho_0 = \tilde{\rho} \rho_0^* \quad  , \quad \nu = \tilde{\nu} \nu^* \quad , \quad D & = \tilde{D} D^* \quad , \quad \alpha = \tilde{\alpha} \alpha^* \quad , \quad g = \tilde{g} g^* \\
    h = \tilde{L} h^* \quad & , \quad \Delta T = \tilde{\Theta} \Delta T^* \ ,
\end{aligned}$$ avendo utilizzato la stessa scala di lunghezza
$\tilde{L}$ come riferimento per la coordinata spaziale indipendente
$\bm{x}$ e la distanza $h$ tra le due superifici, e la stessa scala di
temperatura $\tilde{\Theta}$ come riferimento per il campo di
temperatura $\tau$ e la differenza di temperatura tra le due superfici
$\Delta T$, come anticipato in precedenza. Le 12 grandezze dimensionali
sono state adimensionalizzate usando 10 scale di riferimento: da queste
è possibile ricavare 6 numeri adimensionali con cui descrivere il
problema. Inserendo le espressioni
([\[eqn:var-adim\]](#eqn:var-adim){reference-type="ref"
reference="eqn:var-adim"}) nel problema di Boussinesq
([\[eqn:Bouss-tau\]](#eqn:Bouss-tau){reference-type="ref"
reference="eqn:Bouss-tau"}), si ricava $$\label{eqn:Bouss-tau-adim-1}
    \begin{cases}
      \dfrac{\tilde{U}}{\tilde{T}}\dfrac{\partial \bm{u}^*}{\partial t^*} + \dfrac{\tilde{U}^2}{\tilde{L}}
      \left( \bm{u}^* \cdot \bm{\nabla}^* \right) \bm{u}^* -
      \dfrac{\tilde{\nu} \tilde{U}}{\tilde{L}^2} \nu^* \nabla^{*2} \bm{u}^* + \dfrac{\tilde{P}}{\tilde{\rho} \tilde{L}}\dfrac{1}{\rho_0^*}\bm{\nabla} P^{*'} = \tilde{\alpha} \tilde{g} \tilde{\theta} \alpha^*  g^* \tau^* \bm{\hat{z}} \\
      \dfrac{\tilde{U}}{\tilde{L}}\bm{\nabla}^* \cdot \bm{u}^* = 0 \\
      \dfrac{\tilde{\Theta}}{\tilde{T}}\dfrac{\partial \tau^*}{\partial t^*} + \dfrac{\tilde{U}\tilde{\Theta}}{\tilde{L}}\bm{u}^* \cdot 
      \bm{\nabla}^* \tau^* - \dfrac{\tilde{U}\tilde{\Theta}}{\tilde{L}}\dfrac{\Delta T^*}{h^*} w^* = \dfrac{\tilde{D}\tilde{\Theta}}{\tilde{L}^2} D^* \nabla^{*2} \tau^* \ ,
    \end{cases}$$ con le conzioni al contorno "free"
$$\text{free: } \left\{
    \begin{aligned}
      \tilde{\Theta}\tau^*(\tilde{L}x^*,\tilde{L}z^*=0) = 0 \quad & , \quad  
      \tilde{\Theta}\tau^*(\tilde{L}x^*,\tilde{L}z^*=\tilde{L}h^*) = 0 \\
      \dfrac{\tilde{U}}{\tilde{L}}\dfrac{\partial u^*}{\partial z^*}(\tilde{L}x^*,\tilde{L}z^*=0) = 0 \quad  & , \quad 
      \dfrac{\tilde{U}}{\tilde{L}}\dfrac{\partial u}{\partial z^*}(\tilde{L}x^*,\tilde{L}z^*=\tilde{L}h^*) = 0 \\
      \tilde{U} w^*(\tilde{L}x^*,\tilde{L}z^*=0) = 0 \quad  & , \quad 
      \tilde{U} w^*(\tilde{L}x^*,\tilde{L}z^*=\tilde{L}h^*) = 0
    \end{aligned} \right.$$ Con un abuso di notazione, d'ora in poi si
indicano le grandezze adimensionali senza asterisco e i campi
adimensionali vengono definiti come funzione delle variabili
indipendenti adimensionali,
$$\bm{u}(\bm{x},t) = \tilde{U} \bm{u}^*(\tilde{L} \bm{x}^*, \tilde{T} t^*) \quad \rightarrow \quad \tilde{U} \bm{u}(\bm{x},  t) \ .$$
Le grandezze di riferimento delle grandezze costanti vengono scelte
coincidenti con la grandezza stessa, cosicché le grandezze adimensionali
relative sono uguali a 1, $$\label{eqn:var-adim-2}
\begin{aligned}
    \rho_0 = \tilde{\rho} \quad  , \quad \nu = \tilde{\nu} \quad , \quad D & = \tilde{D}  \quad , \quad \alpha = \tilde{\alpha}  \quad , \quad g = \tilde{g}  \\
    h = \tilde{L}  \quad & , \quad \Delta T = \tilde{\Theta}  \ .
\end{aligned}$$ Dividendo l'equazione della quantità di moto per
$\tilde{\nu}\tilde{U}/\tilde{L}^2$, il vincolo di incomprimibilità per
$\tilde{U}/\tilde{L}$ e l'equazione dell'energia per
$\tilde{D}\tilde{\Theta}/\tilde{L}^2$, il problema di Boussinesq diventa
$$\label{eqn:Bouss-tau-adim-2}
    \begin{cases}
      \dfrac{\tilde{L}^2}{\tilde{\nu}\tilde{T}}\dfrac{\partial \bm{u}^*}{\partial t^*} + \dfrac{\tilde{U}\tilde{L}}{\tilde{\nu}}
      \left( \bm{u}^* \cdot \bm{\nabla}^* \right) \bm{u}^* -
      \nabla^{*2} \bm{u}^* + \dfrac{\tilde{P}\tilde{L}}{\tilde{\rho} \tilde{\nu} \tilde{U}}\bm{\nabla} P^{*'} = \dfrac{\tilde{\alpha} \tilde{g} \tilde{\Theta} \tilde{L}^2}{\tilde{\nu} \tilde{U}} \tau^* \bm{\hat{z}} \\
      \bm{\nabla}^* \cdot \bm{u}^* = 0 \\
      \dfrac{\tilde{L}^2}{\tilde{D}\tilde{T}}\dfrac{\partial \tau^*}{\partial t^*} + \dfrac{\tilde{U}\tilde{L}}{\tilde{D}}\bm{u}^* \cdot 
      \bm{\nabla}^* \tau^* - \dfrac{\tilde{U}\tilde{L}}{\tilde{D}} w^* = \nabla^{*2} \tau^* \ ,
    \end{cases}$$ con le conzioni al contorno "free"
$$\label{eqn:Bouss-adim-2-bc}
    \text{free: }
    \left\{
    \begin{aligned}
      \tau^*(x^*,z^*=0) = 0 \qquad  & , \qquad 
      \tau^*(x^*,z^*=1) = 0 \\
      \dfrac{\partial u^*}{\partial z^*}(x^*,z^*=0) = 0 \qquad & , \qquad 
      \dfrac{\partial u^*}{\partial z^*}(x^*,z^*=1) = 0 \\
      w^*(x^*,z^*=0) = 0 \qquad & , \qquad w^*(x^*,z^*=1) = 0 \ .
    \end{aligned} \right.$$ Nel problema
([\[eqn:Bouss-tau-adim-2\]](#eqn:Bouss-tau-adim-2){reference-type="ref"
reference="eqn:Bouss-tau-adim-2"}-[\[eqn:Bouss-adim-2-bc\]](#eqn:Bouss-adim-2-bc){reference-type="ref"
reference="eqn:Bouss-adim-2-bc"}) compaiono 6 numeri adimensionali.
Siamo arrivati al risultato previsto dal teorema di Buckingham. Prima di
andare avanti, conviene comunque fare un'osservazione. Solo 5 dei 6
numeri adimensionali trovati sono tra di loro indipendenti: in
particolare solo 3 dei 4 numeri adimensionali
$$\pi_1 = \frac{\tilde{L}^2}{\tilde{D}\tilde{T}} \ , \quad
    \pi_2 = \frac{\tilde{U}\tilde{L}}{\tilde{D}} \ , \quad
    \pi_3 = \frac{\tilde{L}^2}{\tilde{\nu}\tilde{T}} \ , \quad 
    \hat{\pi}_4 = \frac{\tilde{U}\tilde{L}}{\tilde{\nu}} = \pi_2 \dfrac{\pi_3}{\pi_1}$$
sono linearmente indipendenti. Sembra di aver commesso un errore poiché
abbiamo trovato una contraddizione del teorema di Buckingham.
L'apparente errore si nasconde nel termine adimensionale
$\frac{\tilde{\alpha} \tilde{g} \tilde{\theta} \tilde{L}^2}{\tilde{\nu} \tilde{U}}$.
Questo termine infatti è il prodotto dei numeri adimensionali
$\tilde{\alpha} \tilde{\theta}$ e
$\frac{\tilde{g} \tilde{L}^2}{\tilde{\nu} \tilde{U}}$. I sei numeri
adimensionali indipendenti che caratterizzano il problema sono quindi
$$\begin{aligned}
    \pi_1 = \frac{\tilde{L}^2}{\tilde{D}\tilde{T}} \quad ,\quad
    \pi_2 & = \frac{\tilde{U}\tilde{L}}{\tilde{D}} \quad ,\quad
    \pi_3 = \frac{\tilde{L}^2}{\tilde{\nu}\tilde{T}} \\
    \pi_4 = \frac{\tilde{P}\tilde{L}}{\tilde{\rho}\tilde{\nu}\tilde{U}} \quad ,\quad
    \pi_5 & = {\tilde{\alpha}\tilde{\Theta}} \quad ,\quad
    \pi_6 = \frac{\tilde{g} \tilde{L}^2}{\tilde{\nu} \tilde{U}} \ .
\end{aligned}$$ Poiché il coefficiente di dilatazione termica $\alpha$ e
la forza per unità di volume $g$ comapiono sempre attraverso il loro
prodotto, questo si può considerare come un'unica variabile, $\alpha g$.
In questo caso, i 5 numeri adimensionali che descrivono il problema
composto dalle 9 (10-1) scale di riferimento sono
$$\pi'_1 = \pi_1, \  \pi'_2 = \pi_2, \ \pi'_3 = \pi_3, \ \pi'_4 = \pi_4, \ \pi'_5 = \pi_5 \pi_6 \ .$$
Non essendoci scale di velocità, tempo e pressione indipendenti, è
possibile definire queste scale a partire dalle 4 grandezze fisiche di
riferimento $\tilde{L}$, $\Delta \tilde{T}$, $\tilde{\rho}$,
$\tilde{D}$, imponendo il valore unitario di alcuni parametri
adimensionali, $$\begin{aligned}
      \pi'_1 = 1 & \quad \rightarrow \quad \tilde{T} = \dfrac{\tilde{L}^2}{\tilde{D}} \\
      \pi'_2 = 1 & \quad \rightarrow \quad \tilde{U} = \dfrac{\tilde{D}}{\tilde{L}} \\
      \pi'_4 = 1 & \quad \rightarrow \quad \tilde{P} = \dfrac{\tilde{\rho}\tilde{\nu}\tilde{U}}{\tilde{L}} \ .
    \end{aligned}$$ Gli unici due parametri adimensionali caratteristici
del problema rimangono $$\begin{aligned}
 \Pi_1 = \pi'_3 = \dfrac{\tilde{L^2}}{\tilde{\nu} \tilde{L}^2/\tilde{D}} \qquad \rightarrow \qquad \Pi_1  & = \dfrac{\tilde{D}}{\tilde{\nu}} = \dfrac{1}{Pr} \\
 \Pi_5 = \pi'_5 = \dfrac{\tilde{\alpha}\tilde{\Theta} \tilde{g} \tilde{L}^2}{\tilde{\nu} \tilde{D}/\tilde{L}} \qquad \rightarrow \qquad \Pi_5 & = \dfrac{\tilde{\alpha}\tilde{g}\tilde{\Theta}  \tilde{L}^3}{\tilde{\nu} \tilde{D}} = Ra = \\
 & = \dfrac{\tilde{\alpha}\tilde{g}\tilde{\Theta}  \tilde{L}^3}{\tilde{\nu}^2}\dfrac{\tilde{\nu}}{\tilde{D}} = Gr \, Pr \ ,
\end{aligned}$$ nei quali si possono riconoscere i numeri di Prandtl,
$Pr$, di Rayleigh, $Ra$, e di Grashof, $Gr$. La forma adimensionale del
problema di Boussinesq tra due superfici piane è quindi
$$\label{eqn:Bouss-tau-adim-3}
    \begin{cases}
      \dfrac{1}{Pr} \left[ \dfrac{\partial \bm{u}}{\partial t} +
      \left( \bm{u} \cdot \bm{\nabla} \right) \bm{u} \right] -
      \nabla^2 \bm{u} + \bm{\nabla} P' = Ra \, \tau \bm{\hat{z}} \\
      \bm{\nabla} \cdot \bm{u} = 0 \\
      \dfrac{\partial \tau}{\partial t} + \bm{u} \cdot 
      \bm{\nabla} \tau -  w = \nabla^{2} \tau \ ,
    \end{cases}$$ con le conzioni al contorno "free"
$$\label{eqn:Bouss-adim-3-bc}
    \text{free: }
    \left\{
    \begin{aligned}
      \tau(x,z=0) = 0 \qquad  & , \qquad 
      \tau(x,z=1) = 0 \\
      \dfrac{\partial u}{\partial z}(x,z=0) = 0 \qquad & , \qquad 
      \dfrac{\partial u}{\partial z}(x,z=1) = 0 \\
      w(x,z=0) = 0 \qquad & , \qquad w(x,z=1) = 0 \ .
    \end{aligned} \right.$$

Equazione della vorticità e funzione di corrente nell'approssimazione di Boussinesq
===================================================================================

Dall'equazione della quantità di moto in
([\[eqn:Bouss-tau-adim-3\]](#eqn:Bouss-tau-adim-3){reference-type="ref"
reference="eqn:Bouss-tau-adim-3"}) è possibile ricavare l'equazione
della vorticità, applicandole l'operatore di rotore. Poichè il problema
è piano e bidimensionale, il campo di vorticità ha componente non nulla
solo fuori dal piano $xz$. Utilizzando un sistema di coordinate
cartesiano, il campo di vorticità
$\bm{\omega}(x,z,t) = \xi(x,z,t) \bm{\hat{y}}$ soddisfa l'equazione
$$\dfrac{1}{Pr} \left[ \dfrac{\partial \xi}{\partial t} +
      \bm{u} \cdot \bm{\nabla} \xi \right] -
      \nabla^2 \xi = - Ra \, \dfrac{\partial \tau}{\partial x} \ .$$ Si
può poi introdurre la funzione di corrente $\psi$,
$$u =   \dfrac{\partial \psi}{ \partial z} \quad , \quad 
    w = - \dfrac{\partial \psi}{ \partial x} \ ,$$ in modo tale da
soddisfare identicamente il vincolo di incomprimibilità. La componente
$y$ del campo di vorticità diventa
$$\xi = \dfrac{\partial u}{\partial z} - \dfrac{\partial w}{\partial x} =
    \dfrac{\partial^2 u}{\partial z^2} +
    \dfrac{\partial^2 w}{\partial x^2} = 
    \nabla^2 \psi \ ,$$ e il termine advettivo di una funzione $f$
qualsiasi può essere scritta come un determinante,
$$\bm{u} \cdot \bm{\nabla} f = u \dfrac{\partial f}{\partial x} + w \dfrac{\partial f}{\partial z} =
    \dfrac{\partial \psi}{ \partial z} \dfrac{\partial f}{\partial x} - \dfrac{\partial \psi}{ \partial x} \dfrac{\partial f}{\partial z} = \left| \begin{matrix} f_x & f_z \\ \psi_x & \psi_z \end{matrix} \right| =: \dfrac{\partial(f,\psi)}{\partial(x,z)} \ .$$
Il sistema di equazioni del problema di Boussinesq diventa quindi
$$\label{eqn:Bouss-vort-psi-tau}
    \begin{cases}
      \dfrac{\partial \xi}{\partial t} +
      \dfrac{\partial(\xi,\psi)}{\partial(x,z)} 
      = Pr \, \nabla^2 \xi 
      - Pr \, Ra \, \dfrac{\partial \tau}{\partial x} \\
      \dfrac{\partial \tau}{\partial t} +
      \dfrac{\partial(\tau,\psi)}{\partial(x,z)} =
      \nabla^{2} \tau + w \ .
    \end{cases}$$

Approssimazione di Fourier--Galerkin del problema di Boussinesq
===============================================================

Utilizzando la geometria del dominio, è possibile espandere le funzioni
che compaiono nelle equazioni
([\[eqn:Bouss-vort-psi-tau\]](#eqn:Bouss-vort-psi-tau){reference-type="ref"
reference="eqn:Bouss-vort-psi-tau"}) come somma di prodotti di funzioni
armoniche in $x$ e $z$, la cui ampiezza dipende dal tempo
$$\label{eqn:harm-1}
\begin{aligned}
    \psi(x,z,t) & = \sum_m \sum_k a_{m,k}(t) \sin{(m\pi z + \phi^a_m)}\sin{(k\pi x + \phi^a_k)} \\
    \tau(x,z,t) & = \sum_m \sum_k b_{m,k}(t) \sin{(m\pi z + \phi^b_m)}\sin{(k\pi x + \phi^b_k)} \ .
\end{aligned}$$ Le condizioni al contorno
([\[eqn:Bouss-adim-3-bc\]](#eqn:Bouss-adim-3-bc){reference-type="ref"
reference="eqn:Bouss-adim-3-bc"}) del problema con due superfici
infinite "free" impongono che la componente
$w=-\partial{\psi}/\partial{x}$ e la derivata
$\partial u/\partial z = \partial^2 \psi/\partial z^2$ siano nulle per
$z = 0, \ 1$ per ogni istante temporale e per ogni valore di $x$. Le
condizioni al contorno su $w$ impongono le seguenti condizioni
sull'espanzione armonica delle funzioni, $$\begin{aligned}
      0 = \dfrac{\partial \psi}{\partial x}\Big|_{z=0} & = \sum_m \sum_k k \pi a_{m,k}(t) \sin{ \phi^a_m }\cos{(k\pi x + \phi^a_k)} \\
      & \hspace{4.0cm} \rightarrow \qquad \phi^a_m = 0 \ , \\
      0 = \dfrac{\partial \psi}{\partial x}\Big|_{z=1} & = \sum_m \sum_k k \pi a_{m,k}(t) \sin{ m \pi }\cos{(k\pi x + \phi^a_k)} \\
      & \hspace{4.0cm} \rightarrow \qquad m \in \mathbb{Z} \ .
    \end{aligned}$$ Le stesse condizioni derivano dalle condizioni al
contorno su $\partial u/\partial z$. Le condizioni al contorno sulla
temperatura in impongono le seguenti condizioni sull'espansione armonica
della funzione $\tau$ $$\begin{aligned}
      0 = \tau \Big|_{z=0} & = \sum_m \sum_k b_{m,k}(t) \sin{ \phi^b_m }\sin{(k\pi x + \phi^b_k)} \\
      & \hspace{4.0cm} \rightarrow \qquad \phi^b_m = 0 \ ,\\
      0 = \tau \Big|_{z=1} & = \sum_m \sum_k b_{m,k}(t) \sin{ m \pi }\sin{(k\pi x + \phi^b_k)} \\
      & \hspace{4.0cm} \rightarrow \qquad m \in \mathbb{Z} \ .
    \end{aligned}$$ A causa dell'omogeneità della direzione $x$, nella
quale il dominio è infinito, non ci sono condizioni sul numero d'onda
$k$, che può assumere tutti i valori $\in \mathbb{R}$, e sulla fase
delle armoniche in $x$. Le espansioni
([\[eqn:harm-1\]](#eqn:harm-1){reference-type="ref"
reference="eqn:harm-1"}) possono quindi essere scritte come
$$\label{eqn:harm-2}
\begin{aligned}
    \psi(x,z,t) & = \sum_{m \in \mathbb{Z}} \sum_k a^1_{m,k}(t) \sin{(m\pi z)} \sin{(k\pi x )} +  a^2_{m,k}(t) \sin{(m\pi z)} \cos{(k \pi x)} \\
    \tau(x,z,t) & = \sum_{m \in \mathbb{Z}} \sum_k b^1_{m,k}(t) \sin{(m\pi z)} \sin{(k\pi x )} + b^2_{m,k}(t) \sin{(m\pi z)} \cos{(k \pi x)}  \ .
\end{aligned}$$

Dal problema di Boussinesq al modello di Lorenz
===============================================

Le espansioni ([\[eqn:harm-2\]](#eqn:harm-2){reference-type="ref"
reference="eqn:harm-2"}) possono essere *brutalmente* troncate per
ottenere un modello dinamico di dimensione $N_d = 3$ partendo dal
modello continuo, che ha dimensione infinita. Le espansioni
([\[eqn:harm-2\]](#eqn:harm-2){reference-type="ref"
reference="eqn:harm-2"}) vengono troncate mantenendo solo 3 termini
$$\label{eqn:harm-3}
\begin{aligned}
    \psi(x,z,t) & = a(t) \sin{(\pi z)} \sin{(k\pi x )}  \\
    \tau(x,z,t) & = b(t) \sin{(\pi z)} \cos{(k\pi x )} + c(t) \sin{(2 \pi z)}   \ ,
\end{aligned}$$ avendo definito $a(t) = a^1_{1,k}(t)$,
$b(t) = b^2_{1,k}(t)$, $c(t) = b^1_{2,0}(t)$. Usando le espansioni
([\[eqn:harm-3\]](#eqn:harm-3){reference-type="ref"
reference="eqn:harm-3"}), la componente $y$ del campo di vorticità
$\xi = \nabla^2 \psi$ diventa
$$\xi = - \pi^2 (1 + k^2) \psi = - \pi^2 (1 + k^2) a(t) \sin{(\pi z)} \sin{(k\pi x )}$$
I due determinanti che compaiono nelle equazioni
([\[eqn:Bouss-vort-psi-tau\]](#eqn:Bouss-vort-psi-tau){reference-type="ref"
reference="eqn:Bouss-vort-psi-tau"}) valgono $$\begin{aligned}
     \dfrac{\partial (\xi, \psi)}{\partial (x,z)} = &
     \left[ -\pi^3 k(1+k^2) a(t) \sin{(\pi z)}  \cos{(k \pi x)} \right]
     \left[ a(t) \pi \cos{(\pi z)} \sin{(k \pi x)} \right] + \\
      - & \left[  -\pi^3 (1+k^2) a(t) \cos{(\pi z)}  \sin{(k \pi x)} \right]
      \left[ a(t) \pi k \sin{(\pi z)} \cos{(k \pi x)} \right] = 0 \ ,
\end{aligned}$$ e $$\begin{aligned}
    \dfrac{\partial (\tau, \psi)}{\partial (x,z)} = &
    \left[ - \pi k b(t) \sin{(\pi z )} \sin{(k \pi x)} \right]
    \left[ a(t) \pi \cos{(\pi z)} \sin{(k \pi x)} \right] + \\
    - & \left[ \pi b(t) \cos{(\pi z )} \cos{(k \pi x)} + 2\pi c(t) \cos{(2\pi z)} \right]
    \left[ a(t) \pi k \sin{(\pi z)} \cos{(k \pi x)} \right] = \\
    = & - k \pi^2 a(t) b(t) \dfrac{\sin{( 2 \pi z)}}{2} -
    2 k \pi^2 a(t)c(t) \sin(\pi z) \cos(2\pi z) \cos(k \pi x) \ .
\end{aligned}$$ I laplaciani che compaiono nelle equazioni
([\[eqn:Bouss-vort-psi-tau\]](#eqn:Bouss-vort-psi-tau){reference-type="ref"
reference="eqn:Bouss-vort-psi-tau"}) valgono
$$\nabla^2 \xi = -\pi^2 (1+k^2) \xi = \pi^4 (1+k^2)^2 a(t) \sin{(\pi z)} \sin{(k \pi x)} \ ,$$
e
$$\nabla^2 \tau = -\pi^2 (1+k^2) b(t) \sin{(\pi z)}\cos{(k \pi x)} - 4 \pi^2 c(t) \sin{(2\pi x)} \ .$$
Il numero di Prantl viene indicato come $Pr = \sigma$, il numero di
Rayleigh come $Ra = R$. Inserendo le espansioni
([\[eqn:harm-3\]](#eqn:harm-3){reference-type="ref"
reference="eqn:harm-3"}) all'interno delle equazioni
([\[eqn:Bouss-vort-psi-tau\]](#eqn:Bouss-vort-psi-tau){reference-type="ref"
reference="eqn:Bouss-vort-psi-tau"}), il problema troncato di Boussinesq
diventa, $$\begin{cases}
- \sigma \pi^2 (1+k^2) \dot{a}(t) \sin{(\pi z)} \sin{(k\pi x )} = \sigma \pi^4 (1+k^2)^2 a(t) \sin{(\pi z)} \sin{(k \pi x)} + \\
      \hspace{6.0cm} + \sigma R \, \pi k \, b(t) \sin{(\pi z)}\sin{(k \pi x)} \\
     \dot{b}(t)\sin{(\pi z)} \cos{(k\pi x )} + \dot{c}(t) \sin{(2\pi x)} + \\
     \hspace{2.0cm} - k \pi^2 a(t) b(t) \dfrac{\sin{(2 \pi z)}}{2} -
    2 k \pi^2 a(t)c(t) \sin(\pi z) \cos(2\pi z) \cos(k \pi x) = \\ 
    \hspace{1.5cm} = -\pi^2 (1+k^2) b(t) \sin{(\pi z)}\cos{(k \pi x)} - 4 \pi^2 c(t) \sin{(2\pi x)} + \\
    \hspace{2.0cm} - \pi k a(t) \sin{(\pi z)} \cos{(k \pi x)} \ .
    \end{cases}$$ Raccogliendo il termine
$\sin{(\pi z)} \sin{(k \pi x)}$ nell'equazione della vorticità si
ottiene l'equazione
$$- \pi^2 (1+k^2) \dot{a} = \sigma \pi^4 (1+k^2)^2 a(t) +  \sigma R \, \pi k \, b(t) \ .$$
L'equazione della temperatura viene "proiettata" sulle funzioni di base
$\sin{(\pi z)} \cos{(k \pi x)}$ e $\sin{(2 \pi x)}$ e sfruttando
l'ortogonalità delle funzioni armoniche. La proiezione consiste nella
moltiplicazione dell'equazione per le funzioni di base
$\sin{(\pi z)} \cos{(k \pi x)}$ e nell'integrazione in
$(x,z) \in \left[0,\frac{2}{k}\right]\times\left[0,1\right]$. Usando il
valore degli integrali, $$\begin{aligned}
 \int_{x=0}^{2/k} \sin{(k \pi x)}^2 dx & = \dfrac{1}{2} \int_{x=0}^{2/k} \left[ 1 - \cos{(2 k \pi x)} \right] dx = \dfrac{1}{k} \\
 \int_{x=0}^{2/k} \sin{(k \pi x)}\cos{(k \pi x)} dx & = \dfrac{1}{k \pi} \int_{x=0}^{2/k} \sin{(k \pi x)} d \big( \sin{(k \pi x)} \big) = 0 \\
 \int_{x=0}^{2/k} \cos{(k \pi x)}^2 dx & = \dfrac{1}{k} \ ,
\end{aligned}$$ e degli integrali $$\begin{aligned}
 \int_{z=0}^{1} \sin{(\pi z)}^2 dz & = \dfrac{1}{2} \int_{x=0}^{1} \left[ 1 - \cos{(2\pi z)} \right] dz = \dfrac{1}{2} \\
 \int_{z=0}^{1} \sin{(\pi z)} \sin{(\pi z)} \cos{(2\pi z)} dz  & =
 \dfrac{1}{2} \int_{z=0}^{1} \left[ 1 - \cos{(2\pi z)} \right]  \cos{(2\pi z)} dz = \\
 & = - \dfrac{1}{2} \int_{z=0}^{1} \cos^2{(2\pi z)}  dz = 
  - \dfrac{1}{4} \ .
\end{aligned}$$ La proiezione dell'equazione della vorticità sulla
funzione $\sin{(\pi z)} \cos{(k \pi x)}$ è
$$\dfrac{1}{2}\dot{b}(t) - \dfrac{1}{4} 2 k \pi^2 a(t) c(t) =
    -\dfrac{1}{2} \pi^2 (1+k^2) b(t) - \dfrac{1}{2}\pi k a(t) \ ,$$
mentre la proiezione dell'equazione della vorticità sulla funzione
$\sin{(2 \pi z)}$ è
$$\dfrac{1}{k}\dot{c}(t) - \dfrac{1}{k} \dfrac{\pi^2 k}{2} a(t) b(t) =
    - \dfrac{1}{k} 4 \pi^2 c(t) \ .$$ Le equazioni diventano quindi
$$\begin{cases}
   - \pi^2 (1+k^2) \dot{a} = \sigma \pi^4 (1+k^2)^2 a(t) +  \sigma R \, \pi k \, b(t) \\
    \dot{b} = -\pi^2 (1+k^2) b(t) + \pi^2 k a(t)c(t)  - \pi k a(t)  \\
    \dot{c} = \dfrac{\pi^2 k}{2} a(t) b(t) - 4 \pi^2 c(t) \ .
    \end{cases}$$ Partendo da queste equazioni, si introduce qualche
cambio di variabile per riportarsi all'espressione classica del sistema
di Lorenz. Viene introdotto il tempo $t' = \pi^2 (k^2 + 1) t$, cosicché
$$\dot{f} = \dfrac{df}{dt} = \dfrac{dt'}{dt}\dfrac{df}{dt'} =
    \pi^2 (k^2 + 1) \dfrac{df}{dt'} \ .$$ Con un abuso di notazione,
d'ora in poi si indica $\dot{(\ )}$ la derivata rispetto a $t'$. La
stessa variabile $t'$ viene indicata con $t$. Le equazioni diventano
$$\begin{cases}
    \dot{a}(t) = \sigma a(t) +  \sigma R \dfrac{k}{\pi^3 (k^2+1)^2} b(t) \\
    \dot{b}(t) = - b(t) + \dfrac{ k}{k^2+1} a(t)c(t)  - \dfrac{ k}{\pi(k^2+1)} a(t)  \\
    \dot{c}(t) = \dfrac{k}{2(k^2+1)} a(t) b(t) - \dfrac{4}{k^2+1}  c(t) \ .
    \end{cases}$$ Viene definito infine il cambio di variabili
$$\begin{cases}
     X(t) = \dfrac{k}{\sqrt{2}(k^2+1)} a(t) \\
     Y(t) = \dfrac{k}{\sqrt{2}(k^2+1)}
     \left[-\dfrac{R k}{\pi^3 (k^2+1)^2}\right] b(t) \\
     Z(t) = \left[-\dfrac{R k^2}{\pi^3 (k^2+1)}\right] c(t)
    \end{cases}$$ che porta alla forma classica delle equazioni di
Lorenz $$\begin{cases}
      \dot{X} = - \sigma X + \sigma Y \\
      \dot{Y} = - Y + \rho X - X Z \\
      \dot{Z} = - \beta Z + X Y \ ,
    \end{cases}$$ avendo definito i parameteri
$$\rho = \dfrac{R k^2}{\pi^4 (k^2+1)^2} \qquad , \qquad
    \beta = \dfrac{4}{k^2+1} \ .$$
