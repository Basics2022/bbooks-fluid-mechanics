(fluid-mechanics:balances)=
# Balance equations

In questo capitolo vengono introdotti i bilanci di alcune quantità
meccaniche per un mezzo continuo. I bilanci in forma integrale
permettono di descrivere l'evoluzione complessiva (integrale) di un
sistema e vengono ricavati partendo da alcuni principi fondamentali
della meccanica classica: la conservazione della massa, l'equazioni
cardinali della dinamica, il primo principio della termodinamica o
bilancio dell'energia. Vengono scritti prima per un volume materiale e
poi per volumi di controllo o volumi in moto generico, utilizzando il
teorema del trasporto di Reynolds.

Dai bilanci in forma integrale, sotto ipotesi di sufficiente regolarità
dei campi, vengono poi ricavati i bilanci in forma differenziale, che
permettono di descrivere l'evoluzione locale (puntuale) di un sistema.
La forma lagrangiana del bilanci di massa, di quantità di moto e della
vorticità verrà utilizzata per meglio apprezzare il significato del
vincolo di incomprimibilità, il ruolo della pressione (e degli sforzi in
generale) nella dinamica di un fluido e intuire l'influenza del campo di
velocità sul campo di vorticità.

Successivamente, dai bilanci integrali vengono ricavate le relazioni di
salto delle quantità meccaniche. Queste relazioni possono essere
utilizzate per trovare determinare lo stato di un sistema formato da due
sotto-sistemi, all'interno dei quali i campi sono regolari, ma che sono
separati da una frontiera, attraverso la quale i campi non sono
regolari: alcuni esempi di queste sono le superfici "di scorrimento" in
fluidi non viscosi, attraverso le quali è discontinua la componente
tangenziale della velocità, o le onde d'urto che possono formarsi in
correnti comprimibili di fluidi non viscosi.

Infine, viene fornita una breve introduzione agli esercizi sui bilanci
integrali, che costituisce una prima linea guida al loro svolgimento.

(fluid-mechanics:balance:integral)=
## Bilanci in forma integrale

Vengono ricavati i bilanci integrali per un volume materiale $V(t)$
partendo dai principi fondamentali della meccanica classica.
Successivamente si ricavano i bilanci per un volumi in moto arbitrario
$v(t)$ e, come caso particolare, volumi di controllo $V_c$.

Bilancio di massa
-----------------

La massa di un volume materiale è uguale all'integrale sul volume della
densità $\rho$. Per il **principio di conservazione della massa**, la
massa di un sistema chiuso (che non ha scambi di materia con l'esterno),
come ad esempio un volume materiale $V(t)$, rimane costante e quindi la
sua derivata nel tempo deve essere uguale a zero,

$$\dfrac{d}{dt} \int_{V(t)} \rho = 0 \ .$$

Bilancio della quantità di moto
-------------------------------

La quantità di moto di un volume materiale è uguale all'integrale sul
volume della quantità di moto per unità di volume $\rho \mathbf{u}$, dove
$\mathbf{u}$ è la velocità delle particelle materiali. Per la **prima
equazione cardinale della dinamica**, la derivata nel tempo della
quantità di moto di un sistema è uguale alla risultante delle forze
esterne agenti sul sistema,

$$\dfrac{d}{dt} \int_{V(t)} \rho \mathbf{u} = \int_{V(t)} \mathbf{f} + \oint_{S(t)} \mathbf{t_n} \ ,$$

dove $\int_{V(t)} \mathbf{f}$ rappresenta la risultante delle forze esterne
di volume e $\oint_{S(t)} \mathbf{t_n}$ la risultante delle forze esterne di
superficie, avendo indicato con $\mathbf{f}$ il campo di forze per unità di
volume e $\mathbf{t_n}$ il vettore sforzo agente sulla supreficie esterna
$S(t)$ del volume $V(t)$. Il teorema di Cauchy nella meccanica del
continuo, permette di esprimere il vettore sforzo $\mathbf{t_n}$ in funzione
del tensore degli sforzi $\mathbb{T}$ e la normale alla superficie
$\mathbf{\hat{n}}$, come $\mathbf{t_n} = \mathbf{\hat{n}} \cdot \mathbb{T}$.

Bilancio del momento quantità di moto
-------------------------------------

Il momento della quantità di moto di un volume materiale è uguale
all'integrale sul volume del momento della quantità di moto per unità di
volume $\rho \mathbf{r} \times \mathbf{u}$, dove $\mathbf{r}$ è il vettore che
congiunge il polo con i punti del volume materiale. Per la **seconda
equazione cardinale della dinamica**, la derivata nel tempo del momento
della quantità di moto di un sistema, rispetto a un polo fisso, è uguale
alla risultante momenti esterni sul sistema,

$$\dfrac{d}{dt} \int_{V(t)} \rho \mathbf{r} \times \mathbf{u} = \int_{V(t)} \mathbf{r} \times \mathbf{f} + \oint_{S(t)} \mathbf{r} \times \mathbf{t_n} \ ,$$

nell'ipotesi che non ci siano momenti esterni per unità di volume e che
il materiale non sia polare (due elementi di materiale adiacenti non si
scambiano momenti ma solo forze).

Bilancio dell'energia totale
----------------------------

L'energia totale di un volume materiale è uguale all'integrale sul
volume della sua energia interna per unità di volume $\rho e$ e della
sua energia cinetica per unità di volume $\rho |\mathbf{u}|^2/2$. Combinando
il **primo principio della termodinamica** (che riguarda solo sistemi in
equilibrio) con il **teorema dell'energia cinetica** (che non include il
contributo di energia interna), la derivata nel tempo dell'energia
totale del sistema di un sistema è uguale alla differenza tra la potenza
delle forze agenti sul sistema e i flussi di calore uscenti da esso,

