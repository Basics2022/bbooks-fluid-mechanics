Stabilità idrodinamica
======================

In questa sezione viene data una breve introduzione allo studio della
stabilità idrodinamica, viene accennato alla possibile inadeguatezza
dell'analisi modale e viene introdotta l'analisi lineare non modale, in
grado di spiegare la dinamica di alcune correnti che non viene colta
dall'analisi modale. La stabilità idrodinamica si occupa delle prime
instabilità delle correnti laminari, di solito descritte con l'approccio
deterministico della teoria dei sistemi dinamici. Le equazioni di
Navier--Stokes dotate delle appropriate condizioni iniziali, condizioni
al contorno (ed eventualmente condizioni di compatibilità) descrivono il
moto di una corrente incomprimibile di un fluido newtoniano. Nella forma
adimensionale delle equazioni, $$\begin{cases}
  \dfrac{\partial \bm{u}}{\partial t} + (\bm{u} \cdot \bm{\nabla} ) \bm{u}
  -\dfrac{1}{Re} \nabla^2 \bm{u} + \bm{\nabla} p = \bm{0} \ , \\
  \bm{\nabla} \cdot \bm{u} = 0 \ ,
 \end{cases}$$ il numero di Reynolds $Re$ è un parametro che rappresenta
il rapporto tra la "scala" degli effetti inerziali e quella degli
effetti viscosi. Fin dai primi studi di Reynolds (1883) sulla
transizione al regime turbolento nelle correnti in canali, questo numero
adimensionale è stato riconosciuto come il principale parametro che
determina il regime della corrente, laminare o turbolento. La turbolenza
è frequentemente considerata come l'ultimo problema non risolto della
meccanica classica, e solo recentemente sono stati spiegati alcuni
fenomeni riguardanti la stabilità idrodinamica. L'approccio tradizionale
all'analisi di stabilità dei sistemi dinamici consiste nella ricerca dei
punti di equilibrio, ossia le soluzioni stazionarie del sistema, e nella
soluzione del problema agli autovalori del sistema linearizzato attorno
all'equilibrio. L'approccio modale, "alla Lyapunov", permette di
ottenere alcune informazioni locali sulla stabilità di un equilibrio in
seguito a condizioni iniziali perturbate. É noto che l'analisi modale
delle correnti stazionarie, che rappresentano equilibri delle equazioni
di Navier--Stokes, riesce a descrivere il comportamento di alcune
correnti, come ad esempio la convezione di Rayliegh--Benard, la corrente
di Taylor--Couette tra due cilindri coassiali rotanti o la scia di Von
Kármán dietro un cilindro, mentre non è in grado di descrivere le
osservazioni sperimentali di altre correnti, come la corrente di
Newton--Couette e la corrente di Poiseuille, sia in canali piani sia in
canali cilindrici, e alcune correnti a getto.

Fallimento dell'analisi modale: correnti amplificatrici di disturbi
-------------------------------------------------------------------

