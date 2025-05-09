L'equazione di continuità può essere riscritta mettendo in evidenza la
derivata materiale
$$\frac{\partial \rho}{\partial t} + \bm{\nabla} \cdot (\rho \bm{u}) = 0 
  \quad  \rightarrow  \quad 
  \frac{D\rho}{Dt} = -\rho \bm{\nabla} \cdot \bm{u}$$ É possibile
dimostrare[^1] la relazione $DJ/Dt = J \bm{\nabla} \cdot \bm{u}$, dove
$J$ indica il determinante del gradiente $\partial \bm{x}/\partial 
 \bm{x}_0$, si può scrivere l'equazione in coordinate lagrangiane, dopo
averla moltiplicata per $J$ ($\ne 0$)
$$J \frac{D\rho}{Dt} = - \rho \frac{DJ}{Dt} \Rightarrow
 \frac{D (J\rho)}{Dt} = 0 \Rightarrow J \rho = \rho_0$$ La variazione
della densità di una particella materiale è legata alla variazione del
volume della stessa (ricordare che $dv = J dV$). Questa conclusione è
ragionevole se si pensa che la massa della particella materiale si
conserva ($dm = \rho dv = 
 \rho_0 dV$).

Il vincolo di incomprimibilità rappresenta la costanza del volume della
particella materiale. Il volume $dv$ coincide con il volume di
riferimento $dV$, implicando $J \equiv 1$ e quindi
$\bm{\nabla} \cdot \bm{u} = 0$.

[^1]: I più curiosi, cerchino "fornmula di Jacobi".
