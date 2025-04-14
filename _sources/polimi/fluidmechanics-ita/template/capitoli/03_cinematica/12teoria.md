(fluid-mechanics:kinematics)=
# Kinematics

La cinematica è la parte della meccanica che studia il moto di sistemi,
indipendentemente dalle cause che lo generano, a differenza della
dinamica. Prima di ricavare le equazioni che descrivono la dinamica di
un fluido, sembra quindi opportuno concentrarsi sulla sua cinematica.

La cinematica e la dinamica dei mezzi continui, come ad esempio i solidi
o i fluidi, possono essere descritte con un approccio lagrangiano o
euleriano. La **descrizione lagrangiana**, utilizzata spesso in
meccanica dei solidi, consiste nel seguire nello spazio il moto delle
singole particelle del mezzo continuo. La **descrizione euleriana**,
utilizzata spesso in meccanica dei fluidi, consiste nel descrivere
l'evoluzione del mezzo continuo utilizzando come variabili indipendenti
sia la variabile spaziale $\mathbf{r}$ sia la variabile temporale $t$.

(fluid-mechanics:kinematics:integral-lagrange-euler)=
## Descrizione integrale lagrangiana ed euleriana

In una descrizione *integrale* del fenomeno, l'approccio lagrangiano
segue l'evoluzione di un **volume materiale**, i cui punti si muovono in
maniera solidale con il mezzo continuo. In un approccio euleriano invece
viene introdotto un **volume di controllo**, fisso nello spazio, e i
flussi delle quantità meccaniche (massa, quantità di moto, energia, ...)
contribuiscono ai bilancio delle quantità meccaniche relative al volume
di controllo considerato. Queste due descrizioni sono casi particolari
di un approccio generale al problema, definito *ALE* (arbitrario
lagrangiano-euleriano), che descrive l'evoluzione di un volume in moto
arbitrario. Le tre diverse descrizioni del problema possono essere messe
in relazione tra di loro, tramite le formule di Leibniz, che forniscono
l'espressione della derivata temporale di integrali su domini dipendenti
dal tempo. Si riporta qui, senza dimostrazione, il **teorema del
trasporto di Reynolds**

$$\dfrac{d}{d t} \int_{V(t)} f = \int_{V(t)} \dfrac{\partial f}{\partial t} +
  \oint_{S(t)} f\mathbf{v} \cdot \mathbf{\hat{n}} \ ,$$

che fornisce l'espressione della derivata temporale dell'integrale della
funzione $f(\mathbf{x},t)$ (che può essere scalare, vettoriale o in generale
tensoriale) nel volume mobile $V(t) \ni \mathbf{x}$, la cui frontiera $S(t)$
si muove con velocità $\mathbf{v}(\mathbf{x}_s,t)$, $\mathbf{x}_s \in S(t)$. La
normale $\mathbf{\hat{n}}$ alla superficie $S(t)$ è uscente dal volume
$V(t)$. Si rimanda all'appendice "Richiami di analisi" per la
dimostrazione del teorema e per le formule della derivata temporale di
flussi e circuitazioni su domini dipendenti dal tempo. Siano ora

-   $V(t)$ un volume materiale, la cui frontiera si muove con la
    velocità del fluido $\mathbf{v}=\mathbf{u}$

-   $V_c$ un volume di controllo, la cui frontiera è fissa nello spazio,
    $\mathbf{v}=\mathbf{0}$

-   $v(t)$ un volume in moto arbitrario, la cui frontiera si muove con
    velocità generica $\mathbf{v}$.

Come si vedrà nel capitolo sui "Bilanci integrali", il bilancio
integrale di una quantità meccanica $f$ in un volume materiale $V(t)$
descrive la variazione nel tempo dell'integrale $\int_{V(t)} f$. Il
teorema di Reynolds applicato all'integrale svolto su un volume
materiale $V(t)$ e all'integrale svolto sul volume in moto generico
$v(t)$, coincidente con $V(t)$ all'istante di tempo $t$ considerato,

$$\begin{aligned}
  \dfrac{d}{d t} \int_{V(t)} f & = \int_{V(t)} \dfrac{\partial f}{\partial t} +
  \oint_{S(t)} f\mathbf{u} \cdot \mathbf{\hat{n}}  \\
  \dfrac{d}{d t} \int_{v(t)\equiv V(t)} f & = \int_{v(t)\equiv V(t)} \dfrac{\partial f}{\partial t} +
  \oint_{s(t)\equiv S(t)} f\mathbf{v} \cdot \mathbf{\hat{n}}  \ , \\
\end{aligned}$$

permette di ricavare il legame tra la descrizione
lagrangiana e una descrizione arbitraria del problema. Confrontando le
ultime due espressioni, si ottiene

$$\dfrac{d}{d t} \int_{V(t)} f = \dfrac{d}{d t} \int_{v(t)\equiv V(t)} f +
 \oint_{s(t)\equiv S(t)} f (\mathbf{u} - \mathbf{v}) \cdot \mathbf{\hat{n}} \ .$$

Dalla formula scritta per il volume arbitrario $v(t)$, si ricava il
legame tra a descrizione lagrangiana e la descrizione euleriana del
problema, considerando il volume arbitrario coincidente con un volume di
controllo $V_c$ fisso, per il quale $\mathbf{v}=\mathbf{0}$,

$$\dfrac{d}{d t} \int_{V(t)} f = \dfrac{d}{d t} \int_{V_c\equiv V(t)} f +
 \oint_{S_c\equiv S(t)} f \mathbf{u} \cdot \mathbf{\hat{n}} \ .$$

(fluid-mechanics:kinematics:differential-lagrange-euler)=
## Descrizione puntuale lagrangiana ed euleriana

