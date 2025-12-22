(fluid-mechanics:bl)=
# Boundary layer

(fluid-mechanics:bl:prandtl-eq)=
## Equazioni di Prandtl dello strato limite

Steady Navier&mdash;Stokes equations for a 2-dimensional flow using Cartesian coordinates read

$$\begin{cases}
  u \partial_x u + v \partial_y u - \nu \left( \partial_{xx} u + \partial_{yy} u \right) + \frac{1}{\rho} \partial_x P = 0 \\
  u \partial_x v + v \partial_y v - \nu \left( \partial_{xx} v + \partial_{yy} v \right) + \frac{1}{\rho} \partial_y P = 0 \\
  \partial_x u + \partial_y v = 0
\end{cases}$$

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

$$\begin{cases}
  u \partial_x u + v \partial_y u - \partial_{yy} u + \partial_x P = 0 \\
  \partial_y P = 0 \\
  \partial_x u + \partial_y v = 0 \ ,
\end{cases}$$

**todo**
- *Discuss the mathematical nature of Prandtl equations (parabolic equation?): which boundary conditions? Examples for different flows: b.l. on flat surface, jet flows, shear layers, wakes behing a body,...*
- Pressure across boundary layers is approximately constant, as $\partial_y P = 0$

(fluid-mechanics:bl:integral-thickness)=
## Integral thicknesses

(fluid-mechanics:bl:vk-integral-eq)=
## Von Karman integral equation

(fluid-mechanics:bl:vk-integral-eq:integration)=
### Integration of Von Karman integral equation

(fluid-mechanics:bl:vk-integral-eq:thwaites)=
### Thwaites method

(fluid-mechanics:bl:self-similar)=
## Self-similar laminar boundary layer flows

(fluid-mechanics:bl:self-similar:blasius)=
### Boundary layer on flat plate: Blasius solution

Boundary conditions read

$$\begin{aligned}
  u(x=0, y        ) & = U \\
  u(x  , y=0      ) & = 0 \\
  v(x  , y=0      ) & = 0 \\
  u(x  , y=+\infty) & = U \\
\end{aligned}$$

Assuming irrotational flow outside the b.l., pressure is uniform in the whole domain: as the velocity is uniform in the irrotational region, pressure is uniform there, as a consequence of Bernoulli's theorems. As pressure is constant across the boundary layer in the orthogonal direction, pressure is uniform both inside and outside the boundary layer, $P(x,y) = \overline{P}$.

Without any reference length scale, a self-similar solution may exist: for a self-similar flow, fields are function of a self-similarity coordindate $\eta(x,y) = \frac{y}{\delta(x)}$ and not of $x$, $y$ independently.

Using stream-function $\psi$, $u = \psi_{/y}$, $v = - \psi_{/x}$, incompressibility constraint is identically satisfied. The last equation to deal with is the $x$-component of the momentum equation, that becomes

$$\psi_{/y} \psi_{/yx} - \psi_{/x} \psi_{/yy} - \nu \psi_{/yyy} = 0 \ .$$

Let $\psi(x,y) = U \delta(x) g\left( \eta(x,y) \right)$, the components of the velocity field becomes

$$\begin{aligned}
  \frac{u}{U} = \psi_{/y}
    & = \delta(x) g'(\eta) \eta_{/y} = \\
    & = \delta(x) g'(\eta) \frac{1}{\delta(x)} = \\
    & = g'(\eta) \\
  \frac{v}{U} = - \psi_{/x} 
    & = \delta'(x) g(\eta) + \delta(x) g'(\eta) \eta_{/x} = \\
    & = \delta'(x) g(\eta) - \delta(x) g'(\eta) \frac{y \delta'(x)}{\delta^2(x)} = \\
    & = \delta'(x) g(\eta) - \eta g'(\eta) \delta'(x)
\end{aligned}$$

while all the other derivatives appearing in the $x$-component of the momentum equation read

$$\begin{aligned}
  \psi_{/yy}  & = g''(\eta) \frac{1}{\delta(x)} \\
  \psi_{/yyy} & = g'''(\eta) \frac{1}{\delta^2(x)} \\
  \psi_{/yx}  & = - g''(\eta) \frac{y \delta'(x)}{\delta^2(x)} = - \eta g''(\eta) \frac{\delta'(x)}{\delta(x)} \\
\end{aligned}$$

Inserting these expression in the $x$-component of the momentum equation,

$$\begin{aligned}
 0 
 & = - U^2 g' g'' \eta \frac{\delta'}{\delta} - \left( \delta' g - \eta g' \delta' \right) g'' \frac{1}{\delta} - \nu U g''' \frac{1}{\delta^2} = \\
 & = - U^2 g  g'' \frac{\delta'}{\delta} - \nu U g''' \frac{1}{\delta^2} \ ,
\end{aligned}$$

or

$$0 = \frac{U \delta'(x) \delta(x)}{\nu} g(\eta) g''(\eta) + g'''(\eta) \ .$$

In order to get a self-similar solution, no term depending only on $x$ or $y$ may appear in the equation. Thus, the coefficient of the first term must be constant,

$$C = \frac{U \delta'(x) \delta(x)}{\nu} = \frac{U}{\nu} \dfrac{d}{dx} \dfrac{\delta^2(x)}{2} \ ,$$

and usually $C$ is chosen to be $C = \frac{1}{2}$ (this choice just changes the definition of the arbitrary thickness of the b.l. $\delta(x)$ by a multiplicative factor. Solving this equation, the arbitrary thickness of the b.l. goes as

$$\delta(x) - \delta(x_0) = \sqrt{ \frac{\nu}{U} ( x - x_0 ) } \ ,$$

while the $x$-component of the momentum equation becomes

$$\frac{1}{2} g g'' + g''' = 0 \ ,$$

supplied with the boundary conditions

$$\begin{aligned}
  g(0) & = 0 \\
  g'(0) & = 0 \\
  g'(+\infty) & = 1 \ ,
\end{aligned}$$

for the b.l. on a flat plate.

```{dropdown} Proof of the boundary conditions for the b.l on the flat plate

Proof that the 4 boundary conditions written as a function of the velocity field or the stream-function are equivalent to teh 3 boundary conditions written in terms of the similarity function $g(\eta)$

**todo**


```
