**Esercizi per il corso di Fluidodinamica**

+:---------------------------------:+:---------------------------------:+
| Una lastra piana di lunghezza e   | ![image](./fig/lastracanale.eps){ |
| apertura infinita si spessore     | width="70%"}                      |
| $t=1\ mm$ scorre in un canale     |                                   |
| piano di altezza $H=2.22\  mm$    |                                   |
| contenente acqua in condizioni    |                                   |
| standard. Essa viene mantenuta a  |                                   |
| distanza costante $h_1=0.5\  mm$  |                                   |
| dalla parete superiore e si muove |                                   |
| a velocità constante              |                                   |
| $U=0.55 \  m/s$.                  |                                   |
|                                   |                                   |
| Calcolare:                        |                                   |
|                                   |                                   |
| -   il numero di Reynolds basato  |                                   |
|     sulla velocità $U$ della      |                                   |
|     parete e sulla distanza fra   |                                   |
|     le pareti sia per la porzione |                                   |
|     di corrente superiore sia per |                                   |
|     quella inferiore;             |                                   |
|                                   |                                   |
| -   la componente orizzontale del |                                   |
|     risultante delle forze per    |                                   |
|     unità di superficie           |                                   |
|     esercitate dal fluido sulla   |                                   |
|     lamina;                       |                                   |
|                                   |                                   |
| -   la potenza per unità di       |                                   |
|     superficie che occorre        |                                   |
|     fornire alla lastra per       |                                   |
|     mantenerla in moto uniforme.  |                                   |
|                                   |                                   |
| ($Re_{sup}=239$, $Re_{inf}=344$,  |                                   |
| $F_x=-2.14\ N/m^2$,               |                                   |
| $P=1.17\  W/m^2$)                 |                                   |
+-----------------------------------+-----------------------------------+

### Soluzione {#soluzione .unnumbered}

     **Concetti.** Soluzioni esatte delle equazioni di Navier-Stokes.
Corrente di Newton.

**Svolgimento.** La soluzione del problema può essere ricondotta alla
soluzione esatta della corrente di Newton nel canale piano. Si può
calcolare immediatamente il numero di Reynolds basato sulle due diverse
lunghezze di riferimento, poichè densità e viscosità sono date e la
velocità di riferimento del problema è quella della lastra, nota
anch'essa.

In seguito, si calcola lo sforzo a parete per ricavare la forza per
unità di superficie esercitata dal fluido sulla lamina e la potenza
(prodotto di forza e velocità) necessaria a mantenere la lamina in moto
uniforme.

-   Numero di Reynolds
    $$Re = \frac{\rho U L}{\mu}  \qquad \Rightarrow \qquad Re_{sup} = 239 , \quad Re_{inf} = 344$$

-   Scrivendo le equazioni per uno solo dei due lati, indicando con
    $z=0$ la coordinata della parete fissa e $z=l$ quella della parete
    mobile, si ricava la corrente di Newton: $$u(z) = U \frac{z}{l}$$

-   Il profilo di velocità per la corrente di Newton è lineare. Lo
    sforzo viscoso a parete (su una sola delle superfici) vale
    $$\tau_w = \mu \frac{U}{l}$$

    Sommando gli effetti su entrambe le pareti, la forza per unità di
    superficie si scrive come
    $$\frac{F}{S} = \tau = \mu U \displaystyle\left( \frac{1}{H-h-t} + \frac{1}{h} \right)
       \qquad \Rightarrow \qquad \tau = 2.14 N/m^2$$

-   La potenza per unità di superficie si ricava dal prodotto della
    forza per unità di superfici e della velocità della lastra
    $$\frac{P}{S} = \frac{F}{S} U \qquad \Rightarrow \qquad \frac{P}{S} = 1.17 W/m^2$$
