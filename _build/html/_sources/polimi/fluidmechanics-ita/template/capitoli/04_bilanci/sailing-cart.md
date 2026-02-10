(fluid-mechanics:balances:ex-cart)=
# Sailing cart

::::{grid}
:gutter: 2

:::{grid-item-card} Exercise 4.11
:columns: 8

Siano $S_1$ la sezione del tubo di flusso a sinistra dell'elica, $S_2$ la sezione del tubo di flusso deviata dalla vela, $S_3$ la sezione del tubo di flusso che passa per traspirazione attraverso la vela. Si conosce l'area delle tre sezioni del tubo di flusso, la velocità del carrello $\mathbf{v} = v \hat{\mathbf{x}}$, la velocità relativa $\mathbf{u}^{rel}_1 = \mathbf{u}_1 - \mathbf{v}$ sulla sezione $S_1$, e la frazione $\alpha_3 \in [0,1]$ di flusso di massa che attraversa la vela. Siano $A_2 = \beta_2 A_1$ e $A_3 = \beta_3 A_1$.

...

:::

:::{grid-item-card}
:columns: 4

![](../../fig/cart.png)

:::

::::


![](../../fig/cart-volume.png)

**Ipotesi:** densità uniforme, regime stazionario, profili di velocità uniformi sulle sezioni, pressione ambiente sulle superficie $S_1$, $S_2$ del condotto e sulle superfici laterali del solido, forze di volume trascurabili $\mathbf{g}$,...

**Bilancio di massa.** I vettori normali sulle tre sezioni del tubo di flusso sono $\hat{\mathbf{n}}_1 = - \hat{\mathbf{x}}$, $\hat{\mathbf{n}}_2 = \hat{\mathbf{y}}$, $\hat{\mathbf{n}}_3 = \hat{\mathbf{x}}$. La velocità relativa al carrello sulla superficie laterale del volume tratteggiato non appartenente alle sezioni del tubo di flusso è uguale e contraria alla velocità del carrello, $\mathbf{u}^{rel}|_{S_0} = - \mathbf{v}$, nell'ipotesi che il fluido sia in quiete rispetto al sistema di riferimento inerziale rispetto al quale sono state scritte le equazioni, $\mathbf{u}|_{S_0} = \mathbf{0}$. La direzione della velocità sulla sezione $S_2$ è $\hat{\mathbf{t}}_2 = \hat{\mathbf{x}} \, \cos \theta + \hat{\mathbf{y}} \, \sin \theta$.

$$\begin{aligned}
  0 
  & = \underbrace{\dfrac{d}{dt} \int_{V} \rho}_{ = 0 \, \text{steady}} + \oint_{\partial V} \rho \mathbf{u}^{rel} \cdot \hat{\mathbf{n}} = \\
  & = \oint_{\partial V} \rho \mathbf{u} \cdot \hat{\mathbf{n}} \underbrace{ - \oint_{\partial V} \rho \mathbf{v} \cdot \hat{\mathbf{n}} }_{ = 0 \, \text{ for rigid $V$ and uniform $\rho$}} =  \\
  & = \int_{S_1 \cup S_2 \cup S_3} \rho \mathbf{u} \cdot \hat{\mathbf{n}} \ ,
\end{aligned}$$

e quindi

$$\begin{aligned}
  0
  & = \rho_1 u_{n,1} A_1 + \rho_2 u_{n,2} A_2 + \rho u_{n,3} A_3  = \\
  & = - \rho_1 u_{x,1} A_1 + \rho_2 u_{y,2} A_2 + \rho u_{x,3} A_3  
\end{aligned}$$

Si definisce $\dot{m}_1 := \rho u^{rel}_{x,1} A_1 = \rho \left( u_{x,1} - v \right) A_1$; il flusso attraverso $S_3$ è uguale a $\dot{m}_3 = \rho u^{rel}_{n,3} A_3 = \rho \left( u_{n,3} - v \right) A_3 = \alpha_3 \dot{m}_1$. Il flusso di massa attraverso la sezione $S_2$ vale quindi

$$\begin{aligned}
  \dot{m}_2 
  & = \rho u^{rel}_{n,2} A_2 = \\
  & = \rho u_{y,2} A_2 = \\
  & = \rho u_{x,1} A_1 - \rho u_{x,3} A_3 = \\
  & = \dot{m}_1 + \rho v A_1 - \left( \dot{m}_3 + \rho v A_3 \right) = \\
  & = \left( 1 - \alpha_3 \right) \dot{m}_1 + \rho v A_1 \left( 1 - \beta_3 \right) \ .
