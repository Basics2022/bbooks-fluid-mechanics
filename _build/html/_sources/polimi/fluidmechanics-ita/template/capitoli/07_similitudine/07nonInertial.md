### Equazioni di Navier--Stokes

In un sistema di riferimento inerziale[^1] le equazioni di
Navier--Stokes governano la dinamica di una corrente incomprimibile di
un fluido a proprietà costanti $$\begin{cases}
 \rho \Dt{\vel} = \rho \g - \grad p + \mu \lapl \vel \\
 \dive \vel = 0 \ ,
\end{cases}$$ dove l'operatore di derivata materiale applicata al campo
di velocità coincide con il campo di accelerazione delle particelle,
$$\acc = \Dt{\vel} = \pt{\vel} + ( \vel \cdot \grad ) \vel \ .$$

### Cinematica relativa

Sia dato un sistema di riferimento ortonormale inerziale $I$ e un
sistema di riferimento non inerziale $J$, con origine $O_I$ e $O_J$
rispettivamente. La velocità e l'accelerazione di $O_J$ definite nel
sistema di riferimento inerziale sono $\vel_{O_J}$, $\acc_{O_J}$, mentre
vengono indicate con $\bm{\Omega}_{J/I}$ e $\bm{\alpha}_{J/I}$ la
velocità e l'accelerazione angolare del sistema di riferimento $J$
rispetto al sistema $I$. Si può esprimere la posizione di un punto $P$
nel sistema di riferimento $I$ come $$\label{eqn:rel:pos}
 \pos = \pos_{O_J} + \pos^J \ ,$$ avendo indicato ... Dalla derivata
temporale della posizione di $P$, si ottiene la velocità
$$\label{eqn:rel:vel}
 \vel = \vel_{O_J} + \vel^J + \bm{\Omega}_{J/I} \times \pos^J \ ,$$
avendo indicato ... Dalla derivata temporale della velocità di $P$, si
ottiene l'accelerazione $$\label{eqn:rel:acc}
 \acc = \acc_{O_J} + \acc^J + \bm{\alpha}_{J/I} \times \pos^J + 2~\bm{\Omega}_{J/I} \times \vel^J + 
   \bm{\Omega}_{J/I} \times \left( \bm{\Omega}_{J/I} \times \pos^J \right) \ ,$$
avendo indicato ...

### Equazioni di Navier--Stokes in un sistema di riferimento non inerziale

Si possono quindi riscrivere le equazioni di Navier--Stokes, utilizzando
le grandezze cinematiche riferite al sistema di riferimento non
inerziale, mettendo in evidenza i contributi non inerziali e lasciando
cadere i pedici $_{J/I}$ della velocità e dell'accelerazione angolare
$$\begin{cases}
\begin{aligned}
 \rho \acc^J = &  \rho \g - \grad p + \mu \lapl \vel + \\
               & - \rho \left[
   \acc_{O_J} + \bm{\alpha} \times \pos^J + 2~\bm{\Omega} \times \vel^J + 
   \bm{\Omega} \times \left( \bm{\Omega} \times \pos^J \right) 
             \right] \ ,
\end{aligned} \\
\dive \vel = 0 \ .
\end{cases}$$ In questa espressione delle equazioni compare ancora la
velocità $\vel$ riferita al sistema di riferimento inerziale, nel
contributo viscoso della quantità di moto e nel vincolo di
incomprimibilità. Per riportartci a un'espressione delle equazioni di
Navier--Stokes dove compaiano solo grandezze cinematiche riferite al
sistema non inerziale, utilizziamo le formule
([\[eqn:rel:pos\]](#eqn:rel:pos){reference-type="ref"
reference="eqn:rel:pos"},
[\[eqn:rel:vel\]](#eqn:rel:vel){reference-type="ref"
reference="eqn:rel:vel"}) nel laplaciano e nella divergenza di $\vel$,
ricordando che la velocità $\vel_{O_J}(t)$ dell'origine e la velocità
angolare $\bm{\Omega}(t)$ del sistema non inerziale sono solo funzioni
del tempo che non dipendono dallo spazio, e che quindi le loro derivate
spaziali sono nulle. La divergenza della velocità diventa quindi
$$\begin{aligned}
 \dive \vel & = \dive \left( \vel_{O_J} + \vel^J + \bm{\Omega} \times \pos^J \right) \\
            & = \dive \left( \vel^J + \bm{\Omega} \times ( \pos - \pos_{O_J} ) \right) \\
