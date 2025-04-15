(fluid-mechanics:similitude:exercises)=
# Exercises

::::{grid}
:gutter: 2

:::{grid-item-card} Exercise 7.1
:columns: 12

La velocità di pattugliamento di un sottomarino vale $V_v = 2.5\ m/s$.
Considerando che il sottomarino si muova in acqua in condizioni standard, a quale velocit\`{a}
deve essere provato un modello in scala $\lambda = 1/10$, avendo a disposizione
rispettivamente:

- una galleria ad acqua in condizioni standard,
- una galleria ad aria a pressione di $10 \ bar$ e temperatura di 
  $30^\circ  C$?


Se la resistenza al vero vale $D_v=6000\ N$, quanto vale la resistenza sui
modelli in scala nei due casi?

(Galleria ad aria: $V_m = 35.17\  m/s$, $D_m = 136.1\ N$. 
 Galleria ad acqua: $V_m = 25\  m/s$, $D_m = 6000\ N$.)

::::

<!-- ++++++++++++++++++++++++++++++++++++++++++++++++++++++++++++++++++++++++ -->

::::{grid}
:gutter: 2

:::{grid-item-card} Exercise 7.2
:columns: 12

Un missile vola alla quota di $7000\  m$, dove la densit\`{a} 
dell'aria \`{e} $\rho = 0.59\  kg/m^3$ e la sua temperatura 
\`e $T=-30.45^\circ   C$, alla velocit\`{a} costante $V_v=505\  km/h$.

Determinare:
\begin{itemize}
  \item il fattore di scala geometrico $\lambda=L_m/L_v$,
  \item la velocit\`{a} dell'aria $V_m$,
\end{itemize}
necessari per riprodurre correttamente i coefficienti aerodinamici 
del missile in una galleria del vento che operi a condizioni 
atmosferiche standard ($\rho=1.225\ kg/m^3$, $p=101325\ Pa$,
$T=15^\circ  C$).
    
($V_m =152.8\  m/s$, $\lambda=0.507$)

:::

::::

<!-- ++++++++++++++++++++++++++++++++++++++++++++++++++++++++++++++++++++++++ -->

::::{grid}
:gutter: 2

:::{grid-item-card} Exercise 7.3
:columns: 12

Un aeromobile vola nell'alta atmosfera a velocità costante $V_v=252\  m/s$,
in condizioni di densit\`{a} $\rho_v$ e temperatura $T_v$ assegnate: 
$\rho_v = 0.424\ kg/m^3$, $T_v = -50.3^\circ  C$.
%
\newline
Determinare la velocit\`{a}, la densit\`{a} e la pressione dell'aria da utilizzarsi 
in una galleria del vento pressurizzata che operi alla temperatura di $15^\circ {\rm C}$
per ottenere la similitudine dinamica corretta con un modello in scala ridotta $\lambda = 0.2$.

($V_m = 286.6\ m/s$, $\rho_m = 2.292\ kg/m^3$, $p_m= 189560\ Pa$)

:::

::::

<!-- ++++++++++++++++++++++++++++++++++++++++++++++++++++++++++++++++++++++++ -->

::::{grid}
:gutter: 2

:::{grid-item-card} Exercise 7.4
:columns: 8

 Si vuole studiare con la corrente di aria che esce da un ugello verticale
 di diametro $\tilde{D}=0.01\ m$, nell'intervallo di velocità di riferimento
 $\tilde{U} \in [1,10] \ m/s$. Si ha a disposizione un codice numerico 
 che risolve le equazioni in forma adimensionale, in cui non è possibile
 variare le condizioni al contorno, e una sola griglia di calcolo.
 Si chiede di:

- determinare l'intervallo di numeri di Reynolds $Re$ da inserire
 nel codice, sapendo che la velocità di riferimento nel codice è $U=1$
 e il diametro nella griglia vale $D=1$.
- la frequenza $\tilde{f}$ di rilascio di vortici quando
 $\tilde{U}=1\ m/s$, sapendo che la frequenza estratta dai risultati
 numerici è $f=0.2$;
- stimare l'errore compiuto dal codice nel trascurare l'effetto
  della gravità.

:::

:::{grid-item-card}
:columns: 4

![](../../fig/slnEsatte-newton-couette.png)

:::

::::

<!-- ++++++++++++++++++++++++++++++++++++++++++++++++++++++++++++++++++++++++ -->

::::{grid}
:gutter: 2

:::{grid-item-card} Exercise 7.5
:columns: 8

Si deve progettare un condotto che trasporti un fluido con densità
$\rho_1$ e viscosità $\mu_1$, di diametro $d_1$ e lunghezza $L_1$.
Si suppone che la rugosità della superficie interna del condotto possa
essere descritta interamente dall'altezza media $\epsilon_1$
delle asperità. Il condotto deve garantire una portata massica $Q_1$.
Viene realizzato un modello in scala $\lambda = d_2 / d_1$ del condotto
di lunghezza $L_2$, nel quale viene fatto scorrere lo stesso fluido 
alle stesse condizioni termodinamiche. Si chiede di determinare:

 - la finitura superficiale della superficie interna del modello,
   in termini di dimensione caratteristica della rugosità $\epsilon_2$;
 - la velocità media di prova $U_2$;
 - la differenza di pressione da imporre alle estremità del condotto
   al vero, conoscendo che la differenza di pressione $\Delta P_2$
   misurata in laboratorio.

Si supponga il fluido incomprimibile.


:::

:::{grid-item-card}
:columns: 4

![](../../fig/pipe.png)

:::

::::

<!-- ++++++++++++++++++++++++++++++++++++++++++++++++++++++++++++++++++++++++ -->

::::{grid}
:gutter: 2

:::{grid-item-card} Exercise 7.6
:columns: 8

 L'obiettivo di una prova in galleria è lo studio del campo di moto
  attorno a una pala di elicottero, in particolare attorno alla sezione
  che si trova a metà della lunghezza della pala, $R_v = 6.85\ m$. Il rotore
  dell'elicottero ruota con una velocità angolare $\Omega_v$, tale da
  avere una velocità $U_{tip} = 200 \ m/s$ (per evitare il regime
  supersonico). La corda della pala nella sezione analizzata è
  $c_v = 0.30 \ m$.
 Il modello di galleria a circuito aperto è costituito da una superficie
  alare, incernierata su un asse perpendicolare alla direzione del vento
  di galleria, in corrispondenza dell'asse ``di comando del passo''.
 Sapendo che la massima velocità raggiungibile nell'impianto utilizzato
  è $U_m = 50 \ m/s$, si chiede di determinare:

  - la corda del modello $c_m$, per ottenere la similitudine in $Re$ e di
    commentare gli effetti di comprimibilità;
  - la frequenza di oscillazione $\omega_m$ da imporre al profilo per
    simulare il cambio di incidenza dovuti ai comandi di passo collettivo
    e ciclico;
  - una stima della potenza dell'impianto necessaria a svolgere la prova,
    conoscendo le dimensioni della camera di prova rettangolare, $b = 1.5 \ m$,
    $h = \ 1.0 m$.


:::

:::{grid-item-card}
:columns: 4

![](../../fig/helicopter.png)

:::

::::