$$\dfrac{d}{dt} \int_{V(t)} \rho e^t = \int_{V(t)} \mathbf{f} \cdot \mathbf{u} + \oint_{S(t)} \mathbf{t_n} \cdot \mathbf{u} - \oint_{S(t)} \mathbf{q} \cdot \mathbf{\hat{n}} + \int_{V(t)} \rho r \ ,$$

avendo indicato con $\mathbf{q}$ il flusso di calore uscente dal volume
materiale $V(t)$, e con $r$ l'intensità di una sorgente di calore per
unità di massa $r$, distributia all'interno del volume $V(t)$, come ad
esempio il calore rilasciato da una reazione chimica come la
combustione.

Bilanci integrali per volumi in moto arbitrario
-----------------------------------------------

Utilizzando il teorema del trasporto di Reynolds, è possibile esprimere
la derivata nel tempo dell'integrale di un campo $f$ su un volume
materiale $V(t)$ come somma della derivata nel tempo dell'integrale
dello stesso campo $f$ su un volume arbitrario $v(t)$ e al flusso della
quantità $f$ attraverso la frontiera $s(t)=\partial v(t)$ di $v(t)$,
dovuto alla velocità relativa $\mathbf{u} - \mathbf{v}$ tra le particelle
materiali e la superficie $s(t)$,

$$\dfrac{d}{d t} \int_{V(t)} f = \dfrac{d}{d t} \int_{v(t)\equiv V(t)} f +
 \oint_{s(t)\equiv S(t)} f (\mathbf{u} - \mathbf{v}) \cdot \mathbf{\hat{n}} \ .$$

I bilanci integrali riferiti a un volume arbitrario $v(t)$, la cui
superficie $s(t)$ si muove con velocità $\mathbf{v}$, risultano

$$\begin{cases}
 \dfrac{d}{dt} \displaystyle\int_{v(t)} \rho + \oint_{s(t)} \rho (\mathbf{u}-\mathbf{v}) \cdot \mathbf{\hat{n}}= 0  \\
 \dfrac{d}{dt} \displaystyle\int_{v(t)} \rho \mathbf{u} + \oint_{s(t)} \rho \mathbf{u} (\mathbf{u} - \mathbf{v}) \cdot \mathbf{\hat{n}} = \int_{v(t)} \mathbf{f} + \oint_{s(t)} \mathbf{t_n}  \\
 \dfrac{d}{dt} \displaystyle\int_{v(t)} \rho \mathbf{r} \times \mathbf{u} + \oint_{s(t)} \rho \mathbf{r} \times \mathbf{u} (\mathbf{u}-\mathbf{v}) \cdot \mathbf{\hat{n}}= \int_{v(t)} \mathbf{r} \times \mathbf{f} + \oint_{s(t)} \mathbf{r} \times \mathbf{t_n} \\
 \dfrac{d}{dt} \displaystyle\int_{v(t)} \rho e^t + \oint_{s(t)} \rho e^t (\mathbf{u}-\mathbf{v}) \cdot \mathbf{\hat{n}}= \int_{v(t)} \mathbf{f} \cdot \mathbf{u} + \oint_{s(t)} \mathbf{t_n} \cdot \mathbf{u} - \oint_{s(t)} \mathbf{q} \cdot \mathbf{\hat{n}} + \int_{V(t)} \rho r \ .
