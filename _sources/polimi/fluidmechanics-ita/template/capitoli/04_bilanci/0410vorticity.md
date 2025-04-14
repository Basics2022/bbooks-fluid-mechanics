L'equazione della vorticità in coordinate euleriane è
$$\frac{\partial \bm{\omega}}{\partial t}
   + (\bm{u}\cdot\bm{\nabla}) \bm{\omega} =
 (\bm{\omega}\cdot\bm{\nabla}) \bm{u} + \nu \bm{\Delta} \bm{\omega}$$

Se viene fatta l'ipotesi di viscosità nulla, il termine contenente il
laplaciano della vorticità non compare nell'equazione: questo termine è
il responsabile della diffusione (isotropa per come è scritto) della
vorticità.

L'equazione può essere quindi riscritta come:
$$\frac{D\bm{\omega}}{Dt} = (\bm{\omega} \cdot \bm{\nabla}) \bm{u}$$

Scritta in componenti $$\begin{aligned}
  \frac{D \omega_i}{D t} = \omega_k \frac{\partial u_i}{\partial x_k} \\
\end{aligned}$$

Il termine di destra può essere riscritto come $$\begin{aligned}
 \omega_k \frac{\partial u_i}{\partial x_k} & = 
 \omega_k \frac{\partial u_i}{\partial x_{0 l}}
      \frac{\partial x_{0 l}}{\partial x_k} = \qquad \qquad
      \left(u_i = \frac{D x_i}{D t}\right)  \\
 & = \omega_k \frac{D}{Dt} \left( \frac{\partial x_i}{\partial x_{0 l}}
    \right)\frac{\partial x_{0 l}}{\partial x_k} 
\end{aligned}$$ Vale la relazione
$$\frac{\partial x_i}{\partial x_{0 l}}
   \frac{\partial x_{0 l}}{\partial x_k} = \delta_{ik}$$ Il termine di
sinistra può essere riscritto come
$$\frac{D \omega_i}{Dt} = \frac{D}{Dt} \left(\delta_{ik} \omega_k \right) =
 \frac{D}{Dt} \left( \frac{\partial x_i}{\partial x_{0 l}}
   \frac{\partial x_{0 l}}{\partial x_k} \omega_k \right)$$

Inserendo nell'equazione della vorticità e sfruttando le proprietà della
derivata del prodotto: $$\begin{aligned}
 &  \frac{D}{Dt} \left(  \frac{\partial x_i}{\partial x_{0 l}}
   \frac{\partial x_{0 l}}{\partial x_k} \omega_k  \right)  - 
  \omega_k \frac{D}{Dt} \left( \frac{\partial x_i}{\partial x_{0 l}}
    \right)\frac{\partial x_{0 l}}{\partial x_k} = 0 \\
 &  \frac{\partial x_i}{\partial x_{0 l}} 
  \frac{D}{Dt} \left( \frac{\partial x_{0 l}}{\partial x_k} \omega_k
    \right) = 0
\end{aligned}$$ Se la trasformazione non è singolare, risulta quindi
$$\frac{D}{Dt} \left( \frac{\partial x_{0 l}}{\partial x_k} \omega_k
    \right) = 0  \quad \Rightarrow \quad
  \frac{\partial x_{0 l}}{\partial x_k} \omega_k = \omega_{l 0}$$ e in
conclusione, invertendo il gradiente della trasformazione delle
coordinate $$\label{eqn:bilanci:vorticitàLagrange}
   \omega_k = \frac{\partial x_k}{\partial x_{0 l}}\omega_{l 0}
   \qquad , \qquad \bm{\omega} = \frac{\partial \bm{x}}{\partial \bm{x}_0}
      \bm{\omega}_0$$

Si può quindi notare che la vorticità segue la stessa evoluzione di un
segmento infinitesimo materiale, per il quale vale:
$$d\bm{x} = \frac{\partial \bm{x}}{\partial \bm{x}_0}
      d\bm{x}_0$$
