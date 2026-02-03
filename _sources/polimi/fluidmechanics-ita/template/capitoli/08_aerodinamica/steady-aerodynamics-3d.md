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

Helmholtz's decomposition of the velocity field reads

$$\mathbf{u}(\mathbf{r}) = \mathbf{u}_\phi(\mathbf{r}) + \mathbf{u}_{\boldsymbol\psi}(\mathbf{r}) = \nabla \phi(\mathbf{r}) + \nabla \times \boldsymbol\psi(\mathbf{r}) \ ,$$

with $\mathbf{u}_\phi$ the irrotational part and $\mathbf{u}_{\boldsymbol\psi}$ the incompressible part, that can be written in terms of a kinetic potential $\phi$ and a vector potential $\boldsymbol\psi$ (or the vector stream function). With a meaningful irrotational free-stream velocity $\mathbf{U}_\infty$, Helmholtz's decomposition becomes

$$\mathbf{u}(\mathbf{r}) = \mathbf{U}_\infty + \nabla \varphi(\mathbf{r}) + \nabla \times \boldsymbol\psi(\mathbf{r}) \ ,$$

having introduced the perturbation kinetic potential $\varphi$. For an **incompressible flow**, the divergence of the velocity field is identically zero, while the curl of the velocity field is the definition of the vorticity,

$$\begin{aligned}
  \nabla \cdot \mathbf{u} & = 0 \\
  \nabla \times \mathbf{u} & = \boldsymbol\omega \ .
\end{aligned}$$

Introducing the expression of teh velocity field and exploiting vector identities $\nabla \cdot \nabla \times \mathbf{a} = 0$, $\nabla \times \nabla a = \mathbf{0}$, $\nabla \cdot \nabla a = \nabla^2 a$, $\nabla^2 \mathbf{a} = \nabla ( \nabla \cdot \mathbf{a} ) - \nabla \times \nabla\times \mathbf{a}$, two Poisson equations for $\varphi(\mathbf{r})$ and $\boldsymbol\psi(\mathbf{r})$ appear

$$\begin{aligned}
  - \nabla^2 \varphi & = 0 \\
  - \nabla^2 \boldsymbol\psi & = \boldsymbol\omega \ ,
\end{aligned}$$

provided that $\boldsymbol\psi$ is divergence free[^psi-div]. This equations are defined in the whole 3-dimensional space $V$ as a domain, without any jump in viscous flows (finite thickness of boundary layers and wakes); in the limit of infinite $\text{Re}$, with boundary layers and wakes collapsing in votex surfaces with infinitesimal thickness, the vorticity field contains impulsive contributions from boundary layers and wakes. These equations must be supplied with proper **boundary conditions**. **todo** *discuss*

[^psi-div]: The stream-function $\boldsymbol\psi(\mathbf{r})$ is uniquely defined up to an additive gradient of a scalar function, as $\mathbf{u}_\psi = \nabla \times \widetilde{\boldsymbol\psi} = \nabla \times \left( \boldsymbol\psi + \nabla f ) = \nabla \times \boldsymbol\psi$. This arbitrariety can be exploited to get a divergence-free stream function from a non-divergence-free stream function.


```{dropdown} Only potential, with jumps across rotational regions

$$\begin{aligned}
 - \Delta \phi & = 0  && \mathbf{r} \in \Omega \\
 \hat{\mathbf{n}} \cdot \boldsymbol\nabla \phi & = 0 && \mathbf{r} \in S_{body} \\
\end{aligned}$$

In order to build a domain where the flow is irrotational, wake regions must be cut from the domain: both sides of these regions become part of the boundary of the domain. In an open domain, the boundary of the domain of the mathematical problem for the kinetic potential is the set union of body boundaries $S_b$, wakes sides $S_{w^+}$, $S_{w^-}$, and a surface at the infinity $S_{\infty}$,

$$\partial \Omega = S_b \cup S_{w^+} \cup S_{w^-} \cup S_{\infty} \ .$$

Boundary conditions on both sides of the [**wakes**]() follow from *jump conditions* of mass and momentum across a wake. Boundary conditions at the boundary **at the infinity** $S_{\infty}$ follow from the [*asymptotic behavior*]() of velocity and kinetic potential fields.

...
```

