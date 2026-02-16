(compressible:bernoulli)=
# Bernoulli's theorem in compressible fluid mechanics

Assuming no discontinuity occurs in physical quantities (reasonable for viscous and diffusive fluids?), the differential form of governing equations holds.
Starting from governing equations of compressible fluids,

$$\begin{aligned}
  & \dfrac{D \rho}{D t} = - \rho \nabla \cdot \mathbf{u} \\
  & \rho \dfrac{D \mathbf{u}}{D t} = \rho \mathbf{g} + \nabla \cdot \mathbb{T} \\
  & \rho \dfrac{D e^t}{D t} = \rho \mathbf{g} \cdot \mathbf{u} + \nabla \cdot (\mathbb{T} \cdot \mathbf{u}) - \nabla \cdot \mathbf{q} \\
\end{aligned}$$

with the stress tensor sum of a pressure and viscous contribution, $\mathbb{T} = - p \mathbb{I} + \mathbb{S}$. For Newtonian fluids, viscous stress tensor can be written as

$$\mathbb{S} = 2 \mu \mathbb{D} + \lambda \left( \nabla \cdot \mathbf{u} \right) \mathbb{I} \ .$$

Total energy per unit mass $e^t$ is the sum of internal and kinetic energy, $e^t = e + \frac{|\mathbf{u}|^2}{2}$. Total derivative operator reads

$$\dfrac{D}{Dt} = \dfrac{\partial }{\partial t} + \mathbf{u} \cdot \nabla $$

Total energy equation can be recast as

$$\rho \mathbf{u} \cdot \left[ \nabla e^t - \mathbf{g} - \frac{1}{\rho} \nabla \cdot \mathbb{T} \right] = - \rho \dfrac{\partial e^t}{\partial t} + \nabla \mathbf{u} : \mathbb{T} - \nabla \cdot \mathbf{q} $$

Keeping only conservative (pressure) contributions to stress on the LHS

$$\begin{aligned}
  \rho \mathbf{u} \cdot \left[ \nabla e^t - \mathbf{g} + \frac{1}{\rho} \nabla P \right] & = - \rho \dfrac{\partial e^t}{\partial t} + \mathbf{u} \cdot \nabla \cdot \mathbb{S} - P \, \nabla \cdot \mathbf{u} + \nabla \mathbf{u} : \mathbb{S} - \nabla \cdot \mathbf{q} \\
  \rho \mathbf{u} \cdot \left[ \nabla  e^t + \nabla \chi + \frac{1}{\rho} \nabla P \right] & = - \rho \dfrac{\partial e^t}{\partial t} + \mathbf{u} \cdot \nabla \cdot \mathbb{S} + \dfrac{P}{\rho} \dfrac{D \rho}{D t} + \nabla \mathbf{u} : \mathbb{S} - \nabla \cdot \mathbf{q} \\
  \rho \mathbf{u} \cdot \left[ \nabla  e^t + \nabla \chi + \frac{1}{\rho} \nabla P \right] & = - \rho \dfrac{\partial e^t}{\partial t} + \mathbf{u} \cdot \nabla \cdot \mathbb{S} + \dfrac{P}{\rho} \dfrac{\partial \rho}{\partial t} + \dfrac{P}{\rho} \mathbf{u} \cdot \nabla \rho + \nabla \mathbf{u} : \mathbb{S} - \nabla \cdot \mathbf{q} \\
  \rho \mathbf{u} \cdot \nabla \left[ e^t + \chi + \frac{P}{\rho} \right] & = - \rho \dfrac{\partial e^t}{\partial t} + \dfrac{P}{\rho} \dfrac{\partial \rho}{\partial t} + \nabla \cdot \left( \mathbb{S} \cdot \mathbf{u} \right) - \nabla \cdot \mathbf{q} \\
  \rho \mathbf{u} \cdot \nabla \left[ e^t + \chi + \frac{P}{\rho} \right] & = - \rho \dfrac{\partial e^t}{\partial t} + \underbrace{\dfrac{P}{\rho} \dfrac{\partial \rho}{\partial t} - \rho \dfrac{\partial P}{\partial t}}_{= - \rho \frac{\partial }{\partial t} \left( \frac{P}{\rho} \right)} + \rho \dfrac{\partial P}{\partial t} + \nabla \cdot \left( \mathbb{S} \cdot \mathbf{u} \right) - \nabla \cdot \mathbf{q} \\
  \rho \mathbf{u} \cdot \nabla \left[ e^t + \chi + \frac{P}{\rho} \right] & = - \rho \dfrac{\partial }{\partial t} \left( e^t + \dfrac{P}{\rho} \right) + \rho \dfrac{\partial P}{\partial t} + \nabla \cdot \left( \mathbb{S} \cdot \mathbf{u} \right) - \nabla \cdot \mathbf{q} \\
\end{aligned}$$

```{prf:theorem} Bernoulli's theorem for compressible flow on streamlines

Now, for steady flows $\frac{\partial }{\partial t} \equiv 0$, with negligible viscous stress $\mathbb{S} \equiv \mathbb{0}$ and heat conduction $\mathbf{q} \equiv 0$, **Bernoulli's polynomial is constant for every point of a streamline**, as

$$\rho \mathbf{u} \cdot \nabla \left[ e + \dfrac{|\mathbf{u}|^2}{2} + \frac{P}{\rho} + \chi \right] = 0 \ .$$

```

```{prf:theorem} Dynamical equation for total enthalpy

Governing equations of fluid mechanics can be recast to get a dynamical equation for the total enthaply $h^t = e^t + \frac{P}{\rho}$, whose convective form reads

$$\rho \dfrac{D h^t}{D t} = - \rho \mathbf{u} \cdot \nabla \chi + \rho \dfrac{\partial P}{\partial t} + \nabla \cdot \left( \mathbb{S} \cdot \mathbf{u} - \mathbf{q} \right) \ . $$


```

```{prf:theorem} Dynamical equation for Bernoulli's polynomial

If the conservative force field per unit mass $\mathbf{g} = - \nabla \chi$ has no explicit dependence on time, $\partial_t \chi = 0$ and $D_t \chi = \mathbf{u} \cdot \nabla \chi$, it's possible to write a dynamical equation for the Bernoulli's polynomial, $B = h^t + \chi$,

$$\rho \dfrac{D B}{D t} = \rho \dfrac{\partial P}{\partial t} + \nabla \cdot \left( \mathbb{S} \cdot \mathbf{u} - \mathbf{q} \right) \ , $$

```







