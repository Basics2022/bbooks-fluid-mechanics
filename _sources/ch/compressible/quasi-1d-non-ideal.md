(compressible:quasi-1d:non-ideal)=
# Non-ideal quasi-1 dimensional flows

```{dropdown} Details
:open:

**3-dimensional flows.** Equations for a generic volume $v_t$,

$$\begin{aligned}
  & \dfrac{d}{dt} \int_{v_t} \rho + \oint_{\partial v_t} \rho \mathbf{u}^{rel} \cdot \hat{\mathbf{n}} = 0 \\
  & \dfrac{d}{dt} \int_{v_t} \rho \mathbf{u} + \oint_{\partial v_t} \rho \mathbf{u} \mathbf{u}^{rel} \cdot \hat{\mathbf{n}} = \int_{v_t} \rho \mathbf{g}  + \oint_{\partial v_t} \mathbf{t}_{\mathbf{n}} \\
  & \dfrac{d}{dt} \int_{v_t} \rho e^t + \oint_{\partial v_t} \rho e^t \mathbf{u}^{rel} \cdot \hat{\mathbf{n}} = \int_{v_t} \rho \mathbf{g} \cdot \mathbf{u}  + \oint_{\partial v_t} \mathbf{t}_{\mathbf{n}} \cdot \mathbf{u} - \oint_{\partial v_t} \mathbf{q} \cdot \hat{\mathbf{n}} + \int_{v_t} \rho r \\
\end{aligned}$$

For a volume $V$ at rest, $\mathbf{u}^{rel} = \mathbf{u}$.

**Quasi-1 dimensional approximation.** Introducing the quasi-1 dimensional model, the contributions of heat conduction through lateral walls and heat source can be collected in one term,

$$-\int_{\partial \Delta S^{lat}} \hat{\mathbf{n}} \cdot \mathbf{q} + \int_{\Delta V} \rho r = \rho r A \Delta z \ ,$$

while the conduction along the axis of the stream-tube reads

$$-\int_{\partial A(z)} \hat{\mathbf{n}} \cdot \mathbf{q} - \int_{\partial A(z+\Delta z)} \hat{\mathbf{n}} \cdot \mathbf{q} \simeq 
A(z) q(z) - A(z+\Delta z) q(z+\Delta z) = - \partial_{z} ( q A ) \Delta z + o(\Delta z) \ .$$

With a hydraulic approximation[^hydraulic-re], the contribution of viscous stress in the momentum equation can be written as

$$\oint_{\partial v_t} \mathbf{s}_{\mathbf{n}} = - \frac{f_d A}{2 D_h} \rho \mathbf{u} |\mathbf{u}|$$

[^hydraulic-re]: This is a high-Reynolds model, with viscous stress proportional to dynamic pressure through a friction coefficient and the ration of the area of the section and the hydraulic diameter, $\frac{A}{D_h}$. As a reference see chapter about [Similitude](fluid-mechanics:similitude) and in particular the exexricse and the discussion about [Moody's diagram](fluid-mechanics:similitude:moody).

**Quasi-1 dimensional model: differential equations.** The conservative form of governing equations of compressible flows with friction and heat coduction reads

$$\partial_t \mathbf{u} + \partial_z \mathbf{F}(\mathbf{u}) + \partial_z \mathbf{F}^d(\mathbf{u}) = \mathbf{s} \ ,$$

or explicitly

$$
  \partial_t \begin{bmatrix} \rho A \\ \rho u A \\ \rho e^t A \end{bmatrix}
+ \partial_z \begin{bmatrix} \rho u A \\ \rho u^2 A + p A \\ \rho u h^t \end{bmatrix}  
+ \partial_z \begin{bmatrix} 0 \\ 0 \\ - q A \end{bmatrix}  
= \begin{bmatrix} 0 \\ p \partial_z A - \frac{f A}{2 D_h} \rho u |u| \\ \rho r A  \end{bmatrix}  \ ,
$$

where the axial heat conduction is logically serapated from the "convective" flux, as it's usually a **diffusive term** containing 2-nd order spatial derivative of primary variables, and changing the mathematical nature of the equations. As an example, using Fourier's law, $q = -k \partial_z T$, this term becomes

$$\begin{bmatrix} 0 \\ 0 \\ \partial_z ( k \partial_z T ) \end{bmatrix} \ .$$

If axial conduction is negligible if compared to convection and heat conduction through the walls of the streamtube, this contribution can be set to zero.

```

(compressible:quasi-1d:non-ideal:fanno)=
## Fanno

With non-negligible friction...

**todo** 
- analytical solution and diagrams for steady flows
- simulation for unsteady flows

(compressible:quasi-1d:non-ideal:rayleigh)=
## Rayleigh

With non-negligible heat conduction through lateral walls...

**todo** 
- analytical solution and diagrams for steady flows
- simulation for unsteady flows