## Green's function method, for solving Poisson equations

Poisson equations can be recast as *boundary problem* and solved with a *boundary element method*, e.g. exploiting Green's function properties. The Green's function of a 3-dimensional Poisson problem reads

$$G(\mathbf{r}; \mathbf{r}_0) = \frac{1}{4\pi |\mathbf{r} - \mathbf{r}_0|} \ ,$$

so that the integral boundary value problems read

$$\begin{aligned}
  E(\mathbf{r}_0) \varphi(\mathbf{r}_0) & = - \oint_{\partial V} \left\{ \hat{\mathbf{n}}(\mathbf{r}) \cdot \nabla G(\mathbf{r}; \mathbf{r}_0) \, \varphi(\mathbf{r}) - \hat{\mathbf{n}}(\mathbf{r}) \cdot \nabla \varphi(\mathbf{r}) \, G(\mathbf{r}; \mathbf{r}_0) \right\} \\
  E(\mathbf{r}_0) \boldsymbol\psi(\mathbf{r}_0) & = - \oint_{\partial V} \left\{ \hat{\mathbf{n}}(\mathbf{r}) \cdot \nabla G(\mathbf{r}; \mathbf{r}_0) \, \boldsymbol\psi(\mathbf{r}) - \hat{\mathbf{n}}(\mathbf{r}) \cdot \nabla \boldsymbol\psi(\mathbf{r}) \, G(\mathbf{r}; \mathbf{r}_0) \right\} - \int_{V} G(\mathbf{r}; \mathbf{r}_0) \, \boldsymbol\omega(\mathbf{r}) \ .
\end{aligned}$$

The volume contribution of vorticity field is a function of the vorticity on the body **todo** *see wake. Discuss and add details about this statement. For a given shape of the wake, the problem is linear: only the vorticity field, related to the stream function with linear dependence, is unkown; for a free-wake the problem becomes non-linear, as the shape of the wake - i.e. the position of its points - is unknown: this makes the problem non-linear, as the shape of the wake is determined by the condition of not-loaded wake*.


```{dropdown} $E(\mathbf{r}_0)$
:open:

The term $E(\mathbf{r}_0)$ comes from the computation of the integral with the Dirac delta.

$$E(\mathbf{r}_0) = \begin{cases} 1 && \mathbf{r}_0 \in \Omega \\ \frac{1}{2} && \mathbf{r}_0 \in \partial \Omega \\ 0 && \mathbf{r}_0 \notin \Omega \cup \partial \Omega \end{cases}$$

The value $\frac{1}{2}$ is a particular case indeed, if the point $\mathbf{r}_0$ is on a locally flat - no sharp angles - of the boundary. If the point is at a sharp angle - being $\Theta$ the solid angle outside the domain - $E(\mathbf{r}_0) = \frac{\Theta}{4 \pi}$.

```

Once the value of the potential $\varphi$ and the free-stream function $\boldsymbol\psi$ is known, it's possible to evaluate the value of the potential and the free-stream function in every point of the domain, $\mathbf{r}_0 \in V$

$$\begin{aligned}
  \mathbf{u}_\varphi(\mathbf{r}_0) = \nabla_0 \varphi(\mathbf{r}_0) 
  & =  \\
  \mathbf{u}_{\boldsymbol\psi}(\mathbf{r}_0)  = \nabla_0 \times \boldsymbol\psi(\mathbf{r}_0) 
  & =  \\ 
\end{aligned}$$




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


