**Esercizi per il corso di Fluidodinamica**

  --------------------------------------------------- --------------------------------------------------
                                                      
   ($F_x = 1.876\,10^6\ N$, $F_y = -6.251\,10^6\ N$)   ![image](./fig/gomito_galleria.eps){width="60%"}
  --------------------------------------------------- --------------------------------------------------

Bilanci integrali di massa e quantità di moto. $$\begin{cases}
  \frac{d}{dt} \int_V \rho = -\oint_{\partial V} \rho \bm{u} \cdot \hat{\bm{n}}  & \text{(massa)} \\
  \frac{d}{dt} \int_V \rho \bm{u} = -\oint_{\partial V} \rho \bm{u} \bm{u} \cdot \hat{\bm{n}}
  +\int_V \bm{f} - \oint_{\partial V} p \hat{\bm{n}} + \oint_{\partial V} {\bm{t}_s} & \text{(quantità di moto)}
\end{cases}$$

Vengono fatte alcune ipotesi: regime stazionario, fluido incomprimibile,
fluido non viscoso, profili costanti di velocità, no gravità. Si
scrivono i bilanci integrali semplificati, si riconoscono in essi e si
calcolano le azioni scambiate con il corpo.

-   Scrittura dei bilanci integrali con le semplificazioni opportune,
    derivanti dalle ipotesi. $$\begin{cases}
          \oint_{\partial V} \rho \bm{u} \cdot \hat{\bm{n}} = 0  & \text{(massa)} \\
          \oint_{\partial V} \rho \bm{u} \bm{u} \cdot \hat{\bm{n}} = \oint_{\partial V} \bm{t_n} & \text{(quantità di moto)}
         \end{cases}$$

-   Ulteriore semplificazione usando l'ipotesi di densità costante e
    profili di velocità uniformi $$\begin{cases}
          -V_1 A_1 + V_2 A_2 = 0  & \quad \Rightarrow \quad V_1 A_1 = V_2 A_2 = Q \\
          - \rho \vec{V_1} V_1 A_1 + \rho \vec{V_2} V_2 A_2 = \oint_{\partial V} \bm{t_n}
         \end{cases}$$

-   Relazione tra l'integrale della pressione e la risultante delle
    forze agenti sul gomito, sfruttando il fatto che l'integrale della
    normale su tutta la superficie è identicamente nullo. Si
    identificano con $S_1$ la superficie di ingresso, $S_2$ la
    superficie di uscita, $S_3$ la superficie laterale.
    $$\begin{aligned}
          \displaystyle\oint_{S_1\cup S_2\cup S_3} p \hat{n} & =  \displaystyle\oint_{S_1\cup S_2\cup S_3} \bm{t_n} + \displaystyle\oint_{S_1\cup S_2\cup S_3} p_a \hat{n} = \\
          & = -\oint_{S_1} (p-p_a) \hat{n} - \oint_{S_2} (p-p_a) \hat{n} + \underbrace{\oint_{S_3} (\bm{t_n}+p_a\hat{n})}_{=-\bm{f}}  =  \\
          & = -\oint_{S_1} (p-p_a) \hat{n} - \oint_{S_2} (p-p_a) \hat{n} - \bm{f}
         \end{aligned}$$

-   L'equazione della quantità di moto diventa quindi:
    $$- \rho \bm{V_1} V_1 A_1 + \rho \bm{V_2} V_2 A_2 = - (p_1 - p_a) A_1 \hat{n}_1 - (p_2 - p_a) A_2 \hat{n}_2 - \bm{F}$$

-   Proiezione lungo i due assi del sistema di riferimento della
    risultante delle forze agenti sul gomito. Se si considera $p_a = 0$,
    i risultati numerici sono i seguenti: $$\begin{cases}
        F_x = \rho \frac{Q^2}{A_1} + (p_1 - p_a)A_1  & \quad \Rightarrow \quad   F_x = 1.876 \cdot 10^6 N  \\
        F_y = -  \rho \frac{Q^2}{A_2} - (p_2 - p_a)A_2  & \quad \Rightarrow \quad   F_y =-6.250 \cdot 10^6 N
      \end{cases}$$