\end{cases}$$

Bilanci integrali per volumi di controllo fissi
-----------------------------------------------

Come caso particolare dei bilanci integrali riferiti a un volume
arbitrario $v(t)$, i bilanci integrali riferiti a un volume di controllo
fisso $V_c$ risultano 

$$\begin{cases}
   \dfrac{d}{d t} \displaystyle\int_{V_c} \rho + \oint_{S_c} \rho \mathbf{u} \cdot \mathbf{\hat{n}} = 0 \\
   \dfrac{d}{d t} \displaystyle\int_{V_c} \rho  \mathbf{u}+ \oint_{S_c} \rho \mathbf{u} \mathbf{u} \cdot \mathbf{\hat{n}} = \int_{V_c} \mathbf{f} + \oint_{S_c} \mathbf{t_n} \\
   \dfrac{d}{d t} \displaystyle\int_{V_c} \rho \mathbf{r} \times \mathbf{u}+ \oint_{S_c} \rho \mathbf{r} \times \mathbf{u} \mathbf{u} \cdot \mathbf{\hat{n}} = \int_{V_c} \mathbf{r} \times \mathbf{f} + \oint_{S_c} \mathbf{r} \times \mathbf{t_n} \\
   \dfrac{d}{d t} \displaystyle\int_{V_c} \rho e^t + \oint_{S_c} \rho e^t \mathbf{u} \cdot \mathbf{\hat{n}} = \int_{V_c} \mathbf{f} \cdot \mathbf{u} + \oint_{S_c} \mathbf{t_n} \cdot \mathbf{u} - \oint_{S_c} \mathbf{q} \cdot \mathbf{\hat{n}} + \int_{V(t)} \rho r  \ .
 \end{cases}$$

(fluid-mechanics:balance:differential)=
## Bilanci in forma differenziale

Sotto le ipotesi di sufficiente regolarità dei campi che compaiono negli
integrali di superficie, è possibile trasformare gli integrali di
superficie in integrali di volume, applicando il teorema della
divergenza o il lemma del teorema di Green

$$\oint_{S} f n_i = \int_V f_{/i} \ ,$$

avendo indicato con $f_{/i}$ la
derivata parziale rispetto alla coordinata cartesiana $x_i$ e con $n_i$
la proiezione lungo $x_i$ della normale uscente dalla superficie
$S=\partial V$. Una volta scritti tutti i termini come integrali di
volume, sullo stesso volume $V$, è possibile sfruttare l'arbitrarietà
del volume $V$ per ricavare i bilanci in forma differenziale. In questa
sezione, si partirà dai bilanci in forma integrale scritti per un volume
di controllo fisso $V=V_c$, per il quale vale

$$\dfrac{d}{d t} \int_V f = \int_V \dfrac{\partial f}{\partial t} \ ,$$

secondo il teorema del trasporto di Reynolds.

Bilancio di massa
-----------------

Usando il teorema del trasporto di Reynolds per volumi di controllo
fissi e applicando il teorema della divergenza al termine di flusso, si
può scrivere

$$\dfrac{d}{d t} \displaystyle\int_{V} \rho + \oint_{S} \rho \mathbf{u} \cdot \mathbf{\hat{n}} = \int_V \left[ \dfrac{\partial \rho}{\partial t} + \mathbf{\nabla} \cdot (\rho \mathbf{u})\right] = 0 \ .$$

Sfruttando l'arbitrarietà del bilancio integrale dal volume considerato
e imponendo che l'integranda sia nulla, si ricava la *forma
conservativa* del bilancio differenziale di massa,

$$\dfrac{\partial \rho}{\partial t} + \mathbf{\nabla} \cdot (\rho \mathbf{u}) = 0$$

Sviluppando la divergenza
$\mathbf{\nabla} \cdot (\rho \mathbf{u}) = \rho \mathbf{\nabla} \cdot \mathbf{u} + \mathbf{u} \cdot \mathbf{\nabla} \rho$,
e riconoscendo l'espressione della derivata materiale, si ottiene la
*forma convettiva* del bilancio differenziale di massa,

