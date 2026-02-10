(fluid-mechanics:balances:non-inertial)=
# Fluid dynamics in a non-inertial reference frame

Following the same approach as [Mechanics:Relative Kinematics:Point](https://basics2022.github.io/bbooks-physics-mechanics/ch/kinematics-relative.html), the position of a point $P$ is determined by the position vectors w.r.t. an inertial reference frame - here defined by an origin and a set oc Cartesian coordinates - $I: \, (O, x, y, z)$, and w.r.t. a generic reference frame - $G: \, (O_1, x_1, y_1, z_1)$.

$$\begin{aligned}
  (P - O) & = (O_1 - O) + (P - O_1) \\
  \mathbf{r}_{P/O} & = \mathbf{r}_{O_1/O} + \mathbf{r}_{P/O_1}
\end{aligned}$$

The unit vectors of the generic basis can be projected on the inertial basis as

$$\hat{\mathbf{e}}^1_i = \hat{\mathbf{e}}^1_i \cdot \hat{\mathbf{e}}_k \hat{\mathbf{e}}_k = \mathbb{R}^{\rightarrow 1} \cdot \hat{\mathbf{e}}_i \ ,$$

and their time derivatives read

$$\dfrac{d}{dt}\hat{\mathbf{e}}^1_i = \boldsymbol\omega_{1/} \times \hat{\mathbf{e}}^1_i \ .$$

**Time derivatives.** Time is the same in every referenece frame - in classical mechanics, time is absolute. Here the time derivative **as seen by an observer at rest with a reference frame** is defined and discussed.

...

Time derivative for an observer at rest with a reference frame is defined for vectors and tensors as the mathematical object expressed in the basis of the reference frame with time derivative of the components only.

...


The velocity of a point reads

$$\begin{aligned}
  \mathbf{u}^I_{P/O} 
  & := \dfrac{{}^I d}{d t} \mathbf{r}_{P/O} = \\
  & = \mathbf{u}^I_{O_1/O} + \dfrac{{}^I d}{dt} \left( r^1_{P/O_1, \, k} \hat{\mathbf{e}}^1_k \right) = \\
  & = \mathbf{u}^I_{O_1/O} + \mathbf{u}^G_{P/O_1} + \boldsymbol\omega_{G/I} \times \mathbf{r}_{P/O_1} \ .
\end{aligned}$$

## Differential equations

**Mass.** Conservative form of differential mass equation reads

$$\begin{aligned}
  0 
  & = \partial_t \rho + \nabla \cdot \left( \rho \mathbf{u} \right) = \\
\end{aligned}$$

### Homogeneity and isotropy

### Galilean relativity

With $\mathbf{v}$ constant in time and independent from position in space

$$
\begin{cases}
\mathbf{r} = \mathbf{r}' + \mathbf{v} t \\
t = t'
\end{cases}
\qquad , \qquad
\begin{cases}
\mathbf{r}' = \mathbf{r} - \mathbf{v} t \\
t' = t
\end{cases}
$$

and thus, the velocity of a point whose position in function of time $\mathbf{r}(t)$ reads

$$
\mathbf{u} = \mathbf{u}' + \mathbf{v} \\
$$

Using derivatives of composite functions

$$\begin{aligned}
  \partial_t & = \partial_{t'} - \mathbf{v} \cdot \nabla' \\
  \nabla     & = \nabla'
\end{aligned}$$

```{dropdown} Details

$$\begin{aligned}
  \partial_t f(\mathbf{r},t)
  & = \partial_t f'(\mathbf{r}'(\mathbf{r},t), t'(\mathbf{r},t)) = \\
  & = \partial_t \mathbf{r}' \cdot \partial_{\mathbf{r}'} f' + \partial_t t' \, \partial_{t'} f' = \\
  & = - \mathbf{v} \cdot \nabla' f' + \partial_{t'} f'  \ .
\end{aligned}$$ 

$$\begin{aligned}
  \nabla = \dots = \nabla' 
\end{aligned}$$

```

**Mass.** Conservative form

$$\begin{aligned}
  0 
  & = \partial_t \rho + \nabla \cdot \left( \rho \mathbf{u} \right) = \\
  & = \partial_{t'} \rho - \mathbf{v} \cdot \nabla' \rho + \nabla' \cdot \left( \rho \left( \mathbf{u}' + \mathbf{v} \right) \right) = \\
  & = \partial_{t'} \rho - \mathbf{v} \cdot \nabla' \rho + \nabla' \cdot \left( \rho \mathbf{u}' \right) + \mathbf{v} \cdot \nabla' \rho  = \\
  & = \partial_{t'} \rho + \nabla' \cdot \left( \rho \mathbf{u}' \right) \ .
\end{aligned}$$

## Integral equations

### Galilean relativity