```{dropdown} Vorticity field from the velocity field
:open:

Given the velocity field

$$\mathbf{u}(\mathbf{r}_0) = \nabla_0 \times \boldsymbol\psi(\mathbf{r}_0) + \nabla_0 \varphi(\mathbf{r}_0) \ ,$$

the vorticity field reads

$$\begin{aligned}
  \boldsymbol\omega(\mathbf{r}_0)
  & = \nabla_0 \times \mathbf{u}(\mathbf{r}_0) = \\
  & = \nabla_0 \times \left[ \nabla_0 \times \boldsymbol\psi(\mathbf{r}_0) + \nabla_0 \varphi(\mathbf{r}_0) \right] = \\
  & = \nabla_0 \times \left( \nabla_0 \times \boldsymbol\psi(\mathbf{r}_0) \right) = \\
  & = \nabla_0 \left( \nabla_0 \cdot \boldsymbol\psi(\mathbf{r}_0) \right) - \nabla^2_0 \boldsymbol\psi(\mathbf{r}_0) \ ,
\end{aligned}$$

with the vector identity $\nabla^2 \mathbf{v} = \nabla (\nabla \cdot \mathbf{v}) - \nabla \times \nabla \times \mathbf{v}$. With uniform free-stream the vorticity can be evaluated using perturbation velocity,

$$\begin{aligned}
  \boldsymbol\omega(\mathbf{r}_0)
  & = \nabla_0 \times \mathbf{u}_{\gamma}(\mathbf{r}_0) = \\
  & = \nabla_0 \times \left[
      \oint_{\mathbf{r}\in \partial S_{b,w,\infty}} \mu(\mathbf{r}) \hat{\mathbf{t}}(\mathbf{r}) \times \nabla_0 G(\mathbf{r}; \mathbf{r}_0)
     - \int_{\mathbf{r}\in S_{b,w,\infty}} \left[ \hat{\mathbf{n}}(\mathbf{r}) \times \nabla^s \mu(\mathbf{r} ) \right] \times \nabla_0 G(\mathbf{r}; \mathbf{r}_0) \right] = \\
  & = \nabla_0 \times \left[
      \oint_{\mathbf{r}\in \partial S_{b,w,\infty}} \boldsymbol\Gamma(\mathbf{r}) \times \nabla_0 G(\mathbf{r}; \mathbf{r}_0)
    + \int_{\mathbf{r}\in S_{b,w,\infty}} \boldsymbol\gamma(\mathbf{r})  \times \nabla_0 G(\mathbf{r}; \mathbf{r}_0) \right] = \\
\end{aligned}$$


**todo** Provide the meaning of $\boldsymbol\Gamma$, $\boldsymbol\gamma$ as (impulsive) vorticity distribution on lines and surfaces, using

- identity 

   $$\begin{aligned}
     \nabla \times ( \mathbf{a} \times \nabla f(\mathbf{r}) ) 
     & = \hat{\mathbf{x}}_i \varepsilon_{ijk} \partial_j \varepsilon_{klm} a_l \partial_m f = \\
     & = \hat{\mathbf{x}}_i \left( \delta_{il} \delta_{jm} - \delta_{im} \delta_{jl} \right) a_l \partial_{jm} f = \\
     & = \hat{\mathbf{x}}_i \left( a_i \partial_{ll} f - a_l \partial_{il} f \right) = \\
     & = \mathbf{a} \nabla^2 f(\mathbf{r}) - ( \mathbf{a} \cdot \nabla ) \nabla f(\mathbf{r}) = \\
     & = \mathbf{a} \nabla^2 f(\mathbf{r}) - \nabla ( \mathbf{a} \cdot \nabla f(\mathbf{r}) ) \ ,
   \end{aligned}$$
   
   for $\mathbf{a}$ constant.

- $- \nabla_0^2 G(\mathbf{r}; \mathbf{r}_0) = \delta(\mathbf{r} - \mathbf{r}_0)$

-  ...

    $$\begin{aligned}
      \nabla_0 \cdot \left( \nabla_0 G(\mathbf{r}; \mathbf{r}_0) \right)
      & = \frac{\partial}{\partial x^0_i} \left[ \frac{x_i - x_i^0)}{|\mathbf{r}-\mathbf{r}_0|^3} \right] = \\
      & = \frac{-3}{|\mathbf{r}-\mathbf{r}_0|^3} + 3 \frac{( x_i - x^0_i)(x_i - x^0_i)}{|\mathbf{r}-\mathbf{r}_0|^5} = 0 \ ,
    \end{aligned}$$

    when $\mathbf{r} \ne \mathbf{r}_0$.

- ...

    $$\begin{aligned}
      4 \pi \nabla_0 \left( \mathbf{a} \cdot \nabla_0 G(\mathbf{r}; \mathbf{r}_0) \right)
      & = \nabla_0 \left( \mathbf{a} \cdot \frac{\mathbf{r}-\mathbf{r}_0}{|\mathbf{r}-\mathbf{r}_0|^3} \right) = \\
      & = \hat{\mathbf{x}}^0_i \frac{\partial}{\partial x^0_i} \left[ \frac{a_k(x_k - x_k^0)}{|\mathbf{r}-\mathbf{r}_0|^3} \right] = \\
      & = \hat{\mathbf{x}}^0_i \left[ \frac{ - a_k \delta_{ik} }{|\mathbf{r}-\mathbf{r}_0|^3} + 3 \frac{\mathbf{a}\cdot(\mathbf{r}-\mathbf{r}_0)( x_i - x^0_i)}{|\mathbf{r}-\mathbf{r}_0|^5} \right] = \\
    \end{aligned}$$

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
  & = \int_{\mathbf{r}\in S_b, S_w, S_\infty} \boldsymbol\gamma(\mathbf{r}) \times \nabla_0 G(\mathbf{r}; \mathbf{r}_0)
      + \int_{\mathbf{r} \in S_b, S_w, S_\infty} \sigma(\mathbf{r}) \nabla_0 G(\mathbf{r}; \mathbf{r}_0) = \\
  & \simeq \int_{\mathbf{r}\in S_b, S_w, S_\infty} \boldsymbol\gamma(\mathbf{r}) \times \left[ \frac{1}{4 \pi} \frac{\mathbf{r}_0}{|\mathbf{r}_0|^3} - \frac{1}{4 \pi} \frac{\mathbf{r}}{|\mathbf{r}_0|^3} + \frac{3}{4\pi} \mathbf{r} \cdot \mathbf{r}_0 \frac{\mathbf{r}_0}{|\mathbf{r}_0|^5}  \right] + \\ 
   & \quad  + \int_{\mathbf{r} \in S_b, S_w, S_\infty} \sigma(\mathbf{r}) \left[ \frac{1}{4 \pi} \frac{\mathbf{r}_0}{|\mathbf{r}_0|^3} - \frac{1}{4 \pi} \frac{\mathbf{r}}{|\mathbf{r}_0|^3} + \frac{3}{4\pi} \mathbf{r} \cdot \mathbf{r}_0 \frac{\mathbf{r}_0}{|\mathbf{r}_0|^5}  \right] \ .
\end{aligned}$$

The first term in the second integral is proportional to the mass flux $\dot{m} = \int_{\mathbf{r} \in S_b} \hat{\mathbf{n}} \cdot \nabla_{\mathbf{r}} \varphi = \int_{\mathbf{r} \in S_b} \hat{\mathbf{n}} \cdot \mathbf{u}$ across $S_b$, and so it's identically zero if $\dot{m} = 0$, as in the case of solid boundaries. The first term in the first integral is proportional to the "vector" circulation $\boldsymbol\Gamma = \Gamma \hat{\mathbf{z}} = \oint_{\mathbf{r} \in \partial S_b} \boldsymbol\gamma(\mathbf{r})$ (**todo** *Prove it*), thus the asymptotic behavior of the perturbation velocity as $|\mathbf{r}_0| \gg |\mathbf{r}|$ reads

$$\mathbf{u}'(\mathbf{r}_0) \simeq
 \frac{1}{2 \pi} \boldsymbol\Gamma \times \frac{\mathbf{r}_0}{|\mathbf{r}_0|^2} + 
 \frac{1}{2 \pi} \dot{m} \frac{\mathbf{r}_0}{|\mathbf{r}_0|^2} + O\left( \frac{1}{|\mathbf{r}_0|^2} \right)
$$


```