In una descrizione *puntuale* del fenomeno, vengono introdotti due
sistemi di coordinate: uno è solidale con il mezzo continuo dipendente
dal tempo, mentre l'altro è fisso. Si può pensare al sistema di
riferimento solidale con il continuo come un' "etichetta" che viene
applicata a ogni **punto materiale** del mezzo continuo stesso. Un
sistema di riferimento fisso, invece, è indipendente dal moto del mezzo
continuo, come ad esempio un sistema di coordinate cartesiane, la cui
origine e i cui assi sono fissi nel tempo. Mentre il mezzo continuo
evolve nel tempo (trasla, ruota, si deforma ...), un punto materiale ha
coordinate costanti $\mathbf{x_0}$ rispetto al sistema di riferimento
"solidale al volume", cioè che si muove e si deforma insieme al volume:
questa coordinata, detta lagrangiana, può essere pensata come
l'"etichetta" assegnata al punto materiale del continuo. Le coordinate
euleriane $\mathbf{x}(\mathbf{x_0},t)$ del punto materiale con coordinate
lagrangiane $\mathbf{x_0}$, ne descrivono il moto nel sistema di riferimento
fisso e in generale sono una funzione del tempo

Il sistema di riferimento solidale al corpo dipende dal tempo, mentre le
coordinate lagrangiane $\mathbf{x_0}$ di un punto materiale sono costanti.
Il sistema di riferimento fisso è indipendente dal tempo, mentre le
coordinate euleriane $\mathbf{x}$ di un punto materiale del volume (quindi
con $\mathbf{x_0}$ costante) sono dipendenti dal tempo.

Assumendo che all'istante $t=0$ i due sistemi di coordinate coincidano,
e che quindi coincidano anche le coordinate euleriane e lagrangiane
$\mathbf{x}(\mathbf{x_0},0) = \mathbf{x_0}$, le coordinate lagrangiane $\mathbf{x_0}$
rappresentano la configurazione (iniziale) di riferimento della
configurazione attuale $\mathbf{x}(\mathbf{x_0},t)$. La trasformazione
$\mathbf{x}(\mathbf{x_0},t)$ descrive l'evoluzione nel tempo $t$ dei punti
$\mathbf{x}(0) = \mathbf{x_0}$ appartenenti al volume $V_0 = V(0)$, all'istante
iniziale. La velocità $\mathbf{u}(\mathbf{x},t)$ del mezzo continuo nel punto
$\mathbf{x}(\mathbf{x_0},t)$, per definizione di punto materiale, coincide con
la velocità $\mathbf{u_0}(\mathbf{x_0},t)$ del punto etichettato con $\mathbf{x_0}$:
questa è la derivata nel tempo della sua posizione $\mathbf{x}$, cioè con la
derivata nel tempo della mappa $\mathbf{x}(\mathbf{x_0},t)$ a coordinata
lagrangiana (che identifica la particella) costante,

$$\mathbf{u_0}(\mathbf{x_0},t) = \dfrac{\partial \mathbf{x}}{\partial t}\bigg|_{\mathbf{x_0}}(\mathbf{x_0},t) =: \dfrac{d \mathbf{x}}{d t}(\mathbf{x_0},t) =: \dfrac{D\mathbf{x}}{D t}(\mathbf{x_0},t) \ ,$$

dove è stato introdotto il simbolo $D/Dt$ di **derivata materiale** che
rappresenta l'evoluzione della quantità alla quale è applicata, seguendo
il moto del mezzo continuo: la derivata materiale rappresenta la
variazione nel tempo della quantità "sentita" dalle singole particelle
materiali. Nella descrizione euleriana del problema, i campi sono
funzioni delle variabili indipendenti spazio $\mathbf{x}$ e tempo $t$. Data
una funzione $f(\mathbf{x},t)$ (scalare, vettoriale, tensoriale), viene
indicata con

$$\dfrac{\partial f}{\partial t} = \dfrac{\partial f}{\partial t}\bigg|_{\mathbf{x}}(\mathbf{x},t) \ ,$$

la derivata parziale rispetto al tempo, che rappresenta la variazione
della quantità $f(\mathbf{x},t)$ nel punto fisso $\mathbf{x}$ dello spazio, che
coordinata euleriana costante.

É possibile trovare il legame tra le due derivate utilizzando la *regola
di derivazione di funzioni composte* e la funzione $\mathbf{x}(\mathbf{x_0},t)$
che descrive il moto dei punti materiali del sistema. Data una funzione
$f(\mathbf{x},t)$ (rappresentazione euleriana), viene definita
$f_0(\mathbf{x_0},t)$ come la funzione composta $f_0 = f \circ \mathbf{x}$
(descrizione lagrangiana). Ipotizzando poi che si possano esprimere le
coordinate lagrangiane come funzione di quelle euleriane,
$\mathbf{x_0}(\mathbf{x},t)$, è possibile scrivere
$$f(\mathbf{x},t) = f(\mathbf{x}(\mathbf{x_0},t),t) = f_0(\mathbf{x}_0,t) = f_0(\mathbf{x_0}(\mathbf{x},t),t) \ .$$
Utilizzando la regola di derivazione per le funzioni composte, si
ottiene il legame cercato, 

$$\label{eqn:cin:lagr-eul}
\begin{aligned}
 \dfrac{D f}{D t}(\mathbf{x},t) & = \dfrac{\partial f}{\partial t}\bigg|_{\mathbf{x_0}} = \dfrac{\partial}{\partial t}\bigg|_{\mathbf{x_0}} f(\mathbf{x}(\mathbf{x_0},t),t) =  \\ 
  & = \dfrac{\partial f}{\partial \mathbf{x}}\bigg|_{t} \cdot \dfrac{\partial \mathbf{x}}{\partial t}\bigg|_{\mathbf{x_0}} 
  + \dfrac{\partial f}{\partial t}\bigg|_{\mathbf{x}} = 
  \dfrac{\partial f}{\partial t} +  
  \dfrac{\partial x_i}{\partial t}\bigg|_{\mathbf{x_0}} \dfrac{\partial f}{\partial x_i}\bigg|_{t}  = 
  \dfrac{\partial f}{\partial t} + \mathbf{u} \cdot \mathbf{\nabla} f \ ,
