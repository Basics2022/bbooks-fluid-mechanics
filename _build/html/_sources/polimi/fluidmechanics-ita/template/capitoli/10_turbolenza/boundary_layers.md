(fluid-mechanics:turbulence:boundary-layer-flows)=
# Boundary layer flows

(fluid-mechanics:turbulence:boundary-layer-flows:prandtl-eq)=
## Prandtl equations

Steady RANS equations for a 2-dimensional flow using Cartesian coordinates read

$$\begin{cases}
  u \partial_x u + v \partial_y u + \partial_x \overline{u'u'} + \partial_y \overline{u'v'} - \nu \left( \partial_{xx} u + \partial_{yy} u \right) + \frac{1}{\rho} \partial_x P = 0 \\
  u \partial_x v + v \partial_y v + \partial_x \overline{u'v'} + \partial_y \overline{v'v'} - \nu \left( \partial_{xx} v + \partial_{yy} v \right) + \frac{1}{\rho} \partial_y P = 0 \\
  \partial_x u + \partial_y v = 0
\end{cases}$$

<!--
Let's assume the flow of interest has a main stream-wise direction, here identified by $x$ coordinate, while $y$ runs in the orthogonal direction. Let $U$, $V$, $X$, $\delta$ be characteristic $x$- and $y$- components of the velocity field and lengths. Non-dimensional equations become

$$\begin{cases}
  \frac{U^2}{X} u \partial_x u + \frac{U V}{\delta} v \partial_y u - \frac{\nu U}{X^2} \partial_{xx} u - \frac{\nu U}{\delta^2} \partial_{yy} u + \frac{P}{\rho X} \partial_x P = 0 \\
  \frac{U V}{X} u \partial_x v + \frac{V^2}{\delta} v \partial_y v - \frac{\nu V}{X^2} \partial_{xx} v - \frac{\nu V}{\delta^2} \partial_{yy} v + \frac{P}{\rho \delta} \partial_y P = 0 \\
  \frac{U}{X} \partial_x u + \frac{V}{\delta} \partial_y v = 0
\end{cases}$$

Let the 2 terms in the incompressibility constraint have the same order of magnitude. It follows that $V \sim \frac{\delta}{X} U$. Using this relation, and assuming $P \sim \rho U^2$, the non-dimensional equations become

$$\begin{cases}
  \frac{U^2}{X} \left[ \left( u \partial_x u + v \partial_y u - \partial_{yy} u + \partial_x P \right) - \left(\frac{\delta}{X}\right)^2 \left( \partial_{xx} u  \right) \right] = 0 \\
  \frac{U^2}{X} \left[ \frac{X}{\delta} \left( \partial_y P \right) + \frac{\delta}{X} \left( u \partial_x v + v \partial_y v - \partial_{yy} v \right) - \left( \frac{\delta}{X} \right)^3 \partial_{xx} v  \right] = 0 \\
  \frac{U}{X} \left(  \partial_x u + \partial_y v \right) = 0 \ ,
\end{cases}$$

If $X \gg \delta$ (or equivalently $U \gg V$),
- in the $x$-component of the momentum equation $\partial_{yy} u$ prevails over $\partial_{xx} u$; the convective term and the $x$-component of the pressure gradient has the same order of magnitude, given $P \sim \rho U^2$; the leading contribution of the viscous term has the same order of magnitude if $\frac{\nu X}{U \delta^2} \sim 1$, and thus 

   $$\delta(x) \sim \left( \frac{\nu x}{U} \right)^{\frac{1}{2}} = x \left( \frac{\nu}{x U} \right)^{\frac{1}{2}} = x \, \text{Re}_x^{-\frac{1}{2}} \ ,$$

   i.e.

   $$\delta(x) \sim x^{\frac{1}{2}} \ .$$

   In order to have thin boundary layers, $\delta(x) \ll x$, i.e. viscoisty should be "small enough" to be dominated by convection, except for the $\nu \partial_{yy} u$ contribution in the thin boundary layer region. Once divided by $\frac{U^2}{X}$ the leading order of the $x$-component of the momentum equation is $\sim 1$.

- in the $y$-component of the momentum equation, the leading term is the $y$-component of the pressure gradient, $\partial_y P$, with order $\varepsilon^{-1}$, being $\varepsilon := \frac{\delta}{X}$

Retaining the leading components of the equations, Navier-Stokes equation reduces to Prandtl equations, whose non-dimensional form reads
-->

...


