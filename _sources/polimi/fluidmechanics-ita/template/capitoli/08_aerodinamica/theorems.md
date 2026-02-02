(fluid-mechanics:aerodynamics:vortex-theorems)=
# Theorems about vorticity

## Kelvin's theorem

```{prf:theorem} Kelvin's theorem

In a barotropic or constant density flow, with negligible viscosity effects, the circulation on a material line $\ell(t)$ is constant in time,

$$0 = \frac{d \Gamma_{\ell(t)}}{dt} = \dfrac{d}{dt} \oint_{\ell(t)} \mathbf{u} \cdot \hat{\mathbf{t}} \ .$$

```

```{dropdown} Proof 1, using time derivative over time dependent domains
:open:

Using the expression of the time derivative over a [work line integral](https://basics2022.github.io/bbooks-math-miscellanea/ch/tensor-algebra-calculus/time-derivative-of-integrals.html#work-line-integral-along-a-line), over a closed line with no discontinuity in the functions so that $\mathbf{f}(\mathbf{r}_B) \cdot \mathbf{v}_B - \mathbf{f}(\mathbf{r}_A) \cdot \mathbf{v}_A = 0$,

$$\begin{aligned}
  \dfrac{d}{dt} \oint_{\ell(t)} \mathbf{u} \cdot \hat{\mathbf{t}} 
  & = \oint_{\ell(t)} \partial_t \mathbf{u} \cdot \hat{\mathbf{t}} + \oint_{\ell(t)} \nabla \times \mathbf{u} \cdot \mathbf{u}_b \times \hat{\mathbf{t}} = && (1) \\
  & = \oint_{\ell(t)} \hat{\mathbf{t}} \cdot \left\{ \partial_t \mathbf{u} + \boldsymbol\omega \times \mathbf{u} \right\} = && (2) \\
  & = \oint_{\ell(t)} \hat{\mathbf{t}} \cdot \left\{ \partial_t \mathbf{u} + \mathbf{u} \cdot \nabla \mathbf{u} - \nabla \frac{|\mathbf{u}|^2}{2} \right\} = && (3) \\
  & = - \oint_{\ell(t)} \hat{\mathbf{t}} \cdot \nabla \left\{ \nabla \Pi + \nabla \chi + \frac{|\mathbf{u}|^2}{2} \right\} + \oint_{\ell(t)} \nu \hat{\mathbf{t}} \cdot \nabla^2 \mathbf{u} = && (4) \\
  & = \oint_{\ell(t)} \nu \hat{\mathbf{t}} \cdot \nabla^2 \mathbf{u} = && (5) \\
  & = 0 \qquad \text{if $\nu = 0$} \ ,
\end{aligned}$$

with $(1)$ $\mathbf{u}_b = \mathbf{u}$ for material lines, and $\boldsymbol\omega = \nabla \times \mathbf{u}$, and using the properties of the mixed vector product $\mathbf{a} \cdot \mathbf{b} \times \mathbf{c} = \mathbf{b} \cdot \mathbf{c} \times \mathbf{a}$, $(2)$ $\mathbf{u} \cdot \nabla \mathbf{u} = \boldsymbol\omega \times \mathbf{u} + \nabla \frac{|\mathbf{u}|^2}{2}$, $(3)$ from the momentum equation $D_t \mathbf{u} = \mathbf{g} + \nu \nabla^2 \mathbf{u} - \nabla \Pi$, and $\mathbf{g} = - \nabla \chi$, and $(4)$ $\oint_{\ell(t)} \hat{\mathbf{t}} \cdot \nabla \Phi = \oint_{\ell(t)} d \Phi = 0$.

```

```{dropdown} Proof 2, using material coordinates
:open:

```

## Helmholtz's theorems

A **vortex line** is defined as a line everywhere tangent to the vorticity vector field $\boldsymbol\omega(\mathbf{r})$. A **vortex tube** is a 3-dimensional region of space with a lateral surface that is delimited by a set of vortex lines, and thus whose normal vector is orthogonal to the vorticity field, $\hat{\mathbf{n}} \cdot \boldsymbol\omega = 0$ on $S_{lat}$. It immediately follows first Helmholtz's theorem.

```{prf:theorem} First Helmholtz's theorem

The flux of the vorticity field is constant across all the sections of a vortex tube, at a given time.


```

