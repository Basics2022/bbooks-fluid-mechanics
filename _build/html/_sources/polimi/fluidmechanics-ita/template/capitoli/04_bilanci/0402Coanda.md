**Esercizi per il corso di Fluidodinamica**

+:---------------------------------:+:---------------------------------:+
| Un getto d'acqua                  | ![image](./fig/coanda.eps){width= |
| ($\rho=999\ kg/m^3$) stazionario, | "90%"}                            |
| piano e orizzontale viene         |                                   |
| indirizzato su un cilindro,       |                                   |
| lambendone la superficie e        |                                   |
| venendo deviato di un angolo      |                                   |
| $\alpha =15^\circ$. Determinare   |                                   |
| la forza agente su una porzione   |                                   |
| del cilindro di lunghezza pari a  |                                   |
| $H = 2\ m$, dovuta sia al getto   |                                   |
| d'acqua, sia all'aria             |                                   |
| circostante, sapendo che:         |                                   |
|                                   |                                   |
| -   il fluido che circonda il     |                                   |
|     getto e il cilindro è aria in |                                   |
|     quiete a pressione            |                                   |
|     atmosferica di $101325\ Pa$;  |                                   |
|                                   |                                   |
| -   la larghezza del getto è      |                                   |
|     $h=2\ cm$;                    |                                   |
|                                   |                                   |
| -   la portata d'acqua per unità  |                                   |
|     di lunghezza nel getto è      |                                   |
|     $Q = 199\ kg\ m^{-1}\ s^{-1}$ |                                   |
| .                                 |                                   |
|                                   |                                   |
| Sufficientemente lontano dal      |                                   |
| cilindro, il profilo di velocità  |                                   |
| sulle sezioni del getto è         |                                   |
| uniforme. Illustrare tutte le     |                                   |
| ipotesi semplificative adottate   |                                   |
| nella risoluzione dell'esercizio. |                                   |
|                                   |                                   |
| ($\bm{F} = 1026\ \hat{\bm{x}} - 1 |                                   |
| 35\ \hat{\bm{y}} \ N$)            |                                   |
+-----------------------------------+-----------------------------------+

Bilanci integrali di massa e quantità di moto. Equazioni di equilibrio
(equazioni fondamentali della dinamica classica). Principio di azione e
reazione. Integrale della normale su una superficie chiusa è
identicamente nullo. Effetto Coanda (esempio della bustina da té sotto
il rubinetto).

Vengono fatte alcune ipotesi: il problema stazionario; attorno al getto
e al solido, l'aria è in quiete con pressione uniforme $p_a$; il profilo
di velocità è uniforme sulle sezioni del getto considerate nelle
equazioni di bilancio.

Partendo dalle equazioni di bilancio per il volume di controllo $V_{f}$
occupato dal fluido, rielaborando il termine degli sforzi di superficie
sforzi di superficie, si ricava la risultante $\bm{R}$ agente sul solido
in funzione del flusso di quantità di moto del fluido attraverso la
superficie $S_{f} = \partial V_f$.

Innanzitutto viene ricavata l'espressione della risultante $\bm{R}$
agente sul solido.

-   Vengono scritte le equazioni di bilancio per il fluido, considerando
    il volume $V_f$ $$\begin{cases}
           \dfrac{d}{d t} \displaystyle\int_{V_f} \rho + \oint_{S_f} \rho \bm{u} \cdot \hat{\bm{n}} = 0 & \qquad \text{(massa)} \\
           \dfrac{d}{d t} \displaystyle\int_{V_f} \rho \bm{u} + \oint_{S_f} \rho \bm{u} \bm{u} \cdot \hat{\bm{n}} =
            \oint_{S_f} \bm{t_n} = 0  
    %        \oint_{\partial \Omega} p \hat{\bm{n}} - \oint_{\partial \Omega} \bm{s_n} = 0  
            & \qquad \text{(quantità di moto)}  %\Rb^{ext}
          \end{cases}$$

