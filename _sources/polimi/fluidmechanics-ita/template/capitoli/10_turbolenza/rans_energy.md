(fluid-mechanics:turbulence:rans-energy)=
# RANS and energy equations

## RANS

**Incompressible Navier&mdash;Stokes equations.**

$$\begin{cases}
  \partial_t \mathbf{u} + ( \mathbf{u} \cdot \nabla ) \mathbf{u} - \nu \Delta \mathbf{u} + \nabla P = \mathbf{0} \\
  \nabla \cdot \mathbf{u} = 0 \ ,
\end{cases}$$

with $P = \frac{P}{\overline{\rho}}$ with little abuse of notation, and no volume force. For incompressible flows, the following relation holds

$$\nabla \cdot \left( \mathbf{u} \otimes \mathbf{u} \right) = ( \mathbf{u} \cdot \nabla ) \mathbf{u} \ .$$

```{dropdown} Proof

Using Cartesian coordinates

$$\left\{ \nabla \cdot \left( \mathbf{u} \otimes \mathbf{u} \right) \right}_i = ( u_j u_i )_{/j} = \underbrace{u_{j/j}}_{=0} u_i + u_j u_{i/j} = \left\{ ( \mathbf{u} \cdot \nabla ) \mathbf{u} \right\}_i \ ,$$

as $u_{j/j} = \nabla \cdot \mathbf{u} = 0$, for the incompressiblity constraint.

```

**Incompressible Reynolds-averaged Navier&mdash;Stokes equations, RANS.** Applying average operator[^avg-operator] to NS equations

[^avg-operator]: What's a proper definition? Can equations be time-dependent? It looks so, if fields are interpreted as stochastic fields and average is an average in probability and not time.

$$\overline{\text{NS}} \ ,$$

after having defined the relation between the realization of a field, its average and fluctuation,

$$f = \overline{f} + f' \ ,$$