$$\begin{aligned}
 \dfrac{\partial \rho}{\partial t} + \mathbf{u} \cdot \mathbf{\nabla} \rho &+ \rho \mathbf{\nabla} \cdot \mathbf{u} = 0 \\ 
 \dfrac{D \rho}{D t} = &- \rho \mathbf{\nabla} \cdot \mathbf{u} \ .
\end{aligned}$$

Il vincolo cinematico di incomprimibilità $\mathbf{\nabla} \cdot \mathbf{u} = 0$
equivale al vincolo "fisico" che impone che la densità delle singole
particelle materiali rimanga costante, $D\rho/Dt = 0$.

Bilancio di quantità di moto
----------------------------

É possibile trasformare in un integrale di volume la risultante degli
sforzi di superficie, utilizzando il teorema di Cauchy per i mezzi
continui, 

$$\mathbf{t_n} = \mathbf{\hat{n}} \cdot \mathbb{T} \quad , \quad 
  t_i = n_j T_{ji} \ ,$$

  dove $\mathbf{t_n}$ è il vettore sforzo,
$\mathbf{\hat{n}}$ la normale alla superficie e $\mathbb{T}$ il tensore
degli sforzi. La risultante degli sforzi di superficie diventa, usando
un po' di libertà nel passare dalla notazione astratta a quella
indiciale, 

$$\oint_S \mathbf{t_n} = \oint_S t_i = \oint_S n_j T_{ji} =
  \int_V T_{ji/j} = \int_V \mathbf{\nabla} \cdot \mathbb{T} \ .$$

  Usando il
teorema del trasporto di Reynolds per volumi di controllo fissi e
applicando il teorema della divergenza al termine di flusso,

$$\oint_S \big\{ \rho \mathbf{u} \mathbf{u} \cdot \mathbf{\hat{n}} \big\}_i = \oint_S \rho u_i u_j n_j = \int_V (\rho u_i u_j)_{/j} = \int_{V} \mathbf{\nabla} \cdot ( \rho \mathbf{u} \otimes \mathbf{u} ) \ ,$$

si può scrivere il bilancio di quantità di moto

$$\displaystyle\int_{V} \dfrac{\partial(\rho \mathbf{u})}{\partial t}  + \int_{V} \mathbf{\nabla} \cdot ( \rho \mathbf{u} \otimes \mathbf{u} ) = \int_{V} \left[ \mathbf{f} +  \mathbf{\nabla} \cdot \mathbb{T} \right] \ .$$

Sfruttando l'arbitrarietà del bilancio integrale dal volume considerato
e imponendo che l'integranda sia nulla, si ricava la *forma
conservativa* del bilancio differenziale di quantità di moto,

$$\dfrac{\partial(\rho \mathbf{u})}{\partial t}  + \mathbf{\nabla} \cdot ( \rho \mathbf{u} \otimes \mathbf{u} - \mathbb{T} ) = \mathbf{f} \ .$$

Sviluppando i termini

$$\begin{aligned}
 \dfrac{\partial (\rho \mathbf{u})}{\partial t} = \rho \dfrac{\partial \mathbf{u}}{\partial t} + \mathbf{u} \dfrac{\partial \rho}{\partial t} \quad & , \quad 
 \dfrac{\partial (\rho u_i)}{\partial t} = \rho \dfrac{\partial u_i}{\partial t} + u_i \dfrac{\partial \rho}{\partial t} \\
 \mathbf{\nabla} \cdot ( \rho \mathbf{u} \otimes \mathbf{u} ) = \rho (\mathbf{u} \cdot \mathbf{\nabla}) \mathbf{u} + \mathbf{u} \mathbf{\nabla} \cdot (\rho \mathbf{u}) \quad & , \quad 
 ( \rho u_i u_j )_{/j} = \rho u_j u_{i/j} + u_i (\rho u_j)_{/j} 
  \ ,
\end{aligned}$$

riconoscendo che
$\mathbf{u} \cdot (\partial \rho/\partial t + \mathbf{\nabla} \cdot (\rho \mathbf{u}))=0$
come conseguenza della conservazione della massa, si ottiene la *forma
convettiva* dell'equazione della quantità di moto

$$\begin{aligned}
   \rho \dfrac{\partial\mathbf{u}}{\partial t}  +  \rho (\mathbf{u}  \cdot \mathbf{\nabla} ) \mathbf{u}& = \mathbf{f} + \mathbf{\nabla} \cdot \mathbb{T}  \\ 
   \rho \dfrac{D \mathbf{u}}{D t} & = \mathbf{f} + \mathbf{\nabla} \cdot \mathbb{T} \ . \\ 
  \end{aligned}$$

