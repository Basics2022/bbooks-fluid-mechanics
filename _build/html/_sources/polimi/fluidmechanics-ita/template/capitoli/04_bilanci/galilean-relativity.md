(fluid-mechanics:balances:galilean-relativity)=
# Galilean relativity

Galilean transformation between position in two reference frames in relative uniform motion reads

$$\begin{cases}
  \mathbf{r}' = \mathbf{r} + \mathbf{v} t \\
  t' = t
\end{cases}$$

with $\mathbf{v}$ constant and independent from position in space. Derivative of composite functions gives

$$\begin{aligned}
  \partial_t = \partial_{t'} + \mathbf{v} \cdot \nabla' \\
  \nabla = \nabla'
\end{aligned}$$


## Differential equations

**Mass.**

$$\begin{aligned}
  0
  & = \partial_t \rho + \nabla \cdot \left( \rho \mathbf{u} \right) = \\
  & = \partial_{t'} \rho - \mathbf{v} \cdot \nabla' \rho + \nabla \cdot \left( \rho' \left( \mathbf{u}' + \mathbf{v} \right) \right) = \\
  & = \partial_{t'} \rho - \mathbf{v} \cdot \nabla' \rho + \nabla \cdot \left( \rho' \mathbf{u}' \right) + \mathbf{v} \cdot \nabla' \rho = \\
  & = \partial_{t'} \rho + \nabla' \cdot \left( \rho \mathbf{u}' \right) \ .
\end{aligned}$$

**Momentum.**

$$\begin{aligned}
  \nabla \cdot \mathbb{T} + \rho \mathbf{g}
  & = \partial_t \left( \rho \mathbf{u} \right) + \nabla \cdot \left( \rho \mathbf{u} \mathbf{u} \right) = \\
  & = \partial_{t'} \left( \rho \mathbf{u} \right) - \mathbf{v} \cdot \nabla' \left( \rho \mathbf{u} \right) + \nabla' \cdot \left( \rho \mathbf{u} \mathbf{u} \right) = \\
  & = \partial_{t'} \left( \rho \mathbf{u}' \right) + \partial_{t'} \left( \rho \mathbf{v} \right) - \mathbf{v} \cdot \nabla' \left( \rho \mathbf{u} \right) + \nabla' \cdot \left( \rho \left( \mathbf{u}' + \mathbf{v} \right) \mathbf{u} \right) = \\
  & = \partial_{t'} \left( \rho \mathbf{u}' \right) + \mathbf{v} \partial_{t'} \rho - \mathbf{v} \cdot \nabla' \left( \rho \mathbf{u} \right) + \nabla' \cdot \left( \rho \mathbf{u}' \mathbf{u} \right) + \nabla' \cdot \left( \rho \mathbf{v} \mathbf{u} \right) = \\
  & = \partial_{t'} \left( \rho \mathbf{u}' \right) + \mathbf{v} \partial_{t'} \rho - \mathbf{v} \cdot \nabla' \left( \rho \mathbf{u} \right) + \nabla' \cdot \left( \rho \mathbf{u}' \mathbf{u}' \right) + \nabla' \cdot \left( \rho \mathbf{u}' \right) \, \mathbf{v} +  \mathbf{v} \cdot \nabla' \left( \rho \mathbf{u} \right) = \\
  & = \partial_{t'} \left( \rho \mathbf{u}' \right) + \nabla' \cdot \left( \rho \mathbf{u}' \mathbf{u}' \right) \ .
\end{aligned}$$

with the stress tensor and the volume force independent from Galilean transformations.

**Total energy.** Total energy can be written as the sum of internal and kinetic energy $e^t = e + \frac{|\mathbf{u}|^2}{2}$. Internal energy is independent from a change of reference frame, being a scalar quantity quantifying the microscopic dynamics w.r.t. the macroscopic average motion. Total energy equation reads 

$$\begin{aligned}
 \nabla \cdot \left( \mathbb{T} \cdot \mathbf{u} \right) + \rho \mathbf{g} \cdot \mathbf{u}
  & = \partial_t \left( \rho e^t \right) + \nabla \cdot \left( \rho e^t \mathbf{u} \right) \ ,
\end{aligned}$$

Contributions of the kinetic energy transform as shown below for the kinetic energy equation. Power of stress and terms with internal energy become

$$\begin{aligned}
  \nabla \cdot \left( \mathbb{T} \cdot \mathbf{u} \right)
  & = \underbrace{\nabla \cdot \left( \mathbb{T} \cdot \mathbf{u}' \right)}_{ \text{e.1} } + \underbrace{\mathbf{v} \cdot \nabla \cdot \mathbb{T}}_{ \text{q.1} } \\ 
  & \dots \\
  \partial_t \left( \rho e \right) + \nabla \left( \rho e \mathbf{u} \right)
  & = \partial_{t'} \left( \rho e \right) - \mathbf{v} \cdot \nabla' \left( \rho e \right) + \nabla' \cdot \left( \rho e \mathbf{u}' \right) + \mathbf{v} \cdot \nabla \left( \rho e \right)  = \\
  & = \underbrace{\partial_{t'} \left( \rho e \right) + \nabla' \cdot \left( \rho e \mathbf{u}' \right)}_{ \text{e.2} } 
\end{aligned}$$

**Kinetic energy.**

$$\begin{aligned}
  \mathbf{u} \cdot \nabla \cdot \mathbb{T} + \rho \mathbf{g} \cdot \mathbf{u}
  & = \partial_t \left( \rho \frac{|\mathbf{u}|^2}{2} \right) + \nabla \cdot \left( \rho \frac{|\mathbf{u}|^2}{2} \mathbf{u} \right)  \ ,
\end{aligned}$$

$$\begin{aligned}
  \mathbf{u} \cdot \nabla \cdot \mathbb{T} 
  & = \underbrace{\mathbf{u}' \cdot \nabla \cdot \mathbb{T}}_{ \text{k.1} } + \underbrace{\mathbf{v} \cdot \nabla \cdot \mathbb{T}}_{ \text{q.1} } \\ 
  \mathbf{u} \cdot \rho \mathbf{g}
  & = \underbrace{ \mathbf{u}' \cdot \rho \mathbf{g} }_{ \text{k.2} } + \underbrace{\mathbf{v} \cdot \rho \mathbf{g}}_{\text{q.2}} \\
  \partial_t \left( \rho \frac{|\mathbf{u}|^2}{2} \right)
  & = \partial_{t'} \left( \rho \frac{|\mathbf{u}|^2}{2} \right) - \mathbf{v} \cdot \nabla' \left( \rho \frac{|\mathbf{u}|^2}{2} \right) = \\ 
  & = \underbrace{ \partial_{t'} \left( \rho \frac{|\mathbf{u}'|^2}{2} \right)}_{\text{k.3}} + \underbrace{\mathbf{v} \cdot \partial_{t'} \left( \rho \mathbf{u} \right)}_{ \text{q.3}} + \underbrace{\frac{|\mathbf{v}|^2}{2} \partial_{t'} \rho}_{\text{m.3}} - \underbrace{ \mathbf{v} \cdot \left( \rho \frac{|\mathbf{u}|^2}{2} \right)}_{ \text{0.1} } \\
  \nabla \cdot \left( \rho \frac{|\mathbf{u}|^2}{2} \mathbf{u} \right) 
  & = \nabla' \cdot \left( \rho \frac{|\mathbf{u}|^2}{2} \mathbf{u}' \right) + \mathbf{v} \cdot \nabla' \left( \rho \frac{|\mathbf{u}|^2}{2} \right) = \\ 
  & = \underbrace{\nabla' \cdot \left( \rho \frac{|\mathbf{u}'|^2}{2} \mathbf{u}' \right)}_{\text{k.4}} + \underbrace{\mathbf{v} \cdot \nabla' \cdot \left( \rho \mathbf{u}' \mathbf{u}' \right)}_{\text{q.4}} + \underbrace{\frac{|\mathbf{v}|^2}{2} \nabla' \cdot \left( \rho \mathbf{u}' \right)}_{\text{m.4}} + \underbrace{\mathbf{v} \cdot \nabla' \left( \rho \frac{|\mathbf{u}|^2}{2} \right)}_{\text{0.2}} \ , 
\end{aligned}$$

Terms $\text{q.x}$ make the kinetic energy equation in the new reference frame, $\text{m.x}$, $\text{q.x}$ simplify for the mass and momentum equation respectively, as they are $\mathbf{v} \cdot \text{mom. eq.}$ and $\frac{|\mathbf{v}|^2}{2} \left( \text{mass eq.} \right)$, $\text{0.x}$ sum up to zero.

## Integral equations

**Mass.**

**Momentum.**

**Total energy.**

**Kinetic energy.**




