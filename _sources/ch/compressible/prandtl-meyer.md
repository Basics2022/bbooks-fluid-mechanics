(compressible:prandtl-meyer)=
# Expansion fans - Prandtl-Meyer relation

A Prandtl-Meyer expansion fan is a continuous centering of Mach waves that occurs when a **supersonic flow** is turned "away" from itself, such as around a convex corner. The flow is homoentropic, and the flow properties (density, pressure, temperature, velocity,...) vary smoothly across the fan while the Mach number increases. The fan connects two regions of the domain with uniform properties.

**todo** 
- *Figure*
- *Script with Euler solver in 2-dimensional domains. To be written, so far only 1-d solver on GDrive*

---

Under the assumptions of:

1. ideal flow - negligible viscosity and heat conduction
2. no shocks, so that the differential equation holds in the whole domain
3. uniform entropy and zero vorticity at the inflow of the domain

the flow in the whole domain is **homoentropic**, $s(\mathbf{r}, t) = \overline{s}$, and **irrotational**, $\boldsymbol\omega(\mathbf{r},t) = \mathbf{0}$.

Under the additional assumption of steady flow and uniform conditions at inflow, the flow is **homo-total-enthalpic**, i.e. $h^t(\mathbf{r}) = \overline{h}^t$.

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

```{dropdown} Total enthalpy - steady flow

The differential form of total energy equation reads

$$\rho \partial_t e^t + \rho \mathbf{u} \cdot \nabla e^t = \rho \mathbf{g} \cdot \mathbf{u} + \nabla \cdot \left( \mathbb{T} \cdot \mathbf{u} \right) - \nabla \cdot \mathbf{q} \ ,$$

with the stress tensor of a Newtonian fluid $\mathbb{T} = - p \mathbb{I} + \mathbb{S}$, and the viscous stress tensor $\mathbb{S} = 2 \mu \mathbb{D} + \lambda \left( \nabla \cdot \mathbf{u} \right) \mathbb{I}$. For an ideal flow, $\mathbb{S} = \mathbb{0}$, $\mathbf{q} = \mathbf{0}$. If volume force is negligible, $\mathbf{g}=\mathbf{0}$. Under these assumptions, 

$$\begin{aligned}
  \rho \partial_t e^t + \rho \mathbf{u} \cdot \nabla e^t
  & = - \nabla \cdot ( p \mathbf{u} ) = \\
  & = - \mathbf{u} \cdot \nabla p - p \nabla \cdot \mathbf{u} = \\
  & = - \rho \mathbf{u} \cdot \frac{ \nabla p }{\rho} - \frac{p}{\rho} \left( - \partial_t \rho - \mathbf{u} \cdot \nabla \rho \right) = \\
  & = \frac{p}{\rho} \partial_t \rho - \rho \mathbf{u} \cdot \left[ \frac{\nabla p}{\rho} - \frac{p}{\rho^2} \nabla \rho \right] = \\ 
  & = \frac{p}{\rho} \partial_t \rho - \rho \mathbf{u} \cdot \nabla \left( \frac{p}{\rho} \right) \ ,
\end{aligned}$$

or

$$-\rho \left[ \partial_t e^t - \frac{p}{\rho^2} \partial_t \rho \right] = \rho \mathbf{u} \cdot \nabla h^t \ ,$$

with the total enthalpy $h^t = e^t + \frac{p}{\rho}$. Under steady conditons, $\partial_t \equiv 0$, it follows that

$$ \rho \mathbf{u} \cdot \nabla h^t = 0 \ ,$$

i.e. the total enthalpy is constant on every trajectory. If the physical quantities are uniform at the inflow, total enthalpy is uniform in the whole domain, and not only on every individual trajectory, i.e. the flow is **homo-total-enthalpic**.

```

Under these assumptions, the governing equations of the flow are the homoentropic Euler equations, i.e. in convective form using $\rho, \mathbf{u}$ as the dynamical variables

$$\begin{aligned}
  & D_t \rho + \rho \nabla \cdot \mathbf{u} = 0 \\
  & \rho D_t \mathbf{u} + a^2(\rho, \overline{s}) \nabla \rho = \mathbf{0} \ ,
\end{aligned}$$

with the constraint $s(\mathbf{r}, t) = \overline{s}$, and a constitutive equation to write the speed of sound as a function of the independent thermodynamic variables. As the entropy is uniform, it can be treated as a parameter, so that there's need for only one independent thermodynamic variable, here $\rho$. All the other thermodynamic variables can be evaluated a posteriori, once the density field is known as $f(\mathbf{r},t) = f(\rho(\mathbf{r},t), \overline{s})$, with the notational abuse of using $f$ for the same physical quantity, but for functions with different arguments.