Bilancio del momento della quantità di moto
-------------------------------------------

Il bilancio del momento della quantità di moto per un mezzo continuo non
polare è equivalente alla condizione di simmetria del tensore degli
sforzi $$\mathbb{T}^T = \mathbb{T} \quad , \quad T_{ij} = T_{ji} \ .$$

Bilancio dell'energia totale
----------------------------

Usando un po' di libertà nel passare dalla notazione astratta a quella
indiciale, la potenza degli sforzi di superficie diventa

$$\begin{aligned}
 \oint_S \mathbf{t_n} \cdot \mathbf{u} = \oint_S t_i u_i = \oint_S n_j T_{ji} u_i & =
  \int_V (T_{ji} u_i)_{/j}= \int_V \mathbf{\nabla} \cdot ( \mathbb{T} \cdot \mathbf{u}) \\
  & = \int_V (T_{ij/j} u_i + T_{ij} u_{j/i}) = \int_V \big( (\mathbf{\nabla} \cdot \mathbb{T}) \cdot \mathbf{u} + \mathbb{T} : \mathbf{\nabla} \mathbf{u} \big) \ , 
\end{aligned}$$ 

avendo utilizzato la simmetria del tensore degli sforzi,
$T_{ij/j} = \{ \mathbf{\nabla} \cdot \mathbb{T}^T \}_i = \{ \mathbf{\nabla} \cdot \mathbb{T} \}_i$.
Applicando il teorema della divergenza, il termine di flusso di calore

viene scritto come

$$\oint_S \mathbf{q} \cdot \mathbf{\hat{n}} = \int_V \mathbf{\nabla} \cdot \mathbf{q} \ .$$

La *forma conservativa* del bilancio differenziale di energia totale
diventa quindi

$$\dfrac{\partial (\rho e^t)}{\partial t} + \mathbf{\nabla} \cdot (\rho e^t \mathbf{u} - \mathbb{T} \cdot \mathbf{u} + \mathbf{q}) = \mathbf{f} \cdot \mathbf{u} + \rho r \ .$$

Sviluppando la derivata temporale e il termine
$\mathbf{\nabla} \cdot (\rho e^t \mathbf{u}) = \rho \mathbf{u} \cdot \mathbf{\nabla} e^t + e^t \mathbf{\nabla} \cdot (\rho \mathbf{u})$,
riconoscendo che
$e^t (\partial \rho/\partial t + \mathbf{\nabla} \cdot (\rho \mathbf{u}))=0$
come conseguenza della conservazione della massa, si ottiene la *forma
convettiva* dell'equazione dell'energia totale,

$$\begin{aligned}
   \rho \dfrac{\partial e^t}{\partial t}  +  \rho \mathbf{u}  \cdot  \mathbf{\nabla} e^t & = \mathbf{f} \cdot \mathbf{u} + \mathbf{\nabla} \cdot ( \mathbb{T} \cdot \mathbf{u} ) - \mathbf{\nabla} \cdot \mathbf{q} + \rho r \\ 
   \rho \dfrac{D e^t}{D t} & =  \mathbf{f} \cdot \mathbf{u} + \mathbf{\nabla} \cdot ( \mathbb{T} \cdot \mathbf{u} ) - \mathbf{\nabla} \cdot \mathbf{q} + \rho r  \ . \\ 
  \end{aligned}$$

Chiusura del problema
---------------------

Affinché il sistema di equazioni differenziali alle derivate parziali
formato dai bilanci di massa, quantità di moto ed energia totale, con le
condizioni iniziali e al contorno adeguate, sono necessarie l'equazione
di stato del materiale che ne descriva le proprietà termodinamiche[^1] e
i legami costitutivi che esprimano il tensore degli sforzi e il flusso
di calore come funzioni dello stato dinamico e termodinamico del
sistema. Per un fluido, il tensore degli sforzi viscosi $\mathbb{T}$ può
essere scritto come la somma del contributo idrostatico dovuto alla
pressione $p$ e il tensore degli sforzi viscosi $\mathbb{S}$, funzione
delle derivate spaziali del campo di velocità. Un fluido che ha un
*legame costitutivo lineare* tra il tensore degli sforzi viscosi e il
gradiente di velocità $\mathbf{\nabla} \mathbf{u}$, viene definito **fluido
newtoniano**. Per un fluido newtoniano isotropo, il legame costitutivo
che definisce il tensore degli sforzi è

