(compressible:characteristics)=
# Characteristics

## Unsteady

Euler equations

$$\begin{aligned}
 0          & = D_t \rho + \rho \nabla \cdot \mathbf{u}  \\
 \mathbf{0} & = \rho D_t \mathbf{u} + \nabla p  \\
 0          & = \rho D_t e^t + \nabla \cdot \left( p \mathbf{u} \right)  \ .
\end{aligned}$$

$$\begin{aligned}
 0          & =  \partial_t \rho + \mathbf{u} \cdot \nabla \rho + \rho \nabla \cdot \mathbf{u}  \\
 \mathbf{0} & =  \partial_t \mathbf{u} + \mathbf{u} \cdot \nabla \mathbf{u} + \frac{1}{\rho} \nabla p  \\
 0          & =  \partial_t e + \mathbf{u} \cdot \nabla e + \frac{p}{\rho} \nabla \cdot \mathbf{u}  \ .
\end{aligned}$$

with $p(\rho, e)$. In Cartesian coordinates

$$
\begin{bmatrix}
 1     & \cdot & \cdot & \cdot \\
 \cdot & 1     & \cdot & \cdot \\
 \cdot & \cdot & 1     & \cdot \\
 \cdot & \cdot & \cdot & 1     \\
\end{bmatrix}
\partial_t \begin{bmatrix} \rho \\ u \\ v \\ e \end{bmatrix} +
\begin{bmatrix}
  u & \rho & \cdot & \cdot \\
  \frac{1}{\rho}\left(\frac{\partial p}{\partial \rho}\right)_e & u     & \cdot & \frac{1}{\rho}\left(\frac{\partial p}{\partial e}\right)_\rho \\
  \cdot & \cdot & u     & \cdot \\
  \cdot & \frac{p}{\rho} & \cdot & u     \\
\end{bmatrix}
\partial_x \begin{bmatrix} \rho \\ u \\ v \\ e \end{bmatrix} +
\begin{bmatrix}
  v & \cdot & \rho & \cdot \\
  \cdot & v     & \cdot & \cdot \\
  \frac{1}{\rho}\left(\frac{\partial p}{\partial \rho}\right)_e & \cdot & v     & \frac{1}{\rho}\left(\frac{\partial p}{\partial e}\right)_\rho  \\
  \cdot & \cdot & \frac{p}{\rho} & v     \\
\end{bmatrix}
\partial_y \begin{bmatrix} \rho \\ u \\ v \\ e \end{bmatrix} =
\begin{bmatrix} 0 \\ 0 \\ 0 \\ 0 \end{bmatrix} \ .
$$

and looking for curves $\mathbf{R}(t)$, s.t. the equations become ODEs, for the function $\mathbf{U}(t) = \mathbf{u}(\mathbf{R}(s(t)), t)$. Since

$$d_t \mathbf{U} = \partial_t \mathbf{u} + \frac{d \mathbf{R}}{d s} \frac{d s}{dt} \cdot \nabla \mathbf{u} = \partial_t \mathbf{u} + X'(s) \dot{s} \partial_x \mathbf{u} + Y'(s) \dot{s} \partial_y \mathbf{u} \ ,$$

**todo** *Uncomment. Fix and continue*

<!--
it follows

$$\begin{aligned}
  \mathbf{0}
  & = \partial_t \mathbf{u}(\mathbf{r},t) + \mathbf{A}_x \partial_x \mathbf{u}(\mathbf{r},t) + \mathbf{A}_y \partial_y \mathbf{u}(\mathbf{r},t) = \\
  & =  d_t \mathbf{u} + \left[ \mathbf{A}_x - X'(s) \dot{s} \mathbf{I} \right] \partial_x \mathbf{u} + \left[ \mathbf{A}_y - Y'(s) \dot{s} \mathbf{I} \right] \partial_y \mathbf{u} \\
\end{aligned}$$

$$\begin{aligned}
 \mathbf{0}
 & = \partial_t \mathbf{u} + \mathbf{A}_i \partial_i \mathbf{u} = \\
 & = \partial_t \mathbf{u} + \mathbf{A}_i \hat{\mathbf{e}}_i \cdot \nabla \mathbf{u} = \\
 & = d_t \mathbf{u} - \left[ \dot{\mathbf{R}} - \mathbf{A}_i \hat{\mathbf{e}}_i \right] \cdot \nabla \mathbf{u} = \\
\end{aligned}$$

-->

## Steady

$$\begin{aligned}
 0          & = \mathbf{u} \cdot \nabla \rho + \rho \nabla \cdot \mathbf{u}  \\
 \mathbf{0} & = \mathbf{u} \cdot \nabla \mathbf{u} + \frac{1}{\rho} \nabla p  \\
 0          & = \mathbf{u} \cdot \nabla e + \frac{p}{\rho} \nabla \cdot \mathbf{u}  \ .
\end{aligned}$$

with $p(\rho, e)$. In Cartesian coordinates

$$
\begin{bmatrix}
  u & \rho & \cdot & \cdot \\
  \frac{1}{\rho}\left(\frac{\partial p}{\partial \rho}\right)_e & u     & \cdot & \frac{1}{\rho}\left(\frac{\partial p}{\partial e}\right)_\rho \\
  \cdot & \cdot & u     & \cdot \\
  \cdot & \frac{p}{\rho} & \cdot & u     \\
\end{bmatrix}
\partial_x \begin{bmatrix} \rho \\ u \\ v \\ e \end{bmatrix} +
\begin{bmatrix}
  v & \cdot & \rho & \cdot \\
  \cdot & v     & \cdot & \cdot \\
  \frac{1}{\rho}\left(\frac{\partial p}{\partial \rho}\right)_e & \cdot & v     & \frac{1}{\rho}\left(\frac{\partial p}{\partial e}\right)_\rho  \\
  \cdot & \cdot & \frac{p}{\rho} & v     \\
\end{bmatrix}
\partial_y \begin{bmatrix} \rho \\ u \\ v \\ e \end{bmatrix} =
\begin{bmatrix} 0 \\ 0 \\ 0 \\ 0 \end{bmatrix} \ .
$$
