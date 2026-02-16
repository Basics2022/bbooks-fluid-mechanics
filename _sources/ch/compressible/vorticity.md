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
  \nabla \cdot \left( \nabla \cdot \mathbf{u} \mathbb{I} \right) & = \partial_{k} \left( u_{l/l} \delta_{ki} \right) = u_{l/li} = \nabla \left( \nabla \cdot \mathbf{u} \right) \ .
\end{aligned}$$

Taking the curl of the momentum equation above,

$$\begin{aligned}
\partial_t \boldsymbol\omega + \nabla \times \left( \boldsymbol\omega \times \mathbf{u} \right) & = - \nabla \times \frac{\nabla p}{\rho} + \dots \\
\partial_t \boldsymbol\omega + \nabla \times \left( \boldsymbol\omega \times \mathbf{u} \right) & = \frac{1}{\rho^2}  \nabla \rho \times \nabla p + \dots 
\end{aligned}$$

**todo** *Manipulate second term*

```{dropdown}
:open:

**todo** *Uncomment*

<!--
$$\nabla \left( \mathbf{a} \cdot \mathbf{b} \right) = a_{i/j} b_i + a_i b_{i/j}$$

$$\begin{aligned}
  \left(\nabla \times \mathbf{a} \right) \times \mathbf{b} 
  & = \varepsilon_{ijk} \varepsilon_{jlm} \partial_l a_m b_k = \\
  & = \left( \delta_{kl} \delta_{im} - \delta_{km} \delta_{il} \right) \partial_l a_m b_k = \\
  & = a_{i/k} b_k - a_{k/i} b_k = \mathbf{b} \cdot \nabla \mathbf{a} - \nabla \mathbf{a} \cdot \mathbf{b} 
\end{aligned}$$

$$\begin{aligned}
  \nabla \times \left( \mathbf{a} \times \mathbf{b} \right)  
  & = \varepsilon_{ijk} \partial_j \varepsilon_{klm} a_l b_m = \\
  & = \left( \delta_{il} \delta_{jm} - \delta_{im} \delta_{jl} \right) \partial_j a_l b_m = \\
  & = a_{i/j} b_j - a_{j/j} b_i = \mathbf{b} \cdot \nabla \mathbf{a} - \mathbf{b} \nabla \cdot \mathbf{a} 
\end{aligned}$$

$$\begin{aligned}
  \left(\nabla \times \mathbf{a} \right) \times \mathbf{b} 
  & = \varepsilon_{ijk} \varepsilon_{jlm} \partial_l a_m b_k = \\
  & = \left( \delta_{kl} \delta_{im} - \delta_{km} \delta_{il} \right) \partial_l a_m b_k = \\
  & = \omega_{i/k} u_k - u_{k/i} \omega_k = \mathbf{u} \cdot \nabla \boldsymbol\omega - \nabla \mathbf{a} \cdot \mathbf{b} 
\end{aligned}$$

$$\nabla \times \left[ \left( \mathbf{u} \cdot \nabla \right) \mathbf{u} \right] = \nabla \times \left[ \boldsymbol\omega \times \mathbf{u} + \nabla \frac{|\mathbf{u}|^2}{2} \right]$$

$$\nabla \times \left( a \mathbf{v} \right) = \varepsilon_{ijk} \partial_j ( a v_k ) =  \varepsilon_{ijk} \left( a_{/j} v_k + a v_{k/j} \right) = \nabla a \times \mathbf{v} + a \nabla \times \mathbf{v} \ .$$
-->

```