\end{aligned}$$

dove si è indicato con
$\mathbf{u}(\mathbf{x},t) = \dfrac{\partial \mathbf{x}}{\partial t}\bigg|_{\mathbf{x_0}} (\mathbf{x_0}(\mathbf{x},t),t)$
il campo di velocità riferito a una descrizione euleriana del problema e
si è riconosciuto l'operatore $\mathbf{\nabla}$ nell'ultimo passaggio.
Infine è possibile "rimuovere" la funzione $f$ per ottenere la relazione
tra la forma delle due derivate, valida per funzioni scalari,
vettoriali, tensoriali,

$$\label{eqn:cin:lagr-eul-2}
 \dfrac{D \rule{1.5ex}{.4pt}}{D t} := \dfrac{d \rule{1.5ex}{.4pt}}{d t} := \dfrac{\partial \rule{1.5ex}{.4pt}}{\partial t}\bigg|_{\mathbf{x_0}} = \dfrac{\partial \rule{1.5ex}{.4pt}}{\partial t} + \mathbf{u} \cdot \mathbf{\nabla} \rule{1.5ex}{.4pt} \ .$$

Come esempio, applichiamo la regola
([\[eqn:cin:lagr-eul\]](#eqn:cin:lagr-eul){reference-type="ref"
reference="eqn:cin:lagr-eul"}) per ricavare la forma euleriana e
lagrangiana del campo di velocità e di accelerazione delle particelle
del continuo. Il campo di velocità $\mathbf{u}(\mathbf{x},t)$ si ottiene dalla
derivata materiale della trasformazione $\mathbf{x}(x_0,t)$,

$$\mathbf{u}(\mathbf{x},t) = \dfrac{D \mathbf{x}}{D t} = \underbrace{\dfrac{\partial \mathbf{x}}{\partial t}\bigg|_{\mathbf{x}} }_{=0} + \mathbf{u_0}(\mathbf{x_0},t) \cdot \underbrace{ \mathbf{\nabla} \mathbf{x} }_{=\mathbb{I}} =
 \mathbf{u_0}(\mathbf{x_0},t) \ .$$ 

 In questo caso, non è stato ottenuto nulla
di nuovo. Il campo di accelerazione nella descrizione euleriana del
fenomeno viene ottenuto calcolando l'accelerazione delle particelle
materiali con la derivata materiale alla velocità. Per componenti,
l'accelerazione della particella materiale identificata con $\mathbf{x_0}$ è

$$a_{i}(\mathbf{x},t) = \dfrac{D u_{i}}{D t} = 
 \dfrac{\partial u_i}{\partial t} + u_{k} \dfrac{\partial u_i}{\partial x_k} \ .$$

Introducendo l'operatore advettivo $\mathbf{v}\cdot \mathbf{\nabla}$, è
possibile scrivere il campo di accelerazione (che comparirà nel bilancio
della quantità di moto) in forma vettoriale

$$\mathbf{a}(\mathbf{x},t) = \dfrac{D \mathbf{u}}{D t}(\mathbf{x},t) = \dfrac{\partial \mathbf{u}}{\partial t}(\mathbf{x},t) + (\mathbf{u}(\mathbf{x},t) \cdot \mathbf{\nabla}) \mathbf{u}(\mathbf{x},t) \ ,$$

dove sono stati esplicitati gli argomenti $(\mathbf{x},t)$ delle funzioni,
per evidenziare la rappresentazione euleriana.

Una volta compresa la differenza tra le due descrizioni del problema,
non è necessario esprimere in maniera esplicita gli argomenti delle
funzioni. Da qui in avanti, verrà privilegiata una descrizione
euleriana, per campi, del problema.

In alcuni casi, come ad esempio problemi che riguardano lo studio di
correnti attorno a corpi mobili, può essere conveniente utilizzare una
rappresentazione arbitraria del problema, descrivendo il fenomeno
seguendo l'evoluzione delle grandezza meccaniche su punti, "etichettati"
dalla coordinata arbitraria $\mathbf{\chi}$, il cui moto è descritto in
coordinate euleriane dalla funzione $\mathbf{x}(\mathbf{\chi},t)$. Seguendo lo
stesso procedimento svolto per le particelle materiali, la velocità
$\mathbf{v}$ di questi punti in moto arbitrario è uguale alla derivata
parziale

$$\mathbf{v} = \dfrac{\partial \mathbf{x}}{\partial t} \bigg|_{\mathbf{\chi}} \ ,$$

svolta a coordinata $\mathbf{\chi}$ costante. Ancora seguendo lo stesso
procedimento svolto in precedenza, è possibile ricavare la relazione tra
la rappresentazione arbitraria e quella euleriana,

$$\label{eqn:cin:ale-eul}
 \dfrac{\partial \rule{1.5ex}{.4pt}}{\partial t} \bigg|_{\mathbf{\chi}} = \dfrac{\partial \rule{1.5ex}{.4pt}}{\partial t} \bigg|_{\mathbf{x}} + \mathbf{v} \cdot \mathbf{\nabla} \rule{1.5ex}{.4pt} \ .$$

e, confrontando la
([\[eqn:cin:lagr-eul\]](#eqn:cin:lagr-eul){reference-type="ref"
reference="eqn:cin:lagr-eul"}) e la
([\[eqn:cin:ale-eul\]](#eqn:cin:ale-eul){reference-type="ref"
reference="eqn:cin:ale-eul"}), la relazione tra la rappresentazione
arbitraria e quella lagrangiana,

