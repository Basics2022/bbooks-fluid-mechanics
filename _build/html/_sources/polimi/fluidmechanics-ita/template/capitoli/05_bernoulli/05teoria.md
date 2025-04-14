(fluid-mechanics:bernoulli)=
# Bernoulli theorems and vorticity dynamics

Per fluidi incomprimibili o barotropici (per i quali la pressione è
funzione solo della densità), il teorema di Bernoulli si ottiene dal
bilancio della quantità di moto. Si elencano qui tre forme del teorema
di Bernoulli, ognuna caratterizzata da diverse ipotesi. Tramite
l'identità vettoriale

$$\mathbf{\nabla} (\mathbf{a} \cdot \mathbf{b}) = (\mathbf{a} \cdot \mathbf{\nabla}) \mathbf{b} +  (\mathbf{b} \cdot \mathbf{\nabla}) \mathbf{a} + \mathbf{a} \times (\mathbf{\nabla} \times \mathbf{b}) + \mathbf{b} \times (\mathbf{\nabla} \times \mathbf{a}),$$

applicata al termine convettivo $(\mathbf{u} \cdot \mathbf{\nabla}) \mathbf{u}$, è
possible ottenere la forma del Crocco dell'equazione della quantità di
moto

$$\label{eqn:bilanci:crocco}
\begin{aligned}
 & \dfrac{\partial \mathbf{u}}{\partial t} + (\mathbf{u} \cdot \mathbf{\nabla}) \mathbf{u} - \nu \Delta \mathbf{u} + \mathbf{\nabla} P = \mathbf{g}  & \\ &  &  \bigg( (\mathbf{u} \cdot \mathbf{\nabla})\mathbf{u} = \mathbf{\nabla} \frac{\mathbf{u} \cdot \mathbf{u}}{2} + (\mathbf{\nabla} \times \mathbf{u}) \times \mathbf{u} \bigg) \\
 & \rightarrow \dfrac{\partial \mathbf{u}}{\partial t} + \mathbf{\nabla} \frac{|\mathbf{u}|^2}{2} + \mathbf{\omega} \times \mathbf{u} - \nu \Delta \mathbf{u} + \mathbf{\nabla} P = \mathbf{g} , & \\
\end{aligned}$$

avendo indicato con $P$ il potenziale termodinamico,
$P =$ che si riduce al rapporto $p/\rho$ nel caso di densità costante e
con $\mathbf{g}$ le forze per unità di massa.

#### Prima forma del teorema di Bernoulli

Nel caso di fluido non viscoso, incomprimibile o barotropico, in regime
stazionario ($\partial / \partial t \equiv 0$), con forze di massa
conservative $\mathbf{g} = -\mathbf{\nabla} \chi$, il trinomio di Bernoulli
$|\mathbf{u}|^2/2 + P + \chi$ è costante lungo le linee di corrente e le
linee vorticose, cioè

$$\mathbf{\hat{t}} \cdot \mathbf{\nabla} \left( \frac{|\mathbf{u}|^2}{2} + P + \chi \right) = 0 ,$$

con $\mathbf{\hat{t}}$ versore tangente alle linee di corrente o alle linee
vorticose. Infatti, il termine $\mathbf{\omega} \times \mathbf{u}$
nell'equazione della quantità di moto nella forma di Crocco
([\[eqn:bilanci:crocco\]](#eqn:bilanci:crocco){reference-type="ref"
reference="eqn:bilanci:crocco"}) è perpendicolare in ogni punto del
dominio alle linee di corrente ($\mathbf{\hat{t}}$ parallelo al campo di
velocità $\mathbf{u}$) e alle linee vorticose ($\mathbf{\hat{t}}$ parallelo al
campo di vorticità $\mathbf{\omega}$): moltiplicando scalarmente l'equazione
([\[eqn:bilanci:crocco\]](#eqn:bilanci:crocco){reference-type="ref"
reference="eqn:bilanci:crocco"}) scritta per un fluido non viscoso
($\nu = 0$) per il versore $\mathbf{\hat{t}}$ , il prodotto scalare
$\mathbf{\hat{t}} \cdot (\mathbf{\omega} \times \mathbf{u})$ è identicamente nullo.

#### Seconda forma del teorema di Bernoulli

