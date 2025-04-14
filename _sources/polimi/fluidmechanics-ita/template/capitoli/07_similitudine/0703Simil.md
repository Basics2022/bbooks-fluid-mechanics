**Esercizi per il corso di Fluidodinamica**

La velocità di pattugliamento di un sottomarino vale $V_v = 2.5\ m/s$.
Considerando che il sottomarino si muova in acqua in condizioni
standard, a quale velocità deve essere provato un modello in scala
$\lambda = 1/10$, avendo a disposizione rispettivamente:

-   una galleria ad acqua in condizioni standard,

-   una galleria ad aria a pressione di $10 \ bar$ e temperatura di
    $30^\circ  C$?

Se la resistenza al vero vale $D_v=6000\ N$, quanto vale la resistenza
sui modelli in scala nei due casi?

(Galleria ad aria: $V_m = 35.17\  m/s$, $D_m = 136.1\ N$. Galleria ad
acqua: $V_m = 25\  m/s$, $D_m = 6000\ N$.)

### Soluzione {#soluzione .unnumbered}

     **Concetti.** Similitudine fluidodinamica per correnti
incomprimibili, numero di Reynolds, $$Re = \frac{\rho U L}{\mu} \ .$$
Formula di Sutherland per la viscosità dinamica **dei gas**,
$$\mu(T) = \mu_0 \displaystyle\left(\frac{T}{T_0}\right)^{1.5}
 \frac{C+T_0}{C+T} \ .$$ Azioni agenti sul modello e coefficienti di
forza.

**Svolgimento.** La velocità sul modello si trova tramite l'uguaglianza
dei numeri di Reynolds,
$$\frac{\rho_v U_v L_v}{\mu_v} = \frac{\rho_m U_m L_m}{\mu_m} \quad 
 \rightarrow \quad U_m = U_v \frac{\rho_v L_v}{\rho_m L_m} \ .
 \frac{\mu_m}{\mu_v}$$ Per trovare la viscosità dell'aria viene
utilizzata la formula di Sutherland (per l'aria i coefficienti sono
$T_0 = 288 K$, $C = 110.4 K$, $\mu_0 = 18.27 \mu Pa s$). Il coefficienti
di viscosità dinamica dell'acqua in condizioni standard è dell'ordine di
$10^{-3} \ kg / (m \ s)$. La forza agente aerodinamica agente sul corpo,
la cui superficie esterna è indicata con $S$, è la risultante degli
sforzi di superficie esterna del corpo ${S_b}$, $$\begin{aligned}
 \bm{F} = \oint_S \bm{t}_{\bm{n}} =  \oint_S -p \bm{\hat{n}} + \mu [\bm{\nabla} \bm{u} + \bm{\nabla}^{T} \bm{u}] \cdot \bm{\hat{n}} 
\end{aligned}$$ Vengono scelte la densità caratteristica del fluido
$\rho$, una velocità caratteristica della corrente $U$ e una lunghezza
caratteristica del problema $L$, per definire la scala della pressione
$P = \rho U^2$. Raccogliendo le dimensioni fisiche fuori dal segno di
integrale è quindi possibile scrivere, $$\begin{aligned} 
 \bm{F} & =  \oint_{S_b} -P p^*\bm{\hat{n}} + \frac{\mu U}{L} [\bm{\nabla}^*
  \bm{u}^* + \bm{\nabla}^{*T} \bm{u}^*] \bm{\hat{n}} = 
  & \qquad \text{($P = \rho U^2$, $dS = L^2 dS^*$)} \\
 & = \rho U^2 L^2 \oint_{S_b^*} - p^*\bm{\hat{n}} + \frac{1}{Re} [\bm{\nabla}^*
  \bm{u}^* + \bm{\nabla}^{*T} \bm{u}^*] \bm{\hat{n}} = \\
 & = \dfrac{1}{2}\rho U^2 S \bm{c}_{\bm{F}}(Re) \ ,
\end{aligned}$$ avendo introdotto il coefficiente di forza
$\bm{c}_{\bm{F}}$,
$$\bm{c}_{\bm{F}} = 2 \dfrac{L^2}{S} \oint_{S_b^*} - p^*\bm{\hat{n}} + \frac{1}{Re} [\bm{\nabla}^* \bm{u}^* + \bm{\nabla}^{*T} \bm{u}^*] \bm{\hat{n}}$$
che può dipendere dalle variabili fisiche solo attraverso i numeri
adimensionali del problema (in questo caso solo da $Re$, per problemi
comprimibili anche da $M$) e che rappresenta la forza agente sul corpo
adimensionalizzata con la pressione dinamica $\frac{1}{2}\rho U^2$ e con
una supreficie di riferimento del corpo $S$. La superficie di
riferimento $S$ scala con $L^2$ ($S = a L^2$, $a$ costante). Si può
scrivere la risultante delle forze sul modello e al vero come
$$\begin{cases}
  \bm{F}_m = \dfrac{1}{2}\rho_m U_m^2 S_m^2 \bm{c_F}(Re_m) \\
  \bm{F}_v = \dfrac{1}{2}\rho_v U_v^2 S_v^2 \bm{c_F}(Re_v) \ .
 \end{cases}$$ Poichè è soddisfatta la similitudine fluidodinamica, i
valori dei coefficienti di forza del modello e "al vero" sono uguali. Si
può quindi scrivere
$$\bm{F}_m = \dfrac{\rho_m}{\rho_v} \left( \dfrac{U_m}{U_v} \right)^2
  \left( \dfrac{S_m}{S_v} \right) \bm{F}_v = 
 \dfrac{\rho_m}{\rho_v} \left( \dfrac{U_m}{U_v} \right)^2
  \left( \dfrac{L_m}{L_v} \right)^2 \bm{F}_v = 
 \dfrac{\rho_m}{\rho_v} \left( \dfrac{U_m}{U_v} \right)^2
  \lambda^2 \bm{F}_v \ ,$$ Nel caso della galleria ad acqua, nella quale
il fluido è lo stesso e nello stesso stato termodinamico della
situazione reale ($\rho_m = \rho_v$, $\mu_m = \mu_v$), l'uguaglianza dei
numeri di Reynolds si semplifica in
$$\dfrac{\rho_m U_m L_m}{\mu_m} = \dfrac{\rho_v U_v L_v}{\mu_v} \quad \rightarrow \quad
  U_m L_m = U_v L_v \ .$$ Quindi, in questo caso la forza agente sul
modello di galleria coincide con la forza agente sul corpo nella
situazione reale, $$\bm{F}^{H_2O,s}_m = \bm{F}^{H_2O,s}_v \ .$$