$$\mathbb{T} = -p \mathbb{I} + 2 \mu \mathbb{D} + \lambda (\mathbf{\nabla} \cdot \mathbf{u}) \mathbb{I} \ ,$$

dove $\mu$ e $\lambda$ sono rispettivamente il coefficiente di viscosità
dinamica e il secondo coefficiente di viscosità, $p$ è la pressione
("termodinamica"), $\mathbb{D}$ il tensore velocità di deformazione. In
generale, sia la pressione $p$ sia i coefficienti di viscosità dipendono
dallo stato termodinamico del sistema. Il flusso di calore $\mathbf{q}$ per
conduzione può essere descritto dalla **legge di Fourier**, che lo mette
in relazione con il gradiente della temepratura tramite il coefficiente
di conduzione termica $k$, in generale funzione dello stato
termodinamico del sistema, 

$$\mathbf{q} = - k \mathbf{\nabla} T \ .$$

L'introduzione di queste leggi costitutive nelle equazioni di bilancio,
aggiunge nuove incognite al sistema, per le quali non abbiamo ricavato
un'equazione dinamica. Sono quindi indispensabili la legge di stato che
fornisca le relazioni necessarie,

$$\begin{aligned}
  p = p(\rho,e) \quad , & \quad \mu = \mu(\rho,e) \\
  T = T(\rho,e) \quad , & \quad \lambda = \lambda(\rho,e) \\
  & \quad k = k(\rho,e) \ ,
 \end{aligned}$$ 

 avendo scelto le variabili termodinamiche delle quali è
nota l'equazione dinamica come due variabili termodinamiche
indipendenti: la densità $\rho$ e l'energia interna $e$. Ve

Altre equazioni di bilancio
---------------------------

Combinando i bilanci delle quantità meccaniche ottenuti partendo dai
principi fondamentali della fisica, si possono ottenere le equazioni di
bilanci di altre quantità, come ad esempio l'energia cinetica
$\rho|\mathbf{u}|^2/2$, l'energia interna $e$, e la vorticità
$\mathbf{\omega} = \nabla \times \mathbf{u}$.

#### Equazione dell'energia cinetica

Moltiplicando scalarmente il bilancio della quantità di moto per il
vettore velocità $\mathbf{u}$, si può scrivere l'equazione di bilancio
dell'energia cinetica. In forma conservativa,

$$\dfrac{\partial}{\partial t}\dfrac{\rho|\mathbf{u}|^2}{2}  + \mathbf{\nabla} \cdot \left( \rho \mathbf{u} \dfrac{|\mathbf{u}|^2}{2} \right) = \mathbf{f} \cdot \mathbf{u} + \mathbf{u} \cdot ( \mathbf{\nabla} \cdot \mathbb{T} ) \ ,$$

in forma convettiva,

$$\begin{aligned}
   \rho \dfrac{\partial}{\partial t} \dfrac{|\mathbf{u}|^2}{2} +  \rho \mathbf{u}  \cdot \mathbf{\nabla} \dfrac{|\mathbf{u}|^2}{2} & = \mathbf{f} \cdot \mathbf{u} + \mathbf{u} \cdot (\mathbf{\nabla} \cdot \mathbb{T} ) \\ 
   \rho \dfrac{D }{D t}\dfrac{|\mathbf{u}|^2}{2} & = \mathbf{f}\cdot \mathbf{u} + \mathbf{u} \cdot ( \mathbf{\nabla} \cdot \mathbb{T} ) \ . \\ 
  \end{aligned}$$

#### Equazione dell'energia interna

Dalla differenza del bilancio dell'energia totale e dell'energia
cinetica, si ottiene il bilancio dell'energia interna. In forma
conservativa,

$$\dfrac{\partial (\rho e)}{\partial t} + \mathbf{\nabla} \cdot (\rho e \mathbf{u}) = \mathbb{T}:\mathbf{\nabla}\mathbf{u} - \mathbf{\nabla} \cdot \mathbf{q} + \rho r \ ,$$

in forma convettiva,

$$\begin{aligned}
   \rho \dfrac{\partial e}{\partial t} +  \rho \mathbf{u}  \cdot \mathbf{\nabla}e & =  \mathbb{T}:\mathbf{\nabla}\mathbf{u} - \mathbf{\nabla} \cdot \mathbf{q} + \rho r \\
   \rho \dfrac{D e}{D t} & =  \mathbb{T}:\mathbf{\nabla}\mathbf{u} - \mathbf{\nabla} \cdot \mathbf{q} + \rho r \ . \\ 
  \end{aligned}$$