Per le *correnti aperte*, per le quali le particelle fluide rimangono
nel dominio euleriano considerato in un intervallo di tempo finito,
vengono definiti i concetti di *instabilità assoluta* e *instabilità
convettiva*. Queste definizioni sono legate alla risposta impulsiva del
sistema e determinano la classificazione storica delle correnti aperte
in **oscillatori fluidodinamici** e **correnti amplificatrici del
rumore**: gli oscillatori fluidodinamici mostrano una dinamica
oscillatoria intrinseca (auto-sostenuta) a una precisa frequenza e sono
poco influenzate da disturbi esterni; nelle correnti amplificatrici del
rumore, invece, disturbi con un ampio spettro di frequenze mostrano
un'enorme amplificazione mentre vengono trasportate lungo il dominio.
Per spiegare il fallimento dell'analisi modale, alcuni studiosi si sono
concentrati sull'inadeguatezza dello studio di stabilità del sistema
linearizzato e hanno incluso alcuni termini non lineari per lo studio di
stabilità dei sistemi con la cosiddetta *teoria dell'instabilità
secondaria*. Comunque, è emerso che la principale ragione della
discrepanza tra i risultati dell'analisi modale e le osservazioni
sperimentali riguardanti correnti amplificatrici di rumore, dominate
dalla convezione, è dovuta alla **non-normalità** del sistema
linearizzato di Navier--Stokes. In particolare, il termine convettivo
rende il problema linearizzato di Navier--Stokes non-normale, cioè
descritto da un operatore linearizzato (l'equivalente della matrice
jacobiana) non simmetrico, che in generale ha modi (autofunzioni,
autovettori) non ortogonali. I sistemi non-normali hanno una dinamica
lineare attorno a un equilibrio stabile più complicata rispetto alla
dinamica dei sistemi lineari normali, caratterizzati da autovettori
ortogonali. I sistemi non-normali possono ad esempio mostrare il
fenomeno del **crescita transitoria**: partendo nelle vicinanze di un
equilibrio stabile, lo stato del sistema può momentaneamente
allontanarsi dall'equilibrio (ad esempio, misurando la distanza con una
norma energetica) per poi tendere asintoticamente ad esso. Quando sono
forzati, i sistemi non-normali possono mostrare una **pseudorisonanza**,
una grande amplificazione di disturbi con frequenza lontana da quella
del autovalore meno stabile, e una grande amplificazione di disturbi
stocastici. A causa della loro natura non-normale, sia la risposta
deterministica sia la risposta stocastica delle correnti amplificatrici
di rumore attorno a equilibri stabili sono state studiate con analisi di
risposta lineari non-modali, sia nel dominio del tempo sia nel dominio
della frequenza. L'analisi della risposta di questi sistemi viene
affrontato come un problema di ottimizzazione: nel dominio del tempo,
tecniche classiche di algebra lineare vegono usare insieme a
un'integrazione "avanti e indietro" nel tempo per risolvere il problema
di ottimizzazione e ricavare la condizione iniziale ottimale, cioè
quella associata alla massima crescita transitoria; nel dominio delle
frequenze, tecniche basate su una decomposizione ai valori singolari
(SVD) della trasformata di Fourier del *resolvent operator*[^1] per
determinare la perturbazione armonica maggiormente amplificata dal
sistema e la sua amplificazione; la risposta stocastica del sistema può
infine essere determinata dalla risposta armonica del sistema in tutto
lo spettro di frequenze.

#### Approccio variazionale e metodi dell'aggiunto

#### Analisi di sensitività

#### Tecniche di controllo

Sistemi dipendenti da un parametro e stabilità strutturale
----------------------------------------------------------

Spesso la dinamica di un sistema è influenzata dal valore di alcuni suoi
parametri caratteristici. Ad esempio la dinamica di una corrente
incomprimibile di un fluido viscoso nuewtoniano dipende dal numero di
Reynolds $Re$, come facilmente intuibile dalla forma adimensionale delle
equazioni di Navier--Stokes. Tipicamente, il numero di Reynolds
determina il regime di moto della corrente: qualitativamente, in alcune
correnti quando il numero di Reynolds supera un valore critico la
soluzione laminare stabile lascia spazio a un regime caotico,
turbolento. Lo studio della stabilità di un sistema dipendente dal
valore di uno o più parametri è l'ogetto della **teoria delle
biforcazioni**, che si occupa di studiare i cambiamenti qualitativi
della dinamica di un sistema al variare dei suoi parametri. Di seguito,
viene fornito lo studio di stabilità del sistema di Lorenz in funzione
del valore di un suo parametro, come primo esempio di studio di
stabilità di un sistema fluidodinamico ridotto: infatti il sistema
tridimensionale di Lorenz può essere ricavato da un'approssimazione di
Galerkin con base armonica della soluzione delle equazioni di Boussinesq
per il problema della convezione di un fluido tra due superfici
parallele. La stabilità del sistema viene studiata al variare di un
parametro che è proporzionale al numero di Rayliegh $Ra$ caratteristico
del problema,
$$\rho \sim Ra = \dfrac{\alpha g \Delta T h^3}{\nu D} \ .$$

