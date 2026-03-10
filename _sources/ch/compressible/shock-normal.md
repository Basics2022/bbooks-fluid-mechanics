(compressible:shocks:normal)=
# Normal shocks

**Jump conditions.** A normal shock is a discontinuity in the physical quantities of the flow, with non-zero mass flux $\dot{m} \ne 0$ across it and zero tangential component of the velocity. [Jump conditions](compressible:jump-conditions) across a normal shock are

$$\begin{aligned}
  0 & = [ \dot{m} ] = [ \rho u_{n}^{rel} ]   \\
  \mathbf{u}_\mathbf{t} & = \mathbf{0} \\
  0 & = \dot{m} [ u_n ] + [ \, p \, ] = \dot{m} [ u_n^{rel} ] + [ \, p \, ]  \\ 
  0 & = \dot{m} [ h^{t,rel} ] = \dot{m} [ h^{t,rel}_n ] 
\end{aligned}$$

<!--
Across a shock wave, the flow undergoes a discontinuous change. For a steady, adiabatic, and inviscid flow of a **Perfect Ideal Gas (PIG)**, the Rankine-Hugoniot relations apply.
-->

(compressible:shocks:normal:pig)=
## Perfect ideal gas

For [perfect ideal gas](thermodynamics:pig), the ratio between quantities before and after normal shocks can be evaluated analitically.

**Notation.** Here $u_n^{rel} = u$ for brevity.

**Jump conditions.**

$$\begin{cases}
  \rho_1 u_1 = \rho_2 u_2 \\
  \rho_1 u_1^2 + p_1 = \rho_2 u_2^2 + p_2 \\
         \frac{u_1^2}{2} + h_1 =        \frac{u_2^2}{2} + h_2 \\
\end{cases}$$

### Quantities as a function of Mach numbers $M_1$, $M_2$

| Property | ... | ... |
| :--- | :--- | :--- |
| **Pressure**              | $\frac{p_2}{p_1}       = \frac{1 + \gamma M_1^2}{1 + \gamma M_2^2}$  | ... |
| **Density**               | $\frac{\rho_2}{\rho_1} = \frac{M_1^2}{M_2^2} \frac{1 + \gamma M_2^2}{1+ \gamma M_1^2}$ ... | ... |
| **Temperature**           | $\frac{T_2}{T_1}       = \left( \frac{1 + \gamma M_1^2}{1 + \gamma M_2^2} \right)^2 \frac{M_2^2}{M_1^2}$  | ... |
| **Velocity**              | $\frac{u_2}{u_1}       = \frac{M_2^2}{M_1^2} \frac{1 + \gamma M_1^2}{1 + \gamma M_2^2}$ | ... |
| **Speed of sound**        | $\frac{a_2}{a_1}       = \sqrt{\frac{T_2}{T_1}}$  | ... |
| **Entropy**               | $s_2 - s_1             = \frac{R}{\gamma-1} \ln \left\{ \left( \frac{1+ \gamma M_1^2}{1 + \gamma M_2^2} \right)^{1+\gamma} \left( \frac{M_2^2}{M_1^2} \right)^{\gamma} \right\}$  | ... |
| **Stagnation pressure**   | $\frac{p_{02}}{p_{01}} =$ ... | ... |
| **Other stag quantities** |                           ... | ... |