$$\begin{cases}
  u \partial_x u + v \partial_y u + \partial_y \left( \overline{u' v'} \right) - \nu \partial_{yy} u + \partial_x P = 0 \\
  \partial_y \overline{v'^2} + \partial_y P = 0 \\
  \partial_x u + \partial_y v = 0 \ ,
\end{cases}$$

As the Reynolds' number increases, the effect of the viscosity in the average flow may become negligible (for flows without solid surfaces, where viscous sublayer exists) if compared with the Reynolds' stress. In these situations, Prandtl equations become

$$\begin{cases}
  u \partial_x u + v \partial_y u + \partial_y \left( \overline{u' v'} \right) + \partial_x P = 0 \\
  \partial_y \overline{v'^2} + \partial_y P = 0 \\
  \partial_x u + \partial_y v = 0 \ ,
\end{cases}$$

(fluid-mechanics:turbulence:boundary-layer-flows:self-similar)=
## Self-similar boundary layer flows

(fluid-mechanics:turbulence:boundary-layer-flows:self-similar:planar-jet)=
### Planar jet

From the $y$-component of the momentum, $P + \overline{v'^2} = P_0(x)$, and 1) if the fluctuation becomes negligible in the outer flow and 2) the outer flow is irrotational with unifrom velocity, then pressure is uniform in the whole domain, $P_0(x) = P_0$, and Prandtl equations from turbulent flows become

$$\begin{cases}
  u \partial_x u + v \partial_y u + \partial_y \left( \overline{u' v'} \right) = 0 \\
  \partial_x u + \partial_y v = 0 \ ,
\end{cases}$$

**Self-similar solution.** Looking for a self-similar solution 

$$\begin{aligned}
  u(x,y) & = U(x) f(\eta(x,y)) \\
  \overline{u'v'}(x,y) & = U^2(x) g(\eta(x,y)) \ ,
\end{aligned}$$

with $\eta(x,y) = \frac{y}{\delta(x)}$. Through the incompressibility constraint, the $y$-component of the velocity reads

$$\begin{aligned}
  v(x,y) - \underbrace{v(x,0)}_{=0}
  & = \int_{t = 0}^{y} \partial_y v(x,t) \, dt = \\
  & = - \int_{t=0}^{y} \partial_x u(x,t) \, dt = \\
  & = \int_{t=0}^{y} \left\{ -U'(x) f(\eta(x,t)) + U(x) \dfrac{df}{d \eta}(\eta(x,t)) \frac{t \delta'(x)}{\delta^2(x)} \right\} \, dt = \\
  & = \int_{\chi=0}^{\eta} \left\{ -U'(x) f(\eta(x,\delta(x) \chi)) \delta(x) + U(x) \dfrac{d f}{d \eta}(\eta(x, \delta(x) \chi)) \chi \delta'(x) \right\} \, d \chi \ ,
\end{aligned}$$

being

$$\partial_x u(x,y) = U'(x) f(\eta(x,y)) - U(x) f'(\eta(x,y)) \frac{y \delta'(x)}{\delta^2(x)} \ ,$$

and having transformed the variable $\chi = \frac{t}{\delta}$, and the extremes of integration accordingly.

**Mass, momentum and energy fluxes across normal planes.** Momentum flux reads

$$Q(x) = \int_{y=0}^{+\infty} u^2(x,y) \, dy \ .$$

Its derivative w.r.t. $x$ reads

$$\begin{aligned}
  \dfrac{d}{dx} Q(x)
  & = \dfrac{d}{dx} \int_{y=-\infty}^{+\infty} u^2(x,y) \, dy = \\
  & = \int_{y=-\infty}^{+\infty} \partial_x u^2 \, dy = \\
  & = - \int_{y=-\infty}^{+\infty} \partial_y \left\{ uv + \overline{u'v'}  \right\} \, dy = 0 \ ,
\end{aligned}$$

if the flow is at rest at infinity. Using the self-similar assumption, this derivative reads

$$0 = \dfrac{d Q}{dx} = \dfrac{d}{dx} \left[ U^2(x) \delta(x) \int_{\eta=-\infty}^{+\infty} f^2(\eta) \, d \eta \right] \ ,$$

so that it follows 

$$0 = \dfrac{d}{dx} \left( U^2(x) \delta(x) \right) = 2 U U' \delta + U^2 \delta' \ ,$$

or

$$U' = - \dfrac{\delta'}{2\delta} U \ .$$

Mass flux.

$$M(x) = \int_{y=-\infty}^{+\infty} u(x,y) \, dy \ , $$

and, if the self-similarity assumption holds, its derivative reads

$$\dfrac{d }{dx}M(x) = \dfrac{d}{dx} \left( U(x) \delta(x) \right) \int_{\eta=-\infty}^{+\infty} f(\eta) \, d\eta \ .$$

Energy flux.

$$E(x) = \int_{y=-\infty}^{+\infty} \dfrac{1}{2} u^3(x,y) \, dy \ , $$

and, if the self-similarity assumption holds, its derivative reads

$$\dfrac{d }{dx}E(x) = \dfrac{d}{dx} \left( \dfrac{1}{2} U^3(x) \delta(x) \right) \int_{\eta=-\infty}^{+\infty} f(\eta) \, d\eta \ .$$

**Solving for the self-similar solution.** Inserting the expressions of the velocity components and the turbulent stress into the $x$-component of the momentum equation,

$$\begin{aligned}
  0
  & = ( U f ) \left( U' f - U f' \eta \frac{\delta'}{\delta} \right) + \int_{\chi = 0}^{\eta} \left\{ -U' f \delta + U f' \chi \delta'  \right\} \, d\chi \, U f' \frac{1}{\delta} + U^2 g' \frac{1}{\delta} = \\
  & = U U' f^2 - U^2 f f' \eta \frac{\delta'}{\delta} - U U' f' \int_{\chi=0}^{\eta} f d \chi + U^2 f' \frac{\delta'}{\delta} \left(\left. \chi f \right|_{0}^{\eta} - \int_{\chi=0}^{\eta} f \, d \chi  \right)+ U^2 g' \frac{1}{\delta} = \\
  & = U U' f^2 - U U' f' \int_{\chi=0}^{\eta} f d \chi - U^2 f' \frac{\delta'}{\delta} \int_{\chi=0}^{\eta} f \, d \chi + U^2 g' \frac{1}{\delta}\ ,
\end{aligned}$$

and introducing the relation between the derivative of $U(x)$ and $\delta(x)$, and dividing by $\frac{U^2}{\delta}$

$$\frac{\delta'(x)}{2} \left[ f^2(\eta) + f'(\eta) \int_{\chi=0}^{\eta} f(\chi) d \chi \right] = g'(\eta) \ .$$

For the existence of a self-similar solution, no coefficient can explicitly depend on $x$ or $y$, so the derivative of the boundary layer thickness must be constant

$$\delta'(x) = S \ ,$$

and thus a linear spreading is found,

$$\delta(x) - \delta(x_0) = S ( x - x_0 ) \ .$$

As the momentum flux is constant in $x$, it follows that &mdash; setting the origin of the coordinates so that $\delta(x) = S x$ &mdash; the maximum velocity (velocity on the symmetry line of the jet) decreases as 

$$U(x) \propto \delta(x)^{-\frac{1}{2}} \propto x^{-\frac{1}{2}} \ .$$

Mass flux goes with $M(x) \sim x^{\frac{1}{2}}$ (increases, **entrainment**), while the energy flux goes with $E(x) \sim x^{-\frac{1}{2}}$ (decreases due to dissipation).

**Solution with constant turbulent viscosity as closure model.** With the assumption

$$- \overline{u'v'} = \nu_T \partial_y u \ ,$$

using self-similarity ansatz

$$-U^2 g = \nu_T U f' \frac{1}{\delta} \ ,$$

and with the additional assumption (**non-physical**, just to get a problem that can be solved analytically. An assumption more, an assumption less...),

$$\hat{\nu}_T := \frac{\nu_T}{\delta(x) U(x)} = \text{const.} \ ,$$

the two non-dimensional functions $f(\eta)$ and $g(\eta)$ are related as

$$g(\eta) = - \hat{\nu}_T f'(\eta) \ .$$

Thus, the solution of the equation

$$\frac{S}{2} \left[ f^2(\eta) + f'(\eta) \int_{\chi=0}^{\eta} f(\chi) d \chi  \right] + \hat{nu}_T f''(\eta) = 0 \ ,$$

with the proper boundary conditions provides the non-dimensional velocity profile. Introducing the function $F(\eta) = \int_{\chi=0}^{\eta} f(\chi) d \chi$,

$$\begin{aligned}
 0
 & = \frac{S}{2} \left( F'^{2}(\eta) + F''(\eta) F(\eta) \right) + \hat{\nu}T  F'''(\eta) = \\
 & = \frac{S}{2} \left( F(\eta) F'(\eta) \right)' + \hat{\nu}_T  F'''(\eta) \ .
\end{aligned}$$

Integrating once, and exploiting the boundary conditions (**todo**...)

$$\begin{aligned}
  0 
  & = \frac{S}{2} F(\eta) F'(\eta) + \hat{\nu}_T F''(\eta) =  \\
  & = \frac{S}{4} \left( F^2(\eta) \right)' + \hat{\nu}_T F''(\eta) \ ,
\end{aligned}$$

and integrating once again with the boundary condition $F'(0) = 1$,

$$\frac{S}{4} F^2(\eta) = \hat{\nu}_T \left( 1 - F'(\eta) \right) \ ,$$

or 

$$F'(\eta) = 1 - \frac{S}{4 \hat{\nu}_T} F^2(\eta) \ .$$

Integrating one last time,

$$F(\eta) = \frac{1}{\alpha} \text{tanh} \left( \alpha \eta \right) \ ,$$

with $\alpha = \sqrt{\frac{S}{4 \hat{\nu}_T}}$.