$$\dfrac{\partial \rule{1.5ex}{.4pt}}{\partial t} \bigg|_{\mathbf{x_0}} = \dfrac{\partial \rule{1.5ex}{.4pt}}{\partial t} \bigg|_{\mathbf{\chi}} + (\mathbf{u} - \mathbf{v}) \cdot \mathbf{\nabla} \rule{1.5ex}{.4pt} \ .$$

## Velocità di traslazione, rotazione e deformazione

In questa sezione viene studiato il moto di un segmento materiale, che
segue il moto del mezzo continuo. Viene introdotto il tensore gradiente
di velocità $\mathbf{\nabla}\mathbf{u}$, con $\mathbf{u}(\mathbf{x},t)$ il campo di
velocità. Questo tensore viene prima scritto come somma della sua parte
antisimmetrica $\mathbb{W}$ e della sua parte simmetrica $\mathbb{D}$,
la quale può essere a sua volta scomposta nella parte idrostatica e
nella parte deviatorica $\mathbb{D}^d$. Viene infine descritta la natura
di questi tensori grazie alla loro influenza sul moto di segmento
materiale.

Il segmento materiale viene identificato dal vettore
$\Delta\mathbf{x_{12}}(t) = \mathbf{x_2}(t) - \mathbf{x_1}(t)$, i cui estremi sono i
punti di coordinate $\mathbf{x_1}(t)$ e $\mathbf{x_2}(t)$. Indicando con
$\mathbf{u_1}(t) = \mathbf{u}(\mathbf{x_1}(t),t)$ e
$\mathbf{u_2}(t) = \mathbf{u}(\mathbf{x_2}(t),t)$ loro velocità, è possibile
ricavare l'evoluzione temporale del segmento materiale,
$$\Delta\mathbf{x_{12}}(t+\Delta t) = \Delta\mathbf{x_{12}}(t) + \left( \mathbf{u_2}(t) - \mathbf{u_1}(t) \right) \Delta t + o(\Delta t) \ .$$
Tornando alla descrizione euleriana del problema, è possibile scrivere
la differenza di velocità introducendo il tensore gradiente di velocità,

$$\begin{aligned}
 \mathbf{u_2}(t) - \mathbf{u_1}(t) & = \mathbf{u}(\mathbf{x_2}(t),t) - \mathbf{u}(\mathbf{x_1}(t),t) = \\
 & = \mathbf{u}\left(\mathbf{x_1}(t)+\Delta\mathbf{x_{12}}(t),t\right) - \mathbf{u}\left(\mathbf{x_1}(t),t\right) = \\
 & = \mathbf{u}\left(\mathbf{x_1}(t),t\right) + \mathbf{\nabla}\mathbf{u}\left(\mathbf{x_1}(t),t\right) \cdot \Delta\mathbf{x_{12}}(t) - \mathbf{u}\left(\mathbf{x_1}(t),t\right) + o(|\Delta\mathbf{x_{12}}(t)|) = \\
 & = \mathbf{\nabla}\mathbf{u}\left(\mathbf{x_1}(t),t\right) \cdot \Delta\mathbf{x_{12}}(t) + o(|\Delta\mathbf{x_{12}}(t)|) \ . \\
 \end{aligned}$$

 Riarrangiando i termini si può scrivere,

$$\label{eqn:cin:material-segm}
 \Delta\mathbf{x_{12}}(t+\Delta t) = \Delta\mathbf{x_{12}}(t) + 
 \big[ \mathbf{\nabla}\mathbf{u}\left(\mathbf{x_1}(t),t\right) \cdot \Delta\mathbf{x_{12}}(t) + o(|\Delta\mathbf{x_{12}}(t)|) \big] \Delta t + o(\Delta t) \ .$$

e facendo tendere a zero $\Delta t$, si ricava

$$\dfrac{d \Delta\mathbf{x_{12}}}{d t}(t) = \mathbf{\nabla}\mathbf{u}\left(\mathbf{x_1}(t),t\right) \cdot \Delta\mathbf{x_{12}}(t) + o(|\Delta\mathbf{x_{12}}(t)|) \ .$$

Nell'ipotesi che i termini $o(|\Delta \mathbf{x_{12}}(t)|)$ siano
trascurabili, la velocità $\mathbf{u_2}$ del punto $\mathbf{x_2}$ differisce
dalla velocità $\mathbf{u_1}$ del punto $\mathbf{x_1}$ del termine
$d \Delta\mathbf{x_{12}}/d t$ che rappresenta le eventuali rotazioni rigide
e le deformazioni del mezzo continuo,

$$\label{eqn:cin:relative-vel-1}
 \mathbf{u_2}(t) = \mathbf{u_1}(t) + \mathbf{\nabla}\mathbf{u}\left(\mathbf{x_1}(t),t\right) \cdot \Delta\mathbf{x_{12}}(t) \ .$$

### Tensore gradiente di velocità

Il tensore gradiente di velocità può essere scritto come somma
$\mathbf{\nabla}\mathbf{u} = \mathbb{D} + \mathbb{W}$ della sua parte simmetrica
$\mathbb{D}$, il **tensore velocità di deformazione**, e della su parte
antisimmetrica $\mathbb{W}$, il **tensore di spin**,

$$\mathbb{D} = \dfrac{1}{2}\left(\mathbf{\nabla} \mathbf{u} + \mathbf{\nabla}^T \mathbf{u}\right)
  \quad , \quad 
  \mathbb{W} = \dfrac{1}{2}\left(\mathbf{\nabla} \mathbf{u} - \mathbf{\nabla}^T \mathbf{u}\right) \ ,$$

