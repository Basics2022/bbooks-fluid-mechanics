(fluid-mechanics:balances:ex-cart-rest)=
# Sailing cart at rest

::::{grid}
:gutter: 2

:::{grid-item-card} Exercise 4.11
:columns: 8
:::

:::{grid-item-card}
:columns: 4

![](../../fig/cart-rest.png)

:::

::::

**Ipotesi:** densità uniforme, regime stazionario, profili di velocità uniformi sulle sezioni, pressione ambiente sulle superficie $S_1$, $S_2$ del condotto e sulle superfici laterali del solido, forze di volume trascurabili $\mathbf{g}$

**Bilancio di massa**

$$0 = \dfrac{d}{dt} \int_{V} \rho + \oint_{\partial V} \rho \mathbf{u}^{rel} \cdot \hat{\mathbf{n}}$$

$$0 = \rho_1 u^{rel}_{n,1} A_1 + \rho_2 u^{rel}_{n,2} A_2$$

Si definisce $\dot{m} := - \rho_1 u^{rel}_{n,1} A_1$ che nel problema in questione risulta uguale a $\dot{m} = \rho_2 u^{rel}_{n,2} A_2$, per il bilancio di massa.

**Bilancio di quantità di moto**

$$\dfrac{d}{dt} \int_{V} \rho \mathbf{u} + \oint_{\partial V} \rho \mathbf{u}  \mathbf{u}^{rel} \cdot \hat{\mathbf{n}} = \int_{V} \rho \mathbf{g} + \oint_{\partial V} \mathbf{t}_{\hat{\mathbf{n}}}$$

$$\begin{aligned}
  \dot{m} \left( - \mathbf{u}_1 + \mathbf{u}_2 \right) 
  & = \int_{S_1 \cup S_2} \mathbf{t}^{f} + \int_{S_{fs}} \mathbf{t}^{f} - \int_{S_{s,a}} \mathbf{t}^s + \int_{S_{s,a}} \mathbf{t}^s - \int_{S_{s,ground}} p_a \hat{\mathbf{n}} + \int_{S_{s,ground}} p_a \hat{\mathbf{n}} = \dots \\
  & = - \mathbf{F}^{s,f} - ( p_1 - p_a ) A_1 \hat{\mathbf{n}}_1 - ( p_2 - p_a ) A_2 \hat{\mathbf{n}}_2 - \hat{\mathbf{z}} p_a A_{ground} \ .
\end{aligned}$$

La forza agente sul solido dovuta all'interazione con il fluido vale quindi

$$\mathbf{F}^{s,f} = - ( p_1 - p_a ) A_1 \hat{\mathbf{n}}_1 - ( p_2 - p_a ) A_2 \hat{\mathbf{n}}_2 + \dot{m} \left( \mathbf{u}_1 - \mathbf{u}_2 \right) - \hat{\mathbf{z}} p_a A_{ground} \ .$$

In condizioni di statica del solido, la risultante della reazione vincolare a terra $\mathbf{F}^r$ deve quindi equilibrare la forza esercitata dal fluido sul sistema

$$\mathbf{0} = \mathbf{R}^{ext} = \mathbf{F}^{f,s} + \mathbf{F}^r \ .$$

**Bilancio di energia cinetica**

$$\dfrac{d}{dt} \int_{V} \rho \dfrac{|\mathbf{u}|^2}{2} + \oint_{\partial V} \rho \dfrac{|\mathbf{u}|^2}{2} \mathbf{u}^{rel} \cdot \hat{\mathbf{n}} = \int_{V} \rho \mathbf{g} \cdot \mathbf{u} + \oint_{\partial V} \mathbf{t}_{\hat{\mathbf{n}}} \cdot \mathbf{u} - \int_V \nabla \mathbf{u} : \mathbb{T}$$

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
