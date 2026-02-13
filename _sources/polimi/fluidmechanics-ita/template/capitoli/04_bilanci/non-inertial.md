(fluid-mechanics:balances:non-inertial)=
# Fluid dynamics in a non-inertial reference frame

Following the same approach as [Mechanics:Relative Kinematics:Point](https://basics2022.github.io/bbooks-physics-mechanics/ch/kinematics-relative.html), the position of a point $P$ is determined by the position vectors w.r.t. an inertial reference frame - here defined by an origin and a set oc Cartesian coordinates - $I: \, (O, x, y, z)$, and w.r.t. a generic reference frame - $G: \, (O_1, x_1, y_1, z_1)$.

$$\begin{aligned}
  (P - O) & = (O_1 - O) + (P - O_1) \\
  \mathbf{r}_{P/O} & = \mathbf{r}_{O_1/O} + \mathbf{r}_{P/O_1}
\end{aligned}$$

The unit vectors of the generic basis can be projected on the inertial basis as

$$\hat{\mathbf{e}}^1_i = \hat{\mathbf{e}}^1_i \cdot \hat{\mathbf{e}}_k \hat{\mathbf{e}}_k = \mathbb{R}^{0 \rightarrow 1} \cdot \hat{\mathbf{e}}_i \ ,$$

and their time derivatives read

$$\dfrac{d}{dt}\hat{\mathbf{e}}^1_i = \boldsymbol\omega_{1/} \times \hat{\mathbf{e}}^1_i \ .$$

Vector $\mathbf{r}_{P/O}$ is written as $\mathbf{r}$ for bervity, and $\mathbf{r}_{P/O_1}$ is written as a reference rotated vector, so that

$$\mathbf{r} = \mathbf{r}_{O_1/O} + \mathbb{R}^{0\rightarrow 1} \cdot \mathbf{r}' \ ,$$

or explicitly writing the dependence from time and the material coordinates - label - along with the relation prescribing absolute time for every observer, to get the transformation $(\mathbf{r},t)(\mathbf{r}',t')$

$$\begin{aligned}
  & \mathbf{r}(\mathbf{r}_m, t) = \mathbf{r}_{O_1/O}(t) + \mathbb{R}^{0\rightarrow 1}(t) \cdot \mathbf{r}'(\mathbf{r}_m, t) \\
  & t = t' \ .
\end{aligned}$$

$$\begin{aligned}
  & \mathbf{r}'(\mathbf{r}_m, t) = \mathbb{R}^T(t) \cdot \left[ \mathbf{r}(\mathbf{r}_m, t) - \mathbf{r}_{O_1}(t) \right] \\
  & t' = t \ .
\end{aligned}$$

**Rule of differentiation of composite functions.**

$$\begin{aligned}
  \partial_{t'} \_         
  & = \partial_{t'} t \, \partial_t \_ + \partial_{t'} \mathbf{r} \cdot \partial_{\mathbf{r}} \_ \\
  & = \partial_t \_ + \left[ \mathbf{v}_{O_1} + \dot{\mathbb{R}} \cdot \mathbf{r}' + \mathbb{R} \cdot \mathbf{v}' \right] \cdot \partial_{\mathbf{r}} \_ \\
  \partial_{\mathbf{r}'} \_ 
  & = \partial_{\mathbf{r}'} t \, \partial_t \_ +  \partial_{\mathbf{r}'} \mathbf{r} \cdot \partial_{\mathbf{r}} \_ \\
  & = \mathbb{R}^T \cdot \partial_{\mathbf{r}} \_
\end{aligned}$$

$$\begin{aligned}
  \partial_{t} \_         
  & = \partial_{t} t' \, \partial_{t'} \_ + \partial_t \mathbf{r'} \cdot \partial_{\mathbf{r'}} \_ \\
  & = \partial_{t'} \_ + \left[ \dot{\mathbb{R}}^T \cdot \left( \mathbf{r} - \mathbf{r}_{O_1} \right) - \mathbb{R}^T \cdot \mathbf{v}_{O_1} \right] \cdot \partial_{\mathbf{r}} \_ \\
  \partial_{\mathbf{r}} \_ 
  & = \partial_{\mathbf{r}} t \, \partial_t \_ +  \partial_{\mathbf{r}} \mathbf{r}' \cdot \partial_{\mathbf{r}'} \_ \\
  & = \mathbb{R} \cdot \partial_{\mathbf{r}'} \_
\end{aligned}$$

```{dropdown} Gradient of $\ \mathbf{v}(\mathbf{r}) = \mathbb{R} \cdot \mathbf{r}$, $\ \nabla \mathbf{v} = \mathbb{R}^T$.

$$\mathbf{v}(\mathbf{r}) = \mathbb{R} \cdot \mathbf{u}(\mathbf{r}) = \mathbf{u}(\mathbf{r}) \cdot \mathbb{R}^T$$

and using Cartesian coordinates, $\mathbf{r} = x^i \hat{\mathbf{e}}_i$

$$\mathbf{v} = v^i \hat{\mathbf{e}}_i = R^{ij} \hat{\mathbf{e}}_i \hat{\mathbf{e}}_j \cdot \left( x^k \hat{\mathbf{e}}_k \right) = R^{ij} x^j \hat{\mathbf{e}}_i$$

so that the gradient becomes

$$\partial_{\mathbf{r}} \mathbf{v} = \hat{\mathbf{e}}_i \partial_{x^{i}} \left( v^k(\mathbf{r}) \hat{\mathbf{e}}_k \right) = \partial_{x^i} v^k \hat{\mathbf{e}}_i \, \hat{\mathbf{e}}_k
= \partial_{x^i} \left( R^{kj} x^j \right) \hat{\mathbf{e}}_i \, \hat{\mathbf{e}}_k
= \left( R^{kj} \delta^{ij} \right) \hat{\mathbf{e}}_i \, \hat{\mathbf{e}}_k
=  R^{ki} \, \hat{\mathbf{e}}_i \, \hat{\mathbf{e}}_k = \mathbb{R}^T \ .
$$

```

```{dropdown} ...
:open:

$$\mathbf{v}(\mathbf{r}) = \mathbb{R} \cdot \mathbf{r} = \mathbf{r} \cdot \mathbb{R}^T$$

and using Cartesian coordinates, $\mathbf{r} = x^i \hat{\mathbf{e}}_i$

$$\mathbf{v} = v^i \hat{\mathbf{e}}_i = R^{ij} \hat{\mathbf{e}}_i \hat{\mathbf{e}}_j \cdot \left( u^k(\mathbf{r}) \hat{\mathbf{e}}_k \right) = R^{ij} u^j(\mathbf{r}) \hat{\mathbf{e}}_i$$

so that the gradient becomes

$$\partial_{\mathbf{r}} \mathbf{v} = \hat{\mathbf{e}}_i \partial_{x^{i}} \left( v^k(\mathbf{r}) \hat{\mathbf{e}}_k \right) = \partial_{x^i} v^k \hat{\mathbf{e}}_i \, \hat{\mathbf{e}}_k
= \partial_{x^i} \left( R^{kj} u^j(x^\ell) \right) \hat{\mathbf{e}}_i \, \hat{\mathbf{e}}_k
= \left( R^{kj} \partial_i u^j \right) \hat{\mathbf{e}}_i \, \hat{\mathbf{e}}_k
=  \nabla \mathbf{u} \cdot \mathbb{R}^T \ .
$$


$$\mathbf{a} \cdot \partial_{\mathbf{r}} \mathbf{v} = a^m \hat{\mathbf{e}}_m \cdot \hat{\mathbf{e}}_i \partial_{x^{i}} \left( v^k(\mathbf{r}) \hat{\mathbf{e}}_k \right) = \partial_{x^m} v^k \, \hat{\mathbf{e}}_k
= a^m \partial_{x^m} \left( R^{kj} u^j(x^\ell) \right) \, \hat{\mathbf{e}}_k
= a^m \left( R^{kj} \partial_m u^j \right) \, \hat{\mathbf{e}}_k
=  \mathbf{a} \cdot \nabla \mathbf{u} \cdot \mathbb{R}
= \mathbb{R} \cdot \left( \mathbf{a} \cdot \nabla \mathbf{u} \right).
$$


```

```{dropdown} Divergence $\ \nabla \cdot \left( \mathbb{A} \cdot \mathbf{v}(\mathbf{r}) \right)$
:open:

If the tensor $\mathbb{A}$ is independent from $\mathbf{r}$,

$$\nabla \cdot \left(  \mathbb{A} \cdot \mathbf{v}(\mathbf{r}) \right) = \partial_{x^i} \left( A^{ij} v^j \right) = \mathbb{A}^T : \nabla \mathbf{v} \ .$$


```

**Velocity.** Velocity of a material point reads

$$\begin{aligned}
\mathbf{u}(\mathbf{r}(\mathbf{r}_m,t), t) 
& := \left.\partial_t \mathbf{r}\right|_{\mathbf{r}_m} = \\
&  = \mathbf{v}_{O_1} + \dot{\mathbb{R}} \cdot \mathbf{r}' + \mathbb{R} \cdot \partial_{t} \mathbf{r}'|_{\mathbf{r}_m} = \\
&  = \mathbf{v}_{O_1} + \dot{\mathbb{R}} \cdot \mathbf{r}' + \mathbb{R} \cdot \mathbf{v}' = \\
\end{aligned}$$

**Acceleration.**

$$\begin{aligned}
  \mathbf{a}
  & = \left.\partial_t \mathbf{u}\right|_{\mathbf{r}_m} = \\
  & = \left.\partial_t \mathbf{u}\right|_{\mathbf{r}} + \partial_{t} \mathbf{r}|_{\mathbf{r}_m} \cdot \partial_{\mathbf{r}} \mathbf{u} = \\
  & = \left.\partial_t \mathbf{u}\right|_{\mathbf{r}} + \mathbf{u} \cdot \partial_{\mathbf{r}} \mathbf{u} \\
\end{aligned}$$

Using diffferentiation rules for composite functions, the advection operator becomes


$$\begin{aligned}
  \partial_t|_{\mathbf{r}} + \mathbf{u} \cdot \partial_{\mathbf{r}}
  & = \partial_{t'} + \left[ \left( \mathbf{r} - \mathbf{r}_{O_1} \right) \cdot \dot{\mathbb{R}} - \mathbf{v}_{O_1} \cdot \mathbb{R} \right] \cdot \partial_{\mathbf{r}'} + \left[ \mathbf{v}_{O_1} + \mathbf{r}' \cdot \dot{\mathbb{R}}^T + \mathbf{v}' \cdot \mathbb{R}^T \right] \cdot \mathbb{R} \cdot \partial_{\mathbf{r}'} = \\
  & = \partial_{t'} + \underbrace{\left[ (\mathbf{r}-\mathbf{r}_{O_1}) - \mathbf{r}' \cdot \mathbb{R}^T \right]}_{ = \mathbf{0} } \cdot \dot{\mathbb{R}} \cdot \partial_{\mathbf{r}'} + \mathbf{v}' \cdot \partial_{\mathbf{r}'} = \\
  & = \left.\partial_{t'}\right|_{\mathbf{r}'} + \mathbf{v}' \cdot \partial_{\mathbf{r}'} \ ,
\end{aligned}$$

and thus

$$\begin{aligned}
  \left[ \partial_{t'}|_{\mathbf{r}'} + \mathbf{v}' \cdot \partial_{\mathbf{r}'} \right] \mathbf{u} 
  & = \left[ \partial_{t'}|_{\mathbf{r}'} + \mathbf{v}' \cdot \partial_{\mathbf{r}'} \right] \left( \mathbf{v}_{O_1}(t) + \dot{\mathbb{R}}(t') \cdot \mathbf{r}' + \mathbb{R}(t) \cdot \mathbf{v}'(\mathbf{r}', t') \right)  \\
  & = \left[ \partial_{t'}|_{\mathbf{r}'} + \mathbf{v}' \cdot \partial_{\mathbf{r}'} \right] \left( \mathbf{v}_{O_1}(t) + \boldsymbol\omega_\times(t') \cdot \mathbb{R}(t') \cdot \mathbf{r}' + \mathbb{R}(t) \cdot \mathbf{v}'(\mathbf{r}', t') \right)  \\
  & = \mathbf{a}_{O_1} + \boldsymbol\alpha_\times \cdot \mathbb{R} \cdot \mathbf{r}' + \boldsymbol\omega_\times \cdot \boldsymbol\omega_\times \cdot \mathbb{R} \cdot \mathbf{r}' + 2 \boldsymbol\omega_\times \cdot \mathbb{R} \cdot \mathbf{v}' + \mathbb{R} \cdot \partial_{t'} \mathbf{v}' + \mathbf{v}' \cdot \partial_{\mathbf{r}'} \left( \mathbb{R} \cdot \mathbf{v}' \right) = \\ 
  & = \mathbf{a}_{O_1} + \boldsymbol\alpha_\times \cdot \mathbb{R} \cdot \mathbf{r}' + \boldsymbol\omega_\times \cdot \boldsymbol\omega_\times \cdot \mathbb{R} \cdot \mathbf{r}' + 2 \boldsymbol\omega_\times \cdot \mathbb{R} \cdot \mathbf{v}' + \mathbb{R} \cdot \left[ \partial_{t'} \mathbf{v}' + \mathbf{v}' \cdot \partial_{\mathbf{r}'} \mathbf{v}' \right] = \\ 
  & = \mathbf{a}_{O_1} + \boldsymbol\alpha_\times \cdot \mathbb{R} \cdot \mathbf{r}' + \boldsymbol\omega_\times \cdot \boldsymbol\omega_\times \cdot \mathbb{R} \cdot \mathbf{r}' + 2 \boldsymbol\omega_\times \cdot \mathbb{R} \cdot \mathbf{v}' + \mathbb{R} \cdot \underbrace{\left[ \partial_{t'} \mathbf{v}' + \mathbf{v}' \cdot \nabla' \mathbf{v}' \right]}_{ =: \mathbf{a}'} \ ,
\end{aligned}$$

having defined the acceleration of the material particles $\mathbf{a}'(\mathbf{r}', t)$ as seen by the non-inertial observer.
Multiplying by $\mathbb{R}^T \cdot$, all the terms are written w.r.t. the reference coordinates of the non-inertial reference frame. The very same procedure applies to the transformation ov balance equations.