```{dropdown} Details

**Pressure.** From momentum equation

$$\begin{aligned}
  p_2 & = p_1 + \rho_1 u_1^2 - \rho_2 u_2^2   \\
\end{aligned}$$

$$\begin{aligned}
  \frac{p_2}{p_1}
  & = 1 + \frac{\rho_1}{p_1} u_1^2 - \frac{p_2}{p_1} \frac{\rho_2}{p_2} u_2^2 = && \left( a^2 = \gamma \frac{p}{\rho} \right) \\
  & = 1 + \gamma M_1^2 - \frac{p_2}{p_1} \gamma M_2^2 \ ,
\end{aligned}$$

and thus

$$\frac{p_2}{p_1} = \frac{1 + \gamma M_1^2}{1 + \gamma M_2^2} \ .$$

**Velocity.** Starting from mass jump condition

$$\begin{aligned}
  \frac{u_2}{u_1} 
  & = \frac{\rho_1}{\rho_2} = \\
  & = \frac{\rho_1}{p_1} \frac{p_2}{\rho_2} \frac{p_1}{p_2} = \\
  & = \frac{a_2^2}{a_1^2}\frac{p_1}{p_2} = \\
  & = \frac{u_2^2}{u_1^2} \frac{M_1^2}{M_2^2} \frac{p_1}{p_2}
\end{aligned}$$

and thus

$$\frac{u_2}{u_1} = \frac{M_2^2}{M_1^2} \frac{p_2}{p_1} = \frac{M_2^2}{M_1^2} \frac{1 + \gamma M_1^2}{1 + \gamma M_2^2} \ .$$

**Density.** Using mass jump condition, and the relation for $\frac{u_2}{u_1}$,

$$\frac{\rho_2}{\rho_1} = \frac{u_1}{u_2} = \frac{M_1^2}{M_2^2} \frac{1 + \gamma M_2^2}{1+ \gamma M_1^2} \ .$$

**Speed of sound.**

$$\frac{a_2}{a_1} = \frac{u_2}{M_2} \frac{M_1}{u_1} = \frac{M_2}{M_1} \frac{1 + \gamma M_1^2}{1 + \gamma M_2^2} \ .$$

**Temperature.**

$$\begin{aligned}
  \frac{T_2}{T_1}
  & = \frac{p_2}{R \rho_2} \frac{R \rho_1}{p_1} = \\
  & = \frac{1 + \gamma M_1^2}{1 + \gamma M_2^2} \cdot \frac{M_2^2}{M_1^2} \frac{1 + \gamma M_1^2}{1+ \gamma M_2^2} = \\
  & = \left( \frac{1 + \gamma M_1^2}{1 + \gamma M_2^2} \right)^2 \frac{M_2^2}{M_1^2} \ . 
\end{aligned}$$

**Entropy.**

<!--
$$\begin{aligned}
  s_1 - s_0 & = c_v \ln \left( \frac{p_1}{p_0} \right) - c_p \ln \left( \frac{\rho_1}{\rho_0} \right) \\ 
  s_2 - s_0 & = c_v \ln \left( \frac{p_2}{p_0} \right) - c_p \ln \left( \frac{\rho_2}{\rho_0} \right) \\ 
\end{aligned}$$

Thus,
-->

$$\begin{aligned}
  s_2 - s_1
  & = c_v \ln \left( \frac{p_2}{p_1} \right) - c_p \ln \left( \frac{\rho_2}{\rho_1} \right) = \\
  & = \frac{R}{\gamma-1} \left\{ \ln \left( \frac{p_2}{p_1} \right) - \gamma \ln \left( \frac{\rho_2}{\rho_1} \right) \right\} = \\
  & = \frac{R}{\gamma-1} \ln \left\{ \left( \frac{p_2}{p_1} \right) \left( \frac{\rho_2}{\rho_1} \right)^{-\gamma} \right\} = \\
  & = \frac{R}{\gamma-1} \ln \left\{ \left( \frac{1+ \gamma M_1^2}{1 + \gamma M_2^2} \left[ \frac{M_1^2}{M_2^2} \frac{1 + \gamma M_2^2}{1+ \gamma M_1^2}  \right]^{-\gamma} \right) \right\} = \\
  & = \frac{R}{\gamma-1} \ln \left\{ \left( \frac{1+ \gamma M_1^2}{1 + \gamma M_2^2} \right)^{1+\gamma} \left( \frac{M_2^2}{M_1^2} \right)^{\gamma} \right\}
\end{aligned}$$

Entropy determines a condition for feasible shocks, i.e. increasing entropy, $s_2 - s_1 \ge 0$.

```

