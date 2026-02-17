(compressible:vorticity)=
# Vorticity equation

A differential equation governing vorticity can be derived starting from the momentum equation. Starting from the convective form of the momentum equation

$$\begin{aligned}
  \partial_t \mathbf{u} + \left( \mathbf{u} \cdot \nabla \right) \mathbf{u} 
  & = \mathbf{g} + \dfrac{1}{\rho} \nabla \cdot \left[ - p \mathbb{I} + 2 \mu \mathbb{D} + \lambda \left( \nabla \cdot \mathbf{u} \right) \mathbb{I} \right] = \\
  & = \mathbf{g} - \dfrac{1}{\rho} \nabla p + \frac{1}{\rho} \left[ 2 \mu \nabla^2 \mathbf{u} + \left( \mu + \lambda \right) \nabla \left( \nabla \cdot \mathbf{u} \right) \right] \ .
\end{aligned}$$

with

$$\begin{aligned}
  2 \nabla \cdot \mathbb{D} & = \partial_i \left( \partial_i u_j + \partial_j u_i \right) = u_{j/ji} + u_{i/jj} = \nabla \left( \nabla \cdot \mathbf{u} \right) + \nabla^2 \mathbf{u} \\
  \nabla \cdot \left( \left( \nabla \cdot \mathbf{u} \right) \mathbb{I} \right) & = \partial_{k} \left( u_{l/l} \delta_{ki} \right) = u_{l/li} = \nabla \left( \nabla \cdot \mathbf{u} \right) \ .
\end{aligned}$$

Taking the curl of the momentum equation above, vorticity equation follows

$$\begin{aligned}
\partial_t \boldsymbol\omega + \nabla \times \left( \boldsymbol\omega \times \mathbf{u} \right) & = - \nabla \times \frac{\nabla p}{\rho} + \dots \\
\partial_t \boldsymbol\omega + \mathbf{u} \cdot \nabla \boldsymbol\omega - \boldsymbol\omega \cdot \nabla \mathbf{u} + \boldsymbol\omega \, \nabla \cdot \mathbf{u} & = \frac{1}{\rho^2}  \nabla \rho \times \nabla p + \dots  \ ,
\end{aligned}$$

or, highlighting the material derivative,

$$
  D_t \boldsymbol\omega = \boldsymbol\omega \cdot \nabla \mathbf{u} - \boldsymbol\omega \, \nabla \cdot \mathbf{u} + \frac{1}{\rho^2}  \nabla \rho \times \nabla p + \dots  \ .
$$


