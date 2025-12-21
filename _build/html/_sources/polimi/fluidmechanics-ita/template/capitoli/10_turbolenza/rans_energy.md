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

$$\overline{\text{NSE}} \ ,$$

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


## Energy equations

Here, kinetic energy equation, average kinetic energy, kinetic energy of the average field, kinetic energy of the fluctuation,...

**Kinetic energy equation.** Ta