so that applying average $\overline{f'} = 0$, RANS equations follows[^avg-operator-properties]

[^avg-operator-properties]: Is it possible to swap average operator and differential operators? Let's assume it is.

$$\begin{cases}
  \partial_t \overline{\mathbf{u}} + ( \overline{\mathbf{u}} \cdot \nabla ) \overline{\mathbf{u}} + \nabla \cdot \overline{\mathbf{u}' \otimes  \mathbf{u}'} - \nu \Delta \overline{\mathbf{u}} + \nabla \overline{P} = \mathbf{0} \\
  \nabla \cdot \overline{\mathbf{u}} = 0 \ ,
\end{cases}$$

if average and differential operators swaps for linear terms. An extra-contribution arises from the non-linear term, as

$$\begin{aligned}
  \overline{ a b } 
  & = \overline{ (\overline{a}+a') (\overline{b}+b')} = \\
  & = \overline{ \overline{a} \overline{b} } + \underbrace{ \overline{ \overline{a} b' } }_{\overline{a} \overline{b'} = 0} + \underbrace{\overline{ a' \overline{b} }}_{\overline{a'} \overline{b}=0} + \overline{ a' b'} = \\
  & = \overline{a} \overline{b}  + \overline{ a' b'} \ .
\end{aligned}$$

This can be interpreted as *extra* stress contribution (as it has the expression of the divergence of a 2-nd order symmetric tensor) felt by the average fields $\overline{\mathbf{u}}, \overline{P}$, due to fluctuations $\mathbf{u}'$.

**Equation of the fluctuation.** Taking the difference between NS equations and RANS equations, the equation for the fluctuation $\mathbf{u}' = \mathbf{u} - \overline{\mathbf{u}}$ seamlessly follows

$$\begin{cases}
  \partial_t \mathbf{u}' + \nabla \cdot (\mathbf{u} \otimes \mathbf{u}) - \nabla \cdot (\overline{\mathbf{u}} \otimes \overline{\mathbf{u}}) - \nabla \cdot \overline{ (\mathbf{u}' \otimes \mathbf{u}')} -  \nu \Delta \mathbf{u}' + \nabla P' = \mathbf{0} \\
  \nabla \cdot \mathbf{u}' = 0 \ ,
\end{cases}$$

and

$$\begin{cases}
  \partial_t \mathbf{u}' + \nabla \cdot (\overline{\mathbf{u}} \otimes \mathbf{u}') + \nabla \cdot (\mathbf{u}' \otimes \overline{\mathbf{u}}) + \nabla \cdot (\mathbf{u}' \otimes \mathbf{u}' ) - \nabla \cdot \overline{ (\mathbf{u}' \otimes \mathbf{u}')} -  \nu \Delta \mathbf{u}' + \nabla P' = \mathbf{0} \\
  \nabla \cdot \mathbf{u}' = 0 \ ,
\end{cases}$$


## Energy equations

Here, kinetic energy equation, average kinetic energy, kinetic energy of the average field, kinetic energy of the fluctuation and its average,...
Kinetic energy per unit-mass is

$$K := \frac{\mathbf{u} \cdot \mathbf{u}}{2} \ ,$$

and it can be recast using the average and the fluctuation fields

$$\begin{aligned}
 K
 & = \frac{\mathbf{u} \cdot \mathbf{u}}{2} = \\
 & = \frac{( \overline{\mathbf{u}} + \mathbf{u}') \cdot (\overline{\mathbf{u}} + \mathbf{u}')}{2} = \\
 & = \frac{\overline{\mathbf{u}} \cdot \overline{\mathbf{u}}}{2} + \frac{\mathbf{u}' \cdot \mathbf{u}'}{2} + \overline{\mathbf{u}} \cdot \mathbf{u}'
\end{aligned}$$

being the first tern the kinetic energy of the average flow, the second term the kinetic energy of the fluctuations, and the last term the cross-effects. Taking average, to get the average kinetic energy $\overline{K}$ the last term disappears, and a relation between the average kinetic energy, the energy of the average flow and the turbulent energy (defined as the average of the kinetic energy of the fluctuations) arises

$$\overline{K} = K_{\overline{\mathbf{u}}} + k \ .$$

**Kinetic energy, $K$.** Taking the dot-product of the NS equations with the velocity field, $\mathbf{u} \cdot \text{NS}$, and exploiting product rule for derivatives,

$$\partial_t \frac{\mathbf{u} \cdot \mathbf{u}}{2} + ( \mathbf{u} \cdot \nabla ) \frac{\mathbf{u} \cdot \mathbf{u}}{2} - \mathbf{u} \cdot \nabla \cdot \mathbb{S} + \mathbf{u} \cdot \nabla P = 0$$

As shown in the box below, the last two contributions can be rearranged to get

```{dropdown} Rearranging terms

Assuming uniform viscosity $\nu$

$$\begin{aligned}
  \mathbf{u} \cdot \nabla \cdot \mathbb{S} 
  & = \nu \mathbf{u} \cdot \nabla \cdot \left( \nabla \mathbf{u} + \nabla^T \mathbf{u} \right) = \\
  & = \nu \mathbf{u} \cdot \Delta \mathbf{u} = \\
  & = \nu \nabla \cdot \left( \left( \nabla \mathbf{u} \right) \cdot \mathbf{u} \right) - \nu |\nabla \mathbf{u}|^2
\end{aligned}$$

as $\nabla \cdot \nabla^T \mathbf{u} = \partial_i \partial_j u_i = \partial_j u_{i/i} = 0$.

Pressure term can be recast as a divergence contribution as

$$\mathbf{u} \cdot \nabla P = \nabla \cdot ( P \mathbf{u} ) - P \underbrace{ \nabla \cdot \mathbf{u} }_{=0} = \nabla \cdot ( P \mathbf{u} ) \ .$$

```

**Average kinetic energy, $\overline{K}$.** Taking the average of the kinetic energy equation,

```{dropdown} Rearranging terms

$$\partial_t \frac{\mathbf{u} \cdot \mathbf{u}}{2} + ( \mathbf{u} \cdot \nabla ) \frac{\mathbf{u} \cdot \mathbf{u}}{2} - \mathbf{u} \cdot \nabla \cdot \mathbb{S} + \mathbf{u} \cdot \nabla P = 0$$


$$\overline{\partial_t \frac{\mathbf{u} \cdot \mathbf{u}}{2}} = \partial_t \overline{K}$$

$$\overline{\mathbf{u} \cdot \nabla K} = \overline{u}$$

...

**todo**


```

**Kinetic energy of the average field, $K_{\overline{\mathbf{u}}}$.** Taking the scalar product $\overline{\mathbf{u}} \cdot \text{RANS}$

Source contributions:
- turbulent energy "production" (as it will be more clear later), $\nabla \overline{\mathbf{u}} : \overline{\mathbf{u}' \otimes \mathbf{u}'}$. This contribution has no defined sign. It appears with the opposite side in the equation of the turbulent energy: it could be interpreted as a term that (mainly?) removes energy from the average flow to produce turbulent kinetic energy
- viscous dissipation from the average flow (always non positive), $- \nu \overline{\nabla \overline{\mathbf{u}} : \nabla \overline{\mathbf{u}}} \le 0$. Is this relevant for large Reynolds number?

Flux contributions: ...

$$\dfrac{\overline{D} K_{\overline{\mathbf{u}}}}{\overline{D} t} = \nabla \cdot \boldsymbol\Phi_{K_{\overline{\mathbf{u}}}} - \mathscr{P} - \mathscr{D}_{\overline{\mathbf{u}}}$$

```{dropdown} Rearranging terms
:open:

$$\begin{cases}
  \partial_t \overline{\mathbf{u}} + ( \overline{\mathbf{u}} \cdot \nabla ) \overline{\mathbf{u}} + \nabla \cdot \overline{\mathbf{u}' \otimes  \mathbf{u}'} - \nu \Delta \overline{\mathbf{u}} + \nabla \overline{P} = \mathbf{0} \\
  \nabla \cdot \overline{\mathbf{u}} = 0 \ ,
\end{cases}$$

$$\partial_t K_{\overline{\mathbf{u}}}$$

$$\overline{\mathbf{u}} \cdot (\overline{\mathbf{u}} \cdot \nabla ) \overline{\mathbf{u}} = \overline{\mathbf{u}} \cdot \nabla K_{\overline{\mathbf{u}}}$$

$$\overline{\mathbf{u}} \cdot \nabla \cdot \overline{\mathbf{u}' \otimes \mathbf{u}'} = U_j ( \overline{ u'_i u'_j } )_{/i} = \nabla \cdot \left( \overline{\mathbf{u}' \otimes \mathbf{u}'} \cdot \overline{\mathbf{u}} \right) - \nabla \overline{\mathbf{u}} : \overline{\mathbf{u}' \otimes \mathbf{u}'} $$

...

$$\begin{aligned}
  0 & = \dfrac{\overline{D} K_{\overline{\mathbf{u}}}}{\overline{D}t} + \\
    & + \nabla \cdot \left( \overline{\mathbf{u}' \otimes \mathbf{u}'} \cdot \overline{\mathbf{u}} \right) - \nabla \overline{\mathbf{u}} : \overline{\mathbf{u}' \otimes \mathbf{u}'} + \\
    & - \nabla \cdot \left( \nu \nabla K_{\overline{\mathbf{u}}} \right) + \nu \nabla \overline{\mathbf{u}} : \nabla \overline{\mathbf{u}} + \\
    & + \nabla \cdot \left( \overline{P} \overline{\mathbf{u}} \right)
\end{aligned}$$

or collecting divergence (or flux, in an integral formulation) terms and volume source terms

$$\begin{aligned}
  \dfrac{\overline{D} K_{\overline{\mathbf{u}}}}{\overline{D}t} 
  = \nabla \cdot \left( \nu \nabla K_{\overline{\mathbf{u}}} - \overline{\mathbf{u}' \otimes \mathbf{u}'} \cdot \overline{\mathbf{u}} - \overline{P} \overline{\mathbf{u}} \right) 
  + \nabla \overline{\mathbf{u}} : \overline{\mathbf{u}' \otimes \mathbf{u}'} - \nu \nabla \overline{\mathbf{u}} : \nabla \overline{\mathbf{u}}
\end{aligned}$$





```


**Kinetic energy of the fluctuation, $k'$.** Taking the scalar product $\mathbf{u}' \cdot \text{Fluctuation equations}$

```{dropdown} Rearranging terms


$$\begin{cases}
  \partial_t \mathbf{u}' + \nabla \cdot (\overline{\mathbf{u}} \otimes \mathbf{u}') + \nabla \cdot (\mathbf{u}' \otimes \overline{\mathbf{u}}) + \nabla \cdot (\mathbf{u}' \otimes \mathbf{u}' ) - \nabla \cdot \overline{ (\mathbf{u}' \otimes \mathbf{u}')} -  \nu \Delta \mathbf{u}' + \nabla P' = \mathbf{0} \\
  \nabla \cdot \mathbf{u}' = 0
\end{cases}$$

$$\mathbf{u}' \cdot \partial_t \mathbf{u}' = \partial_t \frac{\mathbf{u}' \cdot \mathbf{u}'}{2}$$

$$\mathbf{u}' \cdot \nabla \cdot \left( \overline{\mathbf{u}} \otimes \mathbf{u}' \right) = u'_i ( U_j u'_i )_{/j} = U_j \{( u'_i u'_i ) / 2\}_{/j} $$

$$\mathbf{u}' \cdot \nabla \cdot \left( \mathbf{u}' \otimes \overline{\mathbf{u}} \right) = u'_i ( u'_j U_i )_{/j} = u'_i u'_j U_{i/j}$$

$$\mathbf{u}' \cdot \nabla \cdot \left( \mathbf{u}' \otimes \mathbf{u}' \right) = u'_i ( u'_j u'_i )_{/j} = u'_j \left\{ \frac{u'_i u'_i}{ 2 }\right\}_{/j} = \left\{ u'_j \frac{u'_i u'_i}{2} \right\}_{/j}$$

$$\mathbf{u}' \cdot \nabla \cdot\overline{ \left( \mathbf{u}' \otimes \mathbf{u}' \right) } = u'_i \overline{ ( u'_j u'_i )}_{/j}  = (u'_i \overline{u'_j u'_i})_{/j} - u'_{i/j} \overline{u'_j u'_i}  $$

$$\begin{aligned}
  u'_i u'_{i/jj} 
  & = ( u'_i u'_{i/j} )_{/j} - u'_{i/j} u'_{i/j} && = \left(\frac{u'_i u'_i}{2}\right)_{/jj} - u'_{i/j} u'_{i/j} = \\
\end{aligned}$$

and putting everything together

$$\partial_t k' + \mathbf{u} \cdot \nabla k' + \nabla \overline{\mathbf{u}} : \mathbf{u}' \otimes \mathbf{u}' - \nabla \cdot \left( \overline{\mathbf{u}' \otimes \mathbf{u}'} \cdot \mathbf{u}' \right) + \overline{\mathbf{u}'\otimes \mathbf{u}'} : \nabla \mathbf{u}' - \Delta ( \nu k' ) + \nu \nabla \mathbf{u}' : \nabla \mathbf{u}' + \nabla \cdot \left( P' \mathbf{u}' \right) = 0$$


```

**Average kinetic energy of the fluctuation, $k$.** Taking the average of the equation for the kinetic energy of the fluctuation...

$$
\dfrac{\overline{D} k}{\overline{D} t} = \nabla \cdot \left( \nu \nabla k - \overline{\mathbf{u}' k'} - \overline{ P' \mathbf{u}'}  \right) - \nabla \overline{\mathbf{u}} : \overline{\mathbf{u}' \otimes \mathbf{u}'} - \nu \overline{\nabla \mathbf{u}' : \nabla \mathbf{u}'}
$$

Source contributions:
- turbulent energy "production", $\mathscr{P} := - \nabla \overline{\mathbf{u}} : \overline{\mathbf{u}' \otimes \mathbf{u}'}$. This contribution has no defined sign. It appears with the opposite side in the equation of the kinetic eenrgy of the average field: thus, it could be interpreted as a term that (mainly?) removes energy from the average flow to produce turbulent kinetic energy
- viscous dissipation (always non positive), $\mathscr{D} := - \nu \overline{\nabla \mathbf{u}' : \nabla \mathbf{u}'} \le 0$

Flux contributions: ...

$$\dfrac{\overline{D} k}{\overline{D} t} = \nabla \cdot \boldsymbol\Phi_k + \mathscr{P} - \mathscr{D}$$


```{dropdown} Rearranging terms


$$\partial_t k + \overline{\mathbf{u}} \cdot \nabla k +  \nabla \cdot \overline{( \mathbf{u}' k' ) } + \nabla \overline{\mathbf{u}} : \overline{\mathbf{u}' \otimes \mathbf{u}'} - \Delta ( \nu k ) + \nu \overline{ \nabla \mathbf{u}' : \nabla \mathbf{u}' } + \nabla \cdot \overline{ \left( P' \mathbf{u}' \right)} = 0$$

as 

$$\overline{\mathbf{u} \cdot \nabla k'} = \overline{ ( \overline{\mathbf{u}} + \mathbf{u}' ) \cdot \nabla k'} = \overline{\mathbf{u}} \cdot \nabla k + \overline{ \mathbf{u}' \cdot \nabla k'} = \overline{\mathbf{u}} \cdot \nabla k + \nabla \cdot \overline{ ( \mathbf{u}' k' ) }$$

Rearranging terms collecting divergence contributions,

$$
\dfrac{\overline{D} k}{\overline{D} t} = \nabla \cdot \left( \nu \nabla k - \overline{\mathbf{u}' k'} - \overline{ P' \mathbf{u}'}  \right) - \nabla \overline{\mathbf{u}} : \overline{\mathbf{u}' \otimes \mathbf{u}'} - \nu \overline{\nabla \mathbf{u}' : \nabla \mathbf{u}'}
$$

```