#### Equazione della vorticità

Applicando l'operatore di rotore al bilancio della quantità di moto, si
ottiene l'equazione dinamica della vorticità. Per un fluido newtoniano
(con coefficienti di viscosità costanti e uniformi),

$$\begin{aligned}
 \dfrac{\partial \mathbf{\omega}}{\partial t} + (\mathbf{u} \cdot \mathbf{\nabla} ) \mathbf{\omega} & =
  (\mathbf{\omega} \cdot \mathbf{\nabla}) \mathbf{u} - \mathbf{\omega} (\mathbf{\nabla} \cdot \mathbf{u}) +
  \nu \Delta \mathbf{\omega} + \dfrac{\mathbf{\nabla} \rho \times \mathbf{\nabla} p}{\rho^2} \\
   \dfrac{D \mathbf{\omega}}{D t}  & =
  (\mathbf{\omega} \cdot \mathbf{\nabla}) \mathbf{u} - \mathbf{\omega} (\mathbf{\nabla} \cdot \mathbf{u}) +
  \nu \Delta \mathbf{\omega} + \dfrac{\mathbf{\nabla} \rho \times \mathbf{\nabla} p}{\rho^2} \ ,
 \end{aligned}$$

dove è stata introdotta la viscosità cinematica del fluido,
$\nu = \mu / \rho$.

#### Equazione dell'entropia

Nell'ipotesi di equilibrio termodinamico delle singole particelle
materiali[^2] si può ricavare dal primo principio della termodinamica,
$$de = T ds - P dv = T ds + \dfrac{p}{\rho^2} d\rho \ ,$$ l'equazione di
bilancio dell'entropia in forma convettiva,

$$T \dfrac{D s}{D t} = \dfrac{D e}{D t} - \dfrac{p}{\rho^2} \dfrac{D \rho}{D t} \qquad \rightarrow \qquad
 \rho \dfrac{D s}{D t} = \dfrac{1}{T} \left( \rho \dfrac{D e}{D t} -  \dfrac{p}{\rho} \dfrac{D \rho}{D t} \right) \ .$$

Utilizzando il bilancio dell'energia interna e il bilancio di massa, si
può scrivere

$$\rho \dfrac{D s}{D t} = \dfrac{1}{T} \left( \mathbb{T} : \mathbf{\nabla} \mathbf{u} - \mathbf{\nabla} \cdot \mathbf{q} + \rho r + p \mathbf{\nabla} \cdot \mathbf{u} \right) \ ,$$

e separando i contributi viscosi da quelli di presisone nel tensore
degli sforzi, $\mathbb{T} = - p \mathbb{I} + \mathbb{S}$,[^3]

$$\rho \dfrac{D s}{D t} = \dfrac{1}{T} \left( \mathbb{S} : \mathbf{\nabla} \mathbf{u} - \mathbf{\nabla} \cdot \mathbf{q} + \rho r \right) \ .$$

Nel caso di fluidi newtoniani,
$\mathbb{S} = 2\mu\mathbb{D} + \lambda\mathbf{\nabla} \cdot \mathbf{u} \mathbb{I}$,
l'equazione dell'entropia in forma differenziale convettiva diventa

$$\rho \dfrac{D s}{D t} = \dfrac{1}{T} \left( 2 \mu \mathbb{D} : \mathbb{D} + \lambda |\mathbf{\nabla} \cdot \mathbf{u}|^2 - \mathbf{\nabla} \cdot \mathbf{q} + \rho r \right) \ .$$

Utilizzando la legge di Fourier, $\mathbf{q} = -k \mathbf{\nabla} T$, per il
flusso di calore per conduzione, si può riscrivere il termine di
divergenza del flusso di calore,

$$\dfrac{1}{T} \mathbf{\nabla} \cdot \mathbf{q} =
  \mathbf{\nabla} \cdot \left( \dfrac{\mathbf{q}}{T} \right) + \mathbf{q} \cdot \dfrac{\mathbf{\nabla} T}{T^2} =
  \mathbf{\nabla} \cdot \left( \dfrac{\mathbf{q}}{T} \right) - k \mathbf{\nabla}{T} \cdot \dfrac{\mathbf{\nabla} T}{T^2} =
  \mathbf{\nabla} \cdot \left( \dfrac{\mathbf{q}}{T} \right) - k \dfrac{|\mathbf{\nabla} T|^2}{T^2} \ ,$$

