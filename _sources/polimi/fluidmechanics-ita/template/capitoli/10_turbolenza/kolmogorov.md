(fluid-mechanics:turbulence:rans-energy)=
# Scales of turbulence

Kolmogorov scales: large, inertial, viscous scales

Power-law for inertial scales...

Turbulence involves different characteristic scales[^scale-qualitative], with their own characteristic length, time and relevant physical processes. While large scales usually depends on teh geometry of the flow, smaller scales have universal features for different flows: within this universal range, inertial subrange and dissipation range can be identified.

[^scale-qualitative]: Roughly speaking, the characteristic dimension, velocity,... of the vortices. But what's a vortex?

**Large scales.**

**Inertial subrange.** Assumption: turbulence in equilibrium. Spectral energy density $E(\kappa)$[^spectral-energy-density] is written as a function of dissipation $\varepsilon$ (equal to production, in equilibrium), and a length scale $\ell$ or a wave number $\kappa$. From dimensional analysis

[^spectral-energy-density]: Spectral energy density is defined as the energy density per unit wave-length, $E = \int_{\kappa = 0}^{+\infty} E(\kappa) \, d \kappa$, and so it has physical dimension $[ E(\kappa) ] = [ E ][ L ] = L^3 T^{-2}$.

$$[ E(\kappa) ] = \text{L}^3 \text{T}^{-2} \quad , \quad [ \varepsilon ] = \text{L}^2 \text{T}^{-3} \quad , \quad [ \kappa ] = \text{L}^{-1} \ ,$$

it follows

$$E \propto \varepsilon^{\frac{2}{3}} \kappa^{-\frac{5}{3}}$$


```{dropdown} Dimensional analysis

From

$$E = \varepsilon^\alpha \kappa^\beta \ ,$$

it follows

$$\begin{cases}
   3 = 2 \alpha - \beta \\
  -2 =-3 \alpha 
\end{cases}$$

and thus $\alpha = \frac{2}{3}$ and $\beta = \frac{4}{3} - 3 = - \frac{5}{3}$.

```

**Kolmogorov scales.** Two relevant physical quantities: $\nu$ kinematic viscosity, average rate of dissipation per unit-mass $\varepsilon$ or $\mathscr{D}$, with physical dimensions

$$[\nu] = \frac{\text{L}^2}{\text{T}} \quad , \quad [ \mathscr{D} ] = \frac{\text{L}^2}{\text{T}^3} \ .$$

With these two relevant physical quantities, it's possible to build characteristic length, time, velocity and Reynolds number (built with the characteristic dimensions, no surprise it goes to 1)

$$
\ell_{\eta} := \left( \frac{\nu^3}{\varepsilon} \right)^{\frac{1}{4}}  \quad , \quad 
\tau_{\eta} := \left( \frac{\nu}{\varepsilon} \right)^{\frac{1}{2}}  \quad , \quad 
   U_{\eta} := \frac{\ell_{\eta}}{\tau_{\eta}} = \left( \nu \varepsilon \right)^{\frac{1}{4}}  \quad , \quad 
  Re_{\eta} := \frac{U_{\eta} \ell_{\mu}}{\nu} = 1
$$

**todo** evaluate the ratio of characteristic dimension of the viscous range with the chacteristic dimension of the problem in terms of Reynolds' number. Which assumptions to be made to get a Reynolds number of the large scales? Especially about $\varepsilon$.

Under the assumption of [turbulence in equilibrium](fluid-mechanics:turbulence:rans-energy:turbulence-in-equilibrium), dimensional analysis gives

$$\varepsilon = \frac{U^3}{L} \ ,$$

and thus

$$
\frac{\ell_{\eta}}{L} = \text{Re}^{-\frac{3}{4}} \quad , \quad
\frac{\tau_{\eta}}{T} = \text{Re}^{-\frac{1}{2}} \quad , \quad
\frac{U_{\eta}}{U} = \text{Re}^{-frac{1}{4}} \ .
$$

These relation gives an estimate of the spatial resolution &mdash; i.e. the dimension of the mathematical problem &mdash; required by a numerical methods to fully resolve all the structures in the flow. In a 3-dimensional domain of side $L$, grid spacing should be of order $\Delta x \sim \ell_{\eta} \sim L \, \text{Re}^{-\frac{3}{4}}$, and thus the number of grid cells approximately $N \sim \left\frac{L}{\ell_{\tau}}\right)^3 = \text{Re}^{\frac{9}{4}}$.
