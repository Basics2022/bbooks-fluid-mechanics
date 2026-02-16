(compressible:acoustics)=
# Acoustics

Assuming negligible viscosity and conductivity, Navier-Stokes equations for compressible fluids become Euler equations[^ns-to-euler]

[^ns-to-euler]: NS equations are second-order in space due to the diffusive contributions of viscous stress $\nabla \cdot \mathbb{T} = \nabla \cdot \left[ 2 \mu \nabla^s \mathbf{u} + \lambda \left( \nabla \cdot \mathbf{u} \right) \mathbb{T} \right]$ for Newtonian fluids in momentum equation and heat conduction flux $-\nabla \cdot \mathbf{q} = \nabla \cdot \left( k \nabla T \right)$ with Fourier law in total energy equation. Boundary conditions needed for the mathematical problem change as well: while NS equations require no-slip boundary conditions apply on solid bodies, $\mathbf{u} = \mathbf{u}_b$, Euler equations need only no-penetration boundary conditions $\mathbf{u} \cdot \hat{\mathbf{n}} = \mathbf{u}_b \cdot \hat{\mathbf{n}}$.

The conservative form of Navier-Stokes equations

$$\begin{cases}
 \partial_t \rho + \nabla \cdot \left( \rho \mathbf{u} \right) = 0 \\
 \partial_t \left( \rho \mathbf{u} \right) + \nabla \cdot \left( \rho \mathbf{u} \mathbf{u} \right) = \rho \mathbf{g} + \nabla \cdot \mathbb{T} \\
 \partial_t \left( \rho e^t \right) + \nabla \cdot \left( \rho e^t \mathbf{u} \right) = \rho \mathbf{g} \cdot \mathbf{u} + \nabla \cdot \left( \mathbb{T} \cdot \mathbf{u} \right) - \nabla \cdot \mathbf{q}
\end{cases}$$