\end{aligned}$$ Il termine
$\dive \left( \bm{\Omega} \times \pos_{O_J} \right)$ è nullo poiché il
contenuto della parentesi non dipende dallo spazio, ma solo dal tempo.
Anche il termine $\dive \left( \bm{\Omega} \times \pos \right)$ risulta
nullo, come si può dimostrare facilmente utilizzando un sistema di
coordinate ortogonali e i simboli di Ricci per esprimere il prodotto
vettoriale,[^2] $$\dive \left( \bm{\Omega} \times \pos \right) =
  \partial_i \left( \epsilon_{ijk} \Omega_j r_k \right) =
  \epsilon_{ijk} \Omega_j \partial_i r_k =
  \epsilon_{ijk} \Omega_j \delta_{ik} = 
  \epsilon_{iji} \Omega_j = 0 \ ,$$ poiché i simboli di Ricci con indici
ripetuti sono identicamente nulli. Di conseguenza, la divergenza del
campo di velocità $\vel^J$ riferito al sistema di riferimento non
inerziale è uguale alla divergenza del campo di velocità $\vel$ riferito
al sistema di riferimento inerziale, $$\dive \vel = \dive \vel^J \ .$$
Non dovrebbe essere difficile trovare l'espressione del laplaciano, una
volta osservato il grado della dipendenza dallo spazio nell'espressione
([\[eqn:rel:pos\]](#eqn:rel:pos){reference-type="ref"
reference="eqn:rel:pos"}): il termine $\vel_{O_J}$ non dipende dallo
spazio, mentre il termine
$\bm{\Omega} \times \pos^J = \bm{\Omega} \times ( \pos - \pos_{O_J} )$
ha una dipendenza *affine* (e non *lineare*, poiché c'è un termine
costante) dalla posizione nello spazio. Ricordandosi che il laplaciano è
la somma delle derivate spaziali del secondo ordine (in un sistema di
coordinate cartesiane), dovrebbe essere chiaro che il laplaciano di
questi due termini è nullo e che quindi vale, $$\begin{aligned}
 \lapl \vel & = \lapl \left( \vel_{O_J} + \vel^J + \bm{\Omega} \times \pos^J \right) = \\
            & = \lapl \left( \vel_{O_J} + \vel^J + \bm{\Omega} \times ( \pos - \pos_{O_J} ) \right) = \lapl \vel^J
\end{aligned}$$ Utilizzando le due relazioni ottenute per la divergenza
e il laplaciano del campo di velocità, si può ora riscrivere le
equazioni di Navier--Stokes riferite a un sistema di riferimento non
inerziale, utilizzando unicamente le grandezze cinematiche relative a
questo sistema di riferimento, $$\begin{cases}
\begin{aligned}
 \rho \acc^J = &  \rho \g - \grad p + \mu \lapl \vel^J + \\
               & - \rho \left[
   \acc_{O_J} + \bm{\alpha} \times \pos^J + 2~\bm{\Omega} \times \vel^J + 
   \bm{\Omega} \times \left( \bm{\Omega} \times \pos^J \right) 
             \right] \ ,
\end{aligned} \\
\dive \vel^J = 0 \ .
\end{cases}$$

### Alcune osservazioni sulla natura tensoriale delle equazioni

Tranne le grandezze cinematiche che descrivono il moto del sistema di
riferimento non inerziale e le grandezze cinematiche che descrivono il
moto del fluido relativo a questo sistema di riferimento, tutti gli
oggetti che compaiono nelle equazioni vettoriali sono indipendenti dal
sistema di riferimento utilizzato per descrivere il problema. In una
notazione vettoriale ha quindi poco senso indicare in maniera diversa
questi termini, a partire dagli operatori differenziali.

TODO: Relazione tra le coordinate e tra i vettori delle basi ortogonali

TODO: Variabili indipendenti delle funzioni

TODO: Calcolo in componenti del gradiente e del laplaciano "espressi nel
sistema di riferimento non inerziale"

Equazioni in forma adimensionale
--------------------------------

Si ricava ora la forma adimensionale delle equazioni, in un sistema di
riferimento con origine fissa, $\vel_{O_J}=\bm{0}, \acc_{O_J} = \bm{0}$,
e in rotazione con velocità angolare costante, $\bm{\alpha} = \bm{0}$,
$$\begin{cases}
\begin{aligned}
 \rho \acc^J = \rho \g - \grad p + \mu \lapl \vel^J 
  - 2~\rho \bm{\Omega} \times \vel^J
  - \rho \bm{\Omega} \times \left( \bm{\Omega} \times \pos^J \right)
