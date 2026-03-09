(compressible:governing-equations)=
# Governing equations

(compressible:governing-equations:navier-stokes)=
## Compressible Navier-Stokes equations

```{dropdown} Integral balance equations

Integral balance equations of mass (Lavoisier principle), momentum (Second principle of Newton dynamics) and total energy (Principle of energy conservation) for a control volume $V$ at rest read

$$\begin{aligned}
  & \dfrac{d}{dt} \int_V \rho + \oint_{\partial V} \rho \mathbf{u} \cdot \hat{\mathbf{n}} = 0 \\
  & \dfrac{d}{dt} \int_V \rho \mathbf{u} + \oint_{\partial V} \rho \mathbf{u} \mathbf{u} \cdot \hat{\mathbf{n}} = \int_{V} \rho \mathbf{g} + \oint_{\partial V} \mathbf{t}_{\mathbf{n}} \\
  & \dfrac{d}{dt} \int_V \rho e^t + \oint_{\partial V} \rho e^t \mathbf{u} \cdot \hat{\mathbf{n}} = \int_{V} \rho \mathbf{g} \cdot \mathbf{u} + \oint_{\partial V} \mathbf{t}_{\mathbf{n}} \cdot \mathbf{u} - \oint_{\partial V} \mathbf{q} \cdot \hat{\mathbf{n}} \ .
\end{aligned}$$
```

```{dropdown} Differential balance equations

Differential balance equations in conservative form follow from regularity of the functions involved in the equations and from the arbitrariness of the control volume $V$

$$\begin{aligned}
  & \partial_t \rho + \nabla \cdot ( \rho \mathbf{u} ) = 0 \\
  & \partial_t \left( \rho \mathbf{u} \right) + \nabla \cdot ( \rho \mathbf{u} \otimes \mathbf{u} ) = \rho \mathbf{g} + \nabla \cdot \mathbb{T} \\
  & \partial_t \left( \rho e^t        \right) + \nabla \cdot ( \rho \mathbf{u} e^t ) = \rho \mathbf{g} \cdot \mathbf{u} + \nabla \cdot ( \mathbb{T} \cdot \mathbf{u} ) - \nabla \cdot \mathbf{q} \ ,
\end{aligned}$$

being
* $\mathbb{T}$ the stress tensor, relating stress vector $\mathbf{t}_{\mathbf{n}}$ on the a surface and unit normal $\hat{\mathbf{n}}$ of that surface via **Cauchy relation**, $\mathbf{t}_{\mathbf{n}} = \hat{\mathbf{n}} \cdot \mathbb{T}$,
* $e^t$ the total energy, $e^t = e + \frac{|\mathbf{u}|^2}{2}$
* $\mathbf{q}$ heat flux by conduction.

```

```{dropdown} Constitutive equations and equations of state

The problem is completed with initial and boundary conditions, along with constitutive equations and equations of state. As an example:
* A **Newtonian fluid** is defined by the constitutive equation for stress

   $$\mathbb{T} = - p \mathbb{I} + \mathbb{S} = - p \mathbb{I} + 2 \mu \mathbb{D} + \lambda ( \nabla \cdot \mathbf{u} ) \mathbb{I} \ ,$$

   being $p$ the pressure field, $\mu$, $\lambda$ viscosity coefficients, and $\mathbb{D}$ the deformation velocity tensor. In general, they are function of the thermodynamic state.

* **Fourier law** for heat flux by conduction for an isotropic medium reads

   $$\mathbf{q} = - k \nabla T \ .$$

* **Equations of state** relate non-dynamical physical variables to the dynamical variables, to get a well-defined problem from the mathematical point of view with the same numeber of equations and unknowns. A pair of independent thermodynamic variables are required to define a thermodynamic state. As an example, using $(\rho, e)$ as the pair of independent thermodynamic variables (fields here, with the local equilibrium assumption), equations of state need to provide the expression of pressure and temperature (and viscosity and conduction coefficients, if they can't be treated as constant parameters),

   $$\begin{aligned}
     p(\rho, e) \ , \quad T(\rho, e) \ ,  \quad \dots
   \end{aligned}$$

```

(compressible:governing-equations:euler)=
## Euler equations

Neglecting viscosity and heat conduction, diffusive contributions (usually containing second-order spatial derivatives of the unknowns) drop and Navier-Stokes equations become Euler equations. Where differential equations hold (in absence of shoscks and discontinuities), local governing equations read

$$\begin{aligned}
  & \partial_t \rho + \nabla \cdot ( \rho \mathbf{u} ) = 0 \\
  & \partial_t \left( \rho \mathbf{u} \right) + \nabla \cdot ( \rho \mathbf{u} \otimes \mathbf{u} + p \mathbb{I} ) = \rho \mathbf{g} \\
  & \partial_t \left( \rho e^t        \right) + \nabla \cdot \left( \rho \mathbf{u}  \left( e^t + \frac{p}{\rho} \right) \right) = \rho \mathbf{g} \cdot \mathbf{u} \ .
\end{aligned}$$

**Constitutive equations.** There's no need to constitutive equations for viscous stress and heat flux by conduction.

**Equations of state.** Two thermodynamic variables (fields) have dynamical equations (in the conservative form, density and total energy $(\rho, e^t)$), while **only one** other thermodynamic variable doesn't have a dynamical equation, here pressure field $p$. Thus, **only one equation of state** is required to write a well-defined mathematical problem

$$p(\rho, e) \ ,$$

while other dependent theromdynamic variables (fields), like temperature $T$, can be retrieved a posteriori once the problem is solved.

(compressible:governing-equations:ideal)=
## Ideal flow
The definition of an ideal flow immediately follows from the [entropy equation](compressible:entropy): in a fluid with negligible viscosity and heat conduction, where no shock occurs (and thus where differential equations hold in the whole domain), the entropy of each material particle is constant.

(compressible:governing-equations:other)=
## Other form of the governing equations

[**Potential equation for irrotational compressible flows**](compressible:irrotational:potential-equation). Some flow of interest - e.g. in aeronautics - are irrotational flow. It can be proved with [vorticity equation](compressible:vorticity) that an irrotational inflow produces irrotational flow in the whole domain, if viscoisty effects are negligible and no oblique shock occurs. 