\end{aligned}$$

**Bilancio di quantità di moto.** Separando il contorno del volume fluido in 

$$\partial V_f = S_1 \cup S_2 \cup S_3 \cup S_{f,0} \cup S_{f,s} \ ,$$

si può manipolare il bilancio della quantità di moto 

$$\underbrace{\dfrac{d}{dt} \int_{V} \rho \mathbf{u}}_{=\mathbf{0} \, \text{steady}} + \oint_{\partial V} \rho \mathbf{u}  \mathbf{u}^{rel} \cdot \hat{\mathbf{n}} = \underbrace{\int_{V} \rho \mathbf{g}}_{=\mathbf{0} \, \text{negligible}} + \oint_{\partial V} \mathbf{t}_{\hat{\mathbf{n}}} \ ,$$

mantenendo solo i termini non nulli del flusso di quantità di moto (si annulla il contributo della superficie solida $S_{fs}$ poiché $\mathbf{u}^{rel} \cdot \hat{\mathbf{n}} = 0$, e il contributo della superficie libera $S_{f,0}$ dove $\mathbf{u}=\mathbf{0}$). Il termine di flusso di quantità di moto diventa

$$\begin{aligned}
  \oint_{\partial V} \rho \mathbf{u} \mathbf{u}^{rel} \cdot \hat{\mathbf{n}}
  & = \rho A_1 u_{n,1}^{rel} \mathbf{u}_1 +  \rho A_2 u_{n,2}^{rel} \mathbf{u}_2 +  \rho A_3 u_{n,3}^{rel} \mathbf{u}_3 = \\
  & = - \dot{m}_1 \mathbf{u}_1 + \dot{m}_2 \mathbf{u}_2 + \dot{m}_3 \mathbf{u}_3 = \\
  & = - \dot{m}_1 \mathbf{u}_1 + \left[ ( 1 - \alpha_3 ) \dot{m}_1 + \rho v A_1 ( 1 - \beta_3 ) \right] \mathbf{u}_2 + \alpha_3 \dot{m}_1 \mathbf{u}_3 = \ ,
\end{aligned}$$

con 

$$\begin{aligned}
  \mathbf{u}_1 & =   \hat{\mathbf{x}} u_1 = \hat{\mathbf{x}} \left( u_{x,1}^{rel} + v \right) = \hat{\mathbf{x}} \left( \frac{\dot{m}_1}{\rho A_1} + v \right) \\
  \mathbf{u}_2 & = \hat{\mathbf{t}}_2 u_3 = \hat{\mathbf{x}} \left( u_{2,x}^{rel} + v \right) + \hat{\mathbf{y}} u_{2,y}^{rel} = \hat{\mathbf{x}} \, v + \left( \hat{\mathbf{y}} u_{2,y}^{rel} + \hat{\mathbf{x}} u_{2,x}^{rel} \right) = \\
  & = \hat{\mathbf{x}} \, v + \frac{1}{\sin \theta} u_{2,y}^{rel} \, \hat{\mathbf{t}}_2 = \hat{\mathbf{x}} \, v + \frac{1}{\sin \theta} \frac{\dot{m}_2}{\rho A_2} \hat{\mathbf{t}}_2 \\
  \mathbf{u}_3 & =   \hat{\mathbf{x}} u_3 = \hat{\mathbf{x}} \left( u_{x,3}^{rel} + v \right) = \hat{\mathbf{x}} \left( \frac{\dot{m}_3}{\rho A_3} + v \right) \\
\end{aligned}$$

Manipolando il termine di sforzi di superficie, si può far comparire la risultante delle forze aerodinamiche sul solido

$$\begin{aligned}
  & \oint_{S_f} \mathbf{t}^{f} = \\
  & \quad = \int_{S_1 \cup S_2 \cup S_3} \mathbf{t}^{f} + \int_{S_{f,0}} \mathbf{t}^{f} + \int_{S_{fs}} \mathbf{t}^{f} = \\
  & \quad = \int_{S_1 \cup S_2 \cup S_3} \mathbf{t}^{f} + \int_{S_{f,0}} \mathbf{t}^{f} \underbrace{ - \int_{S_{sf}} \mathbf{t}^{s} - \int_{S_{s,0}} \mathbf{t}^{s} }_{= - \mathbf{F}^s } + \int_{S_{s,0}} \mathbf{t}^{s} = \\ 
\end{aligned}$$