i quali possono essere scritti in componenti, in un sistema di
coordinate cartesiane come

$$D_{ij} = \dfrac{1}{2}\left[ \dfrac{\partial u_i}{\partial x_j} + \dfrac{\partial u_j}{\partial x_i} \right] \quad , \quad 
  W_{ij} = \dfrac{1}{2}\left[ \dfrac{\partial u_i}{\partial x_j} - \dfrac{\partial u_j}{\partial x_i} \right] \ .$$

Il tensore velocità di deformazione può essere poi scomposto nella sua
parte idrostatica e nella sua parte deviatorica $\mathbb{D}^d$,

$$\begin{aligned}
  \mathbb{D} & = \dfrac{1}{3} \text{tr}(\mathbb{D}) \mathbb{I} + \mathbb{D}^d \quad , \quad
   \mathbb{D}^d = \mathbb{D} - \dfrac{1}{3} \text{tr}(\mathbb{D}) \mathbb{I} \ ,
 \end{aligned}$$

 dove la traccia $\text{tr}(\mathbb{D})$ è uguale alla
divergenza del campo di velocità $\mathbf{\nabla} \cdot \mathbf{u}$. Il tensore
di spin è un tensore antisimmetrico del secondo ordine. Nello spazio
tridimensionale ha solo tre componenti indipendenti, che contengono le
componenti del vettore vorticità
$\mathbf{\omega} = \mathbf{\nabla} \times \mathbf{u}$. Ad esempio, utilizzando un
sistema di coordinate cartesiane, è possibile scrivere il tensore di
spin come 

$$\mathbb{W} = \dfrac{1}{2}\begin{bmatrix}
   0 & -\omega_z & \omega_y \\
   \omega_z & 0 & -\omega_x \\
   -\omega_y & \omega_x & 0 \\   
  \end{bmatrix} = \dfrac{1}{2}\text{Spin}(\mathbf{\omega}) \ .$$

L'operazione $\mathbb{W} \cdot \mathbf{v}$ tra il tensore antisimmetrico
$\mathbb{W}=\text{Spin}(\mathbf{\Omega})$ e un vettore $\mathbf{v}$ qualsiasi
coincide con l'operazione $\mathbf{\Omega} \times \mathbf{v}$. Introducendo la
scomposizione di $\mathbf{\nabla} \mathbf{u}$ nella formula
([\[eqn:cin:relative-vel-1\]](#eqn:cin:relative-vel-1){reference-type="ref"
reference="eqn:cin:relative-vel-1"}), si ricava

$$\begin{aligned}
 \mathbf{u_2}(t) & = \mathbf{u_1}(t) + \dfrac{1}{2}\mathbf{\omega}(\mathbf{x_1}(t),t) \times (\mathbf{x_2}(t) - \mathbf{x_1}(t) ) +  & \text{(atto di moto rigido)} \\ 
& + \mathbb{D}(\mathbf{x_1}(t),t) \cdot (\mathbf{x_2}(t) - \mathbf{x_1}(t)) \ . & \text{(deformazione)}
 %& + \left[ \dfrac{1}{3} \text{tr}(\mathbb{D}) \mathbb{I} +  \mathbb{D}^d \right] \cdot (\mathbf{x_2}(t) - \mathbf{x_1}(t)) \ . & \text{(deformazione)}
\end{aligned}$$ 

Da questa formula si possono riconoscere i contributi
alla velocità $\mathbf{u_2}$ di "traslazione" (la velocità del punto
$\mathbf{x_1}$), di rotazione con velocità angolare
$\mathbf{\Omega} = \frac{1}{2} \mathbf{\omega}$ e di deformazione,
$\mathbb{D} \cdot \Delta\mathbf{x_{12}}$.

### Derivate temporali di oggetti materiali

In questa sezione vengono descritti gli effetti dei singoli termini nei
quali può essere scomposto il gradiente di velocità tramite i loro
effetti sull'evoluzione di un segmento materiale $\mathbf{v}$ o di una
combinazione di segmenti materiali "elementari" (come ad esempio il
prodotto scalare o il triplo prodotto) , per i quali i termini di ordine
$o(|\mathbf{v}|)$ sono considerati trascurabili.

#### Vettore materiale.

Scrivendo il vettore $\mathbf{v}$ come prodotto del suo modulo $v$ per il
versore $\mathbf{\hat{n}}$ che ne identifica la direzione,
$\mathbf{v} = v \mathbf{\hat{n}}$, è possibile esprimerne la derivata nel tempo
come,

$$\label{eqn:cin:dvvec}
 \dfrac{d \mathbf{v}}{dt} = \dfrac{dv}{dt}\mathbf{\hat{n}} + v \dfrac{d \mathbf{\hat{n}}}{d t} \ .$$

#### Vettore materiale: modulo.

Utilizzando l'identità $\mathbf{\dot{\hat{n}}} \cdot \mathbf{\hat{n}} = 0$[^1],
moltiplicando scalarmente per $\mathbf{\hat{n}}$ l'ultima espressione, si
ricava la derivata nel tempo del modulo $v$ del vettore $\mathbf{v}$,

$$\label{eqn:cin:dvmod}
 \dfrac{d v}{d t} = \mathbf{\hat{n}} \cdot \dfrac{d \mathbf{v}}{dt} 
 - \underbrace{v \dfrac{d\mathbf{\hat{n}}}{dt}\cdot\mathbf{\hat{n}}}_{=0} = \mathbf{\hat{n}} \cdot \left[ \mathbb{D} + \mathbb{W} \right] \cdot \mathbf{v} = 
 \mathbf{\hat{n}} \cdot \mathbb{D} \cdot \mathbf{\hat{n}} v \ ,$$

 avendo
