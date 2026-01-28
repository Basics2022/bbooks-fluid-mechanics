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


### 3-dimensional problems

**Green's function** [Green's function of a 3-dimensional Poisson problem](https://basics2022.github.io/bbooks-math-miscellanea/ch/pde/bem-poisson-helmholtz-waves.html#poisson-equation) reads

$$G(\mathbf{r}; \mathbf{r}_0) = \frac{1}{4\pi} \frac{1}{|\mathbf{r} - \mathbf{r}_0|} \ .$$

**Solution**

## Wake and the shape of the domain

*Physical conditions, with jump conditions*

*No physical wake in 2-dimensional steady flows*

## Theorems

### Kutta-Jukowski theorem

**2-dimensional flows.** Circulation is defined as

$$\Gamma = \oint_{\gamma} \mathbf{u} \cdot \hat{\mathbf{t}} \ .$$

Using integral balance equations


If a set of Cartesian coordinates is used and the free-stream velocity is aligned with the $\hat{\mathbf{x}}$ unit vector, the lift reads

$$\begin{aligned}
  L = \hat{\mathbf{y}} \cdot \mathbf{F} 
\end{aligned}$$

### D'Alembert paradox - 2 dimensional flow



