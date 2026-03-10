(compressible:intro)=
# Introduction to Compressible Fluid Mechanics

```{dropdown} [Governing Equations](compressible:governing-equations)
:open:

* From compressible [**Navier-Stokes equations**](compressible:governing-equations:navier-stokes), to [**Euler equations**](compressible:governing-equations:euler) for compressible fluids with negligible viscosity and heat conduction effects. Under these assumptions, the diffusive parts of the equations disappear, and discontinuities (e.g. [normal shocks](compressible:shocks:normal), [oblique shocks](compressible:shocks:oblique), or [contact discontinuities]()) may appear in the field: as fields are not differentiable and not even continuous across a discontinuity, differential equations fail and [jump conditions](compressible:jump-conditions) from integral equations are required to connect 2 regions of smooth fields.

* The definition of [**ideal flow**](compressible:governing-equations:ideal) requires the additional assumption of absence of shocks, beside negligible viscosity and heat conduction. Without shocks, differential equations hold in the whole domain and [entropy equation](compressible:entropy) shows that the flow is homoentropic, $s(\mathbf{r},t) = \overline{s}$, if the inflow is uniform. 

* If the flow is also irrotational, the governing equations can be written as a PDE for [kinetic potential](compressible:irrotational:potential-equation). Without shocks, differential equations hold in the whole domain and [vorticity equation](compressible:vorticity) shows that the flow is irrotational in the whole domain if the inflow is irrotational.

* [Acoustics](compressible:acoustics) ...linearized equations...

Integral and differential form of the governing equations are provided, along with [**jump conditions**](compressible:jump-conditions): jump conditions play a crucial role in compressible inviscid flows governed by Euler equations where discontinuities (shocks and contact discontinuities) appear as a result of vanishing diffusion terms, in the limit of negligible viscous stress and heat conduction.

```

```{dropdown} Vorticity, entropy and Bernoulli theorems
:open:

Vorticity equation and entropy equation are discussed in detail in order to use them and their conclusions in different models of a flow.

* [Vorticity equation](compressible:vorticity)

* [Entropy equation](compressible:entropy)

* [Bernoulli equation](compressible:bernoulli)

```

```{dropdown} Mathematical nature of equations of physics
:open:

The (local) mathematical nature of the problem depends on the (local) value of the Mach number. As an example, for Euler equations[^ns-math] and derived models
* in subsonic regions:
  * in steady condition, the governing equations are elliptic
  * in unsteady condition, the governing equations are hyperbolic
* in supersonic regions:
  * in steady contditions, the governing equations are hyperbolic
  * in unsteady conditions, the governing equations are hyperbolic

[^ns-math]: Dissipative terms make Navier-Stokes equations elliptic in steady conditions and parabolic in unsteady conditions.

As an example, the mathematical nature of governing equations of steady flows naturally apperas as a function of the (local) Mach number $M$:
- in the potential equation for irrotational homo-entropic flows. The (global) nature of the [linearized potential equation](compressible:irrotational:potential-equation:homoentropic:linearized:steady) depends on the Mach number of the reference flow $M_{\infty}$;
- in the characteristic method for steady compressible flows (**todo** *collect all the material, now here and there, e.g. in Math:PDE:hyperbolic equations*): in a d-dimensional domain, $d+2$ families of characteristic surfaces exist in supersonic regions, while only $d$ families exist in subsonic flows. Thus, it's not possible to use the method of characteristics: the solution in a point $P$ is not function of the values of $d+2$ variables on the $d+2$ characteristic lines through $P$, but depends on the solution in its neighborhood (typical condition for elliptic equations).

Introduction to hyperbolic problems:
- Link to Math jbook: hyperbolic problems, method of characteristics, integral balance, jumps,...
- include script avaiable on GDrive in $\texttt{fvm}$ folder

```

```{dropdown} [Canonical flows](compressible:canonical-flows)
:open:

* 1-dimensional ideal flow
* [quasi 1-dimensional flows](compressible:quasi-1d)
* [(quasi) 1-dimensional non-ideal flows](compressible:quasi-1d:non-ideal): with friction (Fanno), and with heat flux (Rayleigh)
* 2-dimensional flows:
  * shocks: [normal shocks](compressible:shocks:normal) and [oblique shocks](compressible:shocks:oblique) ($\theta - \beta - M $)
  * rarefaction waves: [Prandtl-Meyer exapnsion](compressible:prandtl-meyer)
  * discontituities

```

```{dropdown} [Acoustics](compressible:acoustics)
:open:


```