introdotto la scomposizione
$\mathbf{\nabla} \mathbf{u} = \mathbb{D} + \mathbb{W}$ nella formula
([\[eqn:cin:material-segm\]](#eqn:cin:material-segm){reference-type="ref"
reference="eqn:cin:material-segm"}) applicata al vettore materiale
$\mathbf{v}$ e utilizzato l'identità
$\mathbf{\hat{n}} \cdot \mathbb{W} \cdot \mathbf{\hat{n}} = 0$, poiché
$\mathbb{W}$ è antisimmetrica. Poichè il tensore velocità di
deformazione è simmetrico, esiste una base di vettori ortonormali
$\{\mathbf{\hat{p}_1},\mathbf{\hat{p}_2},\mathbf{\hat{p}_3}\}$ che permettono di
scrivere la decomposizione spettrale di $\mathbb{D}$,

$$\mathbb{D} = \lambda_1 \mathbf{\hat{p}_1} \otimes \mathbf{\hat{p}_1} +
              \lambda_2 \mathbf{\hat{p}_2} \otimes \mathbf{\hat{p}_2} +
              \lambda_3 \mathbf{\hat{p}_3} \otimes \mathbf{\hat{p}_3} \ .$$

I vettori $\mathbf{\hat{p}_i}$ sono gli autovettori del tensore $\mathbb{D}$
che ne rappresentano le *direzioni principali*, mentre gli scalari
$\lambda_i$ sono gli autovalori associati, tali che
$\mathbb{D} \cdot \mathbf{\hat{p}_i} = \lambda_i \mathbf{\hat{p_i}}$. É quindi
possibile scrivere la derivata nel tempo del modulo $v$ del vettore
materiale $\mathbf{v}$ come

$$\dfrac{1}{v} \dfrac{d v}{d t} = \lambda_1 n_1^2 +  \lambda_2 n_2^2 +  \lambda_3 n_3^2 \ ,$$

avendo indicato con $n_i = \mathbf{\hat{n}} \cdot \mathbf{\hat{p}_i}$ le
proiezioni del versore $\mathbf{\hat{n}}$ sugli autovettori del tensore
$\mathbb{D}$.

#### Vettore materiale: direzione.

Combinando la ([\[eqn:cin:dvvec\]](#eqn:cin:dvvec){reference-type="ref"
reference="eqn:cin:dvvec"}) e la
([\[eqn:cin:dvmod\]](#eqn:cin:dvmod){reference-type="ref"
reference="eqn:cin:dvmod"}), è possibile ricavare la derivata nel tempo
della direzione $\mathbf{\hat{n}}$ del vettore materiale $\mathbf{v}$,

$$\begin{aligned}
 \dfrac{d \mathbf{\hat{n}}}{d t} = \dfrac{1}{v}\dfrac{d\mathbf{v}}{dt} - \dfrac{1}{v} \mathbf{\hat{n}} \dfrac{d v}{d t}  & = [ \mathbb{D} + \mathbb{W} ] \cdot \mathbf{\hat{n}} - \mathbf{\hat{n}} \mathbf{\hat{n}} \cdot \mathbb{D} \cdot \mathbf{\hat{n}} = \\
   & =  [ \mathbb{I} - \mathbf{\hat{n}} \otimes \mathbf{\hat{n}} ] \cdot \mathbb{D} \cdot \mathbf{\hat{n}} + \mathbb{W} \cdot \mathbf{\hat{n}} = \\
   & = [ \mathbb{I} - \mathbf{\hat{n}} \otimes \mathbf{\hat{n}} ] \cdot \mathbb{D} \cdot \mathbf{\hat{n}} + \dfrac{1}{2} \mathbf{\omega} \times \mathbf{\hat{n}} \ .
\end{aligned}$$

Il tensore
$\mathbb{P} := \mathbb{I} - \mathbf{\hat{n}} \otimes \mathbf{\hat{n}}$ è il
proiettore ortogoanle in direzione perpendicolare a $\mathbf{\hat{n}}$, che
ha nucleo generato da $\mathbf{\hat{n}}$, cioè
$\mathbb{P} \cdot \mathbf{\hat{n}} = \mathbf{0}$. Introducendo la scomposizione
del tensore $\mathbb{D}$ nella sua parte idrostatica e deviatorica, è
possibile dimostrare che la parte idrostatica non influenza la derivata
del versore $\mathbf{\hat{n}}$

$$\dfrac{d \mathbf{\hat{n}}}{d t} = [ \mathbb{I} - \mathbf{\hat{n}} \otimes \mathbf{\hat{n}} ] \cdot \mathbb{D}^d \cdot \mathbf{\hat{n}} + \dfrac{1}{2} \mathbf{\omega} \times \mathbf{\hat{n}} \ ,$$


poiché
$\mathbb{P} \cdot \mathbb{I} \cdot \mathbf{\hat{n}} = \mathbb{P} \cdot \mathbf{\hat{n}} = \mathbf{0}$.
In generale quindi la direzione di un vettore materiale dipende dalle
rotazioni, rappresentate dal termine
$\frac{1}{2} \mathbf{\omega} \times \mathbf{\hat{n}}$ e dalla parte deviatorica
del tensore velocità di deformazione. Questo ultimo contributo può
essere nullo in alcuni casi, come ad esempio

- quando lo stato di deformazione è "idrostatico", per il quale
  $\mathbb{D}^d = 0$,

- quando il vettore $\mathbf{v}$ appartenente al nucleo di $\mathbb{D}^d$,
  $\mathbb{D}^d \cdot \mathbf{v} = \mathbf{0}$, orientato cioè in una
  direzione che non subisce una deformazione deviatorica,