Prima di indagare il sistema di Lorenz vengono introdotti alcuni
concetti utili per studiare la stabilità di un generico sistema
dinamico,
$$\dfrac{d \bm{x}}{d t } = \bm{f}(\bm{x}(t),t) \qquad , \qquad \bm{x}(0) = \bm{x}_0 \ .$$
Alcuni di questi concetti non sono nuovi; tutte queste definizioni
verranno usate (e risulteranno più chiare) nella sezione successiva
dedicata al sistema di Lorenz.

**Spazio delle fasi e stati di un sistema.** Lo spazio delle fasi è uno
spazio nel quale i punti rappresentano i possibili stati del sistema. Lo
stato di un sistema dinamico è identificato dal valore delle sue
variabili di stato, ovvero le variabili che lo descrivono in maniera
esaustiva da poterne prevederne l'evoluzione.[^2] L'evoluzione libera di
un sistema dinamico viene descritta dalle traiettorie nel suo spazio
delle fasi.

**Equilibri e cicli limite.** Un equilibrio $\overline{\bm{x}}$ del
sistema è una soluzione stazionaria delle equazioni del sistema
dinamico, cioè $$\bm{0} = \bm{f}(\overline{\bm{x}}) \ .$$ Un ciclo
limite di periodo $T$ è una traiettoria periodica del sistema, tale per
cui $$\bm{x}(t+T) = \bm{x}(t) \quad , \quad \forall t \ ,$$
rappresentata nello spazio delle fasi da un'orbita chiusa (e isolata).

**Stabilità alla Lyapunov.** Lo studio di stabilità alla Lyapunov
riguarda l'evoluzione locale del sistema dinamico con **condizioni
iniziali perturbate**. Qualitativamente, un punto di equilibrio è
stabile se, partendo da uno stato "vicino" all'equilibrio, lo stato del
sistema rimane per sempre "vicino" all'equilibrio. Inoltre, l'equilibrio
è asinotiticamente stabile se lo stato converge verso il punto di
equilibrio, $\bm{x} \rightarrow \bm{\overline{x}}$ per
$t \rightarrow \infty$. La stabilità di Lyapunov di un equilibrio può
essere indagata attraverso l'analisi degli autovalori del sistema
linearizzato attorno al punto di equilibrio.

**Stabilità strutturale.** La stabilità strutturale considera
l'evoluzione del sistema in seguito a perturbazioni del sistema stesso.
Un sistema dinamico è strutturalmente stabile se le traiettorie nel suo
spazio delle fasi non cambiano qualitativamente: ad esempio, in un
sistema strutturalmente stabile alla perturbazione di un parametro, non
cambiano il numero dei punti di equilibrio e cicli limite.

### Sistema dinamico di Lorenz

In questa sezione si descrive, senza nessuna pretesa di completezza, lo
di studio di stabilità del sistema dinamico di Lorenz, $$\begin{cases}
      \dot{X} = - \sigma X + \sigma Y \\
      \dot{Y} = - Y + \rho X - X Z \\
      \dot{Z} = - \beta Z + X Y \ ,
    \end{cases}$$ come primo esempio di studio di stabilità di un
sistema fluidodinamico. Si studia la stabilità del sistema di Lorenz al
variare del parametro $\rho$, mantenendo costante il valore dei
parametri $\sigma$ e $\beta$. Lorenz usò come valori $\sigma = 10$ e
$\beta = 8/3$. Il numero di Prantdl assume un valore paragonabile a
quello dell'acqua alla temperatura di $20^\circ C$, che vale circa
$Pr \approx 7$. Il numero di Prandtl per l'aria e altri gas vale circa
$0.7$. Il valore $\beta = 8/3$ corrisponde a un numero d'onda
fondamentale in direzione $x$ uguale a
$\frac{k}{2} = \frac{1}{2} \sqrt{\frac{4}{\beta} - 1} = \frac{\sqrt{2}}{2} =
 0.3536$.

#### Punti di equilibrio

  -- --
     
     
     
  -- --

I punti di equilibrio del sistema di Lorenz soddisfano le equazioni
stazionarie $$\begin{cases}
      0 = - \sigma X + \sigma Y  & \rightarrow Y = X \\
      0 = - Y + \rho X - X Z & \hspace{2.0cm} \searrow \hspace{2.0cm}\rightarrow  X[X^2-(\rho-1)] = 0 \\
      0 = - \beta Z + X Y  & \hspace{1.0cm} \rightarrow \hspace{1.0cm}  X^2 = \beta Z \hspace{0.5cm} \nearrow 
    \end{cases}$$ L'equazione $X(X^2 - \rho) = 0$ ha una sola soluzione