e quindi riscrivere l'equazione dell'entropia, in forma conservativa e
convettiva,

$$\begin{aligned}
 \dfrac{\partial (\rho s)}{\partial t} + \mathbf{\nabla} \cdot (\rho s \mathbf{u} ) & = \dfrac{1}{T} \left( 2 \mu \mathbb{D} : \mathbb{D} + \lambda |\mathbf{\nabla} \cdot \mathbf{u}|^2 \right) + k \dfrac{|\mathbf{\nabla}T|^2}{T^2} - \mathbf{\nabla} \cdot \left( \dfrac{\mathbf{q}}{T} \right) + \dfrac{\rho r}{T} \\
 \rho \dfrac{D s}{D t} & = \dfrac{1}{T} \left( 2 \mu \mathbb{D} : \mathbb{D} + \lambda |\mathbf{\nabla} \cdot \mathbf{u}|^2 \right) + k \dfrac{|\mathbf{\nabla}T|^2}{T^2} - \mathbf{\nabla} \cdot \left( \dfrac{\mathbf{q}}{T} \right) + \dfrac{\rho r}{T}  \ .
\end{aligned}$$

In questa equazione si riconoscono tutti i fenomeni fisici che
influenzano l'entropia di una particella materiale. Si possono
distinguere i contributi dovuti alla *non idealità* del fluido
considerato, legati ai fenomeni viscosi e di conduzione del calore, e i
contributi dovuti ai flussi di calore forniti alla sistema. I fenomeni
viscosi e i processi di conduzione del calore fanno aumentare
l'entropia, poiché 

$$T, \, \mu, \, \lambda, \, k \, \geq 0
 \qquad \text{e} \qquad
 \mathbb{D}:\mathbb{D}, \, |\mathbf{\nabla} \cdot \mathbf{u}|, \, |\mathbf{\nabla} T| \, \geq 0 \ .$$

Gli ultimi due termini rappresentano i flussi di calore forniti al
sistema e si presentano nella forma $Q/T$, flusso di calore diviso la
temperatura della particella, coerentemente con la definizione
dell'entropia in Termodinamica, 

$$dS = \dfrac{\delta Q}{T} \ .$$

Questi
due termini possono dare un contributo positivo o nevativo, a seconda
del segno della sorgente di calore $r$ e del flusso di valore $\mathbf{q}$.
Il bilancio dell'entropia in forma integrale per un volume materiale,

$$\dfrac{d}{dt}\int_{V(t)} \rho s = \int_{V(t)} \dfrac{1}{T} \left( 2 \mu \mathbb{D} : \mathbb{D} + \lambda |\mathbf{\nabla} \cdot \mathbf{u}|^2 + k \dfrac{|\mathbf{\nabla}T|^2}{T} \right)
 - \oint_{\partial V(t)} \dfrac{\mathbf{q}}{T} \cdot \mathbf{\hat{n}} + \int_{V(t)} \dfrac{\rho r}{T} \ ,$$

permette di interpretare il interpretare il ruolo dei fenomeni non
ideali (viscosità e conduzione del calore) come sorgente di volume
sempre positiva dell'entropia, riconoscrere il ruolo della sorgente (o
pozzo) di entropia di intensità per unità di massa $r/T$ svolto da una
sorgente di calore per unità di massa $r$, e il ruolo di flusso di
entropia $\mathbf{q}/T$ attraverso il contorno del volume $V(t)$ svolto da
un flusso di calore $\mathbf{q}$.

(fluid-mechanics:balance:jump)=
## Relazioni di salto
...

[^1]: Si ricorda che lo stato termodinamico di un sistema monofase è
    definito da due variabili termodinamiche indipendenti.

[^2]: Se i tempi caratteristici della termodinamica sono di gran lunga
    inferiori al tempo caratteristico del fenomeno fluidodinamico, si
    può immaginare che la singola particella fluida sia in continuo
    stato di equilibrio termodinamico locale. Si possono quindi
    estendere i risultati della Termodinamica, che in generale studia
    sistemi in equilibrio, alla singola particella fluida.

[^3]: Dovrebbe essere facile dimostrare che
    $\mathbb{I}:\mathbf{\nabla}\mathbf{u} = \mathbf{\nabla} \cdot \mathbf{u}$.
