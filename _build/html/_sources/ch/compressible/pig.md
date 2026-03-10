(compressible:pig)=
# Perfect Ideal Gas (PIG)

**todo** *Add details, and link to [Thermodynamics](https://basics2022.github.io/bbooks-physics-thermodynamics/intro.html) to deal with thermodynamic potentials, coefficients and derivatives in the most general way*

---

**Equation of state.**

$$p = \rho R T \ ,$$

with $R = \frac{R_u}{M_m}$, being $M_m$ the molar mass of the gas and $R_u$ the **universal gas constant**

$$R_u = 8134.46 \frac{\text{J}}{\text{kmol} \, \text{K}} \ .$$

```{prf:example} Molar mass of dry air - mixture of gas

Let the composition of dry air: $\text{N}_2: \, 78.08\%$, $\text{O}_2: \, 20.95 \%$, $\text{Ar}: \, 0.93 \%$, $\text{CO}_2: \, 0.04\%$

...

$$M_{m, air} = 28.97 \, \frac{\text{kg}}{\text{kmol}} \ .$$

Thus the value of gas constant for dry air is

$$R_{air} = \frac{R_u}{M_{m,air}} = \frac{8314.46 \frac{\text{J}}{\text{kmol} \,\text{K}}}{ 28.97 \frac{\text{kg}}{\text{kmol}}} = 287.00 \frac{\text{J}}{\text{kg} \, \text{K}} \ .$$

```

**Internal energy and enthalpy.** In perfect ideal gas, energy and enthalpy are function of temperature only, with constant heat coefficients $c_v$, $c_p$

$$\begin{aligned}
  e & = c_v T \\
  h & = c_p T 
\end{aligned}$$

**Heat coefficient ratio.**

$$\gamma = \frac{c_p}{c_v}$$

**Meyer relation.**

$$c_p - c_v = R$$

Thus, 

$$\begin{aligned}
  \frac{c_v}{R} & = \frac{     1}{\gamma-1} \\
  \frac{c_p}{R} & = \frac{\gamma}{\gamma-1} 
\end{aligned}$$

**Entropy.** Starting from the first principle of thermodynamics

$$de = T ds + \frac{p}{\rho^2} d \rho \ ,$$

with $d e = c_v dT$, it's possible to write the differential of entropy as

$$\begin{aligned}
  d s
  & = c_v \frac{dT}{T} - R \frac{d \rho}{\rho} = \\
  & = c_v \frac{dp}{p} - c_p \frac{d \rho}{\rho} = \\
  & = c_p \frac{dT}{T} - R \frac{d p}{p} \ ,
\end{aligned}$$

having used the equation of state, Meyer relation and the relation between differentials of thermodynamic quantities, like

$$\frac{d T}{T} = \frac{ d\left(\frac{p}{\rho R} \right)}{ \frac{p}{\rho R} } = \frac{\rho}{p} \left( \frac{dp}{\rho} - \frac{p}{\rho^2} d \rho \right) = \frac{dp}{p} - \frac{d \rho}{\rho} \ .$$

The finite difference between two thermodynamic states immediately follows from integration (being $R$, $c_v$, $c_p$ constant for a PIG),

$$\begin{aligned}
  s - s_0
  & = c_v \ln \left( \frac{T}{T_0} \right) - R   \ln \left( \frac{\rho}{\rho_0} \right) = \\
  & = c_v \ln \left( \frac{p}{p_0} \right) - c_p \ln \left( \frac{\rho}{\rho_0} \right) = \\
  & = c_p \ln \left( \frac{T}{T_0} \right) - R   \ln \left( \frac{   p}{   p_0} \right) \ ,
\end{aligned}$$

**Speed of sound.** The speed of sound in a medium is defined as[^speed-of-sound-acoustics]

[^speed-of-sound-acoustics]: The definition of the speed of sound naturally appears in [acoustics]() and in the method of characteristic for hyperbolic problems, like unsteady Euler equations...

$$a^2 = \left( \dfrac{\partial p}{\partial \rho} \right)_s \ .$$

For a PIG, relation (**todo** *Add ref*) links pressure, density and entropy. This relation can be recast as

$$\frac{p}{p_0}(\rho, s; \rho_0, s_0) = \frac{\rho^\gamma}{\rho_0^\gamma} e^{ (\gamma-1) \frac{s-s_0}{R} } \ .$$

Direct evaluation of the partial derivative at constant $s$ gives the expression of speed of sound for a PIG

$$a^2 = \gamma R T = \gamma \frac{p}{\rho} $$

```{dropdown} Details
:open:

$$\begin{aligned}
  a^2
  & = \left( \dfrac{\partial p}{\partial \rho} \right)_s = \\
  & = \left( \dfrac{\partial}{\partial \rho} \right)_s \frac{\rho^{\gamma}}{\rho_0^{\gamma}} e^{(\gamma-1)\frac{s-s_0}{R}} = \\
  & = \gamma \rho^{-1} \frac{\rho^{\gamma}}{\rho_0^{\gamma}} e^{(\gamma-1)\frac{s-s_0}{R}} = \\
  & = \gamma \frac{p}{\rho} = \\
  & = \gamma R T \ .
\end{aligned}$$



```

