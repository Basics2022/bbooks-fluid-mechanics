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

$$\begin{cases}
  \rho_1 u_1 = \rho_2 u_2 \\
  \rho_1 u_1^2 + p_1 = \rho_2 u_2^2 + p_2 \\
  \rho_1 \frac{u_1^2}{2} + h_1 = \rho_2 \frac{u_2^2}{2} + h_2 \\
\end{cases}$$

Mach number

$$M_2^2 = \frac{M_1^2 + \frac{2}{\gamma-1}}{\frac{2\gamma}{\gamma-1}M_1^2 - 1}$$

```{dropdown} Details
:open:

Using

$$$$

```

| Property | ... | ... |
| :--- | :--- | :--- |
| **Pressure**              | $\frac{p_2}{p_1}       =$ ... | ... |
| **Density**               | $\frac{\rho_2}{\rho_1} =$ ... | ... |
| **Temperature**           | $\frac{T_2}{T_1}       =$ ... | ... |
| **Velocity**              | $\frac{u_2}{u_1}       =$ ... | ... |
| **Speed of sound**        | $\frac{a_2}{a_1}       =$ ... | ... |
| **Stagnation pressure**   | $\frac{p_{02}}{p_{01}} =$ ... | ... |
| **Other stag quantities** |                           ... | ... |

```{dropdown} Details
:open:


```


---

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




