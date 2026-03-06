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

```{dropdown} Momentum equation 

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

**todo** 
* Discuss if and why the function $C(t)$ can be included in the definition of "$\phi(\mathbf{r},t) = \phi(\mathbf{r},t) + C(t)$".
* or With homogeneous and steady inflow,

  $$\partial_t \phi(\mathbf{r},t) + \frac{|\nabla \phi(\mathbf{r},t)|^2}{2} + h(\rho(\mathbf{r},t), \overline{s}) = \frac{|\mathbf{u}_\infty|^2}{2} + h_\infty \ .$$

Taking partial derivative in time

$$\begin{aligned}
  0
  & = \partial_{tt} \phi + \partial_t \frac{|\nabla \phi|^2}{2} + \partial_t h = \\
  & = \partial_{tt} \phi + \partial_t \frac{|\nabla \phi|^2}{2} + \left( \frac{\partial h}{\partial \rho} \right)_s \partial_t \rho = \\
  & = \partial_{tt} \phi + \partial_t \frac{|\nabla \phi|^2}{2} + \frac{a^2(\rho,\overline{s})}{\rho} \partial_t \rho  \ ,
\end{aligned}$$

as

$$\left( \frac{\partial h}{\partial \rho} \right)_s = \frac{1}{\rho} \left( \frac{\partial p}{\partial \rho} \right)_s = \frac{a^2(\rho, \overline{s})}{\rho} \ .$$

```

$$\begin{aligned}
 0
 & = \partial_{tt} \phi + \partial_t \frac{|\nabla \phi|^2}{2} + \frac{a^2}{\rho} \partial_t \rho && \left( \text{mass:} \ \partial_t \rho = - \rho \nabla^2 \phi - \nabla \rho \cdot \nabla \phi \right) \\
 & = \partial_{tt} \phi + \partial_t \frac{|\nabla \phi|^2}{2} - \frac{a^2}{\rho} \left\{ \nabla \phi \cdot \nabla \rho + \rho \nabla^2 \phi \right\} = && \left( \text{momentum:} \ a^2 \frac{\nabla \rho}{\rho} = - \left( \partial_t \nabla \phi + \nabla \frac{|\nabla \phi|^2}{2} \right) \right) \\ 
 & = \partial_{tt} \phi + \partial_t \frac{|\nabla \phi|^2}{2} - a^2 \nabla^2 \phi + \nabla \phi \cdot \left( \partial_t \nabla \phi + \nabla \frac{|\nabla \phi|^2}{2} \right) \ ,
\end{aligned}$$

or

$$0 = \partial_{tt} \phi - a^2 \nabla^2 \phi + \partial_t |\nabla \phi|^2 + \nabla \phi \cdot \nabla \frac{|\nabla \phi|^2}{2} \ .$$

(compressible:irrotational:potential-equation:homoentropic:linearized)=
### Linearized equation

Assuming small perturbation of the asymptotic flow, with velocity $\mathbf{u}_\infty$ and thermodynamic state $\text{TD}_{\infty}$ with speed of sound $a^2_\infty$, the velocity field can be written as

$$\mathbf{u}(\mathbf{r},t) \sim \mathbf{u}_\infty + \mathbf{u}'(\mathbf{r},t) \ ,$$

the potential as

$$\phi(\mathbf{r},t) \sim \mathbf{u}_\infty \cdot \mathbf{r} + \varphi(\mathbf{r},t) \ ,$$

and all the thermodynamic variables their linear Taylor expansion around the reference state

$$\begin{aligned}
  \rho & = \rho_\infty + \rho' \\
       & \dots
\end{aligned}$$

Linearization of the potential equation gives

$$D^{\mathbf{u}_\infty}_{tt} \varphi - a^2_\infty \nabla^2 \varphi = 0 \ ,$$

with the differential operator - here applied twice[^Dt-Dt] - $D^{\mathbf{u}_\infty}_t = \partial_t + \mathbf{u}_\infty \cdot \nabla$ representing advection with the free-stream velocity field $\mathbf{u}_\infty$.

