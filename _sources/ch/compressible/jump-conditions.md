(compressible:jump-conditions)=
# Jump conditions

**Continuous medium.** Jump conditions for a continuous medium read

$$\begin{aligned}
  0          & = [ \rho u^{rel}_n ]  \\
  \mathbf{0} & = \dot{m}[ \mathbf{u} ] - [ \mathbf{t}_{\mathbf{n}} ] \\
  0          & = \dot{m}[ e^t ] + [ \mathbf{t}_{\mathbf{n}} \cdot \mathbf{u} - \hat{\mathbf{n}} \cdot \mathbf{q} ]  \ ,
\end{aligned}$$

being $\dot{m} = \rho_1 u^{rel}_{n,1} = \rho_2 u^{rel}_{n,2}$. 

**Inviscid flows, w/o heat conduction (Euler equations).** If viscous stress and heat conduction are negligible (as they're in Euler equations), jump conditions become

$$\begin{aligned}
  0          & = [ \rho u^{rel}_n ]  \\
  \mathbf{0} & = \dot{m}[ \mathbf{u} ] + [ p \mathbf{n} ] \\
  0          & = \dot{m}[ h^t ] + [ p ] \hat{\mathbf{n}} \cdot \mathbf{u}_s  \ .
\end{aligned}$$


```{dropdown} Details

Starting from integral equations

$$\begin{aligned}
  & \dfrac{d}{dt} \int_{v_t} \rho + \oint_{\partial v_t} \rho \mathbf{u}^{rel} \cdot \hat{\mathbf{n}} = 0 \\
  & \dfrac{d}{dt} \int_{v_t} \rho \mathbf{u} + \oint_{\partial v_t} \rho \mathbf{u} \mathbf{u}^{rel} \cdot \hat{\mathbf{n}} = \int_{v_t} \rho \mathbf{g}  + \oint_{\partial v_t} \mathbf{t}_{\mathbf{n}} \\
  & \dfrac{d}{dt} \int_{v_t} \rho e^t + \oint_{\partial v_t} \rho e^t \mathbf{u}^{rel} \cdot \hat{\mathbf{n}} = \int_{v_t} \rho \mathbf{g} \cdot \mathbf{u}  + \oint_{\partial v_t} \mathbf{t}_{\mathbf{n}} \cdot \mathbf{u} - \oint_{\partial v_t} \mathbf{q} \cdot \hat{\mathbf{n}} \\
\end{aligned}$$

and collapsing the volume $v_t$ on one of its dimension, volume contributions become negligible when compared to surface contributions. Jump conditions immeadiately follow, setting $\hat{\mathbf{n}} = \hat{\mathbf{n}}_2 = - \hat{\mathbf{n}}_1$,

$$\begin{aligned}
  0          & = [ \rho u^{rel}_n ]  \\
  \mathbf{0} & = [ \rho \mathbf{u} u^{rel}_n - \mathbf{t}_{\mathbf{n}} ] \\
  0          & = [ \rho e^t u^{rel}_n + \mathbf{t}_{\mathbf{n}} \cdot \mathbf{u} - \hat{\mathbf{n}} \cdot \mathbf{q} ]  \\
\end{aligned}$$

Thus $\rho_1 u_{n,1}^{rel} = \rho_2 u_{n,2}^{rel} = \dot{m}$, and

$$\begin{aligned}
  0          & = [ \rho u^{rel}_n ]  \\
  \mathbf{0} & = \dot{m}[ \mathbf{u} ] - [ \mathbf{t}_{\mathbf{n}} ] \\
  0          & = \dot{m}[ e^t ] + [ \mathbf{t}_{\mathbf{n}} \cdot \mathbf{u} - \hat{\mathbf{n}} \cdot \mathbf{q} ]  \\
\end{aligned}$$

If viscous streass and conduction heat flux are negligible, 

$$\begin{aligned}
  0          & = [ \rho u^{rel}_n ]  \\
  \mathbf{0} & = \dot{m}[ \mathbf{u} ] + [ p \mathbf{n} ] \\
  0          & = \dot{m}[ e^t ] + [ p \hat{\mathbf{n}} \cdot \mathbf{u} ] = \\
             & = \dot{m}[ e^t ] + \left[ \frac{p}{\rho} \underbrace{\hat{\mathbf{n}} \cdot \rho ( \mathbf{u} - \mathbf{u}_s )}_{ \rho u_{n}^{rel} = \dot{m}} + p \hat{\mathbf{n}} \cdot \mathbf{u}_s \right] = \\
             & = \dot{m} \left[ e^t + \frac{p}{\rho} \right] + [ p \hat{\mathbf{n}} \cdot \mathbf{u}_s ] = \\
             & = \dot{m} \left[ h^t \right] + \left[ p \right] \, \hat{\mathbf{n}} \cdot \mathbf{u}_s  \\
\end{aligned}$$

```

Two main cases are determined by the value of the mass flow $\dot{m}$:
- if $\dot{m} = 0$,

   $$\begin{aligned}
     & \dot{m} = 0 \\
     & [ p ] = 0 \ ,
   \end{aligned}$$

   while nothing can be said about the tangential component of the velocity field and the total enthalpy. These conditions hold **contact discontinuities**.

- if $\dot{m} \ne 0$

   $$\begin{aligned}
     0 & = [ \dot{m} ] = [ \rho u_{n}^{rel} ]   \\
     \mathbf{0} & = \dot{m} [ \mathbf{u}_{\mathbf{t}} ]  \\
     0 & = \dot{m} [ u_n ] + [ \, p \, ] = \dot{m} [ u_n^{rel} ] + [ \, p \, ]  \\
     0 & = \dot{m} [ h^{t,rel} ] = \dot{m} [ h^{t,rel}_n ] 
   \end{aligned}$$

   These conditions hold for **shocks** (usually compression shocks, e.g. for PIG, but for heavy fluids expansion shocks may exist as well).


```{dropdown} Details

$$\begin{aligned}
  0 & = [ \dot{m} ] = [ \rho u_{n}^{rel} ]   \\
  \mathbf{0} & = \dot{m} [ \mathbf{u}_{\mathbf{t}} ]  \\
  0 & = \dot{m} [ u_n ] + [ \, p \, ] =  && ([u_s] = 0) \\
    & = \dot{m} [ u_n - u_s ] + [ \, p \, ] = \\
    & = \dot{m} [ u_n^{rel} ] + [ \, p \, ]  \\
  0 & = \dot{m} [ h^t ] + u_{s,n} [ \, p \, ] = \\
    & = \dot{m} \left[ h^t \right] - u_{s,n} \, \dot{m} \left[ u_n \right] = \\
    & = \dot{m} \left[ h + \frac{u_n^2 + u_t^2}{2} - u_{s,n} u_n  \right] = \\
    & = \dot{m} \left[ h + \frac{u_n^2 - 2 u_{s,n} u_n + u_{s,n}^2}{2} - \frac{u_{s,n}^2}{2} + \frac{u_t^2}{2}  \right] = \\
    & = \dot{m} \left[ h + \frac{(u_n - u_{s,n})^2}{2} - \frac{u_{s,n}^2}{2} + \frac{u_t^2}{2}  \right] = \\
    & = \dot{m} \left[ h^{t,rel} \right] = \\
    & = \dot{m} \left[ h^{t,rel}_n \right] \ ,
\end{aligned}$$

as $\left[ u_{s,n}^2 \right] = 0$ being $u_{s,n}$ the velocity of the "discontinuity" surface, $[ \mathbf{u}_t ] = 0$ from the tangential component of the momentum equation, and with the definition of the *relative total enthalpy*

$$h^{t,rel} := h + \frac{1}{2} \left( (u_n - u_{s,n})^2 + u_t^2  \right) = h + \frac{1}{2} \left( \left( u_{n}^{rel} \right)^2 + u_t^2 \right) \ , $$

and $h^{t,rel}_n$ the relative total enthalpy built with the normal component of the relative velocity only.

```