Nell'ipotesi di poter trascurare l'area di contatto tra le ruote e il terreno, l'unione delle superfici $S_1$, $S_2$, $S_3$, $S_{f,0}$ e $S_{s,0}$ forma una superficie chiusa. Nell'ipotesi in cui[^pa-hp] lo sforzo su questa superficie chiusa sia dovuta unicamente alla pressione atmosferica, costante sulla superficie, questo contributo è identicamente nullo.

[^pa-hp]: E' un'ipotesi semplificativa per poter risolvere l'esercizio. E' lecito attendersi che lo sforzo sulle superfici abbia contributi viscosi e di una pressione non uniforme.

Dal bilancio della quantità di moto si ottiene quindi la risultante delle forze agenti sul corpo solido dovute al fluido,

$$\begin{aligned}
  \mathbf{F}^s 
  & = - \oint_{\partial V} \rho \mathbf{u} \mathbf{u}^{rel} \cdot \hat{\mathbf{n}} = \\
  & = \dots
\end{aligned}$$


**Bilancio di energia cinetica.** Usando il bilancio di energia cinetica,

$$\underbrace{\dfrac{d}{dt} \int_{V} \rho \dfrac{|\mathbf{u}|^2}{2}}_{= 0 \, \text{steady}} + \oint_{\partial V} \rho \dfrac{|\mathbf{u}|^2}{2} \mathbf{u}^{rel} \cdot \hat{\mathbf{n}} = \underbrace{\int_{V} \rho \mathbf{g} \cdot \mathbf{u}}_{=0 \, \text{negligible}} + \oint_{\partial V} \mathbf{t}_{\hat{\mathbf{n}}} \cdot \mathbf{u} - \int_V \nabla \mathbf{u} : \mathbb{T} \ ,$$

si può stimare la potenza necessaria al moto e che deve essere fornita dal motore.

---

**todo**

```{dropdown} old

In caso di fluido incomprimibile e dissipazione trascurabile

$$\int_V \nabla \mathbf{u} : \mathbb{T} = \int_V p \nabla \cdot \mathbf{u} + \int_{V} \nabla : \mathbb{S} = 0 \ ,$$

e il bilancio di energia cinetica diventa

$$\begin{aligned}
  \dot{m} \left( -\frac{|\mathbf{u}_1^2|}{2} +\frac{|\mathbf{u}_2^2|}{2} \right) 
  & = \int_{S_f, prop} \mathbf{t}^f \cdot \mathbf{u} - \int_{S_1 \cup S_2} p \hat{\mathbf{u}} \cdot \hat{\mathbf{n}} \\
  & = - \int_{S_s, prop} \mathbf{t}^s \cdot \mathbf{u} + p_1 A_1 u_{n,1} - p_2 A_2 u_{n,2} = \\
  & = - P^{r}_s + \dot{m}_{u,1} \frac{p_1}{\rho_1} - \dot{m}_2 \frac{p_2}{\rho_2} = && (\text{sup. in quiete}) \\
  & = - P^{r}_s + \dot{m} \left( \frac{p_1}{\rho_1} - \frac{p_2}{\rho_2} \right) = \\
\end{aligned}$$

avendo indicato con $P^{r}_s$ la potenza gli sforzi agenti sull'elica (ipotizzato che sia l'unica superficie solida in movimento) a causa del fluido, e con $\dot{m}_{u,k} := \rho_k A_k u_{n,k}$ il flusso di massa dove compare la velocità del fluido (rispetto al sistema di riferimento inerziale nel quale sono scritte le equazioni) e non la velocità relativa alla superficie. Il risultato caso di superfici in quiete $\dot{m} = \dot{m}_{u,k}$. La potenza degli sforzi agenti sull'elica

$$P^r_s = \dot{m} \left[ - \left( \frac{p_2}{\rho_2} + \frac{|\mathbf{u}_2|^2}{2} \right) + \left( \frac{p_2}{\rho_2} + \frac{|\mathbf{u}_2|^2}{2} \right) \right] = - \dot{m} \Delta p^{tot} \ .$$

Il bilancio di energia cinetica dell'elica è $\dot{K}^{prop} = P^{tot} = P^{power,s} + P^r_s$. In caso di funzionamento stazionario, l'energia cinetica dell'elica è costante e la potenza fornita dal motore equilibra la potenza degli sforzi agenti sull'elica dovuti al fluido,

$$P^{power,s} = - P^{r}_s = \dot{m} \Delta p^{tot} \ .$$

```