### Relation between Mach numbers $M_1$, $M_2$

$$M_2^2 = \frac{M_1^2 + \frac{2}{\gamma-1}}{\frac{2\gamma}{\gamma-1}M_1^2 - 1}$$

```{dropdown} Details

**todo** *isn't there any cleaner way to derive the desired relation?*

Comparing the expression of the temperature ratio obtained above using equation of state and momentum equation, with the following expression obtained using energy equation

$$\begin{aligned}
  \frac{u_1^2}{2} + h_1 & = \frac{u_2^2}{2} + h_2 \\
  \frac{u_1^2}{2} + c_p T_1 & = \frac{u_2^2}{2} + c_p T_2 \\
  \frac{a_1^2 M_1^2}{2} + \frac{\gamma}{\gamma-1} R T_1 & = \frac{a_1^2 M_1}{2} + \frac{\gamma}{\gamma-1} R T_2 && \left( a^2 = \gamma R T \right) \\
  T_1 \left( \frac{M_1^2}{2} + \frac{1}{\gamma-1} \right) & = T_2 \left( \frac{M_2^2}{2} + \frac{1}{\gamma-1} \right) \\
  \quad \rightarrow \quad \frac{T_2}{T_1} & = \frac{\frac{M_1^2}{2} + \frac{1}{\gamma-1}}{\frac{M_2^2}{2} + \frac{1}{\gamma-1}}
\end{aligned}$$

it follows

$$\left( \frac{1 + \gamma M_1^2}{1 + \gamma M_2^2} \right)^2 \frac{M_2^2}{M_1^2} = \frac{\frac{M_1^2}{2} + \frac{1}{\gamma-1}}{\frac{M_2^2}{2} + \frac{1}{\gamma-1}}$$

...**todo** *do all the required algebra, to solve the equation. Be smart and gather binomial $M_1^2 - M_2^2$ and simplify*

```
<!--
$$\begin{aligned}
  M_2^2 
  & = \frac{(\gamma-1) M_1^2 + 2}{2 \gamma M_1^2 - (\gamma - 1)} = \\
  & = M_1^2 \left[ \frac{(\gamma-1) + \frac{2}{M_1^2} }{2 \gamma M_1^2 - (\gamma - 1)}  \right] \\ 
\end{aligned}$$

$$\frac{M_2^2}{M_1^2} = \frac{\frac{1}{M_1^2} + \frac{\gamma-1}{2}}{\gamma M_1^2 - \frac{\gamma-1}{2}}$$
-->

**Remarks.**
* $M_2(M_1 = 1) = 1$
* the derivative reads

  $$\begin{aligned}
    \frac{d M_2^2}{d M_1^2}
    & = \frac{\frac{2 \gamma}{\gamma-1}M_1^2 - 1 - \frac{2 \gamma}{\gamma-1} \left( M_1^2 + \frac{2}{\gamma-1} \right)}{\left( \dots \right)^2} = \\
    & = \frac{- 1 - \frac{2}{\gamma-1} }{\left( \dots \right)^2} = \\
    & = - \frac{\gamma+1}{\gamma-1} \left( 2 \gamma M_1^2 - (\gamma - 1) \right)^{-2} < 0 \ ,
  \end{aligned}$$

  and thus if $M_1^2 > 1$, then $M_2^2 < 1$, and viceversa. **Entropy condition** $s_2 - s_1 \ge 0$ defines the feasible shocks: **for a PIG, feasible shocks have $M_1 > 1$ and $M_2 < 1$**, i.e. supersonic flow becomes subsonic after a normal shock.

* the function is singular for $M_1^2 = \frac{\gamma-1}{2\gamma}$. This condition only occurs for $M_1 < 1$, i.e. it never happens for physical shocks.

