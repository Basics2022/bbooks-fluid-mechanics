**Esercizi per il corso di Fluidodinamica**

+:---------------------------------:+:---------------------------------:+
| Si consideri il serbatoio         | ![image](./fig/serbatoio.eps){wid |
| rappresentato in figura,          | th="90%"}                         |
| $D=2\ m$, $H=4.4\ m$ al cui       |                                   |
| interno è contenuta acqua,        |                                   |
| $\overline{\rho}=999\,{kg/m^3}$.  |                                   |
| Supponendo il fluido non viscoso, |                                   |
| determinare la velocità di        |                                   |
| efflusso del fluido dall'ugello   |                                   |
| del serbatoio, $h=0.4\ m$ e       |                                   |
| $d = 1\ cm$, e la sua portata,    |                                   |
| sia in massa sia in volume.       |                                   |
|                                   |                                   |
| ($U = 8.86\ m/s$,                 |                                   |
| $Q=6.96\, 10^{-4}\ m^3/s$,        |                                   |
| $\overline{Q}=0.695\ kg/s$)       |                                   |
+-----------------------------------+-----------------------------------+

### Soluzione {#soluzione .unnumbered}

     **Concetti.** Teorema di Bernoulli, nel caso incomprimibile, non
viscoso, \"stazionario\" (da come è fatto il disegno, il livello del
serbatorio sembra diminuire\...assumiamo che così non sia), con forze
che ammettono potenziale e dominio semplicemente connesso. Se si fa
l'ipotesi che il flusso sia irrotazionale sulla sezione di ingresso, nel
caso non viscoso, si mantiene irrotazionale ovunque (equazione della
vorticità).
$$\frac{D \bm{\omega}}{Dt} = (\bm{\omega} \cdot \bm{\nabla}) \bm{u}$$

Si può quindi scrivere il teorema di Bernoulli nella forma:
$$\frac{P}{\rho} + \frac{|\bm{u}|^2}{2} + gh = \text{cost}$$

**Svolgimento.** Il problema si risolve mettendo a sistema il teorema di
Bernoulli (opportunamente semplificato; vedi sopra) con il bilancio
integrale di massa. Si ipotizza che sulle due sezioni agisca la stessa
pressione esterna.

$$\begin{cases}
  A_1 u_1 = A_2 u_2 & (massa) \\
  \frac{u_1^2}{2} + g h_1 = \frac{u_2^2}{2} + g h_2 & (Bernoulli)
\end{cases}$$

Svolgendo i passaggi, ricordando che le superfici sono circolari,
risulta:
$$u_2 = \sqrt{\frac{2 g (h_1-h_2)}{1-\displaystyle\left(\frac{d_2}{d_1}\right)^4}}$$

Si calcolano poi le portate volumetriche e di massa. $$\begin{aligned}
  & Q = A_2 u_2 \\
  & \dot{m} = \rho Q
\end{aligned}$$