```{dropdown} Vector caluclus identities

$$\nabla \left( \mathbf{a} \cdot \mathbf{b} \right) = a_{i/j} b_i + a_i b_{i/j}$$

$$\begin{aligned}
  \left(\nabla \times \mathbf{a} \right) \times \mathbf{b} 
  & = \varepsilon_{ijk} \varepsilon_{jlm} \partial_l a_m b_k = \\
  & = \left( \delta_{kl} \delta_{im} - \delta_{km} \delta_{il} \right) \partial_l a_m b_k = \\
  & = a_{i/k} b_k - a_{k/i} b_k = \mathbf{b} \cdot \nabla \mathbf{a} - \nabla \mathbf{a} \cdot \mathbf{b} 
\end{aligned}$$

Thus, $\left(\nabla \times \mathbf{u}\right) \times \mathbf{u}$ can be written as

$$\left(\nabla \times \mathbf{u}\right) \times \mathbf{u} = \mathbf{u} \cdot \nabla \mathbf{u} - \nabla \mathbf{u} \cdot \mathbf{u} =  \mathbf{u} \cdot \nabla \mathbf{u} - \nabla \frac{|\mathbf{u}|^2}{2} \ ,$$

so that the advective term can be recast as $\mathbf{u} \cdot \nabla \mathbf{u} = \boldsymbol\omega \times \mathbf{u} - \nabla \frac{|\mathbf{u}|^2}{2} \ ,$

being $\boldsymbol\omega = \nabla \times \mathbf{u}$ the vorticity field. Using vector calculus identity

$$\begin{aligned}
  \nabla \times \left( \mathbf{a} \times \mathbf{b} \right)  
  & = \varepsilon_{ijk} \partial_j \varepsilon_{klm} \left( a_l b_m \right) = \\
  & = \left( \delta_{il} \delta_{jm} - \delta_{im} \delta_{jl} \right) \partial_j \left( a_l b_m \right) = \\
  & = a_{i/j} b_j + a_i b_{j/j} - a_{j/j} b_i - a_j b_{i/j} = \\
  & = \mathbf{b} \cdot \nabla \mathbf{a} + \mathbf{a} \, \nabla \cdot \mathbf{b} - \mathbf{b} \nabla \cdot \mathbf{a} - \mathbf{a} \cdot \nabla \mathbf{b} \ .
\end{aligned}$$

and recalling that the curl of a gradient is identically zero, the curl of the advective term reads

$$\begin{aligned}
  \nabla \times \left[ \left( \mathbf{u} \cdot \nabla \right) \mathbf{u} \right] 
  & = \nabla \times \left[ \boldsymbol\omega \times \mathbf{u} + \nabla \frac{|\mathbf{u}|^2}{2} \right] = \\
  & = \mathbf{u} \cdot \nabla \boldsymbol\omega + \boldsymbol\omega \nabla \cdot \mathbf{u} - \mathbf{u} \underbrace{\nabla \cdot \boldsymbol\omega}_{ = \mathbf{0} \, \text{div  curl}\equiv\mathbf{0}} - \boldsymbol\omega \cdot \nabla \mathbf{u} \ .
\end{aligned}$$

The curl of a Laplacian reads

$$\left\{ \nabla \times \nabla^2 \mathbf{u} \right\}_i = \varepsilon_{ijk} \partial_j \partial_{ll} u_k = \partial_{ll} \left( \varepsilon_{ijk} \partial_j u_k \right) = \nabla^2 \left( \nabla \times \mathbf{u} \right) \ .$$

The curl of the product of a scalar and vector field reads

$$\nabla \times \left( a \mathbf{v} \right) = \varepsilon_{ijk} \partial_j ( a v_k ) =  \varepsilon_{ijk} \left( a_{/j} v_k + a v_{k/j} \right) = \nabla a \times \mathbf{v} + a \nabla \times \mathbf{v} \ .$$

```

## Vorticity and entropy

Starting from the potentials, and $dh = d \left( e + \frac{p}{\rho} \right) = de + \frac{d p}{\rho} - \frac{p}{\rho^2} d\rho$,

$$\begin{aligned}
  de & = T ds + \frac{p}{\rho^2} d \rho \\
  dh & = T ds + \frac{d p}{\rho}
\end{aligned}$$

and taking the gradient, 

$$\frac{\nabla p}{\rho} = \nabla h - T \nabla s \ .$$

Using the momentum equation to replace the first term, 

$$\begin{aligned}
  \frac{\nabla p}{\rho}
  & = - D_t \mathbf{u} + \mathbf{g} + \frac{1}{\rho} \nabla \cdot \mathbb{S} = \\
  & = - \partial_t \mathbf{u} - \boldsymbol\omega \times \mathbf{u} - \nabla \frac{|\mathbf{u}|^2}{2} - \nabla \chi + \frac{1}{\rho} \nabla \cdot \mathbb{S} \ ,
\end{aligned}$$

it follows

$$\mathbf{0} = \partial_t \mathbf{u} + \boldsymbol\omega \times \mathbf{u} + \nabla \left[ h + \frac{|\mathbf{u}|^2}{2} + \chi \right] + \frac{1}{\rho} \nabla \cdot \mathbb{S} - T \nabla s$$

**Steady condition, inviscid flows.** If $\partial_t \equiv 0$ and $\mathbb{S} \equiv \mathbb{0}$, it follows

$$\mathbf{0} = \boldsymbol\omega \times \mathbf{u} + \nabla \left[ h + \frac{|\mathbf{u}|^2}{2} + \chi \right]- T \nabla s \ .$$

**todo** *Rotational flow behind an oblique shock*

**Scalar multiplication by $\rho \mathbf{u} \cdot$** and transforming back the gradient of the entropy field as a function of the gradient of the internal energy and density,

$$\begin{aligned}
  0
  & = \rho \partial_t \frac{|\mathbf{u}|^2}{2} + \rho \mathbf{u} \cdot \nabla \left[ h^t + \chi \right] + \mathbf{u} \cdot \nabla \cdot \mathbb{S} - T \rho \mathbf{u} \cdot \nabla s  = \\
  & = \dots
\end{aligned}$$

**todo** *Going back to Bernoulli...*
