(compressible:shocks:oblique)=
# Oblique shocks

[Jump conditions](compressible:jump-conditions)


## Normal Component Analysis
The oblique shock is treated as a normal shock acting only on the normal component of the Mach number:
* $M_{n1} = M_1 \sin \beta$
* $M_{n2} = M_2 \sin(\beta - \theta)$

The tangential component of velocity remains preserved: $u_{t1} = u_{t2}$.

## The $\theta$-$\beta$-$M$ Relation
By relating the geometry of the velocity vectors ($\tan \beta = \frac{u_{n1}}{u_t}$ and $\tan(\beta - \theta) = \frac{u_{n2}}{u_t}$) and substituting the density ratio $\rho_2/\rho_1$, we arrive at the "$\theta$-$\beta$-$M$ equation":

$$\tan \theta = 2 \cot \beta \left[ \frac{M_1^2 \sin^2 \beta - 1}{M_1^2 (\gamma + \cos 2\beta) + 2} \right]$$



## Observations from the $\theta$-$\beta$-$M$ function
1. **Two Solutions:** For any given $M_1$ and $\theta < \theta_{max}$, there are two possible shock angles $\beta$:
   * **Weak Shock:** Smaller $\beta$, usually results in $M_2 > 1$. This is the one typically observed in open flow.
   * **Strong Shock:** Larger $\beta$, results in $M_2 < 1$. Usually occurs in confined flows or high back-pressure.
2. **Maximum Deflection:** If $\theta$ exceeds $\theta_{max}$ for a given $M_1$, no straight oblique shock solution exists, and the shock becomes **detached** (bow shock).



| Property | Ratio | Trend ($M_1 > 1$) |
| :--- | :--- | :--- |
| **Pressure** | $\frac{p_2}{p_1} = 1 + \frac{2\gamma}{\gamma+1}(M_{n1}^2 - 1)$ | Increase |
| **Density** | $\frac{\rho_2}{\rho_1} = \frac{(\gamma+1)M_{n1}^2}{(\gamma-1)M_{n1}^2 + 2}$ | Increase |
| **Temperature** | $\frac{T_2}{T_1} = \frac{p_2}{p_1} \frac{\rho_1}{\rho_2}$ | Increase |
| **Stagnation Pressure** | $\frac{p_{02}}{p_{01}} = e^{-\Delta s / R}$ | **Decrease** |