reale se $\rho < 1$, tre soluzioni per $\rho \geq 1$. Quindi per valori
di $\rho < 1$ esiste un unico punto di equilibrio,
$$\text{\textbf{E1}: } (\overline{X}_1, \overline{Y}_1, \overline{Z}_1) = (0,0,0) \ .$$
Per valori di $\rho \geq 1$ esistono tre punti di equilibrio,
$$\begin{aligned}
 \text{\textbf{E1}: } &  (\overline{X}_1, \overline{Y}_1, \overline{Z}_1) = (0,0,0) \ , \\
 \text{\textbf{E2}: } &  (\overline{X}_2, \overline{Y}_2, \overline{Z}_2) =
 (-\sqrt{\beta(\rho-1)},-\sqrt{\beta(\rho-1)},\rho-1) \ , \\
 \text{\textbf{E3}: } &  (\overline{X}_3, \overline{Y}_3, \overline{Z}_3) =
 (+\sqrt{\beta(\rho-1)},+\sqrt{\beta(\rho-1)},\rho-1) \ .
\end{aligned}$$ I campi di velocità e temperatura degli equilibri del
sistema fisico corrispondenti ai punti di equilibrio del sistema di
Lorenz sono raffigurati in figura
[\[fig:lorenz-equil\]](#fig:lorenz-equil){reference-type="ref"
reference="fig:lorenz-equil"}. L'equilibrio **E1** rappresenta la
soluzione statica, il cui il campo di velocità è nullo: non sono
presenti moti convettivi e la trasmissione della temperatura avviene
solo per conduzione (diffusione). Questo equilibrio è stabile per valori
del parametro $\rho<1$. Per valori $\rho > 1$ questo equilibrio diventa
instabile e nascono i due equilibri "simmetrici" **E2,3** che
rappresentano dei moti convettivi stabili, traslati tra di loro di metà
della lunghezza d'onda $\frac{k}{2}$: i moti convettivi tendono a
portare il fluido caldo dalla parete inferiore (a temperatura maggiore,
per $\rho>0$, corrispondente a $Ra > 0$, e quindi
$\Delta T = T_w - T_c >0$) verso la parete superiore. La nascita di due
equilibri stabili in corrispondenza del un cambio di stabilità di un
equilibrio esistente è caratteristico dei sistemi dotati di
simmetria.[^3] Questo cambiamento qualitativo nel piano delle fasi,
corrisponde alla *biforcazione pitchfork* che verrà descritta, almeno
brevemente, nelle sezioni successive. I moti convettivi rappresentati
dagli equilibri **E2,3** contribuiscono al mescolamento del fluido e a
una maggiore trasimissione del calore tra le due superfici. Calcolando
il flusso di calore trasmesso attraverso le superfici che delimitano il
dominio in $z=0$ e $z=1$, si può verificare che la convezione è un
fenomeno fisico più efficiente per la trasmissione del calore nei fluidi
rispetto alla conduzione, come mostrato in figura
[\[fig:lorenz-equil-heat-flux\]](#fig:lorenz-equil-heat-flux){reference-type="ref"
reference="fig:lorenz-equil-heat-flux"}.

  -- --
     
  -- --

Per esempio, il problema della trasmissione del calore tra due superfici
parallele separate da un fluido si trova nella costruzione di infissi
con **doppi vetri**: lo scopo dei doppi vetri separati da una sottile
intercapedine d'aria è quello di sfruttare l'aria (ferma!) come ottimo
isolante termico. L'intercapedine tra i due vetri deve essere
sufficiente piccola da impedire la nascita dei moti convettivi, che
ridurrebbero l'efficienza dell'infisso (e l'efficienza energetica della
casa). Le soluzioni convettive nel problema di Lorenz nascono quando il
parametro $\rho$ supera il valore critico $\rho_{cr} = 1$. Il parametro
$\rho$ è proporzionale al numero di Rayleigh,
$$\rho \sim Ra = \frac{\alpha g \Delta T h^3}{\nu D} \ ,$$ e quindi
proporzionale al cubo della distanza tra le due superfici,
$\rho \sim h^3$. Si ricava la stessa conclusione utilizzata nella
costruzione dei doppi vetri: per distanze $h$ tra le due superfici
limitate, il parametro $\rho$ è inferiore del valore critico e l'unica
soluzione stabile esistente è quella isolante di fluido in quiete.

