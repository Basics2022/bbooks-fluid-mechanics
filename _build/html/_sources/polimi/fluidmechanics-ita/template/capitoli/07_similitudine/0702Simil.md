**Esercizi per il corso di Fluidodinamica**

Un aeromobile vola nell'alta atmosfera a velocità costante
$V_v=252\  m/s$, in condizioni di densità $\rho_v$ e temperatura $T_v$
assegnate: $\rho_v = 0.424\ kg/m^3$, $T_v = -50.3^\circ  C$. Determinare
la velocità, la densità e la pressione dell'aria da utilizzarsi in una
galleria del vento pressurizzata che operi alla temperatura di
$15^\circ {\rm C}$ per ottenere la similitudine dinamica corretta con un
modello in scala ridotta $\lambda = 0.2$.

($V_m = 286.6\ m/s$, $\rho_m = 2.292\ kg/m^3$, $p_m= 189560\ Pa$)

### Soluzione {#soluzione .unnumbered}

     **Concetti.** Similitudine fluidodinamica: numeri di Reynolds e di
Mach. $$Re = \frac{\rho U L}{\mu} \quad , \quad M = \frac{U}{c} \ .$$
Formula di Sutherland per la viscosità dinamica **dei gas**,
$$\mu(T) = \mu_0 \displaystyle\left(\frac{T}{T_0}\right)^{1.5}
 \frac{C+T_0}{C+T} \ .$$ **Svolgimento.** Assumendo che l'aria si
comporti come gas ideale, per il quale vale l'equazione di stato
$p = \rho R T$, la velocità del suono vale $c = \sqrt{\gamma R T}$, dove
$\gamma = c_p / c_v$ è il rapporto dei calori specifici a pressione e
volume costante, che vale $\gamma = 1.4$ per un gas biatomico. La
costante del gas $R$ è definita come il rapporto tra la costante
universale dei gas $\mathscr{R}$ e la massa molare $M_m$,
$R = \mathscr{R}/M_m$. La massa molare dell'aria secca vale
$M_m = 28.96 \ kg / kmol$ e la sua costante $R$ vale
$$R = \dfrac{\mathscr{R}}{M_m} = \dfrac{8314.4 \ J / (kmol \ K)}{28.97 \ kg/kmol} = 287.0 \dfrac{J }{kg \ K} \ .$$
La velocità del suono nell'aria alle condizioni termodinamiche del
problema vale $c = 299.2 \ m/s$. Il numero di Mach caratteristico della
corrente è quindi $M=0.84$ e gli effetti di comprimibilità non possono
essere trascurati, poichè il numero di Mach è maggiore della valore
convenzionale $0.3$ che identifica il limite della validità
dell'approssimazione di fluido incomprimibile. Per ottenere la
similitudine tra problema reale e quello modellato (di dimensioni
ridotte) è necessaria la similitudine geometrica e l'uguaglianza dei
numeri adimensionali che caratterizzano il problema, il numero di
Reynolds $Re$ e il numero di Mach $M$. $$\begin{cases}
 M_1 = M_2 \\
 Re_1 = Re_2  
\end{cases} \ .$$ Utilizzando l'equazione di stato dei gas perfetti,
$$\begin{cases}
 \dfrac{V_v}{\sqrt{\gamma R T_v}} = \dfrac{V_m}{\sqrt{\gamma R T_m}} \\
 \dfrac{\rho_v V_v L_v}{\mu(T_v)} = \dfrac{\rho_m V_m L_m}{\mu(T_m)}
\end{cases}$$ Risolvendo il sistema, si ottiene l'espressione delle
incognite: $$\Rightarrow
   \begin{cases}
     V_m = V_v \sqrt{\frac{T_m}{T_v}} \\
     \rho_m = \frac{1}{\lambda} \rho_v \sqrt{\frac{T_v}{T_m}}
     \frac{\mu(T_m)}{\mu(T_v)} \\
     P_m = \rho_m R T_m = \frac{1}{\lambda} \frac{\mu(T_m)}{\mu(T_v)} \rho_v R \sqrt{T_v T_m}
   \end{cases}$$ Per trovare i valori ancora incogniti della viscosità
dinamica si usa la formula di Sutherland: per l'aria i coefficienti sono
$T_0 = 288 K$, $C = 110.4 K$. Si ottengono i valori numerici
$V_m = 286.6 \ m/s$, $\rho_m = 2.292 \ kg/m^3$, $p_m = 189560 \ Pa$.
