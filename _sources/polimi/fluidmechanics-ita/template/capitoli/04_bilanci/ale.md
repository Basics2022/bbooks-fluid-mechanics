(fluid-mechanics:balances:uniformly-accelerated)=
# Generic transformation - ALE

$$\begin{cases}
  \mathbf{r}' = \mathbf{r}'\left( \mathbf{r}, t \right) \\
  t' = t
\end{cases}$$

Derivative of composite functions give

$$\begin{aligned}
  \partial_t
  & = \partial_{t} t' \partial_{t'} + \partial_t \mathbf{r}' \cdot \partial_{\mathbf{r}'} \\
  & = \partial_{t'} + \mathbf{v}(\mathbf{r}, t) \cdot \nabla' \\
  \nabla &  = \nabla' \ ,
\end{aligned}$$

being $\mathbf{v}(\mathbf{r}, t) := \left.\frac{\partial \mathbf{r}'}{\partial t}\right|_{\mathbf{r}}$ the velocity of the point with constant cordinate $\mathbf{r}$ w.r.t. the new reference frame. Here the partial derivative $\partial_{t'}$ is performed at constant $\mathbf{r}'$ position vector.

Let 

## Differential equations

**Mass.**

$$\begin{aligned}
  0 
  & = \partial_t \rho + \nabla \cdot \left( \rho \mathbf{u} \right) =
\end{aligned}$$


## Integral equations