```{dropdown} Entropy condition - PIG

$$\begin{aligned}
 \frac{\gamma-1}{R} (s_2 - s_1)
 & = \ln \left\{ \left( \frac{1+ \gamma M_1^2}{1 + \gamma M_2^2} \right)^{1+\gamma} \left( \frac{M_2^2}{M_1^2} \right)^{\gamma} \right\} = \\
 & = \ln \left\{ \left(\frac{ 2 \gamma M_1^2 - \gamma + 1}{\gamma + 1} \right)^{\gamma+1} \left( \frac{2 + ( \gamma - 1 ) M_1^2}{2 \gamma M_1^2 - \gamma + 1}  \right)^{\gamma} M_1^{-2 \gamma} \right\} = \\
 & = \ln \left\{ \frac{ 2 \gamma M_1^2 - \gamma + 1}{(\gamma + 1)^{\gamma+1}} \frac{(2 + ( \gamma - 1 ) M_1^2)^{\gamma}}{M_1^{2 \gamma}} \right\} \ ,
\end{aligned}$$

**Remarks.**

* For $M_1 = 1$, $x(M_1) = \{ \dots \}$
  
  $$\{ \dots \}(M_1=1) = \frac{(\gamma+1) (\gamma+1)^{\gamma+1}}{(\gamma+1)^{\gamma+1}} = 1 \ ,$$ 

  and thus

  $$s_2 - s_1 \propto \ln \{ \dots \} = 0 \ .$$

* the derivative w.r.t. $M_1^2$ reads

  $$\begin{aligned}
    & \frac{(\gamma+1)^{\gamma+1}}{2 \gamma M_1^2 - \gamma + 1} \frac{2 \gamma}{(\gamma+1)^{\gamma+1}} + \frac{M_1^{2 \gamma}}{(2 + (\gamma-1)M_1^2)^ \gamma } \left( \gamma (2 +(\gamma-1)M_1^2)^{\gamma-1} (\gamma-1) M_1^{-2\gamma} - (\dots) \gamma M_1^{2(\gamma-1)}  \right) = \\
    & = \frac{2 \gamma}{2 \gamma M_1^2 - \gamma + 1} + \frac{\gamma (\gamma-1)}{2 + (\gamma-1) M_1^2} - \frac{\gamma}{M_1^2} = \\
    & = \dots \text{(see below)} =  \\ 
    & = \frac{2 \gamma (\gamma-1) (M_1^2 - 1)^2}{(2 \gamma M_1^2 - \gamma + 1)(2 + (\gamma-1) M_1^2) M_1^2} \ .
  \end{aligned}$$

  The derivative is **always non-negative** and thus **the entropy condition $s_2 - s_1 \ge 0$ is satisfied only for $M_1 \ge 1$**, i.e. for supersonic inflow becoming subsonic (see above) after a normal shock.

$$\begin{aligned}
  & 4 \gamma M_1^2 + 2 \gamma (\gamma - 1) M_1^4 + \\
  & \quad + \underbrace{2 \gamma^2 (\gamma-1) M_1^4}_{1} - \underbrace{\gamma (\gamma-1)^2 M_1^2}_{0} + \\
  & \quad - 4 \gamma^2 M_1^2 - \underbrace{2 \gamma^2 ( \gamma - 1 ) M_1^4}_{1} + 2 \gamma ( \gamma - 1 ) + \underbrace{\gamma ( \gamma - 1 )^2 M_1^2}_{0} = \\
  & = 2 \gamma ( \gamma - 1 ) - M_1^2 4 \gamma ( \gamma - 1 ) + 2 \gamma ( \gamma - 1 ) M_1^4 = \\
  & = 2 \gamma ( \gamma - 1 ) ( M_1^2 - 1 )^2 \ .
\end{aligned}$$


```


### Quantities as a function of Mach numbers $M_1$