- quando il vettore $\mathbf{v}$ è allineato con una delle direzioni
  principali $\mathbf{\hat{p}_i}$ di $\mathbb{D}$: in questo caso, il
  vettore $\mathbb{D} \cdot \mathbf{\hat{n}}$ è allineato con
  $\mathbf{\hat{n}}$, poichè
  $\mathbb{D} \cdot \mathbf{\hat{n}} = \lambda_i \mathbf{\hat{n}}$, e quindi
  appartiene al nucleo del proiettore $\mathbb{P}$, cioè
  $\mathbb{P} \cdot (\mathbb{D} \cdot \mathbf{\hat{n}}) = \mathbf{0}$.

#### Angolo tra vettori materiali.

Calcolando la derivata materiale del prodotto scalare tra due vettori
materiali $\mathbf{v}$ e $\mathbf{w}$, è possibile verificare che il tensore di
spin $\mathbb{W}$ rappresenta una rotazione rigida, non modificando né i
moduli dei singoli vettori materiali, né l'angolo compreso tra di essi.
Infatti la derivata

$$\begin{aligned}
 \dfrac{d}{dt} (\mathbf{v} \cdot \mathbf{w}) & = \dfrac{d\mathbf{v}}{dt} \cdot \mathbf{w} + \mathbf{v} \cdot \dfrac{d\mathbf{w}}{dt} = \\
  & = \mathbf{w} \cdot \mathbb{D} \cdot \mathbf{v} + \dfrac{1}{2} \mathbf{w} \cdot \mathbf{\omega} \times \mathbf{v} + 
   \mathbf{v} \cdot \mathbb{D} \cdot \mathbf{w} + \dfrac{1}{2} \mathbf{v} \cdot \mathbf{\omega} \times \mathbf{w} = \\
   & = 2 \mathbf{w} \cdot \mathbb{D} \cdot \mathbf{v} \ ,
\end{aligned}$$

avendo utilizzato la simmetria del tensore velocità di
deformazione $\mathbb{D}$ e l'identità vettoriale
$\mathbf{c} \cdot \mathbf{a} \times \mathbf{b} = - \mathbf{b} \cdot \mathbf{a} \times \mathbf{c}$.
La derivata del coseno dell'angolo formato dai vettori materiali
$\mathbf{v} = v \mathbf{\hat{n}_v}$, $\mathbf{w} = w \mathbf{\hat{n}_w}$ dipende
solamente dalla parte deviatorica del tensore velocità di deformazione,

$$\begin{aligned}
 \dfrac{d \cos \theta_{vw}}{dt} & = \dfrac{d}{d t} \dfrac{\mathbf{v} \cdot \mathbf{w}}{|\mathbf{v}||\mathbf{w}|} = \\
  & = 2 \mathbf{\hat{n}_w} \cdot \mathbb{D}^d \mathbf{\hat{n}_v} - \mathbf{\hat{n}_v} \cdot \mathbf{\hat{n}_w} (\mathbf{\hat{n}_v} \cdot \mathbb{D}^d \cdot \mathbf{\hat{n}_v} + \mathbf{\hat{n}_w} \cdot \mathbb{D}^d \cdot \mathbf{\hat{n}_w} ) = \\
  & = 2 (1 - \mathbf{\hat{n}_v} \cdot \mathbf{\hat{n}_w}) \mathbf{\hat{n}_w} \cdot \mathbb{D}^d \mathbf{\hat{n}_v} - \mathbf{\hat{n}_v} \cdot \mathbf{\hat{n}_w} (\mathbf{\hat{n}_v} - \mathbf{\hat{n}_w}) \cdot \mathbb{D}^d \cdot (\mathbf{\hat{n}_v} - \mathbf{\hat{n}_w}) \ .
\end{aligned}$$

#### Volume generato da vettori materiali.

Infine, è possibile dimostrare che la derivata del volume materiale
(elementare, per il quale i termini $o(|\Delta \mathbf{x}|)$ siano
trascurabili) $V = \mathbf{a} \times \mathbf{b} \cdot \mathbf{c}$ del
parallelepipedo formato dai tre vettori materiali $\mathbf{a}$, $\mathbf{b}$,
$\mathbf{c}$ vale 

$$\dfrac{d V}{d t} = (\mathbf{\nabla} \cdot \mathbf{u}) V \ .$$

La
divergenza del campo di velocità rappresenta quindi la derivata nel
tempo di un volume materiale relativa al volume materiale stesso. Il
**vincolo cinematico di incomprimibilità** impone che l'estensione di un
volume materiale non vari nel tempo, $dV/dt = 0$, ed è quindi
equivalente alla condizione di solenoidalità del campo di velocità,
$\mathbf{\nabla} \cdot \mathbf{u} = 0$.

## Curve caratteristiche