need
- boundary conditions
- **constitutive laws** for relating stress tensor $\mathbb{T}$ and conductive heat flux $\mathbf{q}$ to *dynamic variables* $\rho$, $\mathbf{m} := \rho \mathbf{u}$, $E^t := \rho e^t$. As a common example, stress tensor for *Newtonian fluids* is the sum of pressure and viscosity stress, and this latter contribution is linear and isotropic w.r.t. first order spatial derivatives of the velocity field[^newton-fluid],

   [^newton-fluid]: **todo** *discuss isotropic tensors, or link to [Math:Vector and Tensor Algebra and Calculus:Isotropic Tensors](https://basics2022.github.io/bbooks-math-miscellanea/ch/tensor-algebra-calculus/algebra-isotropic-tensors.html)*

   $$\mathbb{T} = - p \mathbb{I} + \mathbb{S} = - p \mathbb{I} + 2 \mu \mathbb{D} + \lambda \left( \nabla \cdot \mathbf{u} \right) \mathbb{I} \ ,$$

   being $p$ the pressure field, $\mathbb{D} = \frac{1}{2} \left[ \nabla \mathbf{u} + \nabla^T \mathbf{u} \right]$ the deformation velocity tensor and $\mu$, $\lambda$ the viscosity coefficients. *Fourier's law* provides a linear isotropic relation between the conductive heat flux and the temperature gradient

   $$\mathbf{q} = - k \nabla T \ .$$


- **state equations**, for relating thermodynamic variables appearing in constitutive laws with *dynamic variables*. Using constitutive laws for Newtonian fluids and Fourier's law, there's a need for state equations relating pressure, temperature and - if not possible to model as constant - viscosity coefficients and heat conductivity,

   $$\begin{aligned}
     p & = p(\rho, \mathbf{m}, E_t) \\
     T & = T(\rho, \mathbf{m}, E_t) \\
       & ...
   \end{aligned}$$
   
   Usually internal energy is used in state equations. Mass density of total energy is defined as the sum of internal energy and kinetic energy

   $$e^t = e + \frac{|\mathbf{u}|^2}{2} \ .$$

Introducing the constitutive laws and the state equations in Navier-Stokes equations and collecting terms with 1-st order and 2-nd order space derivatives,

$$\begin{cases}
 \partial_t \rho + \nabla \cdot \left( \rho \mathbf{u} \right) = 0 \\
 \partial_t \left( \rho \mathbf{u} \right) + \nabla \cdot \left( \rho \mathbf{u} \mathbf{u} + p \mathbb{I} \right) = \rho \mathbf{g} + \nabla \cdot \mathbb{S} \\
 \partial_t \left( \rho e^t \right) + \nabla \cdot \left( \rho e^t \mathbf{u} + p \mathbf{u} \right) = \rho \mathbf{g} \cdot \mathbf{u} + \nabla \cdot \left( \mathbb{S} \cdot \mathbf{u} \right) - \nabla \cdot \mathbf{q}
\end{cases}$$

**Euler equations** immediately follow by setting equal to zero the contribution of viscosity and heat conduction, i.e. the terms collecting the 2-nd order space derivatives, those ones that have diffusive nature,

$$\begin{cases}
 \partial_t \rho + \nabla \cdot \left( \rho \mathbf{u} \right) = 0 \\
 \partial_t \left( \rho \mathbf{u} \right) + \nabla \cdot \left( \rho \mathbf{u} \mathbf{u} + p \mathbb{I} \right) = \rho \mathbf{g} \\
 \partial_t \left( \rho e^t \right) + \nabla \cdot \left( \rho h^t \mathbf{u} \right) = \rho \mathbf{g} \cdot \mathbf{u}
\end{cases}$$

**todo** *discuss the hyperbolic mathematical nature of Euler equations, and link to [Math:PDEs:Hyperbolic equations](https://basics2022.github.io/bbooks-math-miscellanea/ch/pde/hyperbolic.html)*

- Convective form...

$$\begin{cases}
 D_t \rho + \rho \nabla \cdot \mathbf{u} = 0 \\
 \rho D_t \mathbf{u} + \nabla p = \rho \mathbf{g} \\
 \rho D_t e^t + \nabla \cdot ( p \mathbf{u} ) = \rho \mathbf{g} \cdot \mathbf{u}
\end{cases}$$

- Alternative sets of equations, if differential equations hold (no discontinuities: no shocks,...): internal energy instead of total energy, entropy,...

   - internal energy, differente of total energy and kinetic energy (momentum equation $\cdot \mathbf{u}$):

      $$\rho D_t e + p \nabla \cdot \mathbf{u} = 0$$

   - entropy, from the 1-st principle of theromdynamics $de = T ds + \frac{p}{\rho^2} d \rho$

      $$\begin{aligned}
        \rho D_t s
        & = \frac{\rho}{T} \left[ D_t e - \frac{p}{\rho^2} D_t \rho \right] = \\
        & = \frac{\rho}{T} \left[ - \frac{p}{\rho} \nabla \cdot \mathbf{u} - \frac{p}{\rho^2} \left( - \rho \nabla \cdot \mathbf{u} \right)  \right] = 0 \ ,
      \end{aligned}$$

      i.e.

      $$D_t s = 0$$

      **todo** *$1)$ entropy and shocks, $2)$ entropy and vorticity,...*

(compressible:acoustics:linearized-euler)=
## Linearized Euler equations

Linearization around a reference state

...

### Uniform and steady reference state

$\overline{\rho}, \overline{\mathbf{u}}, \overline{s}$. Time and space derivatives of the reference state are identically zero, thus Euler equations in convective form

$$\begin{aligned}
  & \partial_t \rho + \mathbf{u} \cdot \nabla \rho + \rho \nabla \cdot \mathbf{u} = 0 \\
  & \rho \partial_t \mathbf{u} + \rho \mathbf{u} \cdot \nabla \mathbf{u} + \nabla p = \rho \mathbf{g} \\
  & \partial_t s + \mathbf{u} \cdot \nabla s = 0
\end{aligned}$$

are linearized as

$$\begin{aligned}
  & \partial_t \rho' + \mathbf{u} \cdot \nabla \rho' + \rho \nabla \cdot \mathbf{u}' = 0 \\
  & \rho \partial_t \mathbf{u}' + \rho \mathbf{u} \cdot \nabla \mathbf{u}' + \nabla p' = \rho' \mathbf{g} \\
  & \partial_t s' + \mathbf{u} \cdot \nabla s' = 0
\end{aligned}$$

