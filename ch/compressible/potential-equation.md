(compressible:irrotational:potential-equation)=
# Potential equation for irrotational compressible flows

Under the assumption of irrotational flow[^irrotational-flow-hp], the velocity field $\mathbf{u}(\mathbf{r},t)$ can be written as a gradient of a scalar potential $\phi(\mathbf{r},t)$,

[^irrotational-flow-hp]: Vorticity is confined in thin layers, like boundary layers and wakes, modelled as tangential velocity discontinuities.

$$\nabla \times \mathbf{u} = \mathbf{0} \quad \rightarrow \quad \mathbf{u} = \nabla \phi \ .$$

Euler equations in convective form with independent variables $(\rho, \mathbf{u}, s)$ read[^advective-term]

[^advective-term]: $\mathbf{u} \cdot \nabla \mathbf{u} = \nabla \frac{|\mathbf{u}|^2}{2} + \boldsymbol\omega \times \mathbf{u}$, with $\boldsymbol = \nabla \times \mathbf{u} = \mathbf{0}$ in irrotational flows.

$$\begin{aligned}
  & \partial_t \rho + \mathbf{u} \cdot \nabla \rho + \rho \nabla \cdot \mathbf{u} = 0 \\
  & \partial_t \mathbf{u} + \nabla \frac{|\mathbf{u}|^2}{2} + \frac{\nabla p}{\rho} = \mathbf{0} \\
  & \partial_t s + \mathbf{u} \cdot \nabla s = 0 \ .
\end{aligned}$$


(compressible:irrotational:potential-equation:homoentropic)=
## Homoentropic flows

If no shock occurs and the inflow is uniform, the flow is homoentropic, $s(\mathbf{r},t) = \overline{s}$. Mass and momentum equations become

$$\begin{aligned}
  & \partial_t \rho + \nabla \phi \cdot \nabla \rho + \rho \nabla^2 \phi = 0 \\
  & \partial_t \nabla \phi + \nabla \frac{|\nabla \phi|^2}{2} + a^2(\rho, \overline{s}) \frac{\nabla \rho}{\rho} = \mathbf{0} \ ,
\end{aligned}$$

being $a^2(\rho, \overline{s}) = \left( \frac{\partial p}{\partial \rho} \right)_s$ the square of the speed of sound.

```{dropdown} Bernoulli
:open:

Momentum equation can be manipulated as

$$\begin{aligned}
  \mathbf{0}
  & = \partial_t \mathbf{u} + \nabla \frac{|\mathbf{u}|^2}{2} + \frac{\nabla p}{\rho} = \\
  & = \partial_t \nabla \phi + \nabla \frac{|\nabla \phi|^2}{2} + \frac{\nabla p}{\rho} = \\
  & = \partial_t \nabla \phi + \nabla \frac{|\nabla \phi|^2}{2} + \nabla h(\rho, \overline{s})  = \\
  & = \nabla \left[ \partial_t \phi + \frac{|\nabla \phi|^2}{2} + h(\rho, \overline{s}) \right] \ ,
\end{aligned}$$

and thus

$$\partial_t \phi + \frac{|\nabla \phi|^2}{2} + h(\rho, \overline{s}) = C(t) \ ,$$

for **homoentropic flows** $\nabla s = 0$, as the relation (**todo** *add link to thermodynamics*)

$$d h = T ds + \frac{dp}{\rho} \ ,$$

produces

$$d h = \frac{dp}{\rho} \quad , \quad \nabla h = \frac{\nabla p}{\rho} \ .$$

```