Prima di studiare la stabilità locale "alla Lyapunov" dei punti di
equilibrio, riprendendo la definizione di *stabilità strutturale* si
scopre che il sistema di Lorenz non è strutturalmente stabile a
perturbazioni del valore di $\rho$, quando $\rho = 1$: infatti per
$\rho < 1$ esiste un solo punto di equilibrio, per $\rho > 1$ esistono
tre punti di equilibrio e di conseguenza le traiettorie nel piano delle
fasi subiscono un cambiamento qualitativo.

  -- --
     
  -- --

#### Stabilità dell'equilibrio E1

Si studia la stabilità "alla Lyapunov" dell'equilibrio **E1**:
$(0,0,0)$. Linearizzando il sistema non lineare di Lorenz attorno
all'equilibrio **E1**, si ottiene il sistema linear(izzato)
$$\begin{bmatrix} \delta \dot{x} \\ \delta \dot{y} \\ \delta \dot{z} \end{bmatrix} = 
 \begin{bmatrix}-\sigma & \sigma & 0 \\ \rho & -1 & 0 \\ 0 & 0 & - \beta \end{bmatrix}  
 \begin{bmatrix} \delta x \\ \delta y \\ \delta z \end{bmatrix} \quad , \quad
 \delta \dot{\bm{x}} = \bm{J}|_{\bm{E1}} \, \delta \bm{x}$$ il cui
polinomio caratteristico è $$\begin{aligned}
 p(\lambda) = det(\bm{J}- \lambda \bm{I}) & = -(\beta+\lambda)[(\sigma+\lambda)(1+\lambda)-\sigma\rho] = \\ 
  & = -(\beta+\lambda) [ \lambda^2 + (\sigma+1)\lambda + \sigma(1-\rho)] \ . 
\end{aligned}$$ Gli autovalori del sistema linearizzato attorno al primo
equilibrio sono quindi $$\lambda^{E1}_1 = - \beta \quad , \quad  
  \lambda^{E1}_{2,3} = - \dfrac{\sigma+1}{2} \mp \dfrac{\sqrt{(\sigma+1)^2-4\sigma(1-\rho)}}{2} \ .$$
Per valori positivi dei parametri, tutti gli autovalori sono reali. Gli
autovalori $\lambda^{E1}_1$ e $\lambda^{E1}_2$ sono negativi per ogni
valore di $\rho$, mentre l'autovalore $\lambda^{E1}_3$ cambia segno per
$\rho = 1$, come mostrato in figura
[\[fig:lorenz-eig\]](#fig:lorenz-eig){reference-type="ref"
reference="fig:lorenz-eig"}(a.1). L'analisi lineare di stabilità
permette di concludere che l'equilibrio **E1** è linearmente stabile per
$\rho<1$ e instabile per $\rho > 1$, mentre non permette di affermare
nulla sul caso $\rho = 1$.

#### Stabilità degli equilibri E2, E3

Per valori di $\rho \geq 1$ esistono i due equilibri **E2**, **E3**. Si
studia la loro stabilità "alla Lyapunov" tramite lo studio degli
autovalori del sistema linearizzato attorno ai punti di equilibrio,
$$\begin{bmatrix} \delta \dot{x} \\ \delta \dot{y} \\ \delta \dot{z} \end{bmatrix} = 
 \begin{bmatrix}-\sigma & \sigma & 0 \\ 1 & -1 & \mp \sqrt{\beta(\rho-1)} \\
 \pm \sqrt{\beta(\rho-1)} & \pm \sqrt{\beta(\rho-1)} & - \beta \end{bmatrix}  
 \begin{bmatrix} \delta x \\ \delta y \\ \delta z \end{bmatrix} \quad , \quad
 \delta \dot{\bm{x}} = \bm{J}|_{\bm{E2,3}} \, \delta \bm{x} \ .$$ Si può