```{prf:example} Speed of sound - Perfect ideal gas
:class: dropdown

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

$$a^2(\rho, s) = \left( \frac{\partial p}{\partial \rho} \right)_s = \gamma R T(\rho, s) = \gamma R \rho^{\gamma-1} e^{\frac{s}{c_v}} \frac{T_0}{\rho_0^{\gamma-1}} e^{-\frac{s_0}{c_v}} \ ,$$

having used the relations derived below for a perfect ideal gas.

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

Dividing the expression of the differential of pressure $dp(s, \rho)$ by $p$, and using the equation of state of ideal gas with constant heat coefficients, 

$$\frac{dp}{p} = \frac{1}{c_v} d s + \gamma \frac{d \rho}{\rho} \ ,$$

and after integration w.r.t. a reference state $0$

$$\begin{aligned}
  \ln \frac{p}{p_0} & = \frac{1}{c_v} \left( s - s_0 \right) + \gamma \ln \frac{\rho}{\rho_0} \\
  \ln \left\{ \left( \frac{p}{p_0} \right) \left( \frac{\rho}{\rho_0} \right)^{-\gamma} \right\} & = \frac{s - s_0}{c_v} \\
  \frac{p \rho^{-\gamma}}{p_0 \rho_0^{-\gamma}} & = e^{ \frac{s-s_0}{c_v} } \\
\end{aligned}$$

or with $p = \rho R T$

$$\begin{aligned}
  \frac{T \rho^{1-\gamma}}{T_0 \rho_0^{1-\gamma}} & = e^{ \frac{s-s_0}{c_v} } \\
  \frac{T}{T_0} & = \left(\frac{\rho}{\rho_0}\right)^{\gamma-1} e^{ \frac{s-s_0}{c_v} } \\
  T(\rho, s) & = \rho^{\gamma-1} e^{\frac{s}{c_v}} \frac{T_0}{\rho_0^{\gamma-1}} e^{-\frac{s_0}{c_v}}
\end{aligned}$$


```

(compressible:prandtl-meyer:characteristics)=
## Characteristic lines and compatibility equations

