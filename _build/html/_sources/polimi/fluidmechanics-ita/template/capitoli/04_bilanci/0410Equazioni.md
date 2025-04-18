**Esercizi per il corso di Fluidodinamica**

Approfondimenti su alcuni bilanci
=================================

In questa sezione vengono analizzate alcune equazioni di bilancio in
forma differenziale (è quindi necessario che queste equazioni siano
valide!): vengono usate sia la rappresentazione euleriana sia la
rappresentazione lagrangiana, al fine di ottenere la migliore
comprensione dei fenomeni fisici coinvolti.

Si indicano con $\bm{x}_0$ le coordinate lagrangiane, solidali con il
continuo; si indicano con $\bm{x}$ le coordinate euleriane. I due
sistemi di coordinate sono legati tra di loro dalle relazioni
$$\begin{aligned}
 \bm{x} = \bm{x}(\bm{x}_0,t) \\
 \frac{D \bm{x}}{D t} = \left.\frac{\partial \bm{x}}{\partial t}\right|_{\bm{x}_0} = 
 \bm{u}
\end{aligned}$$ La derivata $\partial/\partial t$ indica la derivata
temporale fatta a coordinata euleriana $\bm{x}$ costante. La derivata
materiale $D/D t$ indica la derivata fatta \"a coordinata lagrangiana\"
costante e rappresenta quindi la variazione temporale di una quantità
legata alla particella materiale, che si muove come il continuo, per la
definizione di coordinate materiali.

Il legame tra $D/Dt$ e $\partial/\partial t$ si trova utilizzando le
regole di derivazione per funzioni composte. Scrivendo la funzione
generica $f$ come $$f(\bm{x},t) = f(\bm{x}(\bm{x}_0,t),t)
  = f_0(\bm{x}_0,t) = f_0(\bm{x}_0(\bm{x},t),t) ,$$ si ottiene
$$\frac{D}{Dt} f = \left.\frac{\partial}{\partial t}\right|_{\bm{x}_0} f(\bm{x},t) =
   \left.\frac{\partial}{\partial t}\right|_{\bm{x}_0} f(\bm{x}(\bm{x_0},t),t) = 
   \left.\frac{\partial f}{\partial t}\right|_{\bm{x}} +
   \left.\frac{\partial \bm{x}}{\partial t}\right|_{\bm{x}_0} \cdot
   \left.\frac{\partial f}{\partial \bm{x}}\right|_{t}
   = \frac{\partial f}{\partial t} +
    \bm{u} \cdot \bm{\nabla} f .$$

Continuità
----------

Quantità di moto
----------------

Vorticità
---------