dimostrare (con il criterio di Routh-Hurwitz analiticamente, o
calcolandone numericamente il valore) che i due punti di equilibrio sono
stabili se
$\rho < \frac{\sigma(\sigma+\beta+3)}{\sigma-1-\beta} \approx 24.7368$,
utilizzando i valori $\sigma = 10$, $\beta = 8/3$.

  -- --
     
  -- --

#### Biforcazioni, cicli limite e attrattori strani

L'analisi degli autovalori del sistema linearizzato attorno ai punti di
equilibrio permette di determinarne le caratteristiche locali quando gli
autovalori hanno parte reale diversa da zero. In corrispondenza del
cambio di stabilità di un punto di equilibrio e/o della
comparsa/scomparsa di punti di equilibrio (ma non solo!), le traiettorie
nello spazio delle fasi del sistema subiscono un cambiamento
qualitativo: il sistema non è strutturalmente stabile e si verifica una
**biforcazione**. Per studiare la stabità locale di un equilibrio in
presenza di autovalori a parte reale nulla è necessario costruire
un'approssimazione non lineare del sistema. Si considera un punto di
equilibrio per il quale il sistema linearizzato non ha autovalori
instabili, ha $N_s$ autovalori stabili e $N_c$ autovalori a parte reale
nulla e si vuole determinare l'evoluzione del sistema nelle vicinanze
del punto di equilibrio. Si può dimostrare che la dinamica del sistema
$N=N_s+N_c$-dimensionale si riduce velocemente alla dinamica di un
sistema $N_c$ dimensionale: le $N_s$ dinamiche asintoticamente stabili
associate agli autovalori con parte reale negativa tendono
asintoticamente ad annullarsi nell'intorno dell'equilibrio, mentre
rimangono solo le dinamiche associate alle $N_c$ dinamiche marginalmente
stabili. Si può usare un'espansione polinomiale per approssimare il
sistema non lineare originale e costruire la **varietà centrale**, cioè
la regione dello spazio delle fasi nella quale si svolgono le dinamiche
marginalmente stabili. Ad esempio, quando $\rho = 1$ il sistema di
Lorenz nell'intorno dell'equilibrio **E1** (e dei nascenti equilibri
**E2,3**) può essere ricondotto alla dinamica del sistema
monodimensionale $$\label{eqn:lorenz:pitchfork}
 \dot{a}(t) = f(a(t)) = a(t) [ \alpha \varepsilon - \beta a(t)^2 ] \quad , \quad
 \text{con } \varepsilon := \rho-1 \ ,$$ con $\alpha \approx 0.909$ e
$\beta \approx 0.170$. Questo sistema coincide alla **forma normale**
della biforcazione, cioè il sistema più semplice in grado di descrivere
il cambiamento qualitativo del sistema. Lo studio della forma normale
della biforcazione rivela l'esistenza di un unico equilibrio stabile
$\overline{a}_1 = 0.0$ per $\epsilon \leq 0$, cioé $\rho \leq 1$. Per
$\rho > 1$ l'equilibrio $\overline{a}_1$ diventa instabile e nascono due
equilibri stabili
$\overline{a}_{2,3} = \mp \sqrt{\alpha \varepsilon / \beta}$.
L'equazione
([\[eqn:lorenz:pitchfork\]](#eqn:lorenz:pitchfork){reference-type="ref"
reference="eqn:lorenz:pitchfork"}) rappresenta la forma normale di una
*biforcazione pitchfork*. Poiché $\beta > 0$, la biforcazione si
definisce *supercritica*.

  -- --
     
     
     
  -- --

Analogamente, quando $\rho \approx 24.7368$ i due equilibri **E2,3**
cambiano stabilità: una coppia di autovalori complessi coniugati
attraversa l'asse immaginario e la loro parte reale diventa positiva.
Questo tipo di instabilità strutturale viene definita *biforcazione di
Hopf*: cambia la stabilità del punto di equilibrio considerato e
nasce/sparisce un ciclo limite nel suo intorno (il ciclo limite nasce da
o si riduce al punto di equilibrio). L'approssimazione sulla varietà
centrale del sistema attorno a uno dei due equilibri conduce al sistema
di equazioni $$\label{eqn:lorenz:hopf}
\begin{cases}
 \dot{r}(t) = \alpha_r r \varepsilon - \beta_r r^3 \\
 \dot{\theta}(t) = \omega + \alpha_i \varepsilon + \beta_i r^2 \ 
