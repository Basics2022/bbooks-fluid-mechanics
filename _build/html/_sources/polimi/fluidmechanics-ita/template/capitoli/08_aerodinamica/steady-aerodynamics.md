(fluid-mechanics:aerodynamics:steady)=
# Steady Aerodynamics

## Mathematical model

$$\begin{aligned}
 - \Delta \phi & = 0  && \mathbf{r} \in \Omega \\
 \hat{\mathbf{n}} \cdot \boldsymbol\nabla \phi & = 0 && \mathbf{r} \in S_{body} \\
 \phi & = \dots && \mathbf{r} \in S_{\infty}
\end{aligned}$$

In order to build a domain where the flow is irrotational, wake regions must be cut from the domain: both sides of these regions become part of the boundary of the domain. As shown below, there's no physical wake for 2-dimensional steady flows, while wakes exist in 3-dimensional flows.

## Green's function method

### 2-dimensional problems

**Green's function.** Green's function of a 2-dimensional Poisson problem reads

$$G(\mathbf{r}; \mathbf{r}_0) = - \frac{1}{2\pi} \ln |\mathbf{r} - \mathbf{r}_0| \ .$$

**Note!** When taking the logarithm of a physical quantity, that quantity must be non-dimensional. Here, the problem must be made non-dimensional, as an example scaling all the lengths with a reference length.

```{dropdown} Derivation of the Green's function for 2-dimensional Poisson problem.

Solutions with spherical symmetry of the Poisson equation in 2-dimensional domains, in the whole domain except for the origin of the coordinates (or the position of the *active* point, $\mathbf{r}_0$, as the problem is independent from translation of coordinates under the assumption of homogeneous domain)

$$-\Delta G = \delta(r) \ .$$

The problem is regular for $r \ne 0$

$$-\Delta G \quad , \quad |\mathbf{r}| \ne 0 \ ,$$

and it can be solved using the expression of the Laplacian for spherical symmetric scalar fields

$$0 = \frac{1}{r} \left( r G'(r) \right)' \ ,$$

and integrating twice

$$\begin{aligned}
  G'(r) & = \frac{A}{r} \\
  G (r) & = A \ln r + B \\
\end{aligned}$$

The additive constant $B$ is set to zero, while the constant $A$ is evalauted by the condition

$$1 = \int_{\Omega} \delta(r) = - \int_{\Omega} \Delta G = - \oint_{\partial \Omega} \hat{\mathbf{n}} \cdot \boldsymbol\nabla G = - \oint_{C_r} \hat{\mathbf{r}} \cdot \hat{\mathbf{r}} \partial_r G = - \oint_{C_r} \frac{A}{r} = - \int_{\theta=0}^{2\pi} \frac{A}{r} \, r d\theta = - 2 \pi A \ ,$$

so that $A = -\frac{1}{2 \pi}$, and

$$G(\mathbf{r}; \mathbf{r}_0) = - \frac{1}{2\pi} \ln |\mathbf{r} - \mathbf{r}_0| \ .$$

```

**Solution.**

$$\begin{aligned}
  E(\mathbf{r}_0) \phi(\mathbf{r}_0) 
  & = \int_{\mathbf{r}\in\Omega} \delta(\mathbf{r}-\mathbf{r}_0) \phi(\mathbf{r}) = \\
  & = - \int_{\mathbf{r}\in\Omega} \nabla^2_{\mathbf{r}} G(\mathbf{r}; \mathbf{r}_0) \phi(\mathbf{r}) = \\
  & = - \int_{\mathbf{r}\in\Omega} \nabla_\mathbf{r} \cdot \left( \nabla_{\mathbf{r}} G(\mathbf{r}; \mathbf{r}_0) \phi(\mathbf{r}) -  G(\mathbf{r}; \mathbf{r}_0)  \nabla_{\mathbf{r}} \phi(\mathbf{r}) \right) - \int_{\mathbf{r}\in\Omega} G(\mathbf{r};\mathbf{r}_0) \underbrace{\nabla^2_{\mathbf{r}} \phi(\mathbf{r})}_{=0 \text{ , Poisson eq}} = \\
  & = - \int_{\mathbf{r}\in \partial \Omega} \left\{ \hat{\mathbf{n}}(\mathbf{r}) \cdot \nabla_{\mathbf{r}} G(\mathbf{r}; \mathbf{r}_0) \phi(\mathbf{r}) -  \hat{\mathbf{n}}(\mathbf{r}) \cdot \nabla_{\mathbf{r}} \phi(\mathbf{r}) G(\mathbf{r}; \mathbf{r}_0) \right\}  \ .
\end{aligned}$$

As shown below, in 2-dimensional steady problems there's no physical wake, i.e. $\partial \Omega = S_{body} \cup S_{\infty}$, or equivalently on $S^+_w$and $S^-_w$, 

$$0 = \hat{\mathbf{n}}^- \cdot \mathbf{u}^- + \hat{\mathbf{n}}^+ \cdot \mathbf{u}^+ = \ ...$$

...

For the perturbation potential, $\varphi := \phi - \phi_\infty = \phi - \mathbf{U}_\infty \cdot \mathbf{r}$, with $\varphi|_{S_\infty} = 0$ (**todo** prove it! And find the trend $\propto r^{\alpha}$)

