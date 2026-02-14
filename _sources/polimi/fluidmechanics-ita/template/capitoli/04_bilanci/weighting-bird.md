(fluid-mechanics:balances:ex-weighting-hidden-bird)=
# Weighting a hidden bird

::::{grid}
:gutter: 2

:::{grid-item-card} Exercise 4.11
:columns: 8

Un uccello si trova in una gabbia chiusa di volume interno $V_c$ e di massa $m_c$. Si chiede di determinare la massa dell'uccello. Il riferimento della lettura della bilancia è posto a zero quando sul piatto della bilancia non è posto nessun oggetto. La lettura della bilancia cambia a seconda che l'uccello sia appoggiato alla parete inferiore o sia in volo? Mentre l'uccello è in volo, si può calcolare la componente verticale della forza generata dall'uccello?

Si consideri il fluido incomprimibile di densità costante e uniforme $\rho_a$ all'interno della scatola. Si discuta il caso in cui l'uccello può essere considerato di densità uniforme $\rho_b$, così che il centro geometrico dell'uccello coincide con il suo centro di massa. Si trascuri lo spostamento del piatto della bilancia. Si consideri uniforme la pressione atmosferica $P_a$ che agisce sulle pareti esterne della gabbia e su tutte le superficie del piatto della bilancia.

:::

:::{grid-item-card}
:columns: 4

![](../../fig/hidden-bird.png)

:::

::::

**Soluzione.** Si considera il sistema chiuso formato dal piatto della bilancia, dalla gabbia, e dall'aria e dall'uccello contenuti in essa. Il secondo principio della dinamica per questo sistema chiuso mette in relazione la derivata della quantità di moto $\mathbf{Q}$ del sistema e la risultante delle forze esterne $\mathbf{R}^{ext}$ agenti su di esso,

$$\dfrac{d \mathbf{Q}}{dt} = \mathbf{R}^{ext} \ .$$

La risultante delle forze esterne al sistema è la somma del peso dei sottosistemi, della pressione atmosferica agente sulla superficie esterna e della reazione del piatto della bilancia. Nell'ipotesi che la pressione agente sul sistema sia uniforme, la risultante della pressione atmosferica agente sul sistema non sposta la lettura della bilancia (vedi sotto),

$$\begin{aligned}
  \mathbf{R}^{ext}
  & = \mathbf{F} + \mathbf{P} = \\
  & = \mathbf{F} + m_0 \mathbf{g} + m_c \mathbf{g} + m_a \mathbf{g} + m_b \mathbf{g} \ .
\end{aligned}$$

Dal secondo principio della dinamica, la reazione vincolare della bilancia vale

$$\mathbf{F} = \dot{\mathbf{Q}} - \mathbf{P} \ ,$$

equilibrando il peso e la derivata nel tempo della quantità di moto.

**Una stima più dettagliata.** Assumendo di aver fatto la tara in assenza del volatile nella gabbia, la reazione della bilancia di riferimento si ottiene dalle condizione di equilibrio

$$\mathbf{F}_0 = - m_0 \mathbf{g} - m_c \mathbf{g} - \rho_a (V_a + V_b) \mathbf{g} \ ,$$

con il volume della gabbia $V_c$ uguale alla somma del volume del volatile $V_b$ e quello occupato dall'aria $V_a$, $V_c = V_a + V_b$. La risultante della bilancia può essere riscritta come

$$\begin{aligned}
  \mathbf{R}^{ext}
  & = \mathbf{F} - \mathbf{F}_0 + m_b \mathbf{g} - \rho_a V_b \mathbf{g} = \\
  & = \Delta \mathbf{F} + \left( m_b - \rho_a V_b \right) \mathbf{g} = \\
  & = \Delta \mathbf{F} + \left( \rho_b - \rho_a \right) V_b \mathbf{g} \ .
\end{aligned}$$

La quantità di moto del sistema è la somma della quantità di moto dei suoi componenti: piatto bilancia, gabbia, aria, volatile. Nel caso in cui il movimento del piatto della bilancia sia trascurabile, anche la struttura della gabbia può essere considerata in quiete.

