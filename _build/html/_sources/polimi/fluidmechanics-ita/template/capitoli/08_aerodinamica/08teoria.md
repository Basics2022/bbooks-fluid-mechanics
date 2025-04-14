(fluid-mechanics:aerodynamics)=
# Aerodynamics

Per correnti irrotazionali ($\omega = \mathbf{0}$) in un dominio
semplicemente connesso ($\mathbf{u} = \mathbf{\nabla} \phi$) di fluidi
incomprimibili ($\mathbf{\nabla} \cdot \mathbf{u} = 0$), il potenziale cinetico
soddisfa l'equazione di Laplace $\Delta \phi = 0$. Infatti, inserendo
nel vincolo di incomprimibilità la relazione che lega il potenziale
cinetico alla velocità si ottiene

$$0 = \mathbf{\nabla} \cdot \mathbf{u} = \mathbf{\nabla} \cdot (\mathbf{\nabla} \phi) = \nabla^2 \phi = \Delta \phi .$$

Come nel caso della seconda e della terza forma del teorema di Bernoulli
per fluidi viscosi, vedi introduzione al capitolo
§[\[ch:bernoulli\]](#ch:bernoulli){reference-type="ref"
reference="ch:bernoulli"}, l'ipotesi di fluido non viscoso non è
direttamente necessaria per ottenere l'equazione di Laplace per il
potenziale. L'ipotesi di fluido non viscoso rientra però nel requisito
che la corrente sia irrotazionale. L'equazione della vorticità per
fluido incomprimibile è

$$\frac{\partial \mathbf{\omega}}{\partial t} + (\mathbf{u} \cdot \mathbf{\nabla}) \mathbf{\omega} = (\mathbf{\omega} \cdot \mathbf{\nabla}) \mathbf{u} + \nu \Delta \mathbf{\omega} ,$$

che per un fluido non viscoso, si riduce a

$$\frac{\partial \mathbf{\omega}}{\partial t} + (\mathbf{u} \cdot \mathbf{\nabla}) \mathbf{\omega} = (\mathbf{\omega} \cdot \mathbf{\nabla}) \mathbf{u}  \qquad , \qquad
 \dfrac{D \mathbf{\omega}}{D t} = (\mathbf{\omega} \cdot \mathbf{\nabla}) \mathbf{u} ,$$

dove è stata messa in evidenza la derivata materiale della vorticità,
che rappresenta la variazione della vorticità di una particella fluida,
che si muove con la velocità del fluido. Se si considera un problema in
cui un corpo aerodinamico è investito da una corrente che è uniforme
all'infinito a monte, la vorticità all'infinito a monte è nulla: si può
dimostrare facilmente allora che $D\mathbf{\omega} / D t = \mathbf{0}$, e quindi
la vorticità si mantiene costante e nulla, sulle linee di corrente che
partono dall'infinito a monte[^1]. Per correnti ad alto numero di
Reynolds attorno a corpi affusolati, nelle quali non si verificano
separazioni, gli effetti viscosi e la vorticità sono confinati in strati
limite "sottili" attorno ai corpi solidi e in scie "sottili" che si
staccano da essi.

É quindi possibile descrivere una corrente di un fluido incomprimibile
ad alto numero di Reynolds, all'*esterno* di queste sottili regioni
vorticose, con un modello di fluido non viscoso. Partendo dalle
equazioni di Navier--Stokes che governano la dinamica di un fluido
viscoso, per le quali vale la condizione al contorno di adesione a
parete ($\mathbf{u} = \mathbf{b}$), si arriva a un modello che permette di
calcolare il campo di velocità dal potenziale cinetico, che soddisfa
l'equazione di Laplace $\Delta \phi = 0$ nel dominio e la condizione al
contorno di non penetrazione
($\mathbf{u} \cdot \mathbf{\hat{n}} = \mathbf{b} \cdot \mathbf{\hat{n}}$) in
corrispondenza delle pareti solide, e in seguito di calcolare la
pressione utilizzando il teorema di Bernoulli. 

$$\begin{cases}
  \frac{\partial \mathbf{u}}{\partial t} + (\mathbf{u} \cdot \mathbf{\nabla}) \mathbf{u} - \nu \Delta \mathbf{u} + \mathbf{\nabla}P = \mathbf{g} \\
  \mathbf{\nabla} \cdot \mathbf{u} = 0 \\
  \mathbf{u}\big|_{wall} = \mathbf{b}  \qquad + \textit{altre b.c}
 \end{cases}
 \xrightarrow[{\small \begin{aligned} \nu = 0 , & \ \omega = \mathbf{0} \\ \mathbf{u} & = \mathbf{\nabla}\phi \end{aligned} }]{}
  \begin{cases}
  \frac{\partial \phi}{\partial t} + \frac{|\mathbf{\nabla}\phi|^2}{2} + P + \chi = C(t) \\
  \Delta \phi = 0 \\
  \frac{\partial phi}{\partial n} = \mathbf{u}\cdot\mathbf{\hat{n}} \big|_{wall} = \mathbf{b}\cdot\mathbf{\hat{n}} \qquad +  \textit{altre b.c} \\
 \end{cases}$$ 

Il problema di Laplace è lineare ed è quindi valido il
principio di sovrapposizione di cause ed effetti, se la geometria del
dominio è fissata. Questa considerazione può sembrare strana, ma è
determinata dalla possibile presenza di scie che si distaccano dai corpi
solidi e che possono evolvere (per problemi non stazionari) all'interno
del dominio. L'equazione di Lapalce può rappresentare anche problemi non
stazionari, nonostante non compaia esplicitamente nessuna derivata
temporale nell'equazione. La dipendenza temporale può comparire
all'interno delle condizioni al contorno e la soluzione si adatta
immediatamente ad esse. Memoria della soluzione agli istanti di tempo
precendenti è contenuta all'interno delle scie, la cui vorticità è
legata al valore di circolazione attorno al corpo (e quindi di portanza)
e la cui dinamica è determinata dalle equazioni di governo della
vorticità.

[^1]: É immediato convincersi del fatto, utilizzando la descrizione
    lagrangiana
    ([\[eqn:bilanci:vorticitàLagrange\]](#eqn:bilanci:vorticitàLagrange){reference-type="ref"
    reference="eqn:bilanci:vorticitàLagrange"}) della vorticità per un
    fluido non viscoso.