<!--

**Time derivatives.** Time is the same in every referenece frame - in classical mechanics, time is absolute. Here the time derivative **as seen by an observer at rest with a reference frame** is defined and discussed.

...

Time derivative for an observer at rest with a reference frame is defined for vectors and tensors as the mathematical object expressed in the basis of the reference frame with time derivative of the components only.

...


The velocity of a point reads

$$\begin{aligned}
  \mathbf{u}^I_{P/O} 
  & := \dfrac{{}^I d}{d t} \mathbf{r}_{P/O} = \\
  & = \mathbf{u}^I_{O_1/O} + \dfrac{{}^I d}{dt} \left( r^1_{P/O_1, \, k} \hat{\mathbf{e}}^1_k \right) = \\
  & = \mathbf{u}^I_{O_1/O} + \mathbf{u}^G_{P/O_1} + \boldsymbol\omega_{G/I} \times \mathbf{r}_{P/O_1} \ .
\end{aligned}$$

-->

## Differential equations

### Mass

Conservative form of differential mass equation reads

$$\begin{aligned}
  0 
  & = \partial_t \rho + \nabla \cdot \left( \rho \mathbf{u} \right) = \\
  & = \partial_t \rho + \mathbf{u} \cdot \nabla \rho + \rho \nabla \cdot \mathbf{u} = \\
  & = \partial_{t'} \rho + \mathbf{v}' \cdot \nabla' \rho + \rho \nabla \cdot \mathbf{u} \ ,
\end{aligned}$$

Since 

$$\begin{aligned}
\nabla \cdot \mathbf{u} 
& = \nabla \cdot \left( \mathbf{v}_{O_1} + \dot{\mathbb{R}} \cdot \mathbf{r}' + \mathbb{R} \cdot \mathbf{v}' \right) = && \text{(see dropdown below)} \\
& = \nabla' \cdot \mathbf{v}' \ ,
\end{aligned}$$

the mass equation in the non-inertial reference frame has the very same expression as the mass equation in the inertial reference frame,

$$\begin{aligned}
  0 
  & = \partial_{t'} \rho + \mathbf{v}' \cdot \nabla' \rho + \rho \nabla' \cdot \mathbf{v}' = \\
  & = \partial_{t'} \rho + \nabla' \cdot \left( \rho \mathbf{v}' \right)  \  .
\end{aligned}$$

```{dropdown} $\nabla \cdot \mathbf{u}$
:open:

For generic tensor $\mathbb{A}$ and vector $\mathbf{v}$,

$$\begin{aligned}
  \nabla \cdot \left( \mathbb{A} \cdot \mathbf{v} \right)
  & = \partial_{x^i} \left( A^{ij} v^j \right) = \\
  & = \partial_{x^i} x^{' \ k} \partial_{x^{' \ k}} \left( A^{ij} v^j \right) = \\
  & = \partial_{x^{' \ k}} v^j A^{ij} \partial_{x^i} x^{' \ k} \ .
\end{aligned}$$

If $\mathbb{A} = \mathbb{R}$, $\mathbf{v} = \mathbf{v}'$, then

$$\nabla \cdot \left( \mathbb{R} \cdot \mathbf{v}' \right) = \partial_{x'^k} v'^j \underbrace{R^{ij} R^{ik}}_{\delta_{jk}} = \partial_{x'k} v'^k = \nabla' \cdot \mathbf{v}'(\mathbf{r}',t) \ .$$

If $\mathbb{A} = \dot{\mathbb{R}}$, $\mathbf{v} = \mathbf{r}'$, then

$$\nabla \cdot \left( \dot{\mathbb{R}} \cdot \mathbf{r}' \right) = \underbrace{\partial_{x'^k} r'^j}_{\delta^{jk}} \underbrace{\dot{R}^{ij} R^{ik}}_{ \left\{ - \boldsymbol\omega_\times \right\}_{jk} } = \delta_{jk} \varepsilon_{jlk} \omega_{l} = 0 \ ,$$

as Levi-Civita symbols are zero with repeated indices, and $\dot{\mathbb{R}} = \boldsymbol\omega_\times \cdot \mathbb{R}$, and thus $-\boldsymbol\omega_\times = \boldsymbol\omega_\times^T = \dot{\mathbb{R}}^T \cdot \mathbb{R}$

```

### Momentum

Convective form of differential momentum equation reads

$$\rho \left[ \partial_t + \mathbf{u} \cdot \nabla \right] \mathbf{u} = \rho \mathbf{g} + \nabla \cdot \mathbb{T} \ .$$

Using the expression of the acceleration above

$$\rho \mathbb{R} \cdot \mathbf{a}' = \rho \mathbf{g} + \nabla \cdot \mathbb{T} - \rho \left[ \mathbf{a}_{O_1} + \boldsymbol\alpha_\times \cdot \mathbb{R} \cdot \mathbf{r}' + \boldsymbol\omega_\times \cdot \boldsymbol\omega_\times \cdot \mathbb{R} \cdot \mathbf{r}' + 2 \, \boldsymbol\omega_\times \cdot \mathbb{R} \cdot \mathbf{v}' \right] \ .$$

multiplying by $\mathbb{R}^T \cdot $ gives the expression of the momentum equation as seen by the non-inertial reference frame

$$\rho \mathbf{a}' = \rho \mathbf{g}' + \nabla' \cdot \mathbb{T}' - \rho \left[ \mathbf{a}'_{O_1} + \boldsymbol\alpha'_{\times} \cdot \mathbf{r}' + \boldsymbol\omega'_{\times} \cdot \boldsymbol\omega'_{\times} \cdot \mathbf{r}' + 2 \boldsymbol\omega'_\times \cdot \mathbf{v}' \right] \ ,$$

being $\mathbf{g'} := \mathbb{R}^T \cdot \mathbf{g}$, $\boldsymbol\alpha'_{\times} = \mathbb{R}^T \cdot \boldsymbol\alpha_\times \cdot \mathbb{R}$, and the transformation of the divergence of the stress tensor given in the following dropdown box.

```{dropdown} $\nabla \cdot \mathbb{T}$
:open:

$$\begin{aligned}
  \partial_{x^i} T^{ij}(x^\ell) = \partial_{x^i} x'^{k} \partial_{x'^k} T^{ij}(x^\ell(x'^m)) \ ,
\end{aligned}$$

and thus

$$\mathbb{R}^T \cdot \nabla \cdot \mathbb{T} = R^{j \ell} R^{ik} \partial_{x'^k} T^{ij} = \partial_{x'^k} \left( R^{ik} T^{ij} R^{j \ell} \right) = \nabla \cdot \left( \mathbb{R}^T \cdot \mathbb{T} \cdot \mathbb{R} \right) = \nabla' \cdot \mathbb{T}' \ .$$

```

### Kinetic energy


### Total energy



## Homogeneity and isotropy

## Galilean relativity

With $\mathbf{v}$ constant in time and independent from position in space

$$
\begin{cases}
\mathbf{r} = \mathbf{r}' + \mathbf{v} t \\
t = t'
\end{cases}
\qquad , \qquad
\begin{cases}
\mathbf{r}' = \mathbf{r} - \mathbf{v} t \\
t' = t
\end{cases}
$$

and thus, the velocity of a point whose position in function of time $\mathbf{r}(t)$ reads

$$
\mathbf{u} = \mathbf{u}' + \mathbf{v} \\
$$

Using derivatives of composite functions

$$\begin{aligned}
  \partial_t & = \partial_{t'} - \mathbf{v} \cdot \nabla' \\
  \nabla     & = \nabla'
\end{aligned}$$

```{dropdown} Details

$$\begin{aligned}
  \partial_t f(\mathbf{r},t)
  & = \partial_t f'(\mathbf{r}'(\mathbf{r},t), t'(\mathbf{r},t)) = \\
  & = \partial_t \mathbf{r}' \cdot \partial_{\mathbf{r}'} f' + \partial_t t' \, \partial_{t'} f' = \\
  & = - \mathbf{v} \cdot \nabla' f' + \partial_{t'} f'  \ .
\end{aligned}$$ 

$$\begin{aligned}
  \nabla = \dots = \nabla' 
\end{aligned}$$

```

**Mass.** Conservative form

$$\begin{aligned}
  0 
  & = \partial_t \rho + \nabla \cdot \left( \rho \mathbf{u} \right) = \\
  & = \partial_{t'} \rho - \mathbf{v} \cdot \nabla' \rho + \nabla' \cdot \left( \rho \left( \mathbf{u}' + \mathbf{v} \right) \right) = \\
  & = \partial_{t'} \rho - \mathbf{v} \cdot \nabla' \rho + \nabla' \cdot \left( \rho \mathbf{u}' \right) + \mathbf{v} \cdot \nabla' \rho  = \\
  & = \partial_{t'} \rho + \nabla' \cdot \left( \rho \mathbf{u}' \right) \ .
\end{aligned}$$

## Integral equations

### Galilean relativity
