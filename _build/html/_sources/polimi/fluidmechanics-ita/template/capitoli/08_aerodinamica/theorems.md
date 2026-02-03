(fluid-mechanics:aerodynamics:vortex-theorems)=
# Theorems about vorticity

## Kelvin's theorem

```{prf:theorem} Kelvin's theorem

In a barotropic or constant density flow, with negligible viscosity effects, the circulation on a material line $\ell(t)$ is constant in time,

$$0 = \frac{d \Gamma_{\ell(t)}}{dt} = \dfrac{d}{dt} \oint_{\ell(t)} \mathbf{u} \cdot \hat{\mathbf{t}} \ .$$

```

```{dropdown} Proof 1, using time derivative over time dependent domains

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

```

## Helmholtz's theorems

A **vortex line** is defined as a line everywhere tangent to the vorticity vector field $\boldsymbol\omega(\mathbf{r})$. A **vortex tube** is a 3-dimensional region of space with a lateral surface that is delimited by a set of vortex lines, and thus whose normal vector is orthogonal to the vorticity field, $\hat{\mathbf{n}} \cdot \boldsymbol\omega = 0$ on $S_{lat}$. It immediately follows first Helmholtz's theorem.

```{prf:theorem} First Helmholtz's theorem

The flux of the vorticity field is constant across all the sections of a vortex tube, at a given time.


```

```{dropdown} Proof

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

A vortex tube with a section collapsing to zero, can be modeled as a zero section[^filament-section], infinite vorticity **vortex filament** $\ell_\Gamma$, so that

[^filament-section]: A filament can be cut with a section orthogonal to its axis or with a generic angle w.r.t. it. Orthogonal cut gives the minimum area of the section $S_0$, a generic cut with unit normal $\hat{\mathbf{n}}$ gives $S$ so that $S_0 = \hat{\mathbf{n}} \cdot \hat{\mathbf{t}} S$.

$$\lim_{\begin{aligned} S & \rightarrow 0 \\ |\boldsymbol\omega| & \rightarrow +\infty \end{aligned}} \int_{S} \hat{\mathbf{n}} \cdot \boldsymbol\omega = \Gamma \ .$$

Vorticity in a irrotational 3-dimensional domain, $\mathbf{r} \in V$, containing a vortex filament, $\mathbf{r}_\Gamma \in \ell_\Gamma$, can be modelled using an impulsive *two-dimensional*[^dirac-delta-dimension] Dirac's delta function 

[^dirac-delta-dimension]: The 2-dimensional Dirac's delta $\delta_2(\mathbf{r}-\mathbf{r}_\Gamma)$ has physical dimensions $\left[ \delta_2 \right] = L^{-2}$, and it gives the value of the function in $\mathbf{r}_\Gamma$ from the integral on a 2-dimensional surface $S$, $\int_{\mathbf{r} \in S} f(\mathbf{r}) \delta_2(\mathbf{r}-\mathbf{r}_\Gamma) = f(\mathbf{r}_\Gamma)$, if $\mathbf{r}_\Gamma \in S$.

$$\boldsymbol\omega(\mathbf{r},t) = \boldsymbol\Gamma(\mathbf{r}_\Gamma,t) \delta_{2}(\mathbf{r} - \mathbf{r}_\Gamma) \ ,$$

with $\mathbf{r}_\Gamma \in \ell_\Gamma$, and $\boldsymbol\Gamma = \Gamma \hat{\mathbf{t}}$, with $\hat{\mathbf{t}}$ the unit vector tangent to the axis of the filament.

Circulation on a line winding once around a vortex filament with intensity $\Gamma$ reads $\oint_{\ell} \mathbf{u} \cdot \hat{\mathbf{t}} = \Gamma$.

---

**todo**

A **vortex surface** ...

Across a vortex surface the tangential velocity has a jump

$$\Delta \mathbf{u} = \dots$$