## Wake and the shape of the domain

**Jump conditions.** Jump conditions across the wake read

- for mass

    $$\left[ \rho u_n^{rel} \right] = 0 \ .$$

- for momentum, with negligible viscosity so that $\mathbf{t}_{\mathbf{n}} = - P \hat{\mathbf{n}}$

    $$\left[ \rho \mathbf{u} u_n^{rel} + P \hat{\mathbf{n}} \right] = \mathbf{0} \ .$$

As the wake is (**todo** *Prove or justify*) a contact discontinuity, with no mass flux through it, $\dot{m} = \rho u_n^{rel} = 0$ (a stricter condition w.r.t. to no jump in mass flux across the surface), the momentum jump condition across the wake reads

$$[ P \hat{\mathbf{n}} ] = 0 \ ,$$

i.e. the vector condition contains a non-trivial 1-dimensional information, along the normal direction only $\left[ P \right] = 0$.

Using second Bernoulli theorem, connecting a pair of points on the two sides of the wake (if needed, do an intermediate step connecting each one of these points with a point at infinity) gives 

$$P^+ + \frac{1}{2} \rho \left| \mathbf{u}^+ \right|^2 = P^- + \frac{1}{2} \rho \left| \mathbf{u}^- \right|^2 \ .$$

Using the relation between the velocity on each side of the wake, the average velocity, the velocity jump and the intensity of vortex sheet of the wake,