If the entropy is uniform everywhere (also at the boundary, so that no entropy enters from it), its perturbation is identically zero $s' = 0$, $s(\mathbf{r},t) = \overline{s}$. Thus, for any thermodynamic variable written as function of density and entropy as the pair of independent variable, e.g. pressure $p(\rho, s)$, its differential is a function of the differential of the density only, being $ds = 0$

$$\begin{aligned}
  dp
  & = \left( \frac{\partial p}{\partial \rho} \right)_s d \rho + \left( \frac{\partial p}{\partial s} \right)_\rho \underbrace{d s}_{=0} = \\
  & = \left( \frac{\partial p}{\partial \rho} \right)_s d \rho = \\
  & = c^2(\rho, s) \, d\rho \ .
\end{aligned}$$

Now, for negligible volume forces $\mathbf{g} = \mathbf{0}$, and writing $\nabla p = c^2 \nabla \rho$, mass and momentum linearized equations read

$$\begin{aligned}
  & \partial_t \rho' + \overline{\mathbf{u}} \cdot \nabla \rho' + \overline{\rho} \nabla \cdot \mathbf{u}' = 0 \\
  & \overline{\rho} \partial_t \mathbf{u}' + \overline{\rho} \overline{\mathbf{u}} \cdot \nabla \mathbf{u}' + c^2(\overline{\rho}, \overline{s}) \nabla \rho' = \mathbf{0} \ .
\end{aligned}$$

$$\begin{aligned}
  & D^{\overline{\mathbf{u}}}_t \rho' + \overline{\rho} \nabla \cdot \mathbf{u}' = 0 \\
  & \overline{\rho} D^{\overline{\mathbf{u}}}_t \mathbf{u}' + \overline{c}^2 \nabla \rho' = \mathbf{0} \ .
\end{aligned}$$

being $D^{\overline{\mathbf{u}}}_t$ the material time derivative with the reference velocity field,

$$D^{\overline{\mathbf{u}}}_t = \partial_t + \overline{\mathbf{u}} \cdot \nabla \ .$$


### Wave equations
A wave equation for density perturbation $\rho'(\mathbf{r},t)$ is obtained taking the difference of time derivative of the mass equation and the divergence of momentum equation,

$$\begin{aligned}
  & D^{\overline{\mathbf{u}}}_{tt} \rho' + \overline{\rho} D^{\overline{\mathbf{u}}}_{t} \nabla \cdot \mathbf{u}' = 0 \\
  & \overline{\rho} \nabla \cdot D^{\overline{\mathbf{u}}}_t \mathbf{u}' + \overline{c}^2 \nabla^2 \rho' = 0 \ ,
\end{aligned}$$

it follows

$$\frac{1}{\overline{c}^2} D^{\overline{\mathbf{u}}}_{tt} \rho'- \nabla^2 \rho' = 0 \ .$$

A wave equation for velocity perturbation $\mathbf{u}'(\mathbf{r},t)$ is obtained taking the difference of time gradient of the mass equation and the time derivative of momentum equation,

$$\begin{aligned}
  & \nabla D^{\overline{\mathbf{u}}}_{t} \rho' + \overline{\rho} \nabla \left( \nabla \cdot \mathbf{u}' \right) = 0 \\
  & \overline{\rho} D^{\overline{\mathbf{u}}}_{tt} \mathbf{u}' + \overline{c}^2 D^{\overline{\mathbf{u}}}_{t} \nabla  \rho' = \mathbf{0} \ ,
\end{aligned}$$

and using vector identity $\nabla^2 \mathbf{v} = \nabla \left( \nabla \cdot \mathbf{v} \right) - \nabla \times \nabla \times \mathbf{v}$, it follows

$$\frac{1}{\overline{c}^2} D^{\overline{\mathbf{u}}}_{tt} \mathbf{u}' - \nabla^2 \mathbf{u}' - \nabla \times \boldsymbol\omega' = \mathbf{0} \ ,$$

being $\boldsymbol\omega' = \nabla \times \mathbf{u}'$ the vorticity of the velocity perturbation.

For isentropic flows, differential of density perturbation $d \rho'$ can be related to differential of pressure perturbation, $d \rho' = \frac{1}{\overline{c}^2} dp'$, so that pressure perturbation field is governed by a wave equation as well.


