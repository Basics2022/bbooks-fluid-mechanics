(fluid-mechanics:aerodynamics:singularities)=
# Singularities in Poisson equation

## 3-dimensional Poisson equation

Green's function reads $\mathbf{G}(\mathbf{r}; \mathbf{r}_0) = \frac{1}{4 \pi |\mathbf{r} - \mathbf{r}_0| }$.

**Point Source.**

$$\begin{aligned}
  \varphi   (\mathbf{r}; \mathbf{r}_0) & = G(\mathbf{r}; \mathbf{r}_0)        = \frac{1}{4 \pi |\mathbf{r} - \mathbf{r}_0| } \\
  \mathbf{u}(\mathbf{r}; \mathbf{r}_0) & = \nabla G(\mathbf{r}; \mathbf{r}_0) = \frac{1}{4 \pi} \frac{\mathbf{r} - \mathbf{r}_0}{ |\mathbf{r} - \mathbf{r}_0|^3 }
\end{aligned}$$

having exploited 

$$\nabla |\mathbf{r}-\mathbf{r}_0| = \hat{\mathbf{x}}_i \partial_i |\mathbf{r} - \mathbf{r}_0| = \hat{\mathbf{x}}_i \frac{x_i - x_i^0}{|\mathbf{r}-\mathbf{r}_0|} = \frac{\mathbf{r}-\mathbf{r}_0}{|\mathbf{r}-\mathbf{r}_0|} \ .$$

```{dropdown} Poisson's equation $\ \nabla^2 \varphi = 0$, for $\ \mathbf{r} \ne \mathbf{r}_0$

...

```

```{dropdown} Velocity flux, $\ \oint_{\partial V} \mathbf{u} \cdot \hat{\mathbf{n}} = E_V(\mathbf{r}_0)$

...

```

**Point doublet.**

$$\begin{aligned}
  \varphi   (\mathbf{r}; \mathbf{r}_0) & = \hat{\mathbf{n}}_0 \cdot \nabla G(\mathbf{r}; \mathbf{r}_0)        = \\
  \mathbf{u}(\mathbf{r}; \mathbf{r}_0) & = \dots
\end{aligned}$$

```{dropdown} Poisson's equation $\ \nabla^2 \varphi = 0$, for $\ \mathbf{r} \ne \mathbf{r}_0$

$$\begin{aligned}
  \partial_{ii} \left( n^0_k \partial_k G \right)
  & = n^0_k \partial_k \partial_{ii} G =  0 \ ,
\end{aligned}$$

for $\mathbf{r} \ne \mathbf{r}_0$, as $\hat{\mathbf{n}}_0$ is independent from the spatial coordinate $\mathbf{r}$.

```

**Point vortex.** 

$$\begin{aligned}
  \mathbf{u}(\mathbf{r}; \mathbf{r}_0) & = \nabla G(\mathbf{r}; \mathbf{r}_0) \times \hat{\mathbf{t}}_0 
\end{aligned}$$

There's no irrotational point vortex solution. This is somehow linked to vorticity dynamics, and Hemlholtz's theorem about vortices: whatever a vortex is, vortices must be either lines or surfaces (either closed or with extreme points on solid boundaries), or a volume distribution of vorticity.

```{dropdown} Non-zero vorticity field for point vortices

$$\boldsymbol\omega = \nabla \times \mathbf{u} = \nabla \times \left( \nabla G \times \hat{\mathbf{t}}_0 \right)$$

$$\begin{aligned}
  \varepsilon_{ijk} \partial_j \left( \varepsilon_{klm} \partial_l G t_m \right) 
  & = \left( \delta_{il} \delta_{jm} - \delta_{im} \delta_{jl} \right) \partial_j \left( \partial_l G t_m \right) = \\ 
  & = \partial_m \left( \partial_i G t_m \right) - \partial_m \left( \partial_m G t_i \right) \ , 
\end{aligned}$$

with $\hat{\mathbf{t}}_0$ independent from the spatial coordinate $\mathbf{r}$. Here $\nabla^2 G = 0$, for $\mathbf{r} \ne \mathbf{r}_0$, and

$$\begin{aligned}
  \left( \hat{\mathbf{t}}_0 \cdot \nabla \right) \nabla G
  & = \dots \ne \mathbf{0} \ . 
\end{aligned}$$

```

**Line vortex.**

$$\mathbf{u}(\mathbf{r}) = \int_{\mathbf{r}_0 \in \ell_0} \nabla G(\mathbf{r}; \mathbf{r}_0) \times \hat{\mathbf{t}}_0 \Gamma_0 \ ,$$

with constant $\Gamma_0$ over the vortex line $\ell_0$.


```{dropdown} Vorticity field of a line vortex

If $\ell_0$ is not closed, ...

If $\ell_0$ is closed, (and $\mathbf{r} \notin \ell_0$ so that $G$ is not singular anywhere for $\mathbf{r}_0 \in \ell_0$), the velocity field can be recast as

$$\begin{aligned}
  \oint_{\mathbf{r}_0 \in \ell_0} \nabla G \times \hat{\mathbf{t}}_0 
  & = \oint_{\mathbf{r}_0 \in \ell_0} \varepsilon_{ijk} \partial_j G t^0_k = \\
  & = \int_{S_{\ell_0}} n_a^0 \varepsilon_{abk} \partial_b \left( \varepsilon_{ijk} \partial_j G \right) = \\
  & = \int_{S_{\ell_0}} n_a^0 \left( \delta_{ia} \delta_{jb} - \delta_{ib} \delta_{ja} \right) \partial_{bj} G = \\
  & = \int_{S_{\ell_0}} n_i^0 \underbrace{\partial_{jj} G}_{=0} - \int_{S_{\ell_0}} n_j^0 \partial_{ji} G = \\
\end{aligned}$$

while the vorticity field is identically **equal to zero** in every point $\mathbf{r} \notin \ell_0$,

$$\begin{aligned}
  \nabla \times \oint_{\mathbf{r}_0 \in \ell_0} \nabla G \times \hat{\mathbf{t}}_0 
  & = - \varepsilon_{ijk} \partial_j \int_{S_{\ell_0}} n_l^0 \partial_{lk} G = \\
  & = - \int_{S_{\ell_0}} n_l^0 \varepsilon_{ijk} \partial_{ljk} G = \\
  & = - \int_{S_{\ell_0}} \hat{\mathbf{n}}_0 \cdot \nabla \underbrace{\left( \nabla \times \nabla G \right)}_{= \mathbf{0}}
\end{aligned}$$



```