Nella corrente irrotazionale ($\mathbf{\omega} = \mathbf{0}$) di un fluido non
viscoso, incomprimibile o barotropico, in regime stazionario, con forze
di massa conservative $\mathbf{g} = -\mathbf{\nabla} \chi$, il trinomio di
Bernoulli $|\mathbf{u}|^2/2 + P + \chi$ è costante in tutto il dominio, cioè

$$\mathbf{\nabla} \left( \frac{|\mathbf{u}|^2}{2} + P + \chi \right) = 0  \quad \rightarrow \quad 
  \frac{|\mathbf{\nabla} \phi|^2}{2} + P + \chi = C.$$

#### Terza forma del teorema di Bernoulli

Nella corrente irrotazionale ($\mathbf{\omega} = \mathbf{0}$) di un fluido non
viscoso, incomprimibile o barotropico, in un dominio semplicemente
connesso (nel quale è quindi possibile definire il potenziale cinetico
$\phi$, t.c. $\mathbf{u} = \nabla \phi$, con forze di massa conservative
$\mathbf{g} = -\mathbf{\nabla} \chi$, il quadrinomio di Bernoulli
$\partial \phi / \partial t + |\mathbf{u}|^2/2 + P + \chi$ è uniforme
(costante in spazio, in generale **non** in tempo) in tutto il dominio,
cioè

$$ \left(\mathbf{\nabla}\dfrac{\partial \mathbf{u}}{\partial t}  + \frac{|\mathbf{\nabla} \phi|^2}{2} + P + \chi \right) = 0  \quad \rightarrow \quad 
 \dfrac{\partial \mathbf{u}}{\partial t}  + \frac{|\mathbf{\nabla} \phi|^2}{2} + P + \chi = C(t).$$

#### Teoremi di Bernoulli per fluidi viscosi incomprimibili

Mentre la prima forma del teorema di Bernoulli non è valida se non viene
fatta l'ipotesi di fluido non viscoso[^1], la seconda e la terza forma
sono ancora valide per fluidi viscosi incomprimibili. Infatti, usando
l'identità vettoriale

$$\Delta \mathbf{u} = \mathbf{\nabla} (\mathbf{\nabla}\cdot \mathbf{u})
  - \mathbf{\nabla} \times (\mathbf{\nabla} \times \mathbf{u}) ,$$

  si scopre che il
laplaciano del campo di velocità per correnti irrotazionali
($\mathbf{\nabla} \times \mathbf{u} = \mathbf{0}$) di fluidi incomprimibili
($\mathbf{\nabla} \cdot \mathbf{u} = 0$) è nullo.

L'ipotesi di fluido non viscoso non è direttamente necessaria per la
seconda e la terza forma del teorema di Bernoulli, ma lo diventa tramite
l'ipotesi di corrente irrotazionale. Sotto opportune ipotesi sulla
corrente asintotica, verificate in molti casi di interesse aeronautico,
si dimostra che (quasi) tutto il campo di moto è irrotazionale solo se
viene fatta l'ipotesi di fluido non viscoso. Questo modello viene
utilizzato per studiare correnti di interesse aeronautico, nelle quali
gli effetti della viscosità sono (quasi ovunque) trascurabili: un
esempio è la corrente, uniforme a monte, che investe un corpo
aerodinamico a bassi angoli di incidenza (corpo affusolato, attorno al
quale non si verifichino separazioni) per alti numeri di Reynolds: in
queste correnti, le zone vorticose sono confinate in regioni di spessore
sottile (strato limite sulla superficie dei corpi solidi e scie libere).

[^1]: Moltiplicando scalarmente l'equazione
    ([\[eqn:bilanci:crocco\]](#eqn:bilanci:crocco){reference-type="ref"
    reference="eqn:bilanci:crocco"}) per il versore $\mathbf{\hat{t}}$, il
    termine $\mathbf{\hat{t}}\cdot \nu \Delta \mathbf{u}$ non si annulla. Rimane
    quindi

    $$\mathbf{\hat{t}} \cdot \mathbf{\nabla} \left( \frac{|\mathbf{u}|^2}{2} + P + \chi \right) - \nu \mathbf{\hat{t}} \cdot \Delta \mathbf{u} = 0$$
