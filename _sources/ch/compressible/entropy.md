(compressible:entropy)=
# Entropy equation

**Differential equation.**

$$\begin{aligned}
  \rho D_t s
  & = \frac{1}{T} \left[ \rho D_t e - \rho \frac{P}{\rho^2} D_t \rho \right] = \\
  & = \frac{1}{T} \left[ - p \nabla \cdot \mathbf{u} + \mathbb{S} : \nabla \mathbf{u} - \nabla \cdot \mathbf{q} - \frac{P}{\rho} \left( - \rho \nabla \cdot \mathbf{u} \right) \right] = \\
  & = \frac{1}{T} \left[ 2 \mu |\mathbb{D}|^2 + \lambda \left( \nabla \cdot \mathbf{u} \right)^2 + \nabla \cdot \left( k \nabla T \right) \right] = \\
  & = \frac{2 \mu |\mathbb{D}|^2 + \lambda \left( \nabla \cdot \mathbf{u} \right)^2}{T} - \frac{\mathbf{q} \cdot \nabla T}{T^2} - \nabla \cdot \left( \frac{\mathbf{q}}{T} \right)  = \\
  & = \frac{2 \mu |\mathbb{D}|^2 + \lambda \left( \nabla \cdot \mathbf{u} \right)^2}{T} + \frac{k | \nabla T |^2}{T^2} - \nabla \cdot \left( \frac{\mathbf{q}}{T} \right) \ .
\end{aligned}$$
