(compressible:quasi-1d)=
# Quasi-1-dimensional flows

**Assumptions.** Whenever no explict assumption is made in this section, the following assumptions are made:
* uniform properties on each section of the stream tube
* negligible viscous and conductivity (non-ideal flows: friction-dominated (Fanno), with heat transfer (Rayleigh))
* negligible radial velocity component
* no azimuthal component 
* *cylindrical symmetry of streamtube*

(compressible:quasi-1d:steady)=
## Steady flow

**Integral balance equations.** 

$$\begin{aligned}
  & \dfrac{d}{dt} \int_{v_t} \rho + \oint_{\partial v_t} \rho \mathbf{u}^{rel} \cdot \hat{\mathbf{n}} = 0 \\
  & \dfrac{d}{dt} \int_{v_t} \rho \mathbf{u} + \oint_{\partial v_t} \rho \mathbf{u} \mathbf{u}^{rel} \cdot \hat{\mathbf{n}} = \int_{v_t} \rho \mathbf{g}  + \oint_{\partial v_t} \mathbf{t}_{\mathbf{n}} \\
  & \dfrac{d}{dt} \int_{v_t} \rho e^t + \oint_{\partial v_t} \rho e^t \mathbf{u}^{rel} \cdot \hat{\mathbf{n}} = \int_{v_t} \rho \mathbf{g} \cdot \mathbf{u}  + \oint_{\partial v_t} \mathbf{t}_{\mathbf{n}} \cdot \mathbf{u} - \oint_{\partial v_t} \mathbf{q} \cdot \hat{\mathbf{n}} \\
\end{aligned}$$

For a control volume $v_t = V$ at rest, $\mathbf{u}_b = \mathbf{0}$ and $\mathbf{u}^{rel} = \mathbf{u}$. Neglecting the volume force $\mathbf{g} = \mathbf{0}$, and integrating over an elementary control volume $\Delta V$ cutting a streamtube at coordinates $z$, $z + \Delta z$, under steady conditions

$$\begin{aligned}
  & \oint_{\partial \Delta V} \rho \mathbf{u} \cdot \hat{\mathbf{n}} = 0 \\
  & \oint_{\partial \Delta V} \rho \mathbf{u} \mathbf{u} \cdot \hat{\mathbf{n}} = \oint_{\partial \Delta V} \mathbf{t}_{\mathbf{n}} \\
  & \oint_{\partial \Delta V} \rho e^t \mathbf{u} \cdot \hat{\mathbf{n}} = \oint_{\partial \Delta V} \mathbf{t}_{\mathbf{n}} \cdot \mathbf{u}
\end{aligned}$$

**Differential equations.**
Assuming uniform properties on each section,

$$\begin{aligned}
  & \dfrac{d}{dz} \left( \rho u A \right) = 0 \\
  & \dfrac{d}{dz} \left( \rho u^2 A + p A \right) - p A' = 0 \\
  & \dfrac{d}{dz} \left[ \rho \left( e^t + \frac{p}{\rho} \right) u A \right] = 0 \ .
\end{aligned}$$

Thus, momentum equation can be recast as

$$0 = \left( \rho u^2 A \right)' + p' A \ .$$

```{dropdown} Momentum equation

$$\begin{aligned}
  \mathbf{0} 
  & = \oint_{\partial \Delta V} \rho \mathbf{u} \mathbf{u} \cdot \hat{\mathbf{n}} - \oint_{\partial \Delta V} \mathbf{t}_{\mathbf{n}} = \\
  & = \int_{A(z)} \rho \mathbf{u} \mathbf{u} \cdot \hat{\mathbf{n}} + p \hat{\mathbf{n}} + \int_{A(z+\Delta z)} \rho \mathbf{u} \mathbf{u} \cdot \hat{\mathbf{n}} + p \hat{\mathbf{n}} + \int_{\Delta A^{lat}} p \hat{\mathbf{n}} \ .
\end{aligned}$$

For 2-dimensional flows, 

$$\hat{\mathbf{z}} \cdot \int_{\Delta A^{lat}} p \hat{\mathbf{n}} = - \Delta z \int_{\ell^{lat}} p \hat{\mathbf{n}} \cdot \hat{\mathbf{z}} \simeq - \Delta z \, p \, \frac{A'(z) \Delta z}{\Delta z} = - p(z) A'(z) \Delta z \ . $$

For 3-dimensional flows,...

```

Using mass equation, $( \rho u A )' = 0$, $\rho u A =: \dot{m}$, momentum and total energy equations become

