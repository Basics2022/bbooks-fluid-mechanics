(fluid-mechanics:aerodynamics)=
# Incompressible Aerodynamics

**todo** *Update the introduction*

In many situations in aeronautics, the flow of interest can be modelled as irrotational in the whole domain, except for very thin regions where vorticity and viscous effects are lumped. This is the case of **high-$\text{Re}$** flows, with uniform free-stream velocity (so that incoming vorticity is zero), around **streamlined bodies** with small angles between their "longitudinal" direction and the free-stream velocity: if all these conditions are met, it's likely no large separation and recirculation regions occur and the vorticity and viscosity effects are only relevant in the thin **boundary layer** at the solid surface of the body and in thin **wakes** shed downstream[^thin-bl-high-Re].

Under these circumstances, the governing equations can be recast as **Poisson problems** for the kinetic potential $\phi(\mathbf{r})$, or for the vector potential $\boldsymbol\psi(\mathbf{r})$. Being the problem *linear* - for a wake with given shape - *principle of superposition of causes and effects* holds: the solution of the problem can be written as the linear combination of - usually simpler - solutions of the problem. This strategy naturally arises solving the Poisson problem with Green's function method, that produces a boundary problem and whose solution is the superposition of distributions of *sources*, *doublets*, and *vortices*. These solutions are simple, but *singular*, requiring the need of some caution and some introduction and discussion of their properties, before using them into problems in aerodynamics.

Poisson problems for $\phi(\mathbf{r})$, and $\boldsymbol\psi(\mathbf{r})$ are somehow dual, if jumps in these potential fields are allowed. The problem can be approached without the need for jumps in potentials, by exploiting Helmholtz's decomposition of the velocity field $\mathbf{u} = \nabla \phi + \nabla \times \boldsymbol\psi$ and solving two Poisson equations supplemented with proper boundary conditions and regularity conditions.

[^thin-bl-high-Re]: As an example, the relation between thickness of boundary layer flows and Reynolds number in this book is shown with [Prandtl equations for the laminar boundary layer](), $\delta(x) \sim x \text{Re}_x^{-\frac{1}{2}}$, **todo** *add examples with turbulent flows*.

[**Theorems.**](fluid-mechanics:aerodynamics:vortex-theorems) Kelvin's theorem and Helmholtz's theorems.

[**Singularities.**](fluid-mechanics:aerodynamics:singularities) Introduction of source, doublet and vortex sngularities as solution of Poisson eqautions, and discussion of their properties.

[**Steady aerodynamics.**](fluid-mechanics:aerodynamics:steady)

**Unsteady aerodynamics.**

- *Deal with equations, wakes and shape and connection of the domain*
- *2-dimensional vs. 3-dimensional flows*
- *Thin airfoil and wing theory*

---

```{dropdown} **Old introduction**

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
partono dall'infinito a monte[^free-stream-vorticity]. Per correnti ad alto numero di
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

[^free-stream-vorticity]: É immediato convincersi del fatto, utilizzando la descrizione lagrangiana {eq}`eqn:bilanci:vorticitàLagrange` della vorticità per un fluido non viscoso.

```
