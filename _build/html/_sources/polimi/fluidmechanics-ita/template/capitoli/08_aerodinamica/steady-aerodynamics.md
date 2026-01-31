(fluid-mechanics:aerodynamics:steady)=
# Steady Aerodynamics

[**2-dimensional flows**](fluid-mechanics:aerodynamics:steady:2d)

[**3-dimensional flows**](fluid-mechanics:aerodynamics:steady:3d)

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
 \phi & = \dots && \mathbf{r} \in S_{\infty}
\end{aligned}$$

In order to build a domain where the flow is irrotational, wake regions must be cut from the domain: both sides of these regions become part of the boundary of the domain. As shown below, there's no physical wake for 2-dimensional steady flows, while wakes exist in 3-dimensional flows.

## Green's function method


```{dropdown} Derivation of the Green's function for the Poisson problem

...

```

**Solution.**

...

```{dropdown} $E(\mathbf{r}_0)$

...

```


```{dropdown} Asymptotic behavior of the perturbation velocity

...

```

```{dropdown} Doublet/vortex equivalence
...

```

```{dropdown} Zero wake vorticity in steady 2-dimensional problems

...

```


```{dropdown} Details in integration by parts on surface in doublet/vortex equivalence

...

```


```{dropdown} Relationship between doublet/vortex distribution and the circulation - 2-dimensional steady problems

...

```


```{dropdown} $\oint_{\mathbf{r}_0 \in \ell_0} \hat{\mathbf{t}}_0 \times \nabla_0 G(\mathbf{r}; \mathbf{r}_0)$

...

```


```{dropdown} Asymptotic behavior of the perturbation potential

...

```

## Wake and the shape of the domain

*Physical conditions, with jump conditions*

*No physical wake in 2-dimensional steady flows*

```{dropdown} Wake in steady 2-dimensional flows

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

### D'Alembert paradox - 2 dimensional flow

...
