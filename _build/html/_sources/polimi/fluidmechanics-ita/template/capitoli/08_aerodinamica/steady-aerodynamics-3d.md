(fluid-mechanics:aerodynamics:steady:3d)=
# Steady Aerodynamics - 3-dimensional flows

```{admonition} **todo**
:class: warning

- Some remarks, using vorticity dynamics:
  - the starting vortex: when were vorticity and circulation generated?
  - vortex intensity of the wake: $\boldsymbol\gamma_w(\mathbf{r}_w(\mathbf{r}_TE)) = \Delta \boldsymbol\gamma(\mathbf{r}_TE)$, from integral balance of vorticity in a stream-tube (**todo** *check it and add details*)
  - wake dynamics: transport of vorticity + vortex stretching; using vorticity equation, the shape of the wake $\mathbf{r}_w(\mathbf{r}_TE)$ and its intensity $\gamma(\mathbf{r}_w)$ can be computed (**todo** *check it and add details*) - or use Helmholtz's vortex theorem + Kelvin's circulation theorem (**todo** *Add sections in the vorticity dynamics, or add a section here in Aerodynamics chapter, under the assumptions of almost-everywhere irrotational flow and negliglible viscosity effects.*)

```

## Mathematical model

$$\begin{aligned}
 - \Delta \phi & = 0  && \mathbf{r} \in \Omega \\
 \hat{\mathbf{n}} \cdot \boldsymbol\nabla \phi & = 0 && \mathbf{r} \in S_{body} \\
\end{aligned}$$

In order to build a domain where the flow is irrotational, wake regions must be cut from the domain: both sides of these regions become part of the boundary of the domain. In an open domain, the boundary of the domain of the mathematical problem for the kinetic potential is the set union of body boundaries $S_b$, wakes sides $S_{w^+}$, $S_{w^-}$, and a surface at the infinity $S_{\infty}$,

$$\partial \Omega = S_b \cup S_{w^+} \cup S_{w^-} \cup S_{\infty} \ .$$

Boundary conditions on both sides of the [**wakes**]() follow from *jump conditions* of mass and momentum across a wake. Boundary conditions at the boundary **at the infinity** $S_{\infty}$ follow from the [*asymptotic behavior*]() of velocity and kinetic potential fields.

...


## Green's function method