$$\begin{aligned}
  E(\mathbf{r}_0) \varphi(\mathbf{r}_0) 
  & = - \int_{\mathbf{r}\in \partial \Omega} \left\{ \hat{\mathbf{n}}(\mathbf{r}) \cdot \nabla_{\mathbf{r}} G(\mathbf{r}; \mathbf{r}_0) \varphi(\mathbf{r}) -  \hat{\mathbf{n}}(\mathbf{r}) \cdot \nabla_{\mathbf{r}} \varphi(\mathbf{r}) G(\mathbf{r}; \mathbf{r}_0) \right\} = \\
  & = - \int_{\mathbf{r}\in S_b} \hat{\mathbf{n}}(\mathbf{r}) \cdot \nabla_{\mathbf{r}} G(\mathbf{r}; \mathbf{r}_0) \varphi(\mathbf{r}) -  \mathbf{U}_\infty \cdot \int_{\mathbf{r} \in S_b}  \hat{\mathbf{n}}(\mathbf{r}) G(\mathbf{r}; \mathbf{r}_0)  \ .
\end{aligned}$$

This equation can be recast as an **integro-differential equation** for the perturbation potential on the surface of the body $\mathbf{r}_0 \in S_{b}$ that can be solved by collocation, as an example using [**boundary element methods**](https://basics2022.github.io/bbooks-math-miscellanea/ch/pde/bem.html). Once this problem is solved, the perturbation potential on $S_b$ is known, and the perturbation potential can be computed in every point of the domain.

```{dropdown} $E(\mathbf{r}_0)$
:open:

The term $E(\mathbf{r}_0)$ comes from the computation of the integral with the Dirac delta.

$$E(\mathbf{r}_0) = \begin{cases} 1 && \mathbf{r}_0 \in \Omega \\ \frac{1}{2} && \mathbf{r}_0 \in \partial \Omega \\ 0 && \mathbf{r}_0 \notin \Omega \cup \partial \Omega \end{cases}$$

The value $\frac{1}{2}$ is a particular case indeed, if the point $\mathbf{r}_0$ is on a locally flat - no sharp angles - of the boundary. If the point is at a sharp angle - being $\theta$ the angle outside the domain - $E(\mathbf{r}_0) = \frac{\theta}{2 \pi}$.

```


```{dropdown} Asymptotic behavior of the perturbation velocity
:open:

For $|\mathbf{r}_0| \gg |\mathbf{r}|$, Taylor expansion of the Green's function $G(\mathbf{r}; \mathbf{r}_0)$ and its gradient $\boldsymbol\nabla_{\mathbf{r}} G(\mathbf{r}; \mathbf{r}_0)$ read

$$\begin{aligned}
 G(\mathbf{r}; \mathbf{r}_0)
 & \simeq G(\mathbf{r}; \mathbf{r}_0)|_{\mathbf{r} = \mathbf{0}} + \mathbf{r} \cdot \nabla_{\mathbf{r}} G(\mathbf{r}, \mathbf{r}_0)|_{\mathbf{r} = \mathbf{0}} = \\
 & = - \frac{1}{2 \pi} \ln |\mathbf{r}_0| + \mathbf{r} \cdot \frac{1}{2 \pi} \frac{\mathbf{r}_0}{|\mathbf{r}_0|^2} \ .
\end{aligned}$$

$$\begin{aligned}
 \boldsymbol\nabla_{\mathbf{r}} G(\mathbf{r}; \mathbf{r}_0)
 & \simeq \boldsymbol\nabla_{\mathbf{r}} G(\mathbf{r}; \mathbf{r}_0)|_{\mathbf{r} = \mathbf{0}} + \mathbf{r} \cdot \nabla_{\mathbf{r}} \nabla_{\mathbf{r}} G(\mathbf{r}, \mathbf{r}_0)|_{\mathbf{r} = \mathbf{0}} = \\
 & = \frac{1}{2 \pi} \frac{\mathbf{r}_0}{|\mathbf{r}_0|^2} + \frac{1}{2\pi} \left[ - \dfrac{\mathbf{r}}{|\mathbf{r}_0|^2} + 2 \mathbf{r} \cdot \mathbf{r}_0 \frac{\mathbf{r}_0}{|\mathbf{r}_0|^4} \right] = \\
 & = \frac{1}{2 \pi} \frac{\mathbf{r}_0 - \mathbf{r}}{|\mathbf{r}_0|^2} + \frac{1}{\pi} \mathbf{r} \cdot \mathbf{r}_0 \frac{\mathbf{r}_0}{|\mathbf{r}_0|^4} \ .
\end{aligned}$$

First and second space derivatives of the Green's function read

$$\begin{aligned}
  - \nabla_{\mathbf{r}} \ln |\mathbf{r}_0 - \mathbf{r}| 
  & = - \mathbf{\hat{x}}_i \dfrac{\partial}{\partial x_i} \ln | \mathbf{r}_0 - \mathbf{r} | = \\
  & = - \mathbf{\hat{x}}_i \frac{x_{i} - x_{0,i}}{| \mathbf{r}_0 - \mathbf{r} |^2} = \\
  & = - \frac{\mathbf{r} - \mathbf{r}_0}{| \mathbf{r}_0 - \mathbf{r} |^2} \ .
\end{aligned}$$

$$\begin{aligned}
  - \nabla_{\mathbf{r}} \frac{\mathbf{r} - \mathbf{r}_0}{| \mathbf{r}_0 - \mathbf{r} |^2} 
  & = - \mathbf{\hat{x}}_k \dfrac{\partial}{\partial x_k} \left( \mathbf{\hat{x}}_i \frac{x_{i} - x_{0,i}}{| \mathbf{r}_0 - \mathbf{r} |^2} \right) = \\
  & = - \mathbf{\hat{x}}_k \mathbf{\hat{x}}_i \left[ \dfrac{\delta_{ij} |\mathbf{r}_0 - \mathbf{r}|^2 - 2 (x_i - x_{0,i})(x_k - x_{0,k}) }{| \mathbf{r}_0 - \mathbf{r} |^4} \right] = \\ 
  & = - \frac{1}{| \mathbf{r}_0 - \mathbf{r} |^2} \, \mathbb{I} + 2 \frac{(\mathbf{r}-\mathbf{r}_{0}) \otimes (\mathbf{r}-\mathbf{r}_{0})}{| \mathbf{r}_0 - \mathbf{r} |^4} \ .
\end{aligned}$$

```

```{dropdown} Doublet/vortex equivalence
:open:

A continuous distribution of doublets over a surface $S$ is equivalent to the sum of a surface distribution of vortices over $S$ and a line distribution of vortices over $\partial S$. The perturbation potential in $\mathbf{r}_0 \notin S$ generated by a surface distribution of doublets with intensity $\mu(\mathbf{r})$ on $S$ reads

$$\varphi(\mathbf{r}_0) = \int_{\mathbf{r}\in S} \hat{\mathbf{n}}(\mathbf{r}) \cdot \nabla G(\mathbf{r}; \mathbf{r}_0) \, \mu(\mathbf{r}) \ .$$

Exploiting the properties, $\nabla G = - \nabla_0 G$, the potential can be recast as

$$\varphi(\mathbf{r}_0) = - \nabla_0 \cdot \int_{\mathbf{r}\in S} \hat{\mathbf{n}}(\mathbf{r}) G(\mathbf{r}; \mathbf{r}_0) \, \mu(\mathbf{r}) \ ,$$

so that the velocity reads

$$\begin{aligned}
  \mathbf{u}(\mathbf{r}_0) 
  & = \nabla_0 \varphi(\mathbf{r}_0) = \\
  & = - \nabla_0 \left( \nabla_0 \cdot \int_{\mathbf{r}\in S} \hat{\mathbf{n}}(\mathbf{r}) G(\mathbf{r}; \mathbf{r}_0) \, \mu(\mathbf{r}) \right) = \\
  & = - \nabla_0^2 \left( \int_{\mathbf{r}\in S} \hat{\mathbf{n}}(\mathbf{r}) G(\mathbf{r}; \mathbf{r}_0) \, \mu(\mathbf{r}) \right) - \nabla_0 \times \nabla_0 \times \left( \int_{\mathbf{r}\in S} \hat{\mathbf{n}}(\mathbf{r}) G(\mathbf{r}; \mathbf{r}_0) \, \mu(\mathbf{r}) \right) = \\ 
  & = - \nabla_0 \times \nabla_0 \times \left( \int_{\mathbf{r}\in S} \hat{\mathbf{n}}(\mathbf{r}) G(\mathbf{r}; \mathbf{r}_0) \, \mu(\mathbf{r}) \right) = \\ 
  & = - \nabla_0 \times \left( \int_{\mathbf{r}\in S} \hat{\mathbf{n}}(\mathbf{r}) \times \nabla_0 G(\mathbf{r}; \mathbf{r}_0) \, \mu(\mathbf{r}) \right) = \\ 
  & = \nabla_0 \times \boldsymbol\psi(\mathbf{r}_0) \ ,
\end{aligned}$$

having introduced the definition of vector potential - or stream function - $\boldsymbol\psi(\mathbf{r}_0)$, and
having used the vector identity, $\nabla^2 \mathbf{v} = \nabla ( \nabla \cdot \mathbf{v} ) - \nabla \times \nabla \times \mathbf{v}$, and the definition of the Green's function for Poisson equation to see the first integral is identically zero,

$$\begin{aligned}
  \nabla_0^2 \left( \int_{\mathbf{r}\in S} \hat{\mathbf{n}}(\mathbf{r}) G(\mathbf{r}; \mathbf{r}_0) \, \mu(\mathbf{r}) \right)
  & = \int_{\mathbf{r}\in S} \hat{\mathbf{n}}(\mathbf{r}) \nabla_0^2 G(\mathbf{r}; \mathbf{r}_0) \, \mu(\mathbf{r})  = \\
  & = - \int_{\mathbf{r}\in S} \hat{\mathbf{n}}(\mathbf{r}) \delta(\mathbf{r}-\mathbf{r}_0) \, \mu(\mathbf{r})  = \\
  & = \mathbf{0} \ , \quad \text{for $\mathbf{r}_0 \notin S$} \ ,
\end{aligned}$$

and having exploited the relations $\nabla \times ( \mathbf{a} f(\mathbf{r}) ) = \mathbf{a} \times \nabla f(\mathbf{r})$, $\nabla^2 (\mathbf{a} f(\mathbf{r}) = \mathbf{a} \nabla^2 f(\mathbf{r})$, for constant $\mathbf{a}$.

The expression of the vector potential can be rearranged using integration by parts (be careful about the domain of the functions, and the differential operators. See below),

$$\begin{aligned}
\boldsymbol\psi(\mathbf{r}_0) 
  & = - \int_{\mathbf{r}\in S} \hat{\mathbf{n}}(\mathbf{r}) \times \nabla_0 G(\mathbf{r}; \mathbf{r}_0) \, \mu(\mathbf{r}) = \\
  & =   \int_{\mathbf{r}\in S} \hat{\mathbf{n}}(\mathbf{r}) \times \nabla   G(\mathbf{r}; \mathbf{r}_0) \, \mu(\mathbf{r}) = \\
  & =   \int_{\mathbf{r}\in S} \hat{\mathbf{n}}(\mathbf{r}) \times \nabla \left( G(\mathbf{r}; \mathbf{r}_0) \, \mu(\mathbf{r}) \right)
      - \int_{\mathbf{r}\in S} \hat{\mathbf{n}}(\mathbf{r}) \times \nabla^s \mu(\mathbf{r} ) \, G(\mathbf{r}; \mathbf{r}_0)  = \\
  & =  \oint_{\mathbf{r}\in \partial S} \hat{\mathbf{t}}(\mathbf{r}) \, \mu(\mathbf{r}) \, G(\mathbf{r}; \mathbf{r}_0)
      - \int_{\mathbf{r}\in S} \hat{\mathbf{n}}(\mathbf{r}) \times \nabla^s \mu(\mathbf{r} ) \, G(\mathbf{r}; \mathbf{r}_0)  = \\
\end{aligned}$$

so that a doublet distribution of intensity $\mu$ over surface $S$ is equivalent to the sum of a vortex distribution of intensity $-\hat{\mathbf{n}}(\mathbf{r}) \times \nabla^s \mu(\mathbf{r})$ over surface $S$ and a vortex distribution of intensity $\mu(\mathbf{r}) \hat{\mathbf{t}}(\mathbf{r})$ over the boundary $\partial S$ of the surface, being $\nabla^s \mu(\mathbf{r})$ the *surface gradient*, defined for function on a surface with coordinates $q^i$, $i=1:2$,

$$\nabla^s f = \mathbf{b}^i \frac{\partial f}{\partial q^i} \ ,$$

that can be defined for functions defined not only on the surface as the projection of the gradient on the surface,

$$\nabla^s = \left( \mathbb{I} - \hat{\mathbf{n}} \otimes \hat{\mathbf{n}} \right) \cdot \nabla \ ,$$

so that $\nabla^s f = \nabla f - \hat{\mathbf{n}} \hat{\mathbf{n}} \cdot \nabla f \ .$

In the manipulation of the expression of the vector potential, a [vector identity, see the second of the two useful lemmas in vector calculus](https://basics2022.github.io/bbooks-math-miscellanea/ch/tensor-algebra-calculus/calculus-euclidean.html#two-useful-lemmas) is used to transform the first integral, in Cartesian components

$$\oint_{\partial S} A t_l = \int_S n_i \varepsilon_{ijk} \partial_j ( A \delta_{kl} ) = \int_S n_i \varepsilon_{ijl} \partial_j A $$

or in vector formalism

$$\oint_{\partial S} A \hat{\mathbf{t}} \cdot \hat{\mathbf{e}}_l = \int_S \hat{\mathbf{n}} \cdot \nabla ( A \hat{\mathbf{e}}_l ) = \int_S \hat{\mathbf{n}} \times \nabla A \cdot \hat{\mathbf{e}}_l \ , $$

or, without projecting on the constant unit vector $\hat{\mathbf{e}}_l$ the first and the last expressions,

$$\oint_{\partial S} A \hat{\mathbf{t}} = \int_S \hat{\mathbf{n}} \times \nabla A \ .$$

The perturbation velocity is retrieve from the vector potential as $\mathbf{u}(\mathbf{r}_0) = \nabla_0 \times \boldsymbol\psi(\mathbf{r}_0)$,

$$\begin{aligned}
  \mathbf{u}'(\mathbf{r}_0)
  & = \nabla_0 \times \boldsymbol\psi(\mathbf{r}_0) = \\
  & = \nabla_0 \times \left[ 
       \oint_{\mathbf{r}\in \partial S} \mu(\mathbf{r}) \hat{\mathbf{t}}(\mathbf{r}) \, G(\mathbf{r}; \mathbf{r}_0)
      - \int_{\mathbf{r}\in S} \hat{\mathbf{n}}(\mathbf{r}) \times \nabla \mu(\mathbf{r} ) \, G(\mathbf{r}; \mathbf{r}_0)  = \\
    \right] = \\
  & = \oint_{\mathbf{r}\in \partial S} \mu(\mathbf{r}) \hat{\mathbf{t}}(\mathbf{r}) \times \nabla_0 G(\mathbf{r}; \mathbf{r}_0)
     - \int_{\mathbf{r}\in S} \left[ \hat{\mathbf{n}}(\mathbf{r}) \times \nabla \mu(\mathbf{r} ) \right] \times \nabla_0 G(\mathbf{r}; \mathbf{r}_0) \ .
\end{aligned}$$

```


```{dropdown} Details in integration by parts on surface in doublet/vortex equivalence
:open:

**todo** *Using surface coordinates, a surface nabla seamlessly appears*

```


```{dropdown} Relationship between doublet/vortex distribution and the circulation - 2-dimensional steady problems
:open:

In 2-dimensional steady problems there's no physical wake, i.e. no velocity discontinuities. For closed surfaces $|\partial S_b| = 0$, and thus the velocity field reads (with the unit normal vector pointing into the fluid domain, reversed w.r.t. the original expression at the beginning of this section),

$$\begin{aligned}
  \mathbf{u}'(\mathbf{r}_0) 
  & =   \int_{\mathbf{r} \in S_b} \boldsymbol\gamma(\mathbf{r}) \times \nabla_0 G(\mathbf{r}; \mathbf{r}_0) 
      + \int_{\mathbf{r} \in S_b} \sigma(\mathbf{r}_0) \nabla_0 G(\mathbf{r}; \mathbf{r}_0) \ ,
\end{aligned}$$

having defined vortex intensity $\boldsymbol\gamma(\mathbf{r}) := - \hat{\mathbf{n}} \times \nabla \mu(\mathbf{r})$, and the source intensity $\sigma(\mathbf{r}) := \hat{\mathbf{n}}(\mathbf{r}) \cdot \nabla \varphi(\mathbf{r})$.

Circulation along a line $\ell_0$ is defined as

$$\Gamma_{\ell_0} = \oint_{\ell_0} \mathbf{u}'(\mathbf{r}_0) \cdot \hat{\mathbf{t}}(\mathbf{r}_0) \ ,$$

Focusing on 2-dimensional problems, the surface $S_b$ becomes a line $\ell_b$. Let's deal here with closed surfaces: thus the integral over closed surface (line, in 2D) $\ell_b$ becomes $\oint_{\ell_b}$. The contribution to circulation of the source term is identically zero, as

$$\begin{aligned}
 \Gamma_{\ell_0}^{\sigma}
 & = \oint_{\mathbf{r}_0 \in \ell_0} \hat{\mathbf{t}}(\mathbf{r}_0) \cdot \oint_{\mathbf{r} \in \ell_b} \sigma(\mathbf{r}) \nabla_0 G(\mathbf{r}; \mathbf{r}_0) = \\
 & = \oint_{\mathbf{r} \in \ell_b} \sigma(\mathbf{r}) \oint_{\mathbf{r}_0 \in \ell_0} \hat{\mathbf{t}}(\mathbf{r}_0) \cdot \nabla_0 G(\mathbf{r}; \mathbf{r}_0) = \\
 & = \oint_{\mathbf{r} \in \ell_b} \sigma(\mathbf{r}) \oint_{\mathbf{r}_0 \in \ell_0} d_0 G(\mathbf{r}; \mathbf{r}_0) = \\
 & = 0 \ .
\end{aligned}$$

Thus, the contribution to circulation comes from vortex term only. Manipulating this contribution, it's possible to get an expression for the circulation as a function of the vortex intensity,

$$\begin{aligned}
  \Gamma_{\ell_0} = \Gamma_{\ell_0}^{\gamma}
  & = \oint_{\mathbf{r}_0 \in \ell_0} \hat{\mathbf{t}}(\mathbf{r}_0) \cdot \oint_{\mathbf{r} \in \ell_b} \boldsymbol\gamma(\mathbf{r}) \times \nabla_0 G(\mathbf{r}; \mathbf{r}_0) = \\
  & = - \oint_{\mathbf{r} \in \ell_b} \boldsymbol\gamma(\mathbf{r}) \cdot \oint_{\mathbf{r}_0 \in \ell_0} \hat{\mathbf{t}}(\mathbf{r}_0) \times \nabla_0 G(\mathbf{r}; \mathbf{r}_0) = \\
\end{aligned}$$

The integral over $\ell_0$ is equal to $-\hat{\mathbf{z}}$ (see below), and thus

$$\Gamma_{\ell_0} = \oint_{\mathbf{r} \in \ell_b} \gamma_z(\mathbf{r}) \ .$$

```


```{dropdown} $\oint_{\mathbf{r}_0 \in \ell_0} \hat{\mathbf{t}}_0 \times \nabla_0 G(\mathbf{r}; \mathbf{r}_0)$
:open:

**Method 1 - Using Green's lemma.** In a 2-dimensional plane, using Cartesian coordinates, $\mathbf{r} = x \hat{\mathbf{x}} + y \hat{\mathbf{y}}$, and [Green's lemma](https://basics2022.github.io/bbooks-math-miscellanea/ch/multivariable/intro.html#green-s-lemma) in the plane on a **simple domain**, the integral becomes

$$\begin{aligned}
  \oint_{\mathbf{r} \in \ell} \hat{\mathbf{t}} \times \nabla G(\mathbf{r}; \mathbf{r}_0)
  & = \hat{\mathbf{z}} \oint_{\mathbf{r} \in \ell} \left\{ t_x \partial_y G - t_y \partial_x G \right\} = && \text{(Green's lemma)} \\
  & = - \hat{\mathbf{z}} \int_{\mathbf{r} \in S_\ell} \left\{ \partial_{yy} G + \partial_{xx} G \right\} = \\
  & = - \hat{\mathbf{z}} \int_{\mathbf{r} \in S_\ell} \nabla^2 G(\mathbf{r}; \mathbf{r}_0) = \\
  & = 0 \ , 
\end{aligned}$$

if the singular point $\mathbf{r}_0$ of $G(\mathbf{r}; \mathbf{r}_0)$ is outside $S_{\ell}$, as $-\nabla^2 G(\mathbf{r}; \mathbf{r}_0) = \delta(\mathbf{r}-\mathbf{r}_0)$, and $\int_{\mathbf{r} \in S_\ell} \delta(\mathbf{r}_0 - \mathbf{r}) f(\mathbf{r}) = E_{S_\ell}(\mathbf{r}_0) f(\mathbf{r}_0)$.

In a **non-simply connected domain**, it's possible to introduce a cut in the domain. If the cut is geometrical and not physical - i.e. w/o any discontinuity of the functions across it -, the value of the integral is independent from the path, given a path winding around the hole in the domain the same number of times (**todo** *Add a link to some materia in [(Not so) Mathematics Basics](https://basics2022.github.io/bbooks-math-miscellanea/intro.html)*),

$$\oint_{\mathbf{r} \in \ell_1} \hat{\mathbf{t}} \times \nabla G(\mathbf{r}; \mathbf{r}_0) = \oint_{\mathbf{r} \in \ell_2} \hat{\mathbf{t}} \times \nabla G(\mathbf{r}; \mathbf{r}_0) \ .$$

Exploiting this path-independence, the value of the integral can be evaluated on a circle encolsing $\mathbf{r}_0$,

$$\begin{aligned}
 \oint_{\mathbf{r} \in \ell_1} \hat{\mathbf{t}} \times \nabla G(\mathbf{r}; \mathbf{r}_0) 
 & = \oint_{\mathbf{r} \in C} \hat{\mathbf{t}} \times \nabla G(\mathbf{r}; \mathbf{r}_0) = \\
 & = \int_{\theta = 0}^{2 \pi} \hat{\boldsymbol\theta} \times \frac{1}{2 \pi} \frac{\hat{\mathbf{r}}}{|\mathbf{r}|} |\mathbf{r}| d \theta = \\
 & = - \hat{\mathbf{z}} \ .
\end{aligned}$$

<!--
Thus, the circulation reads

$$\Gamma_{\ell_0} = \oint_{\mathbf{r} \in \ell_b} \gamma_z(\mathbf{r}) \ .$$
-->


```


```{dropdown} Asymptotic behavior of the perturbation potential
:open:

For $|\mathbf{r}_0| \gg |\mathbf{r}|$, using Taylor expansion of the Green's function $G(\mathbf{r}; \mathbf{r}_0)$ and its gradient $\boldsymbol\nabla_{\mathbf{r}} G(\mathbf{r}; \mathbf{r}_0)$, the perturbation velocity reads

$$\begin{aligned}
  \mathbf{u}'(\mathbf{r}_0) 
  & = - \int_{\mathbf{r}\in S_b} \left[ \hat{\mathbf{n}}(\mathbf{r}) \times \nabla \mu(\mathbf{r} ) \right] \times \nabla_0 G(\mathbf{r}; \mathbf{r}_0)
      + \int_{\mathbf{r} \in S_b} \hat{\mathbf{n}}(\mathbf{r}) \cdot \nabla_{\mathbf{r}} \varphi(\mathbf{r}) \nabla_0 G(\mathbf{r}; \mathbf{r}_0) = \\
  & \simeq - \int_{\mathbf{r}\in S_b} \left[ \hat{\mathbf{n}}(\mathbf{r}) \times \nabla \mu(\mathbf{r}) \right] \times \left[ \frac{1}{2 \pi} \frac{\mathbf{r}_0}{|\mathbf{r}_0|^2} - \frac{1}{2 \pi} \frac{\mathbf{r}}{|\mathbf{r}_0|^2} + \frac{1}{\pi} \mathbf{r} \cdot \mathbf{r}_0 \frac{\mathbf{r}_0}{|\mathbf{r}_0|^4}  \right] 
           + \int_{\mathbf{r} \in S_b}  \hat{\mathbf{n}}(\mathbf{r}) \cdot \nabla_{\mathbf{r}} \varphi(\mathbf{r}) \left[ \frac{1}{2 \pi} \frac{\mathbf{r}_0}{|\mathbf{r}_0|^2} - \frac{1}{2 \pi} \frac{\mathbf{r}}{|\mathbf{r}_0|^2} + \frac{1}{\pi} \mathbf{r} \cdot \mathbf{r}_0 \frac{\mathbf{r}_0}{|\mathbf{r}_0|^4}  \right] = \\
\end{aligned}$$

<!--
For $|\mathbf{r}_0| \gg |\mathbf{r}|$, using Taylor expansion of the Green's function $G(\mathbf{r}; \mathbf{r}_0)$ and its gradient $\boldsymbol\nabla_{\mathbf{r}} G(\mathbf{r}; \mathbf{r}_0)$, the perturbation potential reads

$$\begin{aligned}
  E(\mathbf{r}_0) \varphi(\mathbf{r}_0) 
  & = - \int_{\mathbf{r}\in S_b} \hat{\mathbf{n}}(\mathbf{r}) \cdot \nabla_{\mathbf{r}} G(\mathbf{r}; \mathbf{r}_0) \varphi(\mathbf{r}) - \int_{\mathbf{r} \in S_b} \hat{\mathbf{n}}(\mathbf{r}) \cdot \nabla_{\mathbf{r}} \varphi(\mathbf{r}) G(\mathbf{r}; \mathbf{r}_0) = \\
  & \simeq - \int_{\mathbf{r}\in S_b} \hat{\mathbf{n}}(\mathbf{r}) \cdot \left[ \frac{1}{2 \pi} \frac{\mathbf{r}_0 - \mathbf{r}}{|\mathbf{r}_0|^2} + \frac{1}{\pi} \mathbf{r} \cdot \mathbf{r}_0 \frac{\mathbf{r}_0}{|\mathbf{r}_0|^4}  \right] \varphi(\mathbf{r}) - \int_{\mathbf{r} \in S_b}  \hat{\mathbf{n}}(\mathbf{r}) \cdot \nabla_{r} \varphi(\mathbf{r}) \left[ - \frac{1}{2 \pi} \ln |\mathbf{r}_0| + \mathbf{r} \cdot \frac{1}{2 \pi} \frac{\mathbf{r}_0}{|\mathbf{r}_0|^2} \right] = \\
  & = - \int_{\mathbf{r}\in S_b} \hat{\mathbf{n}}(\mathbf{r}) \cdot \left[ \frac{1}{2 \pi} \frac{\mathbf{r}_0 - \mathbf{r}}{|\mathbf{r}_0|^2} + \frac{1}{\pi} \mathbf{r} \cdot \mathbf{r}_0 \frac{\mathbf{r}_0}{|\mathbf{r}_0|^4}  \right] \varphi(\mathbf{r}) - \int_{\mathbf{r} \in S_b}  \hat{\mathbf{n}}(\mathbf{r}) \cdot \nabla_{\mathbf{r}} \varphi(\mathbf{r}) \left[ \mathbf{r} \cdot \frac{1}{2 \pi} \frac{\mathbf{r}_0}{|\mathbf{r}_0|^2} \right] = \\
\end{aligned}$$

if the **surface** $S_b$ is **closed**, and there's no net mass flow through it, $\oint_{S_b} \hat{\mathbf{n}} \cdot \mathbf{u} = \oint_{S_b} \hat{\mathbf{n}} \cdot \nabla_{\mathbf{r}} \varphi(\mathbf{r}) = \mathbf{0}$.
-->

The first term in the second integral is proportional to the mass flux $\dot{m}$ across $S_b$, and so it's identically zero if $\int_{\mathbf{r} \in S_b} \hat{\mathbf{n}} \cdot \nabla_{\mathbf{r}} \varphi = 0$, as in the case of solid boundaries. The first term in the first integral is proportional to the circulation $\boldsymbol\Gamma$ (**todo** *Prove it*), thus the asymptotic behavior of the perturbation velocity as $|\mathbf{r}_0| \gg |\mathbf{r}|$ reads

$$\mathbf{u}'(\mathbf{r}_0) \simeq
 \frac{1}{2 \pi} \boldsymbol\Gamma \times \frac{\mathbf{r}_0}{|\mathbf{r}_0|^2} + 
 \frac{1}{2 \pi} \dot{m} \frac{\mathbf{r}_0}{|\mathbf{r}_0|^2} + O\left( \frac{1}{|\mathbf{r}_0|^2} \right)
$$


```

### 3-dimensional problems

**Green's function** [Green's function of a 3-dimensional Poisson problem](https://basics2022.github.io/bbooks-math-miscellanea/ch/pde/bem-poisson-helmholtz-waves.html#poisson-equation) reads

$$G(\mathbf{r}; \mathbf{r}_0) = \frac{1}{4\pi} \frac{1}{|\mathbf{r} - \mathbf{r}_0|} \ .$$

**Solution**

## Wake and the shape of the domain

*Physical conditions, with jump conditions*

*No physical wake in 2-dimensional steady flows*

## Theorems

### Kutta-Joukowski theorem

**2-dimensional flows.** Circulation along a path $\gamma$ is defined as the integral

$$\Gamma = \oint_{\gamma} \mathbf{u} \cdot \hat{\mathbf{t}} \ .$$

Let's define here a circuilation vector $\boldsymbol\Gamma = \Gamma\hat{\mathbf{z}}$, with $\hat{\mathbf{z}}$ orthogonal w.r.t. the plane of the 2-dimensional flow.

Using integral [balance equations](fluid-mechanics:balances) of mass and momentum 

$$\begin{aligned}
  & \frac{d}{dt} \int_V \rho + \oint_{\partial V} \rho \mathbf{u}^{rel} \cdot \hat{\mathbf{n}} = 0 \\
  & \frac{d}{dt} \int_V \rho \mathbf{u} + \oint_{\partial V} \rho \mathbf{u} \mathbf{u}^{rel} \cdot \hat{\mathbf{n}} = \int_V \rho \mathbf{g} + \oint_{\partial V} \mathbf{t}_{\hat{\mathbf{n}}} \ ,
\end{aligned}$$

under the assumptions of steady flow and control volume, $\frac{d}{dt} \equiv 0$ and $\mathbf{u}^{rel} = \mathbf{u}$, negligible volume force "$\mathbf{g} \sim \mathbf{0}$", and negligible viscous stress, $\mathbf{t}_{\hat{\mathbf{n}}} = - p \hat{\mathbf{n}}$, and rearranging the surface integrals of stress to get the force $\mathbf{F}$ acting on solid body $S_b$, it follows

$$\begin{aligned}
  &  \oint_{\partial V} \rho \mathbf{u} \cdot \hat{\mathbf{n}} = 0 \\
  &  \oint_{\partial V} \rho \mathbf{u} \mathbf{u} \cdot \hat{\mathbf{n}} = - \mathbf{F} + \oint_{S_{\infty}} \mathbf{t}_{\hat{\mathbf{n}}} \ .
\end{aligned}$$

```{dropdown} Details

...

```

The velocity field as the sum of the free-stream velocity and the perturbation velocity, 

$$\mathbf{u} = \mathbf{U}_{\infty} + \mathbf{u}' = \mathbf{U}_{\infty} + \nabla \varphi \ .$$

Under the additional assumption of uniform free-stream velocity, zero vorticity follows and the second [Bernoulli theorem](fluid-mechanics:bernoulli) holds,

$$\begin{aligned}
  P_{\infty} + \frac{1}{2} \rho U_{\infty}^2 
  & = P + \frac{1}{2} \rho |\mathbf{u}|^2 = \\
  & = P + \frac{1}{2} \rho U_\infty^2 + \rho \mathbf{U}_\infty \cdot \mathbf{u}' + \frac{1}{2} \rho |\mathbf{u}'|^2 \ ,
\end{aligned}$$

being $P$, $\mathbf{u}$ the pressure and velocity in any point of the fluid that is reached by a streamline coming from the free-stream. The expression of the aerodynamic force acting on the body can be recast as

$$\begin{aligned}
  \mathbf{F}
  & = - \oint_{S_\infty} \rho \mathbf{u} \mathbf{u} \cdot \hat{\mathbf{n}} - \oint_{S_\infty} P \hat{\mathbf{n}} = \\
  & = - \underbrace{\oint_{S_\infty} \rho \mathbf{U}_\infty \mathbf{U}_\infty \cdot \hat{\mathbf{n}}}_{ = \mathbf{0} \ , \ \ \oint_{S} \mathbf{const} \cdot \hat{\mathbf{n}} = 0 }
      - \underbrace{\oint_{S_\infty} \rho \mathbf{U}_\infty \mathbf{u}'       \cdot \hat{\mathbf{n}}}_{ = \mathbf{0} \text{ , from mass balance}}
      - \oint_{S_\infty} \rho \mathbf{u}'       \mathbf{U}_\infty \cdot \hat{\mathbf{n}}
      - \underbrace{\oint_{S_\infty} \rho \mathbf{u}'       \mathbf{u}'       \cdot \hat{\mathbf{n}}}_{ \rightarrow \ \mathbf{0} \text{ as } |S_{\infty}| \rightarrow \ \infty }
      - \oint_{S_\infty} P \hat{\mathbf{n}} = \\
  & \simeq - \oint_{S_\infty} \rho \mathbf{u}' \, \mathbf{U}_\infty \cdot \hat{\mathbf{n}} - \underbrace{\oint_{S_\infty} P_\infty \hat{\mathbf{n}}}_{= \mathbf{0} \ , \ \ \oint_{S} \hat{\mathbf{n}} = \mathbf{0}} + \oint_{S_\infty} \rho \mathbf{U}_\infty \cdot \mathbf{u}' \ \hat{\mathbf{n}} + \underbrace{\oint_{S_\infty} \frac{1}{2} \rho |\mathbf{u}'|^2 \, \hat{\mathbf{n}}}_{ \rightarrow \ \mathbf{0} \text{ as } |S_{\infty}| \rightarrow \ \infty } = \\
  & \simeq - \rho \mathbf{U}_\infty \cdot \oint_{S_\infty} \left( \hat{\mathbf{n}} \, \mathbf{u}' -  \mathbf{u}' \, \hat{\mathbf{n}} \right) = \\
  & = \rho \mathbf{U}_\infty \times \boldsymbol\Gamma \ .
\end{aligned}$$

```{dropdown} Circulation in Kutta-Joukowski theorem

$$\begin{aligned}
  \mathbf{U}_\infty \times \boldsymbol\Gamma 
  & = \mathbf{U}_\infty \times \hat{\mathbf{z}} \oint_{S} \mathbf{u} \cdot \hat{\mathbf{t}} = \\
  & = \mathbf{U}_\infty \times \hat{\mathbf{z}} \oint_{S} \left( \mathbf{U}_\infty + \mathbf{u}' \right) \cdot \hat{\mathbf{t}} = \\
  & = \mathbf{U}_\infty \times \hat{\mathbf{z}} \oint_{S} \mathbf{u}' \cdot \hat{\mathbf{t}} = \\
  & = \mathbf{U}_\infty \times \hat{\mathbf{z}} \oint_{S} \mathbf{u}' \cdot \left( \hat{\mathbf{z}} \times \hat{\mathbf{n}} \right) \ ,
\end{aligned}$$

Using a Cartesian basis, the $i^{th}$ component of the vector reads

$$\begin{aligned}
  \left\{ \mathbf{U}_\infty \times \boldsymbol\Gamma \right\}_i 
  & = \varepsilon_{ijk} U_j \delta_{kz} \oint_{S} u'_l \varepsilon_{lpq} \delta_{zp} n_q = \\
  & = \varepsilon_{ijz} \varepsilon_{qlz} U_j \oint_{S} u'_l n_q = \\
  & = \left( \delta_{iq} \delta_{jl} - \delta_{il} \delta_{jq} \right) U_j \oint_{S} u'_l n_q = \\
  & = U_j \oint_{S} \left( u'_j n_i - n_j u'_i \right) = \\
  & = \left\{ - \mathbf{U}_\infty \cdot \oint_{S} \left( \hat{\mathbf{n}} \, \mathbf{u}' - \mathbf{u}' \hat{\mathbf{n}} \right) \right\}_i \ .
\end{aligned}$$

having used the properties of the Ricci symbols, $\varepsilon_{ijk} = \varepsilon_{jki}$, and the identity $\varepsilon_{ijk} \varepsilon_{ilm} = \delta_{jl} \delta_{km} - \delta_{jm} \delta_{kl}$.


```


If a set of Cartesian coordinates is used and the free-stream velocity is aligned with the $\hat{\mathbf{x}}$ unit vector, the lift reads

$$\begin{aligned}
  L = \hat{\mathbf{y}} \cdot \mathbf{F} 
\end{aligned}$$

### D'Alembert paradox - 2 dimensional flow