\end{cases} \quad , \quad 
 \text{con } \varepsilon := \rho-24.7368 \ ,$$ dove è stata utilizzata
la rappresentazione polare complessa $a(t) = r(t) e^{i \theta(t)}$ della
variabile $a(t)$ che descrive la dinamica del sistema ridotta alla
varietà centrale. Il parametro $\omega = 9.6245$ coincide con la parte
immaginaria degli autovalori marginalmente stabili e gli altri parametri
valgono: $$\begin{aligned}
 & \alpha_r = 0.0302 \qquad , \qquad \beta_r =-0.003 \\
 & \alpha_i = 0.1815 \qquad , \qquad \beta_i =-0.028 \ . 
\end{aligned}$$ La prima equazione delle
([\[eqn:lorenz:hopf\]](#eqn:lorenz:hopf){reference-type="ref"
reference="eqn:lorenz:hopf"}) è identica all'equazione che descrive la
biforcazione pitchfork. In questo caso, però, il coefficiente $\beta_r$
è minore di zero. Questo tipo di biforcazione si definisce *subcritica*.
Si può facilmente dimostrare che per $\varepsilon < 0$ esistono due (il
raggio $r$ di una rappresentazione polare deve essere $\geq 0$)
equilibri
$$\overline{\rho}_1 = 0 \quad , \quad \overline{\rho}_2 = \sqrt{-\alpha_r \varepsilon / \beta_r} \ .$$
Il primo equilibrio dell'equazione in $r$ corrisponde a un punto fisso,
poichè il raggio è nullo. Il secondo equilibrio corrisponde al raggio
$\overline{\rho}_2$ del ciclo limite esistente per $\varepsilon < 0$. Si
dimostra quindi che un ciclo limite instabile coesiste con ognuno dei
due punti di equilibri stabili **E2,3** per $\varepsilon < 0$ (cioè
$\rho < 24.7368$), almeno in un intervallo finito di valori di $\rho$.
Quando $\varepsilon = 0$ (cioè $\rho < 24.7368$), il ciclo limite
instabile si riduce al punto di equilibrio. Per $\varepsilon > 0$ il
punto di equilibrio diventa instabile, mentre scompare il ciclo limite.

Rimangono aperte alcune questioni: è possibile descrivere i cicli limite
esistenti per (alcuni) valori del parametro $\rho < 24.7368$? Qual è
l'evoluzione del sistema per valori di $\rho > 24.7368$? Ha senso
utilizzare il modello di Lorenz, un brutale troncamento di un sistema
continuo che dà origine a un sistema tridimensionale, per descrivere
l'evoluzione del sistema fisico per valori crescenti del numero di
Rayleigh $Ra$, e quindi del parametro $\rho$?

Partendo dall'espressione approssimata del ciclo limite ottenuta dalla
forma normale della biforcazione di Hopf per $\rho \lesssim 24.7368$ è
possibile calcolare la forma del ciclo limite per valori inferiori del
parametro, tramite tecniche di **continuazione**: negli algoritmi di
continuazione la soluzione di un problema, nota per un valore del
parametro, viene utilizzata per stimare la guess iniziale dello stesso
problema per un valore diverso del parametro. In particolare, per
identificare la traiettoria periodica corrispondente a un ciclo limite
si può utilizzare una tecnica di **bilanciamento armonico**: la
traiettoria periodica viene scritta come serie di Fourier, della quale è
necessario determinare i coefficienti.