[^Dt-Dt]: $D^{\mathbf{u}_\infty}_{tt} \varphi := D^{\mathbf{u}_\infty}_{t} \left( D^{\mathbf{u}_\infty}_{t} \varphi \right)$ $= (\partial_t + \mathbf{u}_\infty \cdot \nabla) (\partial_t \varphi + \mathbf{u}_\infty \cdot \nabla \varphi)$ $= \partial_{tt} \varphi + 2 \mathbf{u} \cdot \partial_t \nabla \varphi + \mathbf{u}_\infty \cdot \nabla ( \mathbf{u}_\infty \cdot \nabla \varphi)$.

```{dropdown} Details

$$\begin{aligned}
  0
  & = \partial_{tt} \phi - a^2 \nabla^2 \phi + \partial_t |\nabla \phi|^2 + \nabla \phi \cdot \nabla \frac{|\nabla \phi|^2}{2} = \\
  & = \partial_{tt} \varphi - ( a^2_\infty + {a'}^2 ) \nabla^2 \varphi + 2 \partial_t ( \nabla \phi \cdot \mathbf{u}_\infty + \dots ) + \mathbf{u}_\infty \cdot \nabla \left( \mathbf{u}_\infty \cdot \nabla \varphi + \dots \right) \simeq \\
  & = \partial_{tt} \varphi - a^2_{\infty} \nabla^2 \varphi + 2 \mathbf{u}_\infty \cdot \partial_t \nabla \phi + \mathbf{u}_\infty \cdot \nabla ( \mathbf{u}_\infty \cdot \nabla \varphi ) \ .
\end{aligned}$$

Introducing the *linear* differential operator

$$D^{\mathbf{u}_\infty}_t := \partial_t + \mathbf{u}_\infty \ ,$$

the linearized equation can be re-written as

$$D^{\mathbf{u}_\infty}_{tt} \varphi - a^2_\infty \nabla^2 \varphi = 0 \ ,$$

being $D^{\mathbf{u}_\infty}_{tt}$ the operator applied twice, $D^{\mathbf{u}_\infty}_{tt} = D^{\mathbf{u}_\infty}_{t}D^{\mathbf{u}_\infty}_{t}$.

```

Introducing a set of Cartesian coordinates with the $\hat{\mathbf{x}}$-axis aligned with the free-stream velocity $\mathbf{u}_\infty = U_{\infty} \hat{\mathbf{x}}$, the differential operator can be written as

$$D_t^{\mathbf{u}_\infty} = \partial_t + U_\infty \partial_x \ ,$$

and the linearized equation of the potential becomes

$$\varphi_{tt} + 2 U_\infty \partial_{xt} \varphi + U_\infty^2 \varphi_{xx} - a_\infty^2 \left( \varphi_{xx} + \varphi_{yy} + \varphi_{zz} \right) = 0 \ .$$

### Linearized steady potential equation - Prandtl-Glauert transformation

Steady equation becomes

$$(1-M_\infty^2) \varphi_{xx} + \varphi_{yy} + \varphi_{zz} = 0 \ .$$

This equation can be transformed into a Laplace equation (the same equation governing the potential for incompressible flows) with a transformation of coordinates

$$\begin{aligned}
 \widetilde{x} & = \frac{ x }{ \sqrt{1 - M_\infty^2} } \\
 \widetilde{y} & = y                       \\
 \widetilde{z} & = z                       \\
\end{aligned}$$

so that 

$$\frac{\partial \widetilde{x}}{\partial x} = \frac{1}{ \sqrt{1 - M^2} } \ ,$$

and

$$\varphi_{\widetilde{x} \widetilde{x}} + \varphi_{\widetilde{y} \widetilde{y}} + \varphi_{\widetilde{z} \widetilde{z}} = 0 \ .$$