```{dropdown} Proof
:open:

As the vorticity is the curl of the velocity field, $\boldsymbol = \nabla \times \mathbf{u}$, it's divergence is identically zero, $\nabla \cdot \boldsymbol\omega = 0$. Integrating over a volume delimited by the lateral surface of a vortex tube and 2 sections, and applying divergence theorem and the definition of the vortex tube,

$$\begin{aligned}
  0
  & = \int_V \nabla \cdot \boldsymbol\omega = \\
  & = \oint_{\partial V} \hat{\mathbf{n}} \cdot \boldsymbol\omega = \\
  & = \int_{S_1    } \hat{\mathbf{n}}_1 \cdot \boldsymbol\omega + 
      \int_{S_2    } \hat{\mathbf{n}}_2 \cdot \boldsymbol\omega + 
      \int_{S_{lat}} \underbrace{\hat{\mathbf{n}} \cdot \boldsymbol\omega}_{=0} = \\
\end{aligned}$$

Reversing the unit normal on surface $S_1$ in order to get an "oriented" vortex tube, with $\hat{\mathbf{n}}|_{S_1} = - \hat{\mathbf{n}}_1$ pointing inward, and  $\hat{\mathbf{n}}|_{S_2} = \hat{\mathbf{n}}_2$, the theorem is proved,

$$\int_{S_1} \hat{\mathbf{n}} \cdot \boldsymbol\omega = \int_{S_2} \hat{\mathbf{n}} \cdot \boldsymbol\omega \ .$$

```

```{prf:theorem} Second Helmholtz's theorem

Vortex lines are material lines.

```

```{dropdown} Proof.
:open:

Let's take two points on a vortex line,

$$\begin{aligned}
 & \mathbf{r}_1(t)  \\
 & \mathbf{r}_2(t) = \mathbf{r}_1(t) + \Delta \ell(t) \hat{\mathbf{t}}(t) + o(\Delta \ell(t)) \ , 
\end{aligned}$$

with $\boldsymbol\omega(\mathbf{r}_1(t), t) = \omega(\mathbf{r}_1(t), t) \hat{\mathbf{t}}(t)$. At time $t + \Delta t$, the position of the two material points reads

$$\begin{aligned}
  \mathbf{r}_1(t + \Delta t) & = \mathbf{r}_1(t) + \mathbf{u}(\mathbf{r}_1(t), t) \Delta t + o (\Delta t) \\
  \mathbf{r}_2(t + \Delta t) & = \mathbf{r}_2(t) + \mathbf{u}(\mathbf{r}_2(t), t) \Delta t \\
                             & = \mathbf{r}_2(t) + \left[ \mathbf{u}(\mathbf{r}_1(t), t) + \Delta \mathbf{r}_{12}(t) \cdot \nabla \mathbf{u}(\mathbf{r}_1(t), t) + o(|\Delta \mathbf{r}_{12}(t)|) \right] \Delta t + o(\Delta t) \ ,
\end{aligned}$$

so that

$$\Delta \mathbf{r}_{12}(t + \Delta t) = \Delta \mathbf{r}_{12}(t) + \Delta \mathbf{r}_{12}(t) \cdot \mathbf{u}(\mathbf{r}_1(t),t) \Delta t + o(|\Delta \mathbf{r}_{12}(t)| \Delta t + o(\Delta t) \ .$$

Now, using the vorticity equation for inviscid flows

$$D_t \boldsymbol\omega = ( \boldsymbol\omega \cdot \nabla ) \mathbf{u} \ ,$$

the vorticity in $\mathbf{r}_1(t+\Delta t)$ at time $t+\Delta t$ is

$$\begin{aligned}
  \boldsymbol\omega(\mathbf{r}_1(t+\Delta t), t+\Delta t)
  & = \boldsymbol\omega(\mathbf{r}_1(t), t) + D_t \boldsymbol\omega (\mathbf{r}_1(t), t) \, \Delta t + o(\Delta t) = \\
  & = \boldsymbol\omega(\mathbf{r}_1(t), t) + \boldsymbol\omega (\mathbf{r}_1(t), t) \cdot \nabla \mathbf{u}(\mathbf{r}_1(t), t) \, \Delta t + o(\Delta t)  \ .
\end{aligned}$$

Comparing the evolution of the material segment $\Delta \mathbf{r}_{12}$ and the vorticity vector in $\mathbf{r}_1$, it's immediate to realize that they have the same evolution, namely for $\Delta t \rightarrow 0$

$$d_t \mathbf{v} = \mathbf{v} \cdot \nabla \mathbf{u}(\mathbf{r}_1(t),t) \ .$$

```