| Property |  |  |
| :--- | :--- | :--- |
| **Entropy** | $s_2 - s_1 = \frac{R}{\gamma - 1} \ln \left\{ \frac{ 2 \gamma M_1^2 - \gamma + 1}{(\gamma + 1)^{\gamma+1}} \frac{(2 + ( \gamma - 1 ) M_1^2)^{\gamma}}{M_1^{2 \gamma}} \right\}$ | $ \ge 0 $  |
| **Inflow  Mach number**   | $M_1$                                                                                          | $ \ge 1 $ |
| **Outflow Mach number**   | $M_2 = \frac{M_1^2 + \frac{2}{\gamma-1}}{\frac{2\gamma}{\gamma-1}M_1^2 - 1} $                  | $ \le 1 $ |
| **Pressure**              | $\frac{p_2}{p_1}       = 1 + \frac{2 \gamma}{\gamma + 1} ( M_1^2 - 1 )$                        | $ \ge 1 $ |
| **Density**               | $\frac{\rho_2}{\rho_1} = \left[ 1 - \frac{2}{\gamma+1}\frac{ M_1^2 - 1 }{M_1^2} \right]^{-1} $ | $ \ge 1 $ |
| **Velocity**              | $\frac{u_2}{u_1}       = 1 - \frac{2}{\gamma+1}\frac{ M_1^2 - 1 }{M_1^2}$                      | $ \le 1 $ |
| **Speed of sound**        | $\left(\frac{a_2}{a_1}\right)^2    = \left( 1 + \frac{2 \gamma}{\gamma + 1} ( M_1^2 - 1 ) \right) \left( 1 - \frac{2}{\gamma+1}\frac{ M_1^2 - 1 }{M_1^2}  \right)$  | $ \ge 1 $ |
| **Temperature**           | $\frac{T_2}{T_1}       = \left(\frac{a_2}{a_1}\right)^2 $  | $ \ge 1 $ |
| **Stagnation pressure**   | $\frac{p_{02}}{p_{01}} = $  | ... |
| **Other stag quantities** |                             | ... |

```{dropdown} Details

Mach number $M_2$ can be recast as

$$M_2^2 = \frac{2 + (\gamma-1)M_1^2}{2 \gamma M_1^2 - (\gamma-1)}$$

Let's evaluate the ratio of functions of Mach numbers apeparing in ratios of physical quantities

$$\begin{aligned}
  \frac{1 + \gamma M_1^2}{1 + \gamma M_2^2}
  & = \frac{1 + \gamma M_1^2}{1 + \gamma \frac{2 + (\gamma-1)M_1^2}{2 \gamma M_1^2 - (\gamma-1)}} = \\
  & = \frac{(1+\gamma M_1^2)(2 \gamma M_1^2 - \gamma + 1)}{2 \gamma M_1^2 - \gamma + 1 + 2 \gamma + \gamma ( \gamma - 1 )M_1^2 } = \\
  & = \frac{(1+\gamma M_1^2)(2 \gamma M_1^2 - \gamma + 1)}{\gamma M_1^2 + 1 + \gamma + \gamma^2 M_1^2} = \\
  & = \frac{(1+\gamma M_1^2)(2 \gamma M_1^2 - \gamma + 1)}{( \gamma + 1 ) ( 1 + \gamma M_1^2 )} = \\
  & = \frac{2 \gamma M_1^2 - \gamma + 1}{\gamma + 1} = \\
  & = 1 + \frac{2 \gamma ( M_1^2 - 1 )}{\gamma + 1} \ .
\end{aligned}$$

**Pressure.**

$$\frac{p_2}{p_1} = 1 + \frac{2 \gamma}{\gamma + 1} ( M_1^2 - 1 )$$

**Velocity.**

$$\begin{aligned}
  \frac{u_2}{u_1}
  & = \frac{M_2^2}{M_1^2} \frac{1+ \gamma M_1^2}{1+\gamma M_2^2} = \\
  & = \frac{2 + (\gamma-1) M_1^2}{(\gamma + 1)M_1^2} = \\
  & = \frac{2 + (\gamma+1) M_1^2 - 2 M_1^2}{(\gamma + 1)M_1^2} = \\
  & = 1 - \frac{2}{\gamma+1}\frac{ M_1^2 - 1 }{M_1^2} \ .
\end{aligned}$$

**Density.**

$$\begin{aligned}
  \frac{\rho_2}{\rho_1}
  & = \frac{u_1}{u_2} = \left[ 1 - \frac{2}{\gamma+1}\frac{ M_1^2 - 1 }{M_1^2} \right]^{-1} \\
\end{aligned}$$


**Speed of sound.**

$$\begin{aligned}
  \frac{a_2^2}{a_1^2} 
  & = \frac{\frac{p_2}{p_1}}{ \frac{\rho_2}{\rho_1} } = \\
  & = \left( 1 + \frac{2 \gamma}{\gamma + 1} ( M_1^2 - 1 ) \right) \left( 1 - \frac{2}{\gamma+1}\frac{ M_1^2 - 1 }{M_1^2}  \right) = \\
  & = 1 + \frac{2}{(\gamma+1) M_1^2} \left( \gamma M_1^2 - 1 \right) \left( M_1^2 - 1 \right) + \gamma \left( \frac{2}{\gamma+1} \right)^2 \left( \frac{M_1^2 - 1}{M_1} \right)^2
\end{aligned}$$

**Temperature.**

$$\frac{T_2}{T_1} = \frac{a_2^2}{a_1^2}$$

**Entropy.**

$$s_2 - s_1 = \ln \left\{ \frac{ 2 \gamma M_1^2 - \gamma + 1}{(\gamma + 1)^{\gamma+1}} \frac{(2 + ( \gamma - 1 ) M_1^2)^{\gamma}}{M_1^{2 \gamma}} \right\}$$



```