$$\begin{aligned}
  \mathbf{u}^+ & = \mathbf{u} + \frac{\Delta \mathbf{u}}{2} \\
  \mathbf{u}^- & = \mathbf{u} - \frac{\Delta \mathbf{u}}{2} \\
  \Delta \mathbf{u} & = - \hat{\mathbf{n}} \times \boldsymbol\gamma \ ,
\end{aligned}$$

gives

$$\begin{aligned}
  0 = \left[ P \right] = \\
  & = P^+ - P^- = \\
  & = \frac{1}{2} \rho \left[
    |\mathbf{u}|^2 + \frac{|\Delta \mathbf{u}|^2}{4} + \mathbf{u} \cdot \Delta \mathbf{u}
  - |\mathbf{u}|^2 - \frac{|\Delta \mathbf{u}|^2}{4} + \mathbf{u} \cdot \Delta \mathbf{u}
  \right] = \\
  & = \mathbf{u} \cdot \Delta \mathbf{u} = \\
  & = - \mathbf{u} \cdot \hat{\mathbf{n}} \times \boldsymbol\gamma = \\
  & = \hat{\mathbf{n}} \cdot \mathbf{u} \times \boldsymbol\gamma \ .
\end{aligned}$$

As (**todo** *discuss*) $\mathbf{u}$ and $\boldsymbol\gamma$ are everywhere orthogonal to $\hat{\mathbf{n}}$, and thus tangent to the wake surface, it follows that 

$$\mathbf{u} \times \boldsymbol\gamma = \mathbf{0} \ ,$$

or, equivalently,

$$
\boldsymbol\gamma \parallel \mathbf{u}
\qquad \text{or} \qquad
\begin{aligned}
  \boldsymbol\gamma & = \gamma \hat{\mathbf{t}} \\
  \mathbf{u}        & = u \hat{\mathbf{t}} \ .
\end{aligned}
$$


*Physical conditions: jump conditions, transport*

...


## Theorems

*Lift and drag*

<!--
### Kutta-Joukowski theorem

...

```{dropdown} Details

...

```
...


```{dropdown} Circulation in Kutta-Joukowski theorem

...

```
-->