$$\begin{aligned}
  \mathbf{Q}
  & = \mathbf{Q}_a + \mathbf{Q}_b = \\
  & = m_a \mathbf{u}_a + m_b \mathbf{u}_b = \\
  & = m_a \mathbf{u}^g_a + m_b \mathbf{u}_b = \\
  & = m_a \dot{\mathbf{r}}^g_a + m_b \dot{\mathbf{r}}_b \ ,
\end{aligned}$$

poiché il centro geometrico del volume di aria e il suo centro di massa coincidono nell'ipotesi di fluido a densità uniforme, e quindi anche le loro velocità, $\mathbf{u}^g_a = \mathbf{u}_a$.

Usando il secondo principio della dinamica con le espressioni della quantità di moto e della risultante delle forze esterne, si ricava l'espressione della lettura della bilancia $\Delta \mathbf{F}$, in funzione delle proprietà di inerzia di aria e volatile e dello stato di moto del volatile (e dell'aria),

$$\Delta \mathbf{F} = - m_b \mathbf{g} +  m_b \ddot{\mathbf{r}}_b + m_a \ddot{\mathbf{r}}^g_a + \rho_a V_b \mathbf{g} \ .$$

La lettura della bilancia è quindi influenzata dal moto del volatile e dell'aria all'interno della gabbia. Nel caso in cui il volatile vola a quota costante, la lettura della bilancia concide esattamente con il peso del volatile (meno il peso di un volume d'aria uguale al volume del volatile, che veniva pesato durante l'operazione di tara definita sopra). Nel caso in cui la massa dell'aria sia trascurabile rispetto alla massa dell'uccello, e la densità media minore $\rho_a \ll \rho_b$, si ottiene $\Delta \mathbf{F} = m_b \left( - \mathbf{g} + \ddot{\mathbf{r}}_b \right)$, o la componente verticale $F_z = m_b \left(g + a_{z,b} \right)$.

**Ma si può trascurare il moto dell'aria?** L'ipotesi di massa dell'aria trascurabile rispetto alla massa del volatile va comunque verificata: una gabbia cubica di lato $50 \, \text{cm}$ contiene circa $150 \text{kg}$ di aria, un fringuello pesa circa $30 \, \text{kg}$, un piccione circa $300 \, \text{kg}$.

**Caso particolare: uccello di densità uniforme.** Nel caso di densità uniforme del volatile, la sua massa può essere espressa come prodotto di volume e densità, $m_b = \rho_b V_b$, e il centro di massa del volatile coincide con il suo centro geometrico (vedi sotto); si può esprimere l'accelerazione del centro geometrico del volume d'aria in funzione del centro di massa del volatile,

$$\mathbf{r}_a^g = -\dfrac{V_b}{V_a}\mathbf{r}_b \ ,$$

e ottenere la seguente espressione della lettura della bilancia

$$\begin{aligned}
  \Delta \mathbf{F} 
  & = - m_b \mathbf{g} +  m_b \ddot{\mathbf{r}}_b + m_a \left( - \dfrac{V_b}{V_a} \ddot{\mathbf{r}}_b \right) + \rho_a V_b \mathbf{g} = \\
  & = - m_b \mathbf{g} +  \left( 1 - \frac{\rho_a}{\rho_b} \right) m_b \ddot{\mathbf{r}}_b + \frac{\rho_a}{\rho_b} m_b \mathbf{g} = \\
  & = - m_b \left( 1 - \frac{\rho_a}{\rho_b} \right) \left( \mathbf{g} - \ddot{\mathbf{r}}_b \right) \ .
\end{aligned}$$

**Forza aerodinamica agente sul volatile.** 

$$\dot{\mathbf{Q}}_b = \mathbf{R}^{ext,b} = \mathbf{F}^{aero} + \mathbf{P}_b \ .$$

Una volta calcolata la massa del volatile $m_b$ da una lettura costante della bilancia, in seguito risulta possibile (immediato nel caso di densità uniforme del volatile, invertendo la formula) misurare l'accelerazione del volatile $\ddot{\mathbf{r}}_b$ dalla lettura della bilancia $\Delta \mathbf{F}$. Risulta quindi possibile misurare la forza aerodinamica agente sul volatile

