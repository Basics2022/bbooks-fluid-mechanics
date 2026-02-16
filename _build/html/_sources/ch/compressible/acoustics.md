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
 \partial_t \left( \rho e^t \right) + \nabla \cdot \left( \rho e^t \mathbf{u} + p \mathbf{u} \right) = \rho \mathbf{g} \cdot \mathbf{u}
\end{cases}$$

**todo** *discuss the hyperbolic mathematical nature of Euler equations, and link to [Math:PDEs:Hyperbolic equations](https://basics2022.github.io/bbooks-math-miscellanea/ch/pde/hyperbolic.html)*


