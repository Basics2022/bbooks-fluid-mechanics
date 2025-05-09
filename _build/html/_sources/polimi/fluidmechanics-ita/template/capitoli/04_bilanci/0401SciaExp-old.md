Attività sperimentali: difetto di scia e volume di controllo.
-------------------------------------------------------------

L'esercizio svolto in precedenza risulta propedeutico ad alcune attività
sperimentali che svolgerete durante il corso di studi o in attività
sperimentali future. Le attività svolte nel mondo reale sono affette da
imprecisioni e incertezze; i *datasheet* che accompagnano uno strumento
raccolgono anche le informazioni sulla sua incertezza di misura, spesso
in forma di intervallo di confidenza di probabilità nota o di scarto
quadratico medio. Le grandezze misurate permettono poi di calcolare
delle grandezze derivate. L'incertezza di misura dei singoli strumenti
si propaga sulla grandezza derivata: nell'ipotesi che le incertezze
siano tra di loro indipendenti e non correlate, è possibile utilizzare
la formula RSS (*root-sum-squares*). Se la grandezza derivata $f$ è
funzione delle $N$ grandezze misurate $x_i$, sulle quali si ha
incertezza $\sigma_{x_i}$, è possibile stimare l'incertezza su $f$
$$\sigma_f^2 = \sum_{i=1}^{N} \left( \dfrac{\partial f}{\partial x_i} \right)^2 \sigma_{x_i}^2$$

L'incertezza $\sigma_f$ è parte integrante del risultato di una attività
sperimentale e un indicatore della bontà dell'apparato sperimentale
pensato per tale attività. In generale, l'incertezza sulla grandezza
desiderata deve essere "molto minore" della grandezza stessa: in caso
contrario, l'apparato sperimentale risulterebbe indatto all'attività da
svolgere. Essendo parte integrante del risultato, è buona regola
indicare l'incertezza sulla grandezza misurata, ad esempio indicandone
il valore numerico, il valore relativo alla misura, gli intervalli di
confidenza sui grafici...

#### Difetto di scia e resistenza del profilo.

É possibile stimare la resistenza di un profilo a partire dalla misura
del difetto di scia. La misura di velocità in scia viene effettuata (con
una sonda di Pitot o altro ...) in punti discreti, più radi lontano
dalla scia del profilo, fiù fitti in corrispondenza della scia dove i
gradienti sono maggiori. L'integrale nella formula
([\[eqn:difetto\_scia\]](#eqn:difetto_scia){reference-type="ref"
reference="eqn:difetto_scia"}) viene approssimato con un metodo
numerico, come ad esempio la formula del punto medio, quella del
trapezio, ... Utilizzando qui per semplicità la formula del punto medio,
è possibile scrivere $$F_x = \int_{0}^{H} \rho u(y) (U_\infty - u(y)) dy
    \approx \sum_{k=1}^{N} \rho \left[ u_k (U_\infty - u_k) \right] \Delta s_k$$
Le misure ottenute dalla sonda sono affette da incertezza
$\sigma_{u_i}$; la derivata $\partial F_x / \partial u_i$ è
$$\dfrac{\partial F_x}{\partial u_m}  = \rho \left( U_\infty - 2 u_m \right) \Delta s_m$$
La stima dell'incertezza sulla resistenza è quindi
$$\sigma_{F_x}^2 = \sum_{i=1}^{N} \left[ \rho \left( U_\infty - 2 u_i \right) \Delta s_i \right]^2 \sigma_{u_i}^2$$

#### Volume di controllo.

Esistono metodi sperimentali (es. PIV) che permettono di ottenere il
campo di velocità in un determinato istante su una griglia di punti. Si
pensi al campo di moto attorno a un'ala allungata, a bassi angoli di
incidenza. Se il campo di moto è bidimensionale (in buona
approssimazione) è possibile utilizzare tecniche sperimentali
bidimensionali (PIV-2D) per misurare il campo di velocità su un piano: è
possibile ottenere una stima delle azioni (per unità di apertura) che
esercita il fluido sul profilo di ala tagliato dal piano di misura,
tramite l'equazione di bilancio di quantità di moto in
([\[eqn:airfoil\_bil\_int\]](#eqn:airfoil_bil_int){reference-type="ref"
reference="eqn:airfoil_bil_int"}).

*(In questa formula compare solo il termine di flusso di quantità di
moto, mentre non è presente il termine di sforzi di superficie
$\oint_S \bm{t}_n$, che include il contributo della pressione, **non**
sempre trascurabile.)*

Seguendo il procedimento svolto nel pragrafo precedente applicato
all'integrale di superficie, è possibile stimare l'incertezza sulla
resistenza e sulla portanza ottenute tramite questo metodo. Si scopre
che l'incertezza sulla misura dipende dalla risoluzione della griglia e
dalle condizioni di prova. Come indicazione generale, l'incertezza su
portanza e resistenza sono dello stesso ordine di grandezza, e possono
raggiungere fino al $30\%$ della misura della resistenza. In molte
applicazioni la portanza è maggiore della resistenza: in una prova ad
efficienza del profilo $E=10$, si ottiene un $3\%$ di incertezza sulla
portanza. In questo caso, questo metodo risulta accettabile per una
stima della portanza, non per la resistenza.