$$\begin{aligned}
  \mathbf{F}^{aero} 
  & = \dot{\mathbf{Q}}_b - \mathbf{P}_b = \\
  & = m_b \left( \ddot{\mathbf{r}}_b(\Delta \mathbf{F}) - \mathbf{g} \right) \ .
\end{aligned}$$

Nel caso di volatile posato sul pavimento o in volo con centro di massa in quiete, la forza aerodinamica equilibra il peso, $\mathbf{F}^{aero} = - \mathbf{P}_b$.


```{dropdown} Quantità di moto dell'aria

Il centro di massa del volume d'aria $V_a(t)$ contenuto all'interno della gabbia è

$$\mathbf{r}_a(t) := \frac{1}{m_a} \int_{V_a(t)} \rho_a(t) \mathbf{r} = \frac{1}{|V_a(t)|} \int_{V_a(t)} \mathbf{r} =: \mathbf{r}^g_a(t) \ ,$$

con $m_a = \rho_a |V_a(t)|$: il sotto-sistema aria è chiuso, e quindi ha massa costante; nell'ipotesi di densità costante, anche il volume d'aria contenuto è costante, $|V_a(t)| = |V_a|$.

Usando il teorema del trasporto di Reynolds per la derivata rispetto al tempo di integrali di volume, si trova l'espressione della velocità del centro di massa del volume d'aria

$$\begin{aligned}
  \mathbf{u}^g_a(t)
  & = \dfrac{d \mathbf{r}^g_a}{d t} = \\
  & = \dfrac{1}{|V_a|} \dfrac{d}{dt} \int_{V_a(t)} \mathbf{r} = \\
  & = \dfrac{1}{|V_a|} \left\{ \underbrace{ \int_{V_a(t)} \partial_t \mathbf{r} }_{=\mathbf{0}} + \oint_{\partial V_a(t)} \mathbf{r} \mathbf{u} \cdot \hat{\mathbf{n}} \right\} = \\
  & = \dfrac{1}{|V_a|} \int_{V_a(t)} \mathbf{u} \ ,
\end{aligned}$$

avendo usato il teorema della divergenza e l'incomprimibilità del fluido

$$\left\{ \oint_{\partial V} \mathbf{r} \mathbf{u} \cdot \hat{\mathbf{n}} \right\}_i = \oint_{\partial V} r_i u_k n_k = \int_{V} \partial_k (r_i u_k) = \int_{V} \delta_{ik} u_k + \int_{V} r_i \underbrace{u_{k/k}}_{=0} = \int_{V} \mathbf{u} \ .$$


La quantità di moto dell'aria all'interno della scatola può essere scritta come

$$\mathbf{Q}_a = \int_{V_a(t)} \rho_a \mathbf{u} = \rho_a \int_{V_a(t)} \mathbf{u} = m_a \mathbf{u}_a(t) = m_a \dfrac{d \mathbf{r}_a}{dt} \ .$$

```

```{dropdown} Centro geometrico - differenza di volumi

Usano la proprietà di additività delle proprietà geometriche, si può ricavare il legame tra i centri geometrici dei componenti del sistema. In particolare, per comodità si prende come riferimento il centro della gabbia, e si trova legame tra il centro geometrico del volume occupato dall'aria (che coincide con il centro di massa, nell'ipotesi di densità costante), e il centro geometrico del volume occupato dal volatile.

$$\mathbf{0} = \int_{V_{a} \cup V_b} \mathbf{r} = \int_{V_a} \mathbf{r} + \int_{V_b} \mathbf{r} = V_a \mathbf{r}^g_a + V_b \mathbf{r}^g_b \ ,$$

e quindi 

$$\mathbf{r}_a = - \dfrac{V_b}{V_a} \mathbf{r}_b \ .$$

Nel caso in cui l'uccello abbia densità uniforme, il centro geometrico coincide con il centro di massa, $\mathbf{r}^g_b = \mathbf{r}_b$.

```

```{dropdown} Tara e risultante delle forze di pressione
:open:

...

```
