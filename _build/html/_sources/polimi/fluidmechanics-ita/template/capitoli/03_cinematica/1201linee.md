**Esercizi per il corso di Fluidodinamica**

Sia dato il campo di moto
$$\bm{u}(x,y) = 2Ax \bm{\hat{x}} - 2Ay \bm{\hat{y}}$$ Calcolare
l'equazione delle linee di corrente, delle traiettorie e delle linee di
fumo (curve di emissione) e disegnarle.

### Soluzione {#soluzione .unnumbered}

     **Concetti.** Definizione di linee di corrente, traiettorie, linee
di fumo, tracce. Soluzione di sistemi di equazioni differenziali
ordinarie (problemi di Cauchy, ai valori iniziali).

**Svolgimento.** Partendo dalle definizioni, si ricavano le equazioni
delle curve caratteristiche.

-   **Linee di corrente.** Dalla scrittura in componenti della
    definizione di linee di corrente si ottiene il sistema
    $$\begin{cases}
      \dfrac{dX}{dp} = \lambda(p) 2 A X \\
      \dfrac{dY}{dp} = - \lambda(p) 2 A Y \ , \\
     \end{cases}
    %  \quad\Rightarrow\quad
    %  \frac{dX}{dY} = -\frac{X}{Y}
    %  \quad\Rightarrow\quad
    %  \ln X = -\ln Y + c 
    %  \quad\Rightarrow\quad
    %  X Y = c$$ risolvibile ad esempio ricavando
    $\lambda(p) = \frac{X'(p)}{2 A X(p)}$ dalla prima equazione e
    inserendolo nella seconda. Integrando tra $p_0$ e $p$, dopo aver
    semplificato i fattori $2 A$, si ottiene (derivare per credere)
    $$0 = \int_{p_0}^{p} \left( \dfrac{X'(p')}{X(p')} + \dfrac{Y'(p')}{Y(p')} \right) dp' =
     \ln{\dfrac{X(p)}{X(p_0)}} + \ln{\dfrac{Y(p)}{Y(p_0)}}$$
    $$\quad \rightarrow \quad
     X(p)Y(p) = X(p_0)Y(p_0)$$ Le linee di corrente appena ricavate sono
    delle iperboli equilatere con gli asintoti coincidenti con gli assi.
    Nel procedimento svolto, per poter dividere per $X(p)$ e $Y(p)$
    dobbiamo imporre la condizione che $X(p)$, $Y(p)$ siano diversi da
    zero. Nella ricerca degli equilibri del sistema, si nota che

    -   il punto $(x,y) = (0,0)$ è l'unico punto di equilibrio del
        sistema, punto di ristagno del campo di velocità;

    -   gli assi coordinati coincidono con linee di corrente: la
        derivata $dX/dp$ è nulla quando $X=0$ (se la parametrizzazione
        della curva è regolare, cioè $\lambda(p) \ne 0$); la derivata
        $dY/dp$ è nulla quando $Y=0$ (se la parametrizzazione della
        curva è regolare, cioè $\lambda(p) \ne 0$). Nel primo caso, la
        linea di corrente coincide con l'asse $y$, avendo coordinata
        $X=0$ costante e coordinata $Y(p)$ descritta dalla seconda
        equazione; nel secondo caso, la linea di corrente coincide con
        l'asse $x$, avendo coordinata $Y=0$ costante e coordinata $X(p)$
        descritta dalla prima equazione.

-   **Traiettorie.** $$\begin{cases}
      \dfrac{dx}{dt} = 2 A x(t) \\
      \dfrac{dy}{dt} = -  2 A y(t) \\
      x(t_0) = x_0 , \quad y(t_0) = y_0
     \end{cases}
     \quad\rightarrow\quad
     \begin{cases}
      x(t;\bm{r_0},t_0) = x_0 e^{2A(t-t_0)} \\
      y(t;\bm{r_0},t_0) = y_0 e^{-2A(t-t_0)} \\
     \end{cases}$$

    #### Osservazione.

    Per ricavare la forma cartesiana dell'equazione delle traiettorie
    bisogna esplicitare il parametro $t$ in funzione di una delle due
    coordinate e inserire la formula ottenuta nell'equazione delle altre
    componenti. In questo caso è possibile eliminare la dipendenza da
    $t$, moltiplicando tra di loro le componenti delle traiettorie e
    ottenendo $x y = x_0 y_0$: si osserva l'equazione delle traiettorie
    coincide con l'equazione delle linee di corrente per il campo di
    velocità considerato. Le linee di corrente coincidono con le linee
    di corrente e le linee di fumo nel caso in cui il **campo di
    veloictà** è **stazionario**: in questo caso, il sistema
    differenziale con il quale si ricavano linee di corrente e linee di
    fumo è **autonomo**, cioè il termine forzante non dipende
    esplicitamente dal tempo. La soluzione di un problema differenziale
    di un sistema autonomo non dipende dal tempo $t$ in sè, ma dalla
    differenza tra il tempo $t$ e il tempo al quale viene imposta la
    condizione iniziale $t_0$: nella formula parametrica delle
    traiettorie, $t$ e $t_0$ compaiono sempre come differenza $t-t_0$ e
    mai "in altre forme", come ad esempio nell'esercizio precedente, nel
    quale il campo di moto non è stazionario. Per questo motivo si
    arriva alla stessa equazione in forma cartesiana per le traiettorie
    e le linee di fumo, dopo aver esplicitato rispettivamente $t$ e
    $t_0$ in funzione di una coordinata e aver inserito questa
    espressione nelle formule delle altre componenti.

-   **Linee di fumo.** Da quanto riportato nel punto e nell'osservazione
    precedenti, è immediato ricavare sia la forma parametrica delle
    linee di fumo, $$\begin{cases}
      x(t_0;t,\bm{r_0}) = x_0 e^{2A(t-t_0)} \\
      y(t_0;t,\bm{r_0}) = y_0 e^{-2A(t-t_0)} \\
     \end{cases}$$ sia la forma cartesiana, $x y = x_0 y_0$.