Per valori di $\rho > 24.7368$ non esistono punti di equilibrio stabili
punti di equilibrio stabili e non esistono cicli limite stabili. La
dinamica del sistema rimane confinata in una regione limitata dello
spazio delle fasi, senza divergere. L'evoluzione del sistema
rappresentata in figura
[\[fig:lorenz-chaos\]](#fig:lorenz-chaos){reference-type="ref"
reference="fig:lorenz-chaos"} dimostra l'elevata sensibilità della
soluzione alle condizioni iniziali e l'assenza di equilibri o dinamiche
periodiche stabili, caratteristici di un **regime caotico**.
L'evoluzione di lungo tempo del sistema avviene "nelle vicinanze"
dell'attrattore di Lorenz, del quale si può intuire la forma grazie alle
traiettorie rappresentate in figura
[\[fig:lorenz-chaos\]](#fig:lorenz-chaos){reference-type="ref"
reference="fig:lorenz-chaos"}(b). La figura
[\[fig:lorenz-chaos-cm\]](#fig:lorenz-chaos-cm){reference-type="ref"
reference="fig:lorenz-chaos-cm"} rappresenta la traiettoria del sistema
di Lorenz e le *varietà centrali* dei due equilibri $\textbf{E2,3}$
marginalmente stabili per $\rho = 24.7368$. Qualitativamente, lo stato
del sistema viene attratto su queste superfici, lungo le direzioni
stabili. Su queste superfici poi, si può osservare la dinamica
marginalmente stabile (di dimensione ridotta: per il sistema di Lorenz,
di dimensione 2, invece della dimensione 3 del sistema completo) del
sistema: lo stato del sistema inizialmente oscilla attorno all'
equilibrio **E2** (ad esempio), prima di essere attratta in maniera
"difficilmente prevedibile" dalla varietà centrale dell'equilibrio
**E3** e iniziare ad oscillare attorno a quest'ultimo equilibrio.

L'approssimazione di Lorenz di dimensioni ridotte del sistema fisico
continuo (e quindi di dimensione infinita) perde significato
all'aumentare del numero di Rayliegh: all'aumentare del numero di
Rayleigh infatti si attivano delle dinamiche più complesse, di
dimensione maggiore, non descrivibili a un sistema tridimensionale.

...
---

[^1]: La risposta armonica di un sistema lineare può essere studiata nel
    dominio delle frequenze. La trasformata di Fourier del sistema
    lineare
    $\qquad \underline{\dot{x}} = \underline{\underline{A}} \, \underline{x} +
                          \underline{\underline{B}} \, \underline{f} \qquad$
    è
    $\qquad i\omega\underline{\hat{x}} = \underline{\underline{A}} \, \underline{\hat{x}} +
                          \underline{\underline{B}} \, \underline{\hat{f}} \ $.
    Il *resolvent operator* $\mathcal{R}(\omega)$ del sistema nel
    dominio delle frequenze è l'operatore che lega la trasformata di
    Fourier $\underline{\hat{f}}(\omega)$ della forzante
    $\underline{f}(t)$ alla trasformata di Fourier
    $\underline{\hat{x}}(\omega)$ dello stato (o dell'uscita)
    $\underline{x}(t)$ del sistema, $$\underline{\hat{x}}(\omega) 
        = [-i\omega \underline{\underline{I}} + \underline{\underline{A}}]^{-1}
        \underline{\underline{B}} \, \underline{\hat{f}}(\omega) = \mathcal{R}(\omega) \underline{\hat{f}}(\omega) \qquad \rightarrow \qquad 
        \mathcal{R}(\omega) =[-i\omega \underline{\underline{I}} + \underline{\underline{A}}]^{-1} \ .$$

[^2]: Conoscendo lo stato del sistema **con esattezza** è possibile
    descrivere l'evoluzione libera del sistema, in assenza di
    perturbazioni e forze esterne. In fondo a questa sezione, sarà più
    chiara la necessità di conoscere *con esattezza* lo stato iniziale
    del sistema, per prevederne l'evoluzione.

[^3]: Un esempio strutturale è quello della trave caricata di punta a
    compressione. Per valori limitati del carico esiste un'unica
    soluzione, stabile, rappresentata dalla trave senza freccia. Quando
    il carico di compressione supera il valore critico, questa soluzione
    diventa instabile. Nel problema piano, nascono due configurazioni di
    equilbirio stabili del sistema strutturale: la trave può inflettersi
    (in maniera indifferente in assenza di imperfezioni) verso destra o
    verso sinistra.