Per descrivere il moto di un fluido vengono definite quattro famiglie di
curve: le linee di corrente, le traiettorie, le curve di emissione (o
linee di fumo) e le tracce. Viene data una definizione matematica di
queste curve, che possono essere ottenute durante le attività
sperimentali tramite delle tecniche di visualizzazione del campo di
moto, come mostrato nel seguente video, [Stanford 1963 - Flow
Visualization](https://www.youtube.com/watch?v=nuQyKGuXJOs).
`https://www.youtube.com/watch?v=nuQyKGuXJOs`, nel caso non funzionasse
il collegamento sopra a uno degli storici video del National Committee.

Come già anticipato, secondo la descrizione euleriana del moto di un
mezzo continuo, il campo di velocità è rappresentato dalla funzione
vettoriale $\mathbf{u}$ i cui argomenti indipendenti sono la coordinata
spaziale $\mathbf{r}$ e quella temporale $t$, $\mathbf{u}(\mathbf{r},t)$. Vengono
ora definite le quattro curve caratteristiche elencate sopra:

-   Le **linee di corrente** sono curve $\mathbf{S}$ tangenti al campo
    vettoriale $\mathbf{u}(\mathbf{r},t)$ in ogni punto dello spazio $\mathbf{r}$,
    all'istante temporale $t$ considerato. Essendo curve (dimensione=1),
    possono essere espresse in forma parametrica come funzioni di un
    parametro scalare $p$, $\mathbf{S}(p)$. La "traduzione matematica" della
    definizione è quindi

    $$\label{eqn:cinematica:ldc}
     \frac{d\mathbf{S}}{dp}(p) = \lambda(p) \mathbf{u}(\mathbf{S}(p),t) \ ,$$

     cioè
    il vettore tangente ${d\mathbf{S}(p)}/{dp}$ alla curva $\mathbf{S}(p)$, nel
    punto identificato dal valore del parametro $p$, è parallelo al
    vettore velocità $\mathbf{u}$ calcolato nello stesso punto $\mathbf{S}(p)$,
    al tempo considerato $t$. La funzione $\lambda(p)$ dipende dalla
    parametrizzazione utilizzata e non influisce sulla forma della linea
    di corrente. L'equazione
    ([\[eqn:cinematica:ldc\]](#eqn:cinematica:ldc){reference-type="ref"
    reference="eqn:cinematica:ldc"}) rappresenta tutte le linee di
    corrente: per ottenere la linea di corrente passante per un punto, è
    necessario imporre questa condizione come condizione al contorno.

-   Una **traiettoria** descrive il moto di una singola particella
    materiale, la cui velocità è uguale a quella del fluido, nella
    posizione in cui si trova e all'istante di tempo "attuale". La
    traiettoria di una particella è descritta dall curva $\mathbf{R}(t)$,
    parametrizzata con il tempo $t$, che soddisfa il seguente problema
    differenziale

    $$\begin{cases}
     \dfrac{d\mathbf{R}}{dt}(t) = \mathbf{u}(\mathbf{R}(t),t) \\
     \mathbf{R}(t_0) = \mathbf{R_0} \ .
    \end{cases}$$

    L'equazione differenziale traduce la definizione di
    particella materiale: la velocità della particella materiale
    $\mathbf{v}(t) = d \mathbf{R} / dt (t)$ è uguale alla velocità del fluido
    nello stesso punto allo stesso istante di tempo,
    $\mathbf{u}(\mathbf{R}(t),t)$. La condizione iniziale identifica tra tutte
    le traiettorie delle infinite particelle materiali, quella della
    particella che all'istante $t_0$ passa per il punto $\mathbf{R_0}$.
    Fissati i "parametri" $t_0$ e $\mathbf{R_0}$ che identificano la
    particella desiderata, la sua traiettoria è descritta dalla curva
    $\mathbf{R}(t;t_0,\mathbf{R_0})$, funzione del tempo "attuale" $t$.

-   Una **linea di fumo** è il luogo dei punti descritto dalla posizione
    al tempo $t$ (fissato) di tutte le particelle materiali passate per
    un punto (fissato) nello spazio, $\mathbf{R_0}$, negli istanti di tempo
    $t_0$ precedenti a $t$, $t_0 < t$.

    $$\begin{cases}
     \dfrac{d\mathbf{R}}{dt}(t) = \mathbf{u}(\mathbf{R}(t),t) \\
     \mathbf{R}(t_0) = \mathbf{R_0} \ .
    \end{cases}$$

    Il problema è identico a quello delle traiettorie.
    Cambia però il ruolo di $t$, $t_0$, $\mathbf{R_0}$: la linea di fumo al
    "tempo di osservazione" $t$ formata da tutte le particelle passanti
    da $\mathbf{R_0}$ a istanti temporali $t_0$, con $t_0<t$, è una
    descritta dalla curva $\mathbf{R}(t_0;t,\mathbf{R_0})$, funzione
    dell'istante $t_0$.

-   Una **traccia** è il luogo dei punti descritto dalla posizione al
    tempo $t$ (fissato) di tutte le particelle materiali che si
    trovavano su una curva $\mathbf{R_0}(p)$ al tempo $t_0$ (fissato).

    $$\begin{cases}
     \dfrac{d\mathbf{R}}{dt}(t) = \mathbf{u}(\mathbf{R}(t),t) \\
     \mathbf{R}(t_0) = \mathbf{R_0} \ .
    \end{cases}$$ 

    Ancora una volta il problema è identico a quello delle
    traiettorie ma cambia il ruolo di $t$, $t_0$, $\mathbf{R_0}$: fissati i
    parametri $t_0$ e $t$ che identificano rispettivamente l'istante di
    tempo in cui le particelle materiali desiderate si trovano sulla
    curva $\mathbf{R_0}$ e l'istante di tempo in cui la curva viene
    osservata, la traccia è una funzione dell luogo dei punti "iniziale"
    $\mathbf{R_0}$, $\mathbf{R}(\mathbf{R_0};t,t_0)$.

#### Osservazione 1.

Nel caso di campi stazionari, cioè indipendenti dal tempo,
$\mathbf{u}(\mathbf{r},t) = \mathbf{u}^{(staz)}(\mathbf{r})$, linee di corrente,
traiettorie e linee di fumo coincidono.

[^1]: Poichè $\mathbf{\hat{n}}$ è un versore,
    $|\mathbf{\hat{n}}|^2 = \mathbf{\hat{n}}\cdot\mathbf{\hat{n}} = 1$. La derivata
    nel tempo di quest'ultima espressione diventa
    $0 = \mathbf{\dot{\hat{n}}} \cdot \mathbf{\hat{n}} + \mathbf{\hat{n}} \cdot \mathbf{\dot{\hat{n}}} = 2 \mathbf{\dot{\hat{n}}} \cdot \mathbf{\hat{n}}$,
    da cui si ricava l'identità desiderata.
