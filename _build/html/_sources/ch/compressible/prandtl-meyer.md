(compressible:prandtl-meyer)=
# Expansion fans - Prandtl-Meyer relation

Under the assumptions of:

1. ideal flow - negligible viscosity and heat conduction
2. no shocks, so that the differential equation holds in the whole domain
3. uniform entropy and zero vorticity at the inflow of the domain

the flow in the whole domain is **homoentropic**, $s(\mathbf{r}, t) = \overline{s}$, and **irrotational**, $\boldsymbol\omega(\mathbf{r},t) = \mathbf{0}$.

```{dropdown} Entropy

Under the assumptions:
1. ideal flow - negligible viscosity an heat conduction
2. no shock

the [differential entropy equation](compressible:entropy) becomes

$$D_t s = 0 \ ,$$

and it governs the evolution of the entropy in the whole domain (as it holds in the whole domain in absence of shocks). Thus, the entropy of any material particle is constant in time. If all the material particles entering the domain have the same entropy, it immediately follows that the entropy is uniform in the whole domain, 

$$s(\mathbf{r},t) = \overline{s} \ .$$

```

```{dropdown} Vorticity

Under ideal flow assumptions - negligible viscosity and heat conduction - [vorticity dynamical equation](compressible:vorticity) reads

$$
  D_t \boldsymbol\omega = \boldsymbol\omega \cdot \nabla \mathbf{u} - \boldsymbol\omega \nabla \cdot \mathbf{u} + \frac{1}{\rho^2} \nabla \rho \times \nabla p
$$

Using mass equation, $D_t \rho + \rho \nabla \cdot \mathbf{u} = 0$, and thus $-\nabla \cdot \mathbf{u} = D_t \rho$. Expressing the pressure field as a function of density and entropy as thermodynamic independent variables, $p(\rho, s)$, its gradient becomes

$$\nabla p = \left( \frac{\partial p}{\partial \rho} \right)_s \nabla \rho + \left( \frac{\partial p}{\partial s} \right)_\rho \nabla s \ .$$

Under the assumptions of homoentropic flow, $s(\mathbf{r},t) = \overline{s}$, it follows that $\nabla s = \mathbf{0}$ and $\nabla p = a^2(\rho, \overline{s}) \nabla \rho$. Under these assumptions, the term $\nabla \rho \times \nabla p$ is identically zero.

The vorticity equation becomes (after multiplying by $\frac{1}{\rho}$, $\rho \ne 0$),

$$\begin{aligned}
  & \frac{1}{\rho} D_t \boldsymbol\omega = \frac{1}{\rho} \boldsymbol\omega \cdot \nabla \mathbf{u} - \frac{1}{\rho} \boldsymbol\omega \nabla \cdot \mathbf{u} \\
  & \frac{1}{\rho} D_t \boldsymbol\omega = \frac{1}{\rho} \boldsymbol\omega \cdot \nabla \mathbf{u} + \frac{1}{\rho^2} \boldsymbol\omega D_t \rho \\
  & \frac{1}{\rho} D_t \boldsymbol\omega - \frac{1}{\rho^2} \boldsymbol\omega D_t \rho  = \frac{1}{\rho} \boldsymbol\omega \cdot \nabla \mathbf{u} \\
  & D_t\left( \frac{ \boldsymbol\omega }{\rho} \right) = \frac{ \boldsymbol\omega }{\rho} \cdot \nabla \mathbf{u} \\
\end{aligned}$$

This equation is formally the same as the vorticity equation for incompressible flow with uniform density: here the vector field $\frac{\boldsymbol\omega}{\rho}$
- evolves as a material vector
- if it's zero at a point in space and time, it remains equal to zero along the trajectory of the material particle
- if it's zero at a set of points where material points enter the domain (inflow), it's equal to zero on all the trajectories originating from those points. If every trajectory in the domain originates in a irrotational region of the flow, and there's no shock in the domain so that the differential equation holds, the flow is irrotational in the whole domain.

```

Under these assumptions, the governing equations of the flow are the homoentropic Euler equations, i.e. in convective form using $\rho, \mathbf{u}$ as the dynamical variables

$$\begin{aligned}
  & D_t \rho + \rho \nabla \cdot \mathbf{u} = 0 \\
  & \rho D_t \mathbf{u} + a^2(\rho, \overline{s}) \nabla \rho = \mathbf{0} \ ,
\end{aligned}$$

with the constraint $s(\mathbf{r}, t) = \mathbf{0}$, and a constitutive equation to write the speed of sound as a function of the independent thermodynamic variables. As the entropy is uniform, it can be treated as a parameter, so that there's need for only one independent thermodynamic variable, here $\rho$. All the other thermodynamic variables can be evaluated a posteriori, once the density field is known as $f(\mathbf{r},t) = f(\rho(\mathbf{r},t), \overline{s})$, with the notational abuse of using $f$ for the same physical quantity, but for functions with different arguments.

```{prf:example} Perfect ideal gas

For a perfect ideal gas,

$$\frac{p}{\rho} = R T \ ,$$

and the internal energy is a function of the temperature $T$ only

$$e = c_v T \ ,$$

with a constant heat capacity at constant volume $c_v$. Using the first principle of thermodynamics

$$de = T ds + \frac{p}{\rho^2} d \rho \ ,$$

it follows, from Meyer relation and the definition of heat coefficient ratio $\gamma$ listed below,

$$\begin{aligned}
  d p 
  & = d \rho R T + \rho R dT = \\
  & = d \rho R T + \rho R \frac{1}{c_v} de = \\
  & = d \rho R T + \rho R \frac{1}{c_v} \left[ T ds + \frac{p}{\rho^2} d \rho \right] = \\
  & = \frac{R}{c_v} \rho T d s + \left[ 1 + \frac{R}{c_v}  \right] R T d \rho = \\
  & = \frac{R}{c_v} \rho T d s + \left[ 1 + \gamma - 1  \right] R T d \rho = \\
  & = \frac{R}{c_v} \rho T d s + \gamma R T d \rho \ ,
\end{aligned}$$

so that the speed of sound is 

$$a^2(\rho, s) = \left( \frac{\partial p}{\partial \rho} \right)_s = \gamma R T(\rho, s) \ .$$

Meyer relation and heat coefficient ratio used above are

$$\begin{aligned}
  & c_p = c_v + R            && \text{(Meyer relation)}\\
  & \gamma = \frac{c_p}{c_v} && \text{(Heat coefficient ratio)} \ ,
\end{aligned}$$

so that 

$$\begin{aligned} 
  \frac{c_v}{R} & = \frac{1}{\gamma - 1} \\
  \frac{c_p}{R} & = \frac{\gamma}{\gamma - 1} \\
\end{aligned}$$
```

- Link to [Method of characteristics:Homoentropic inviscid compressible flows - 2d](https://basics2022.github.io/bbooks-math-miscellanea/ch/pde/characteristics.html#euler-equations-for-homoentropic-inviscid-compressible-flows-2d)




A steady expansion fan at a sharp corner connects to regions of the domain with homogeneous properties, with supersonic flows.