```{dropdown} Details

With

$$\widetilde{x} = \beta x \ ,$$

it follows

$$\frac{\partial}{\partial x} = \frac{\partial \widetilde{x}}{\partial x}\frac{\partial}{\partial \widetilde{x}} = \beta \frac{\partial}{\partial \widetilde{x}} \ ,$$

$$\frac{\partial^2}{\partial x^2} = \beta^2 \frac{\partial^2}{\partial \widetilde{x}^2} \ ,$$

so that 

$$\begin{aligned}
  0
  & = \left( 1 - M_\infty^2 \right) \varphi_{xx} + \varphi_{yy} + \varphi_{zz} = \\
  & = \left( 1 - M_\infty^2 \right) \beta^2 \varphi_{\widetilde{x} \widetilde{x}} + \varphi_{yy} + \varphi_{zz} = \\
  & = \varphi_{\widetilde{x} \widetilde{x}} + \varphi_{yy} + \varphi_{zz} \ ,
\end{aligned}$$

if $\beta = \frac{1}{\sqrt{1-M^2_\infty}}$.


```

#### Nature of the equation

*Discussion with 2-dimensional equation first*

* If the free-stream is **subsonic**, $M_\infty \in [0,1)$[^subsonic-flow], the differential equation is **elliptic**
* If the free-stream is **supersonic**, $M_\infty > 1$ (and no shock occurs? Or how to treat them? How strong can they be?) the differential equation is **hyperbolic**. *Method of characteristics...*


[^subsonic-flow]: In order to get a subsonic flow in the whole domain, the free-stream velocity should be smaller than the speed of sound enough to avoid local supersonic regions in the flow.

**todo** 3-dimensional equation

### Pressure coefficient

Pressure coefficient is defined as

$$c_p = \frac{p-p_\infty}{\frac{1}{2}\rho_\infty U_\infty^2}$$

**Subsonic flow.** Linearizing momentum equation for homoentropic flows,

$$\begin{aligned}
  h - h_\infty 
  = \frac{U_\infty^2}{2} - \frac{(\mathbf{u}_\infty + \mathbf{u}') \cdot (\mathbf{u}_\infty + \mathbf{u}')}{2}
  \simeq - \mathbf{u}_\infty \cdot \mathbf{u}' \ .
\end{aligned}$$

Using $dh = T ds + \frac{dp}{\rho}$ for homoentropic flows, $ds = 0$, $dp = \rho dh$,

$$p' = p - p_\infty \simeq \rho_\infty ( h' - h_\infty ) = - \rho_\infty \mathbf{u}_\infty \cdot \mathbf{u}' \ ,$$

so that the linearized pressure coefficient reads

$$c_p = - \frac{2 \mathbf{u}_\infty \cdot \mathbf{u}'}{U_\infty^2} \ .$$

With the assumption of $\mathbf{u}_\infty = U_\infty \hat{\mathbf{x}}$,

$$c_p = - \frac{2}{U_\infty} \frac{\partial \varphi}{\partial x} \ .$$

Now, the pressure coefficient for compressible flow can be compared with the pressure coefficient for incompressible flow $c_p^{inc}$ in the same domain (e.g. with the same geometry of solid bodies).

$$\begin{aligned}
  c_p(x,y,z)
  & = - \frac{2}{U_\infty} \frac{\partial \varphi(x,y,z)}{\partial x} = && \widetilde{\varphi}(\widetilde{x},y,z) = \varphi(x(\widetilde{x}),y,z) \\
  & = - \frac{2}{U_\infty} \frac{\partial \widetilde{x}}{\partial x} \frac{\partial \widetilde{\varphi}(\widetilde{x},y,z)}{\partial \widetilde{x}} = \\
  & = - \frac{1}{\sqrt{1 - M^2_{\infty}}} \frac{2}{U_\infty} \frac{\partial \widetilde{\varphi}}{\partial \widetilde{x}}(\widetilde{x},y,z \ ,
\end{aligned}$$

so that

$$c_p(x,y,z) = \frac{c_p^{inc}(\widetilde{x},y,z)}{\sqrt{1-M_\infty^2}} \ .$$