<!--

### Conservation Equations (Integral Form)
From the notes, for a control volume enclosing the shock:
* **Continuity:** $\rho_1 u_{n1} = \rho_2 u_{n2} \rightarrow \frac{\rho_2}{\rho_1} = \frac{u_{n1}}{u_{n2}}$
* **Normal Momentum:** $p_1 + \rho_1 u_{n1}^2 = p_2 + \rho_2 u_{n2}^2$
* **Energy (Adiabatic):** $h_1 + \frac{u_{n1}^2}{2} = h_2 + \frac{u_{n2}^2}{2} = h_0$

For a PIG, where $h = c_p T$ and $c_p = \frac{\gamma R}{\gamma - 1}$:

$$\frac{\gamma}{\gamma-1} \frac{p_1}{\rho_1} + \frac{u_{n1}^2}{2} = \frac{\gamma}{\gamma-1} \frac{p_2}{\rho_2} + \frac{u_{n2}^2}{2}$$

## Normal Shocks
In a normal shock, the flow is perpendicular to the wave front ($u = u_n$). 

### Pressure Ratio Derivation
Combining momentum and continuity:

$$p_2 - p_1 = \rho_1 u_1^2 - \rho_2 u_2^2 = \rho_1 u_1^2 \left( 1 - \frac{\rho_1}{\rho_2} \right)$$

Using the Mach number definition $u^2 = M^2 \gamma \frac{p}{\rho}$:

$$\frac{p_2}{p_1} = 1 + \frac{2\gamma}{\gamma+1}(M_1^2 - 1)$$

### Solving for $M_2$
By substituting the temperature ratio $T_2/T_1$ into the energy equation and equating it with the pressure/density ratios, we solve the quadratic for the downstream Mach number:

$$M_2^2 = \frac{M_1^2 + \frac{2}{\gamma-1}}{\frac{2\gamma}{\gamma-1}M_1^2 - 1}$$

> **Note:** As $M_1 \to \infty$, $M_2$ approaches a finite limit: $M_2 \to \sqrt{\frac{\gamma-1}{2\gamma}} \approx 0.378$ (for $\gamma = 1.4$).

-->