\end{aligned} \\
\dive \vel^J = 0 \ .
\end{cases}$$ Lasciamo cadere l'apice $^J$ su tute le grandezze
cinematiche relative al sistema di riferimento non inerziale.
Aggiungendo il modulo $\Omega$ della velocità angolare del sistema di
riferimento, $\bm{\Omega} = \Omega \bm{\hat{\Omega}}$, alle grandezze di
riferimento $( \tilde{\rho}, \, \tilde{U}, \, \tilde{L} )$, usate per
creare anche le scale *non indipendenti* di tempo
$\tilde{T} = \tilde{L}/\tilde{U}$, di accelerazione
$\tilde{A} = \tilde{U}^2 / \tilde{L}$ e di pressione
$\tilde{p} = \tilde{\rho}\, \tilde{U}^2$, si può scrivere
$$\f{\rho \tilde{U}^2}{\tilde{L}} \acc^* = \rho g \bm{\hat{g}}
   - \f{\tilde{\rho}\tilde{U}^2}{\tilde{L}} \grad^* p^*
   + \f{\mu \tilde{U}}{\tilde{L}^2} \Delta^* \bm{u}^*
   - 2 \rho \Omega \tilde{U} \bm{\hat{\Omega}} \times \bm{u}^*
   +   \rho \Omega^2 \tilde{L} \bm{\hat{\Omega}} \times \left( \bm{\hat{\Omega}} \times \bm{r}^* \right) \ ,$$
e, dividendo tutti i termini per $\rho \tilde{U}^2/\tilde{L}$,
$$\acc^* = \f{g \tilde{L}}{\tilde{U}^2} \bm{\hat{g}}
   -  \grad^* p^*
   + \f{\mu }{\rho \tilde{U} \tilde{L}} \Delta^* \bm{u}^*
   - 2 \f{\Omega \tilde{L}}{\tilde{U}} \bm{\hat{\Omega}} \times \bm{u}^*
   +   \f{\Omega^2 \tilde{L}^2}{\tilde{U}^2} \bm{\hat{\Omega}} \times \left( \bm{\hat{\Omega}} \times \bm{r}^* \right) \ ,$$
si possono riconoscere i numeri adimensionali caratteristici del
problema,

-   il numero di Reynolds $Re = \frac{\rho \tilde{U} \tilde{L}}{\mu}$,
    che rappresenta il rapporto tra gli effetti inerziali e gli effetti
    viscosi;

-   il numero di Froude, $Fr = \frac{\tilde{U}^2}{g \tilde{L}}$, che
    rappresenta il rapporto tra gli effetti inerziali e quelli legati al
    campo di forze di volume (ad esempio, gli effetti gravitazionali ss
    $\bm{g}$ è il campo di forze gravitazionale);

-   il numero di Rossby, $Ro = \frac{\tilde{U}}{\Omega \tilde{L}}$
    rappresenta il rapporto tra gli effetti inerziali e gli effetti "di
    trascinamento" dovuti al moto del sistema di riferimento non
    inerziale;

e riscrivere le equazioni in forma adimensionale, $$\begin{cases}
 \acc^* = \f{1}{Fr} \bm{\hat{g}}
   -  \grad^* p^*
   + \f{1}{Re} \Delta^* \bm{u}^*
   - \f{2}{Ro} \bm{\hat{\Omega}} \times \bm{u}^*
   + \f{1}{Ro^2} \bm{\hat{\Omega}} \times \left( \bm{\hat{\Omega}} \times \bm{r}^* \right) \\ \\
 \dive \vel^* = 0 \ .
\end{cases}$$

TODO. Utilizzando il valore della velocità angolare della Terra,
$\Omega_T = 7.27 \cdot 10^{-5} s^{-1}$, è possibile valutare gli effetti
di Coriolis sul moto di una corrente e riconoscere la scala di tempo
$\tilde{L}/\tilde{U} \sim 1/\Omega$ dei fenomeni fisici per i quali gli
effetti di Coriolis sono rilevanti.[^3]

[^1]: Per noi, un **sistema di riferimento inerziale** è un sistema di
    riferimento rispetto al quale le equazioni della fisica assumono la
    loro forma più semplice, senza che compaiano termini di
    trascinamento, come ad esempio i termini di Coriolis.

[^2]: Chi non ci crede, o non è familiare con i simboli di Ricci, può
    calcolare il prodotto vettoriale $\bm{\Omega} \times \pos$
    utilizzando un sistema cartesiano $$\bm{\Omega} \times \pos = 
         \left( \Omega_y \, z - \Omega_z \, y \right) \bm{\hat{x}} +
         \left( \Omega_z \, x - \Omega_x \, z \right) \bm{\hat{y}} +
         \left( \Omega_x \, y - \Omega_y \, x \right) \bm{\hat{z}} \ ,$$
    e verificare immediatamente che
    $\dive (\bm{\Omega} \times \pos) = 0$, poichè nessuna componente del
    vettore dipende dalla coordinata spaziale corrispondente.

[^3]: La scala dei tempi deve essere circa uguale all'inverso della
    velocità angolare del sistema non inerziale,
    $\tilde{L}/\tilde{U} \sim 1/\Omega$, affinché il numero di $Rossby$
    sia circa uguale a $1$ e che quindi i termini di "trascinamento"
    siano dello stesso ordine dei termini di pressione. Se il numero di
    Rossby è molto maggiore di $1$ gli effetti non inerziali saranno
    irrilevanti, mentre se il numero di Rossby è molto minore di $1$, il
    problema sarà dominato da tali effetti.