$$\begin{aligned}
  & \rho u A u' + p' A = 0 \\
  & \rho u A h^{t \, '} = 0 \ ,
\end{aligned}$$

or, simplifying momentum equation for the area of the section of the stream-tube and total energy equation for a mass flux $\dot{m} \ne 0$,

$$\begin{aligned}
  & \rho u u' + p' = 0 \\
  & h^{t \, '} = 0 \ .
\end{aligned}$$

### Mach dependence
Subsonic and supersonic flows show different behavior. If the differential equations hold (no shock, homoentropic flow, $ds = 0$), pressure derivative is proportional to density derivative through the square of the speed of sound,

$$d p = a^2(\rho, \overline{s}) d \rho \ .$$

$$\begin{aligned}
  \frac{A'}{A}
  & = \left( M^2 - 1 \right) \frac{u'}{u}         \\
  & = - \frac{ M^2 - 1 }{M^2} \frac{\rho'}{\rho}  \\
\end{aligned}$$

```{dropdown} Details

Thus,

$$\begin{aligned}
  0 & = \rho u u' + a^2 \rho' && \text{(momentum)} \\
  0 & = \frac{\rho'}{\rho} + \frac{u'}{u} + \frac{A'}{A} && \text{(mass)} \\
    & = - \frac{u u'}{a^2} + \frac{u'}{u} + \frac{A'}{A} \\
\end{aligned}$$

and thus

* **velocity**

   $$\left( M^2 - 1 \right) \frac{u'}{u} = \frac{A'}{A} \ .$$
   
   Thus, 
   * in a subsonic   flow $M < 1$, velocity increases as the section of the stream-tube decreases
   * in a supersonic flow $M > 1$, velocity increases as the section of the stream-tube increases


* **density**

   $$\begin{aligned}
     \frac{\rho'}{\rho} & = - \frac{u^2}{a^2} \frac{u'}{u} \\
     - \frac{M^2 - 1}{M^2} \frac{\rho'}{\rho} & = - \frac{A'}{A} \\
   \end{aligned}$$
   
   Thus, 
   * in a subsonic   flow $M < 1$, density decreases as the section of the stream-tube decreases
   * in a supersonic flow $M > 1$, density decreases as the section of the stream-tube increases

* **pressure**
  
   ...

* **temperature**
  
   ...

```

(compressible:quasi-1d:unsteady)=
## Unsteady flow

**todo** *For a generic control volume $v_t$... It could be useful for mechanical/multi-field system dynamics...*

**Integral equations.**

$$\begin{aligned}
  & \dfrac{d}{dt} \int_{v_t} \rho + \oint_{\partial v_t} \rho \mathbf{u}^{rel} \cdot \hat{\mathbf{n}} = 0 \\
  & \dfrac{d}{dt} \int_{v_t} \rho \mathbf{u} + \oint_{\partial v_t} \rho \mathbf{u} \mathbf{u}^{rel} \cdot \hat{\mathbf{n}} = \int_{v_t} \rho \mathbf{g}  + \oint_{\partial v_t} \mathbf{t}_{\mathbf{n}} \\
  & \dfrac{d}{dt} \int_{v_t} \rho e^t + \oint_{\partial v_t} \rho e^t \mathbf{u}^{rel} \cdot \hat{\mathbf{n}} = \int_{v_t} \rho \mathbf{g} \cdot \mathbf{u}  + \oint_{\partial v_t} \mathbf{t}_{\mathbf{n}} \cdot \mathbf{u} - \oint_{\partial v_t} \mathbf{q} \cdot \hat{\mathbf{n}} \\
\end{aligned}$$

For a control volume $v_t = V$ at rest, $\mathbf{u}_b = \mathbf{0}$ and $\mathbf{u}^{rel} = \mathbf{u}$. Neglecting the volume force $\mathbf{g} = \mathbf{0}$, and integrating over an elementary control volume $\Delta V$ cutting a streamtube at coordinates $z$, $z + \Delta z$, under steady conditions

$$\begin{aligned}
  & \frac{d}{dt} \int_{\Delta V} \rho + \oint_{\partial \Delta V} \rho \mathbf{u} \cdot \hat{\mathbf{n}} = 0 \\
  & \frac{d}{dt} \int_{\Delta V} \rho \mathbf{u} + \oint_{\partial \Delta V} \rho \mathbf{u} \mathbf{u} \cdot \hat{\mathbf{n}} = \oint_{\partial \Delta V} \mathbf{t}_{\mathbf{n}} \\
  & \frac{d}{dt} \int_{\Delta V} \rho e^t + \oint_{\partial \Delta V} \rho e^t \mathbf{u} \cdot \hat{\mathbf{n}} = \oint_{\partial \Delta V} \mathbf{t}_{\mathbf{n}} \cdot \mathbf{u}
\end{aligned}$$

**Differential equations.**
Assuming uniform properties on each section,

$$\begin{aligned}
  & \partial_t \left( \rho A \right) + \partial_z \left( \rho u A \right) = 0 \\
  & \partial_t \left( \rho u A \right) + \partial_z \left[ \left( \rho u^2  + p \right) A \right] - p \partial_z A = 0 \\
  & \partial_t \left( \rho e^t A \right) + \partial_z \left[ \rho \left( e^t + \frac{p}{\rho} \right) u A \right] = 0 \ .
\end{aligned}$$

Assuming here rigid stream-tube with **known section $A(z)$**, **constant in time $\partial_t A(z,t) = 0$**, the differential equations can be recast as a set of PDE, with primary unknowns $(\rho A, m A, E^t A)$ whose 

- conservative form reads

   $$
     \partial_t \begin{bmatrix} \rho A \\ \rho u A \\ \rho e^t A \end{bmatrix} +
     \partial_z \begin{bmatrix} \rho u A \\ \frac{( \rho u A )^2}{\rho A} + p A \\ \frac{ (\rho e^t A + p A) (\rho u A) }{ \rho A }  \end{bmatrix} 
     = \begin{bmatrix} 0 \\ p \partial_z A \\ 0 \end{bmatrix}
   $$

- conservative quasi-linear form reads

   $$
     \partial_t \begin{bmatrix} \rho A \\ \rho u A \\ \rho e^t A \end{bmatrix} +
     \begin{bmatrix}
       \cdot  & 1 & \cdot \\
       - \frac{(\rho u A)^2}{(\rho A)^2} + \partial_{\rho A} (pA) & 2 \frac{\rho u A}{\rho A} + \partial_{\rho u A} (pA) & \partial_{\rho e^t A} (pA) \\
       - \frac{(\rho h^t A)(\rho u A)}{(\rho A)^2} + \partial_{\rho A} (pA) \frac{\rho u A}{\rho A} & \frac{\rho h^t A}{\rho A} + \partial_{\rho u A} ( \rho h^t A ) \frac{\rho u A}{\rho A} & \frac{\rho u A}{\rho A} \left( 1 + \partial_{\rho e^t} ( pA ) \right)
     \end{bmatrix}
     \partial_z \begin{bmatrix} \rho A \\ \rho u A \\ \rho e^t A \end{bmatrix}
     = \begin{bmatrix} 0 \\ p \partial_z A \\ 0 \end{bmatrix}
   $$


- convective form reads

   $$\begin{cases}
     A \partial_t \rho + A ( \rho \partial_z u + u \partial_z \rho ) = - \rho u \partial_z A \\
     \rho A \partial_t u + \rho A u \partial_z u + A \partial_z p = 0 \\
     \rho A \partial_t e^t + \rho A u \partial_z e^t + A \left( u \partial_z p + p \partial_z u \right) = - p u \partial_z A \ .
   \end{cases}$$

   or 

   $$\begin{cases}
     \partial_t \rho + \rho \partial_z u + u \partial_z \rho = - \rho u \frac{\partial_z A}{A} \\
     \partial_t u + u \partial_z u + \frac{ \partial_z p }{\rho} = 0 \\
     \partial_t e^t + u \partial_z e^t + \frac{u}{\rho} \partial_z p + \frac{p}{\rho} \partial_z u  = - \frac{p u}{\rho} \frac{\partial_z A}{A} \ .
   \end{cases}$$

```{dropdown} Internal energy equation

$$\begin{aligned}
  \partial_t e 
  & = \partial_t e^t - \partial_t \frac{u^2}{2} = \\
  & = -u \partial_z e^t - \frac{u}{\rho}\partial_z p - \frac{p}{\rho} \partial_z u - \frac{pu}{\rho} \frac{\partial_z A}{A} + u \partial_z \frac{u^2}{2} + \frac{u}{\rho} \partial_z p = \\
  & = -u \partial_z e - \frac{p}{\rho} \partial_z u - \frac{pu}{\rho} \frac{\partial_z A}{A} \ ,
\end{aligned}$$

i.e.
  
$$ \partial_t e + u \partial_z e = - \frac{p}{\rho} \partial_z u - \frac{pu}{\rho} \frac{\partial_z A}{A} \ .$$

```

```{dropdown} Entropy equation

$$\begin{aligned}
  T D_t s 
  & = D_t e - \frac{p}{\rho^2} D_t \rho = \\
  & = - \frac{p}{\rho} \partial_z u - \frac{pu}{\rho} \frac{\partial_z A}{A} - \frac{p}{\rho^2} \left( - \rho \partial_z u - \rho u \frac{\partial_z A}{A}  \right) = \\
  & = 0 \ ,
\end{aligned}$$

or, as $T > 0$, 

$$\begin{aligned}
  0
  & = D_t s = \\
  & = \partial_t s + u \partial_z s \ .
\end{aligned}$$

**todo** *Discuss homoentropic flow, if no shock occurs*

```


```{dropdown} Characteristics
:open:

Quasi linear form with mass, momentum and entropy equation and $(\rho, u, s)$ primary variables reads

$$
  \partial_t \begin{bmatrix} \rho \\ u \\ s \end{bmatrix} +
  \begin{bmatrix}
    u & \rho & \cdot \\
    \frac{1}{\rho}\left( \partial_\rho p \right)_s & u & \frac{1}{\rho}\left( \partial_s p \right)_\rho \\
    \cdot & \cdot & u
  \end{bmatrix}
  \partial_z \begin{bmatrix} \rho \\ u \\ s \end{bmatrix} =
  \begin{bmatrix} - \rho u \frac{\partial_z A}{A} \\ 0 \\ 0  \end{bmatrix} \ .
$$

These equations looks like 1-dimensional Euler equations for compressible ideal flows, with the exception that a non-uniform section of the stream-tube acts as a source term in mass equation.


```