-   Viene introdotta l'ipotesi di stazionarietà del fenomeno,
    $\frac{d}{dt}\equiv 0$. La risultante degli sforzi viene scritta
    come somma degli sforzi di pressione e degli sforzi viscosi,
    $$\begin{split}
    % & \Rb = \oint_{S_{cyl}}  {\bm{t}}_{\bm{n}} = 
    % \oint_{S_{cyl}}  {\bm{s}}_{\bm{n}} - \oint_{S_{cyl}} p {\hat{\bm{n}}}_{cyl} \\
     & \oint_{S_f} \rho \bm{u} \bm{u} \cdot \hat{\bm{n}} 
      = \oint_{S_{f}}  {\bm{t}}_{\bm{n}} = 
     \oint_{S_{f}}  {\bm{s}}_{\bm{n}} - \oint_{S_f} p {\hat{\bm{n}}}_{f} \ .
    \end{split}$$

-   Viene manipolato il termine degli sforzi di superficie. Il contorno
    $S_f$ del volume fluido viene scomposto come unione della superficie
    a contatto con il solido $S_{fs}$, delle superfici "laterali"
    $S_{f\ell}$ (attraverso le quali non c'è flusso di quantità
    meccaniche, poichè $\bm{u}\cdot\bm{\hat{n}} = 0$) a contatto con
    l'aria in quiete e le sezioni "di ingresso" $S_{f,1}$ e "di uscita"
    $S_{f,2}$ sulle quali la velocità è uniforme, utilizzate per i
    bilanci integrali per il volume fluido. Viene indicata con
    $\bm{\hat{n}_f}$ la normale uscente dal volume $V_f$. Il contorno
    $S_s$ del solido viene scomposto come unione della superficie a
    contatto con il fluido $S_{sf}$ e della superficie $S_{s\ell}$ a
    contatto con l'aria in quiete. Viene indicata con $\bm{\hat{n}_s}$
    la normale uscente dal volume $V_s$. In questo modo, la superficie
    $S_{fs}$ coincide con la superficie $S_{sf}$, a meno della normale
    invertita, $\bm{\hat{n}_f} = \bm{\hat{n}_s}$. Su queste superfici,
    per il terzo principio della dinamica, lo sforzo ${\bm{t_n}}_{sf}$
    agente sul solido dovuto al fluido è uguale e contrario allo sforzo
    ${\bm{t_n}}_{fs}$ agente sul fluido dovuto al fluido,
    ${\bm{t_n}}_{sf}=-{\bm{t_n}}_{fs}$. La superficie formata
    dall'unione
    $S_{f\ell} \cup S_{f,1} \cup S_{f,2} \cup S_{s\ell} =:S_{ext}$ è una
    superficie chiusa con normale uscente $\bm{\hat{n}}$ uguale a
    $\bm{\hat{n}_f}$ sulle prime tre superfici e uguale a $\bm{\hat{n}}$
    su $S_{s\ell}$. Lo sforzo agente su $S_{ext}$ è uguale a
    $-p_a\bm{\hat{n}}$, poiché le superfici libere sono a contatto con
    aria in quiete con pressione $p_a$ e le traiettorie delle particelle
    rettilinee (senza curvatura[^1]) sulle sezioni $S_{f,1}$ e
    $S_{f,2}$.

    $$\begin{aligned}
      \oint_{S_f} \bm{t_n} & = 
      \int_{S_{f\ell}} \bm{t_n} + \int_{S_{f,1+2}} \bm{t_n} + \int_{S_{fs}} \bm{t_n} = & \text{($\bm{t_n} |_{S_{f\ell},S_{f,1+2}} = -p_a \bm{\hat{n}_f}$ )}\\
      & = - \int_{S_{f\ell}\cup S_{f,1+2}} p_a \bm{\hat{n}_f} + \int_{S_{fs}} \bm{t_n} = & \text{(somma e sottrazione di $\int_{S_{fs}} p_a \bm{\hat{n}_f}$)}\\
      & = \underbrace{- \int_{S_{f\ell}\cup S_{f,1+2}} p_a \bm{\hat{n}_f} - \int_{S_{fs}} p_a \bm{\hat{n}_f}}_{-\oint_{S_f} p_a \bm{\hat{n}_f}=0}
      + \int_{S_{fs}} p_a \bm{\hat{n}_f} + \int_{S_{fs}} \bm{t_n} = & \text{($\bm{\hat{n}_f} = -\bm{\hat{n}_s}$, ${\bm{t_n}}_{fs} = - {\bm{t_n}}_{sf}$ su $S_{fs}$)} \\
      & = - \int_{S_{sf}} p_a \bm{\hat{n}}_{s} - \int_{S_{sf}} {\bm{t_n}}_{sf} = &
       \text{($\oint_{S_s=S_{sf}\cup S_{s\ell}} p_a \bm{\hat{n}_s} = 0)$} \\
      & = + \int_{S_{s\ell}} p_a \bm{\hat{n}}_{s} - \int_{S_{sf}} {\bm{t_n}}_{sf} = &
       \text{(${\bm{t_n}}_s = -p_a\bm{\hat{n}_s}$ su $S_{s\ell}$} \\
      & = - \int_{S_{s\ell}} {\bm{t_n}}_{s} - \int_{S_{sf}} {\bm{t_n}}_{sf} = - \oint_{S_{s}} {\bm{t_n}}_{s} = \\
    %  \text{($S_{cyl} = S_c \cup S_{c_l}$ e $\int_{S_{cyl}} p_a \bm{n} = 0$)}\\
    %  & = \int_{{S_c}_l} p_a \bm{n}_{cyl} + \int_{S_c} \bm{t_n} = &
    %  \text{($\bm{t}_{\bm{n}_{s}}|_{S_{c_l}} = -p_a \bm{n}_{cyl}$, $\bm{t}_{\bm{n}_{cyl}}|_{S_c} = - \bm{t_n}$)} \\
    %  & = - \int_{{S_c}_l} \bm{t}_{\bm{n}_{cyl}} - \int_{S_c} \bm{t}_{\bm{n}_{cyl}} = \\
    %  & = - \int_{S_{cyl}} \bm{t}_{\bm{n}_{cyl}} \\
      & = - \bm{R} \ ,
    \end{aligned}$$ dove $\bm{R}$ è la risultante degli sforzi di
    superficie agente sul solido. In questo esercizio è il contributo
    delle forze di volume (ad esempio il peso) agenti sul solido.

-   Sostituendo nell'equazione del bilancio della quantità di moto si
    ottiene:
    $$\bm{R} = - \oint_{S_f} \rho \bm{u} \bm{u} \cdot \hat{\bm{n}}$$

-   Considerando solo le superfici di $V_f$ attraverso le quali c'è un
    flusso non nullo di quantità di moto, la risultante delle forze
    diventa
    $$\bm{R} = - \int_{S_{f,1}} \rho \bm{u} \bm{u} \cdot \hat{\bm{n}} 
              - \int_{S_{f,2}} \rho \bm{u} \bm{u} \cdot \hat{\bm{n}}$$
    dove le quantità all'interno degli integrali sono riferite alle
    superfici di integrazione. Sulle sezioni $S_{f,1}$, $S_{f,2}$ la
    velocità è uniforme con modulo $U$ (dalla continuità, la velocità
    sulle due sezioni è uguale poichè l'area delle due sezioni è uguale)
    diretta lungo la linea media del getto. Le componenti cartesiane
    della risultante $\bm{R}$ sono $$\begin{split}
      & R_x = \frac{Q^2 H}{\rho h} \sin \alpha \\
      & R_y = - \frac{Q^2 H}{\rho h} (1-\cos \alpha) \ ,
    \end{split}$$ riferite agli assi rappresentati in figura.

[^1]: Vedi commento sull'equazione della quantità di moto e sulle
    traiettorie delle particelle