- Link to [Method of characteristics:Homoentropic inviscid compressible flows - 2d](https://basics2022.github.io/bbooks-math-miscellanea/ch/pde/characteristics.html#euler-equations-for-homoentropic-inviscid-compressible-flows-2d)

A steady expansion fan at a sharp corner connects two regions of the domain with supersonic flow and homogeneous characteristics. Let $1$ be the inflow homogeneous region and $2$ the outflow homogeneous region.

In a 2-dimensional domain there are three families of characteristic lines. Characteristic lines (or surfaces in 3-dimensional problems) are defined as those lines orthogonal to the directions $\hat{\mathbf{n}}_i$ that makes the eigenvalue $s_i$ of the matrix $\mathbf{A}_{\mathbf{n}}$ equal to zero. The eigenvalues of the matrix $\mathbf{A}_{\mathbf{n}}$ are

$$\begin{aligned}
  s_{1,3} & = \mathbf{u} \cdot \hat{\mathbf{n}} \mp a \\
  s_{2}   & = \mathbf{u} \cdot \hat{\mathbf{n}} \ .
\end{aligned}$$

Thus, 

$$\begin{aligned}
  \hat{\mathbf{u}} \cdot \hat{\mathbf{n}}_{1,3} & = \pm \frac{1}{M} \\
  \hat{\mathbf{u}} \cdot \hat{\mathbf{n}}_{1,3} & = 0 \ . 
\end{aligned}$$

On characteristic lines the following compatibility equations hold

$$\begin{aligned}
  \ell_{1,3}: \ 0 & = \frac{\sqrt{M^2-1}}{M^2} \frac{\partial_{\tau} \rho}{\rho} \mp \partial_{\tau} \theta \\
  \ell_{2  }: \ 0 & = \frac{1}{\rho} \partial_{\tau} p + \partial_{\tau} \frac{V^2}{2} \ ,
\end{aligned}$$

being $V = |\mathbf{u}|$. Some characteristic lines of family $1$ and $2$ start from inflow homogeneous region and reach outflow homogeneous region. The compatibility equation on characteristic lines of family $2$ is nothing but the directional derivative of the total enthalpy along streamlines, and thus it's identically satisfied.

```{dropdown} $d h$

The differential of enthalpy $h(p(\rho,s), s)$ reads

$$\begin{aligned}
  d h = T ds + \frac{d p }{\rho}
  & = T ds + \frac{1}{\rho} \left[ (\partial_\rho p)_s d \rho + (\partial_s p)_\rho d s \right] = \\
  & = \frac{a^2}{\rho} d \rho + \left( T + \frac{1}{\rho} (\partial_s p)_\rho \right) ds \ ,
\end{aligned}$$

and for homoentropic flows becomes 

$$d h = \frac{dp}{\rho} = \frac{a^2}{\rho} d \rho \ ,$$

with $a^2(\rho,s) = \left( \frac{\partial p}{\partial \rho} \right)_s(\rho,s)$ the square of the local speed of sound.

```

```{dropdown} Total enthalpy on streamlines, or $\, \ell_2 \,$ characteristic lines

If $h^t(\mathbf{r}) = \overline{h^t}$ uniform, then

$$\mathbf{0} = \nabla h^t = \nabla h + V \nabla V = \left( \partial_\rho h \right)_s \nabla \rho + \left( \partial_s h \right)_\rho \nabla s + V \nabla V \ ,$$

and for homoentropic flows, $\nabla s = 0$,

$$\mathbf{0} = \nabla h^t = \frac{\nabla p}{\rho} + V \nabla V = \frac{a^2}{\rho} \nabla \rho + \nabla \frac{V^2}{2} \ . $$

As the relation $\Delta h^t = 0$ holds, the compatibility equations on characteristic lines $\ell_2$ is identically satisfied, being the directional derivative of $h^t$ along the local direction of the velocity field, $\partial_{\mathbf{u}} h^t = \hat{\mathbf{u}} \cdot \nabla h^t \equiv 0$.

```

(compressible:prandtl-meyer:M-theta)=
## Relation between Mach number and flow deflection

First the relation between $d\rho$ and $d M$ is evalauted in the whole domain of the homo-total-enthaplic flow

$$\begin{aligned}
  0 = d h^t 
  & = dh + V d V = \\
  & = \frac{d p}{\rho} + M a d ( M a ) = \\
  & = a^2\frac{d \rho}{\rho} + M a^2 d M + M^2 a d a = \\
  & = a^2\frac{d \rho}{\rho} + M a^2 d M + \frac{1}{2} M^2 d a^2 = \\
  & = a^2\frac{d \rho}{\rho} + M a^2 d M + \frac{1}{2} M^2 \left( \frac{\partial a^2}{\partial \rho} \right)_s d \rho \ ,
\end{aligned}$$

i.e.

$$\frac{d \rho}{\rho} = - \frac{M^2}{1 + \frac{1}{2} M^2 \frac{\rho}{a^2} \left( \frac{\partial a^2}{\partial \rho} \right)_s}  \frac{dM}{M} \ ,$$

and then this relation is inserted in the compatibility equation on $\ell_1$ - connecting the two uniform regions - in terms of $d \rho$, $d \theta$ to get

$$\begin{aligned}
 \partial_{\tau_1} \theta
 & = - \frac{\sqrt{M^2-1}}{1 + \frac{1}{2} M^2 \frac{\rho}{a^2} \left( \frac{\partial a^2}{\partial \rho} \right)_s}\frac{\partial_{\tau_1} M}{M} \ .
\end{aligned}$$

```{dropdown} Details

$$\begin{aligned}
 \partial_{\tau_1} \theta
 & = \frac{\sqrt{M^2-1}}{M^2} \frac{\partial_{\tau_1} \rho}{\rho} = \\
 & = - \frac{\sqrt{M^2-1}}{M^2} \frac{M^2}{1 + \frac{1}{2} M^2 \frac{\rho}{a^2} \left( \frac{\partial a^2}{\partial \rho} \right)_s}\frac{\partial_{\tau_1} M}{M} = \\
 & = - \frac{\sqrt{M^2-1}}{1 + \frac{1}{2} M^2 \frac{\rho}{a^2} \left( \frac{\partial a^2}{\partial \rho} \right)_s}\frac{\partial_{\tau_1} M}{M} \ .
\end{aligned}$$

```

```{prf:example} Perfect Ideal Gas

Equation of state of perfect ideal gas... in a homoentropic flow, $p \rho^{-\gamma} = p_0 \rho_0^{-\gamma}$,

$$\left( \frac{\partial a^2}{\partial \rho} \right)_s = \left( \frac{\partial^2 p}{\partial^2 \rho} \right)_s = \gamma ( \gamma - 1) p_0 \left( \frac{\rho}{\rho_0}  \right)^{\gamma} \rho^{-2} = \gamma ( \gamma - 1 ) p \rho^{-2} $$

so that the denominator reads

$$1 + \frac{M^2}{2} \frac{\rho}{\gamma \frac{p}{\rho}} \gamma ( \gamma - 1 ) \frac{p}{\rho^2} = 1 + \frac{\gamma - 1}{2} M^2 \ ,$$

and the relation between flow deflection and Mach number becomes

$$\begin{aligned}
 \partial_{\tau_1} \theta
 & = - \frac{\sqrt{M^2-1}}{1 + \frac{\gamma - 1}{2} M^2}\frac{\partial_{\tau_1} M}{M} \ .
\end{aligned}$$

```