**Green's function.** [Green's function of a 3-dimensional Poisson problem](https://basics2022.github.io/bbooks-math-miscellanea/ch/pde/bem-poisson-helmholtz-waves.html#poisson-equation)

$$G(\mathbf{r}; \mathbf{r}_0) = \frac{1}{4\pi |\mathbf{r} - \mathbf{r}_0|} \ .$$


```{dropdown} Derivation of the Green's function for 2-dimensional Poisson problem.

*...see reference above...*

```

**Solution.**

$$\begin{aligned}
  E(\mathbf{r}_0) \phi(\mathbf{r}_0) 
  & = \int_{\mathbf{r}\in\Omega} \delta(\mathbf{r}-\mathbf{r}_0) \phi(\mathbf{r}) = \\
  & = - \int_{\mathbf{r}\in\Omega} \nabla^2_{\mathbf{r}} G(\mathbf{r}; \mathbf{r}_0) \phi(\mathbf{r}) = \\
  & = - \int_{\mathbf{r}\in\Omega} \nabla_\mathbf{r} \cdot \left( \nabla_{\mathbf{r}} G(\mathbf{r}; \mathbf{r}_0) \phi(\mathbf{r}) -  G(\mathbf{r}; \mathbf{r}_0)  \nabla_{\mathbf{r}} \phi(\mathbf{r}) \right) - \int_{\mathbf{r}\in\Omega} G(\mathbf{r};\mathbf{r}_0) \underbrace{\nabla^2_{\mathbf{r}} \phi(\mathbf{r})}_{=0 \text{ , Poisson eq}} = \\
  & = - \int_{\mathbf{r}\in \partial \Omega} \left\{ \hat{\mathbf{n}}(\mathbf{r}) \cdot \nabla_{\mathbf{r}} G(\mathbf{r}; \mathbf{r}_0) \phi(\mathbf{r}) -  \hat{\mathbf{n}}(\mathbf{r}) \cdot \nabla_{\mathbf{r}} \phi(\mathbf{r}) G(\mathbf{r}; \mathbf{r}_0) \right\}  \ .
\end{aligned}$$

For the perturbation potential, $\varphi := \phi - \phi_\infty = \phi - \mathbf{U}_\infty \cdot \mathbf{r}$, with $\varphi|_{S_\infty} = 0$ (**todo** prove it! And find the trend $\propto r^{\alpha}$)

$$\begin{aligned}
  E(\mathbf{r}_0) \varphi(\mathbf{r}_0) 
  & = - \int_{\mathbf{r}\in \partial \Omega} \left\{ \hat{\mathbf{n}}(\mathbf{r}) \cdot \nabla_{\mathbf{r}} G(\mathbf{r}; \mathbf{r}_0) \varphi(\mathbf{r}) -  \hat{\mathbf{n}}(\mathbf{r}) \cdot \nabla_{\mathbf{r}} \varphi(\mathbf{r}) G(\mathbf{r}; \mathbf{r}_0) \right\} = \\
  & = - \int_{\mathbf{r}\in S_b} \hat{\mathbf{n}}(\mathbf{r}) \cdot \nabla_{\mathbf{r}} G(\mathbf{r}; \mathbf{r}_0) \varphi(\mathbf{r}) + \int_{\mathbf{r} \in S_b} \underbrace{ \hat{\mathbf{n}}(\mathbf{r}) \cdot \nabla \varphi(\mathbf{r})}_{= - \hat{\mathbf{n}} \cdot \mathbf{U}_\infty \text{ , from b.c.}} G(\mathbf{r}; \mathbf{r}_0) + \\
  & \quad - \int_{\mathbf{r}\in S_w} \hat{\mathbf{n}}(\mathbf{r}) \cdot \nabla_{\mathbf{r}} G(\mathbf{r}; \mathbf{r}_0) \, \underbrace{ \Delta \varphi(\mathbf{r})}_{ = \Delta \varphi_{TE} \text{ , from wake c.} }  + \\
  & \quad - \int_{\mathbf{r}\in S_\infty} \hat{\mathbf{n}}(\mathbf{r}) \cdot \nabla_{\mathbf{r}} G(\mathbf{r}; \mathbf{r}_0) \Delta \varphi(\mathbf{r}) + \int_{\mathbf{r} \in S_\infty} \hat{\mathbf{n}}(\mathbf{r}) \cdot \nabla \varphi(\mathbf{r}) \, G(\mathbf{r}; \mathbf{r}_0) \ .
\end{aligned}$$

This equation can be recast as an **integro-differential equation** for the perturbation potential on the surface of the body $\mathbf{r}_0 \in S_{b}$ that can be solved by collocation, as an example using [**boundary element methods**](https://basics2022.github.io/bbooks-math-miscellanea/ch/pde/bem.html). Once this problem is solved, the perturbation potential on $S_b$ is known, and the perturbation potential can be computed in every point of the domain.

```{dropdown} $E(\mathbf{r}_0)$
:open:

The term $E(\mathbf{r}_0)$ comes from the computation of the integral with the Dirac delta.

$$E(\mathbf{r}_0) = \begin{cases} 1 && \mathbf{r}_0 \in \Omega \\ \frac{1}{2} && \mathbf{r}_0 \in \partial \Omega \\ 0 && \mathbf{r}_0 \notin \Omega \cup \partial \Omega \end{cases}$$

The value $\frac{1}{2}$ is a particular case indeed, if the point $\mathbf{r}_0$ is on a locally flat - no sharp angles - of the boundary. If the point is at a sharp angle - being $\Theta$ the solid angle outside the domain - $E(\mathbf{r}_0) = \frac{\Theta}{4 \pi}$.

```

```{dropdown} Asymptotic behavior of the perturbation velocity
:open:

For $|\mathbf{r}_0| \gg |\mathbf{r}|$, Taylor expansion of the Green's function $G(\mathbf{r}; \mathbf{r}_0)$ and its gradient $\boldsymbol\nabla_{\mathbf{r}} G(\mathbf{r}; \mathbf{r}_0)$ read

$$\begin{aligned}
 G(\mathbf{r}; \mathbf{r}_0)
 & \simeq G(\mathbf{r}; \mathbf{r}_0)|_{\mathbf{r} = \mathbf{0}} + \mathbf{r} \cdot \nabla_{\mathbf{r}} G(\mathbf{r}, \mathbf{r}_0)|_{\mathbf{r} = \mathbf{0}} = \\
 & = \frac{1}{4 \pi}\frac{1}{|\mathbf{r}_0|} +  \frac{1}{4 \pi} \mathbf{r} \cdot \frac{\mathbf{r}_0}{|\mathbf{r}_0|^3} \ .
\end{aligned}$$

$$\begin{aligned}
 \boldsymbol\nabla_{\mathbf{r}} G(\mathbf{r}; \mathbf{r}_0)
 & \simeq \boldsymbol\nabla_{\mathbf{r}} G(\mathbf{r}; \mathbf{r}_0)|_{\mathbf{r} = \mathbf{0}} + \mathbf{r} \cdot \nabla_{\mathbf{r}} \nabla_{\mathbf{r}} G(\mathbf{r}, \mathbf{r}_0)|_{\mathbf{r} = \mathbf{0}} = \\
 & = \frac{1}{4 \pi} \frac{\mathbf{r}_0}{|\mathbf{r}_0|^3} + \frac{1}{4\pi} \left[ - \dfrac{\mathbf{r}}{|\mathbf{r}_0|^3} + 3 \mathbf{r} \cdot \mathbf{r}_0 \frac{\mathbf{r}_0}{|\mathbf{r}_0|^5} \right] = \\
 & = \frac{1}{4 \pi} \frac{\mathbf{r}_0 - \mathbf{r}}{|\mathbf{r}_0|^3} + \frac{3}{4 \pi} \mathbf{r} \cdot \mathbf{r}_0 \frac{\mathbf{r}_0}{|\mathbf{r}_0|^5} \ .
\end{aligned}$$

First and second space derivatives of the Green's function read

$$\begin{aligned}
  \nabla_{\mathbf{r}} |\mathbf{r}_0 - \mathbf{r}|^{-1} 
  & = \mathbf{\hat{x}}_i \dfrac{\partial}{\partial x_i} | \mathbf{r}_0 - \mathbf{r} |^{-1} = \\
  & = - \mathbf{\hat{x}}_i \frac{x_{i} - x_{0,i}}{| \mathbf{r}_0 - \mathbf{r} |^3} = \\
  & = - \frac{\mathbf{r} - \mathbf{r}_0}{| \mathbf{r}_0 - \mathbf{r} |^3} \ .
\end{aligned}$$

$$\begin{aligned}
  - \nabla_{\mathbf{r}} \frac{\mathbf{r} - \mathbf{r}_0}{| \mathbf{r}_0 - \mathbf{r} |^3} 
  & = - \mathbf{\hat{x}}_k \dfrac{\partial}{\partial x_k} \left( \mathbf{\hat{x}}_i \frac{x_{i} - x_{0,i}}{| \mathbf{r}_0 - \mathbf{r} |^3} \right) = \\
  & = - \mathbf{\hat{x}}_k \mathbf{\hat{x}}_i \left[ \dfrac{\delta_{ij} |\mathbf{r}_0 - \mathbf{r}|^3 - 3 (x_i - x_{0,i})(x_k - x_{0,k})| \mathbf{r}_0 - \mathbf{r} | }{| \mathbf{r}_0 - \mathbf{r} |^6} \right] = \\ 
  & = - \frac{1}{| \mathbf{r}_0 - \mathbf{r} |^3} \, \mathbb{I} + 3 \frac{(\mathbf{r}-\mathbf{r}_{0}) \otimes (\mathbf{r}-\mathbf{r}_{0})}{| \mathbf{r}_0 - \mathbf{r} |^5} \ .
\end{aligned}$$

```

```{dropdown} Doublet/vortex equivalence

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

The perturbation velocity is retrieved from the vector potential as $\mathbf{u}(\mathbf{r}_0) = \nabla_0 \times \boldsymbol\psi(\mathbf{r}_0)$,

$$\begin{aligned}
  \mathbf{u}'(\mathbf{r}_0)
  & = \nabla_0 \times \boldsymbol\psi(\mathbf{r}_0) = \\
  & = \nabla_0 \times \left[ 
       \oint_{\mathbf{r}\in \partial S} \mu(\mathbf{r}) \hat{\mathbf{t}}(\mathbf{r}) \, G(\mathbf{r}; \mathbf{r}_0)
      - \int_{\mathbf{r}\in S} \hat{\mathbf{n}}(\mathbf{r}) \times \nabla^s \mu(\mathbf{r} ) \, G(\mathbf{r}; \mathbf{r}_0)  = \\
    \right] = \\
  & = \oint_{\mathbf{r}\in \partial S} \mu(\mathbf{r}) \hat{\mathbf{t}}(\mathbf{r}) \times \nabla_0 G(\mathbf{r}; \mathbf{r}_0)
     - \int_{\mathbf{r}\in S} \left[ \hat{\mathbf{n}}(\mathbf{r}) \times \nabla^s \mu(\mathbf{r} ) \right] \times \nabla_0 G(\mathbf{r}; \mathbf{r}_0) \ .
\end{aligned}$$

```


```{dropdown} Relationship between doublet/vortex distribution and the circulation - 2-dimensional steady problems
:open:

...

```


```{dropdown} $\oint_{\mathbf{r}_0 \in \ell_0} \hat{\mathbf{t}}_0 \times \nabla_0 G(\mathbf{r}; \mathbf{r}_0)$
:open:

...

```


```{dropdown} Asymptotic behavior of the perturbation potential
:open:

For $|\mathbf{r}_0| \gg |\mathbf{r}|$, using Taylor expansion of the Green's function $G(\mathbf{r}; \mathbf{r}_0)$ and its gradient $\boldsymbol\nabla_{\mathbf{r}} G(\mathbf{r}; \mathbf{r}_0)$, the perturbation velocity reads

$$\begin{aligned}
  \mathbf{u}'(\mathbf{r}_0) 
  & = \int_{\mathbf{r}\in S_b} \boldsymbol\gamma(\mathbf{r}) \times \nabla_0 G(\mathbf{r}; \mathbf{r}_0)
      + \int_{\mathbf{r} \in S_b} \sigma(\mathbf{r}) \nabla_0 G(\mathbf{r}; \mathbf{r}_0) = \\
  & \simeq \int_{\mathbf{r}\in S_b} \boldsymbol\gamma(\mathbf{r}) \times \left[ \frac{1}{2 \pi} \frac{\mathbf{r}_0}{|\mathbf{r}_0|^2} - \frac{1}{2 \pi} \frac{\mathbf{r}}{|\mathbf{r}_0|^2} + \frac{1}{\pi} \mathbf{r} \cdot \mathbf{r}_0 \frac{\mathbf{r}_0}{|\mathbf{r}_0|^4}  \right] + \\ 
   & \quad  + \int_{\mathbf{r} \in S_b} \sigma(\mathbf{r}) \left[ \frac{1}{2 \pi} \frac{\mathbf{r}_0}{|\mathbf{r}_0|^2} - \frac{1}{2 \pi} \frac{\mathbf{r}}{|\mathbf{r}_0|^2} + \frac{1}{\pi} \mathbf{r} \cdot \mathbf{r}_0 \frac{\mathbf{r}_0}{|\mathbf{r}_0|^4}  \right] \ .
\end{aligned}$$

The first term in the second integral is proportional to the mass flux $\dot{m} = \int_{\mathbf{r} \in S_b} \hat{\mathbf{n}} \cdot \nabla_{\mathbf{r}} \varphi = \int_{\mathbf{r} \in S_b} \hat{\mathbf{n}} \cdot \mathbf{u}$ across $S_b$, and so it's identically zero if $\dot{m} = 0$, as in the case of solid boundaries. The first term in the first integral is proportional to the "vector" circulation $\boldsymbol\Gamma = \Gamma \hat{\mathbf{z}} = \oint_{\mathbf{r} \in \partial S_b} \boldsymbol\gamma(\mathbf{r})$ (**todo** *Prove it*), thus the asymptotic behavior of the perturbation velocity as $|\mathbf{r}_0| \gg |\mathbf{r}|$ reads

$$\mathbf{u}'(\mathbf{r}_0) \simeq
 \frac{1}{2 \pi} \boldsymbol\Gamma \times \frac{\mathbf{r}_0}{|\mathbf{r}_0|^2} + 
 \frac{1}{2 \pi} \dot{m} \frac{\mathbf{r}_0}{|\mathbf{r}_0|^2} + O\left( \frac{1}{|\mathbf{r}_0|^2} \right)
$$

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

```

### 3-dimensional problems

**Green's function** [Green's function of a 3-dimensional Poisson problem](https://basics2022.github.io/bbooks-math-miscellanea/ch/pde/bem-poisson-helmholtz-waves.html#poisson-equation) reads

$$G(\mathbf{r}; \mathbf{r}_0) = \frac{1}{4\pi} \frac{1}{|\mathbf{r} - \mathbf{r}_0|} \ .$$

**Solution**

## Wake and the shape of the domain

*Physical conditions: jump conditions, transport*


```{dropdown} Wake in steady 2-dimensional flows
:open:

...

```

## Theorems

### Kutta-Joukowski theorem

...

```{dropdown} Details

...

```
...


```{dropdown} Circulation in Kutta-Joukowski theorem

...

```

