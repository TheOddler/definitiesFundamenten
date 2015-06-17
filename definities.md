---
title: definities fundamenten
---

# inleiding

# achtergrond

# Talen, automaten en berekenbaarheid

## strings en talen

### strings 

alfabet
:	een alfabet is een niet-lege eindige verzameling. De elementen van de verzameling worden symbolen genoemd.

string
:	Een string s over een alfabet $\Sigma$ is een eindige rij symbolen uit $\Sigma$. Het aantal symbolen in een string is de lengte van de string, genoteerd met $|s|$.De string met lengte nul wordt de lege string genoemd en wordt genoteerd met $\lambda$. De verzameling van alle strings over een alfabet $\Sigma$ wordt genoteerd met $\Sigma^*$.

### talen

taal
:	een taal over een alfabet $\Sigma$ is een verzameling strings over $\Sigma$, anders gezegd: een taal over $\Sigma$ is een deelverzameling van $\Sigma^*$

### reguliere talen

reguliere taal
:	indien $\Sigma$ een alfabet is, dan wordt de klasse R van alle reguliere talen over $\Sigma$ inductief als volgt gedefinieert:
- $\emptyset \in R, \{\lambda\} \in R$ en $\forall \sigma \in \Sigma: {\sigma} \in R$
- indien $A,B \in R$, dan ook $AB \in R$ en $A^* \in R$.
- Elke taal uit R wordt ook een reguliere taal genoemd.

### reguliere uitdrukkingen

reguliere uitdrukking
:	indien $\Sigma$ een alfabet is, dan wordt een reguliere uitdrukking op volgende wijze inductief gedefieerd:
- $\emptyset$ is een regeliere uitdrukking
- $\lambda$ is een reguliere uitdrukking
- voor elke $\sigma \in \Sigma$ is $\sigma$ een reguliere uitdrukking
- indien A en B reguliere uitdrukkingen zijn, dan zijn ook $(A), A^*, A|B en AB$ reguliere uitdrukkingen

## eindige automaten

### eindige automaten

eindige automaat
:	Een eindige automaat is een vijftal $A=(Q, \Sigma, \delta, q_0, F)$ met
- Q een eindige verzameling, we noemen de elementen van Q de toestanden van de automaat A.
- $F \subseteq Q$ is de verzameling van de aanvaardbare eindtoestanden.
- $q_0 \in Q$ deze toestand wordt de begintoestand genoemd
- $\Sigma$ een alfabet
- $\delta$ een afbeelding, de transitieafbeelding genoemd.  

### Eindige automaten en reguliere talen

taal bepaald door eindige automaat
:	als $A=(Q, \Sigma, \delta, q_0, F)$ een eindige automaat is, noemen we $$L(A)=\{x \in \Sigma^* | \delta^*(q_0,x) \in F\}$$ de taal bepaald door de eindige automaat. Voor een gegeven taal $L\subseteq \Sigma^*$ zeggen we dat A de taal herkent als $L=L(A)$.

### Niet-deterministische automaten

niet-deterministische, eindige automaat
:	Een niet-deterministische eindige automaat is een vijftal $A=9Q,\Sigma, \delta, q_0, F)$ met
- Q een eindige verzameling (de toestanden van de automaat A)
- $F \subseteq Q$ de verzameling van aanvaarde eindtoestanden
- $q_0$ de begintoestand van de automaat
- $\Sigma$ het alfabet van de automaat
- $\delta$ een afbeelding $\delta: Q\times(\Sigma \cup \{\lambda \})\rightarrow P(Q)$

taal bepaald door niet-deterministische eindige automaat
:	als $A=(Q, \Sigma, \delta, q_0, F)$ een niet-deterministische eindige automaat is, noemen we $$L(A)=\{x \in \Sigma^* | \delta^*(q_0,x)\cap F \neq \emptyset \}$$ de taal bepaald door de eindige automaat. Voor een gegeven taal $L\subseteq \Sigma^*$ zeggen we dat A de taal herkent als $L=L(A)$.

## Turingmachines

### Turingmachines

Turingmachine
:	een turingmachine is een zestal $M = (Q, \Sigma, T, P, q_0, F)$ met
- Q een eindige verzameling, we noemen de elementen van Q toestanden.
- $F \subset Q$ de verzameling van aanvaardbare eindtoestanden
- $q_0 \in Q$ de begintoestand
- $\Sigma$ het alfabet van de turingmachine. Dit alfabet bevat naast andere symbolen minstens een speciaal symbool: het blanco of lege symbool, genoteerd met #.
- $T \subseteq \Sigma \backslash \{\#\}$ is de verzameling invoersymbolen. De elementen van $\Sigma\backslash(T \cup \{\#\})$ worden hulpsymbolen genoemd.
- P een functie $P: (Q\backslash F)\times \Sigma \rightarrow Q \times \Sigma \times \{L,R,0\}$. P wordt het programma of de instructieset van de turingmachine genoemd. (in de verzameling {L,R,0} staat L voor links, R voor rechts en 0 voor blijf staan, waarmee de beweging van de schrijfkop wordt aangegeven.)

### Turingmachines en functies

### Turingmachines en talen

taal bepaald door een turingmachine
:	De taal bepaald door een turingmachine M, genoteerd $L(M)$, is de verzameling van alle invoerstrings waarvoor M in een aanvaardbare toestand eindigt. Gegeven een taal L zeggen we dat L herkend wordt door M als $L=L(M)$

turing-herkenbaar
:	Een taal L wordt turing-herkenbaar genoemd als er een turingmachine is die L herkent. Turing-herkenbare talen worden ook recursief opsombare talen genoemd.

beslissen van een taal
:	Een turingmachine beslist een taal als voor elke string $s \in L$ de turingmachine stopt in een aanvaardbare toestand, en voor elke string $s \notin L$ de turingmachine stopt in een onaanvaardbare toestand.

turingbeslisbaar
:	Een taal wordt turing-beslisbaar, of kortweg beslisbaar genoemd als er een turingmachine bestaat die L beslist. Turing-beslisbare talen worden ook wel recursieve talen genoemd.

### Niet-deterministische turing-machines

niet-determinisische turingmachine
:	Een niet-deterministische turingmachine M bestaat uit een zestal $M = (Q, \Sigma, T, P, q_0, F)$ dat aan dezelfde voorwaardes voldoet als die voor een deterministische turingmachine, alleen moet P geen functie meer zijn. P is een relatie tussen $(q \backslash F) \times \Sigma$ en $Q \times \Sigma \times \{L, R, 0\}$

## analyse van algoritmen

### tijdscomplexiteit van algoritmen

tijdscomplexiteit
:	de tijdscomplexiteit van een bepaald algoritme A is een functie $tijd_A(n):  \mathbb{N} \rightarrow  \mathbb{N}$ die voor een gegeven invoeromvang $n$ het maximum aantal elementaire bewerkingen aangeeft die door het algoritme A bij een invoer van grootte n zullen worden uitgevoerd.

de O-notatie
:	indien $f$ en $g$ functies zijn van $mathbb{N}$ naar $\mathbb{R}^+$, dan zeggen we $f(n)$ is $O(g(n))$ of $f$ is $O(g)$ als $$\exists c \in \mathbb{R}_0^+, \exists N \in \mathbb{N}, \forall n \in \mathbb{N}: n \geq N \Rightarrow f(n) \leq c g(n)$$

### het bepalen van complexiteit in enkele voorbeelden

## complexiteitsklassen van beslissingsproblemen

### de klassen P en NP

#### turingmachines en de klasse P

polynomiale beslisbaarheid
:	een taal L wordt in polynomiale tijd beslist door een turingmachine M indien er een $k \in \mathbb{N}$ bestaat zodat M voor elke invoersstring s beslist of $s \in L$ in een aantal stappen dat $O(n^k)$ is met $n = |s|$. Een taal is polynomiaal beslisbaar als er een turingmachine bestaat die de taal in polynomiale tijd beslist

de klasse P
:	men duidt met P de klasse aan van alle talen waarvoor geldt dat er een turingmachine bestaat die die taal in polynomiale tijd beslist.

#### Niet-deterministische turingmachines en de klasse NP

tijdscomplexiteit van een niet-deterministische turing-machine
:	de tijdscomplexiteit $tijd_M: \mathbb{N} \rightarrow \mathbb{R}^+$ voor een NDTM wordt gedefinieerd als 
$$tijd_M = \begin{cases}
0 indien er geen enkele string van lengte n wordt aanvaard\\
max \{m | er bestaat een string x \in T^*, van lengte n die in m stappen aanvaard wordt door M.\}
\end{cases}$$

NDTM van polynomiale tijd
:	een niet-deterministische Turingmachine M heet van polynomiale tijd te zij als en slechts als $tijd_m(n) O(n^k)$ is, voor een $k\in \mathbb{N}$.

niet-deterministisch polynomiaal herkenbaar
:	een taal L wordt herkend in polynomiale tijd door een NDTM indien M L herkent en M van polynomiale tijd is. een taal L is niet-deterministisch polynomiaal herkenbaar als er een NDTM bestaat die L herkent in polynomiale tijd.

de klasse NP
:	Men duidt met NP de klasse aan van alle talen die beslisbaar en niet-deterministisch polynomiaal herkenbaar zijn.

#### Polynomiale verifieerbaarheid

polynomiaal verifieerbaar
:	een taal L is polynomiaal verifieerbaar als en slechts als er een TM bestaat zodat voor elke string s een andere string c, een zogenaamd certificaat, bestaat zodat geldt: M aanvaardt de string (c,s) in een tijd polynomiaal is |s| als en slechts als $s \in L$.

de klasse NP (alternatieve definitie)
:	Men duidt met NP de klasse aan van polynomiaal verifieerbare talen.

### De klasse NP-compleet

polynomiale transformatie van een taal
:	Zij gegeven twee talen $L_1 \subseteq T_1^*$ (op een alfabet $T_1$)en $L2 \subseteq T_2^*$ (op een alfabet T2). We zeggen dat $l_1$ polynomiaal transformeerbaar is in $l_2$ indien er een afbeelding $f: T_1^* \rightarrow T_2^*$ bestaat waarvoor de volgende twee zaken gelden
- $\forall x \in T_1^*: x\in L_1 \Leftrightarrow f(x) \in L_2$
- Er bestaat een deterministische turing-machine die $f$ in polynomiale tijd berekent.

polynomiale equivalentie van talen
:	twee talen $L_1$ en $L_2$ worden polynomiaal equivalent genoemd, notatie $L_1 \sim L_2$ indien $L_1 \alpha L_2$ en $L_2 \alpha L_1$.

de klasse NPC
:	een taal $L$ is NP-compleet als en slechts als 
- $L \in NP$
- voor elke andere taal $L' \in NP$ geldt dat $L' \alpha L$. 

### andere complexiteitsklassen

## besluit

# grafentheorie

## inleiding

### de kortste weg tussen twee adressen

### de bruggen van Koningsberg

### de boer, de wolf, de kool en de geit

### Vier op een rij

## Grafen

### basisdefinities

graaf
:	een graaf is een drietal $(V, E, \phi)$ met V een verzameling waarvan de elementen knopen genoemd worden; E een verzameling waarvan de elementen bogen genoemd wordenen $\phi: E \rightarrow M_2(V)$ een functie die met elke boog twee knopen associeert. 

lus
:	een lus is een boog $e$ waarvoor geldt dat er een $v \in V$ bestaat zodat $\phi(e)=(v,v)$. Met andere woorden een boog die een knoop met zichzelf verbind.

parallelle bogen
:	in een graaf $G(V, E, \phi)$ noemen ze de bogen $e_1$ en $e_2$ parallelle bogen als en slechts als $\phi(e_1)=\phi(e_2)$. Met andere woorden twee bogen zijn parallel als ze dezelfde knopen met elkaar verbinden.

enkelvoudige graaf
:	een enkelvoudige graaf is een graaf die noch lussen noch bogen bevat. 

graaf(vereenvoudigd)
:	een graaf is een koppel $(V, E)$ met V een verzameling knopen en E een multiverzameling multiparen uit V.

graad
:	de graad van een knoop v, genoteerd $\delta(v)$ is het aantal bogen dat op v invalt. Een lus telt hierbij voor twee.

### paden

pad
:	Een pad in een graaf $G(V,E)$ is een rij bogen van de vorm $(V_0, v_1), (v_1, v_2), ..., (v_{n-1}v_n)$ waarbij $\forall i: (v_i, v_{i+1}) \in E$

enkelvoudig pad
:	een enkelvoudig pad is een pad $(v_0, v_1, ..., v_n)$ waarvan alle knopen verschillend zijn, dit wil zeggen : $\forall i,j: i \neq j \Rightarrow v_i \neq v_j$.

kring, enkelvoudige kring
:	Een kring is een pad $(V_0, v_1), (v_1, v_2), ..., (v_{n-1}v_n)$ waarin alle bogen verschillend zijn, en waarin $v_0 = v_n$. Een enkelvoudige kring is een kring waarin ook alle knopen verschillend zijn, afgezien van $v_0 = v_n$.

samenhangende graaf
:	een graaf is samenhangend als en slechts als tussen elke twee knopen een pad bestaat.

Hamiltoniaans pad, hamiltoniaanse kring
:	Zij gegeven een graaf G. Een hamiltoniaans pad van G is een pad waarin elke knoop van G precies een keer voorkomt. Een hamiltoniaanse kring van G is een enkelvoudige kring waarin elke knoop van G voorkomt.

Euleriaans pad, euleriaanse kring
:	Zij gegeven een graaf G. Een euleriaans pad is een pad waarin elke knoop van G minstens 1 keer voorkomt en elke boog van G precies 1 keer voorkomt. Een euleriaanse kring van G is een Euleriaans pad dat ook een kring is.

### deelgrafen en componenten

deelgraaf
:	een graaf $G'(V', E')$ is een deelgraaf van een graaf $G(V,E)$ genoteerd $G' \subseteq G$ als en slechts als $V' \subseteq V$ en $E' \subseteq E$.

geinduceerde deelgraaf
:	gegeven een graaf $G(V,E)$ en een deelverzameling $V' \subseteq V$ noemen we $G'(V', E')$ de deelgraaf van G geinduceerd door V' als en slechts als $E' = \{(v,w)\in E|(v,w) \in V'\}$

component
:	een graaf $G(v,E)$ is een component van een graaf $G'(V',E')$ als en slechts als $G \subset G', G$ is niet leeg, G is samenhangend, en er bestaat geen samenhangende graaf $G"$ waarvoor $G\subset G"\subseteq G'$

### Gerichte grafen

gerichte graaf
:	een gerichte graaf is een koppel (V,E) met V een verzameling waarvan de elementen knopen genoemd worden en $E\subseteq V^2$ een verzameling koppels

gericht pad, ongericht pad
:	een gericht pad in een gerichte graaf $G(V,E)$ is een pad $(v_0, v_1, ..., v_n)$ met $\forall i: (v_i, v_{i+1}) \in E$. Een ongericht pad is een pad $(v_0, v_1, ..., v_n)$ met $\forall i: (v_i, v_{i+1}) \in V \vee (v_{i+1}, v_i) \in E$

## voorstelling van grafen

### buurmatrix

buurmatrix
:	Gegeven een enkelvoudige graaf $G(V,E)$, met $V = \{v_1, v_2, ..., v_n\}$ is de buurmatrix van $G$ een $n\times n$ matrix $A$ met $A_{ij} = 1 \Leftrightarrow (v_i, v_j)\in E$, en $A_{ij}=0 \Leftrightarrow (v_i, v_j) \notin E$

### booleaanse buurmatrix

booleaanse buurmatrix
:	Gegeven een enkelvoudige graaf $G(V,E)$ met $V=\{v_1, v_2, ..., v_n\}$ is de booleaanse buurmatrix van $G$ een $n\times n$ matrix $B$ met $B_{ij} = ((v_i, v_j) \in E)$

### incidentiematrix

incidentiematrix
:	gegeven een enkelvoudige graaf $G(V,E)$ met $V=\{v_1, v_2, ..., v_n\}$ en $E=\{e_1, e_2, e_n\}$ is de incidentiematrix van $G$ een $n\times m$ matrix $A$ met $A_{ij} =1$ als $e_j$ invalt op $v_i$ en $A_{ij}=0$ in alle andere gevallen.

## isomorfisme van grafen 

grafen-isomorfisme
:	Twee grafen $G(V, E)$ en $G'(V', E')$ zijn isomorf als en slechts als er een bijectie $h: V\rightarrow V'$ bestaat zodat $\{h(x)|x \in V\} = V'$ en $\{h(x), h(y)|(x,y)\in E\}=E'$

## gewogen grafen

### kortste pad algoritme van Dijkstra

### Dijkstra, versie 1

### dijkstra versie 2

### complexiteit van Dijkstra's algoritme

## bijzondere klassen van grafen

## vlakke grafen

vlakke graaf
:	een vlakke graaf is een graaf die getekend kan worden zonder snijdende bogen

### de formule van Euler

### karakterisatie van vlakke grafen

$(\beta, B)$
:	Gegeven een vlakke graaf G noteren we het aantal bogen waardoor een zijvlak z begrensd wordt als $\beta(z)$. De som van $\beta(z)$ voor alle zijvlakken $Z$ wordt $B$ genoteerd. $B = \Sigma_{z \in Z} \beta(z)$, met Z de verzameling zijvlakken van de graaf.

### duale grafen

duale graaf
:	Zij G een graaf met $v$ knopen, $e$ knopen en $f$ zijvlakken. De duale graaf $G'$ heeft 1 knoop voor elk zijvlak van $G$, dus $v' = f$ knopen. Voor elke boog tussen de oorspronkelijke zijvlakken is er een boog tussen de overeenkomstige knopen in de duale graaf.

## kleuring van grafen

kleuring
:	Met een kleuring van een graaf $(V, E)$ bedoelt men een toekenning van een kleur aan elke $v \in V$ zodanig dat de kleur van $v$ naar $w$ verschilt indine $(v,W) \in E$. een n-kleuring is een kleuring met $n$ of minder verschillende kleuren. Een minimale kleuring is een n-kleuring met minimale $n$.

## bomen

### opspannende bomen

opspannende boom
:	$T(V_T, E_T)$ is een opspannende boom voor $G(V,E)$ als en slechts als $T$ een boom is, $V_T = V$ en $E_T \subseteq E$

### minimaal opspannende bomen

minimaal opspannende boom
:	een minimaal opspannende boom van een gewogen graaf $G$ is een opspannende boom van $G$ waarvoor geldt dat er geen andere opspannende boom is met een kleiner gewicht.

## gewortelde bomen

gewortelde boom
:	een gewortelde boom is een boom waarin een willekeurige knoop wordt aangeduid als de wortel

### binaire bomen

### zoekbomen

binaire zoekboom
:	een binaire zoekboom is een binaire boom waarin met elke knoop $v$ een waarde $w(v)$ is geassocieerd (bv. een getal) zodanig dat als $l$ behoort tot de linker en $r$ tot de rechterdeelboom van $v$, dat dan $w(l)< w(v) < w(r)$

### Praktische voorstelling van bomen

#### Voorstelling van gewortelde bomen in computerprogramma's

### Het doorlopen van gewortelde bomen

#### Het volledig doorlopen van een gewortelde boom

#### Diepte-eerst en breedte-eerst doorlopen

### Spelbomen

## Netwerkmodellen en petri-netten

### Transportmodel

transportnetwerk
:	een transportnetwerk(of simpelweg een netwerk) is een enkelvoudige gewogen, gerichte graaf die voldoet aan:
- er is juist één knoop in G zonder binnenkomende bogen, deze knoop wordt de bron genoemd.
- er is juist één knoop in G zonder buitengaande bogen, deze knoop wordt de put genoemd.
- het gewicht $c_{i,j}$ van de gerichte boog $(i,j)$ is positief en wordt de capaciteit van de boog genoemd.
- G is samenhangend.

stroming
:	Voor een netwerk $G(V,E)$ met capaciteiten $C_{i,j}, i,j \in V$ is F een stroming als F een afbeelding is van E naar $\mathbb{R}^+$ zodanig dat
- $F(i,j) \leq c_{i,j}$
- voor elke knoop $j$die niet de bron of de put is geldt $\sum\limits_{i \in V} {F(i,j)} = \sum\limits_{i \in V} {j, i}$.

	We noemen $F(i,j)$ de stroming in een boog $(i,j)$. Voor een knoop $j$ noemen we $\sum\limits_{i \in v} {F(i,j)}$ de stroming naar of in $j$ en $\sum\limits_{i \in v} {F(j,i)}$ de stroming van of uit $j$.

grootte van een stroming
:	de grootte van een stroming F in een netwerk $G(V,E)$ met bron $a$ en put $z$ is gedefinieerd door $\sum\limits_{i \in V} F(a,i)$ of $\sum\limits_{i \in V} F(i, z)$

### Maximale stroming

goede/slechte boog
:	in een gerichte graaf $G(V,E)$ met met pad $(v_1, v_2, ..., v_n)$ noemen we een boog $(v_i, v_{i+1})$ goed (gericht) indien $(v_i, v_{i+1}) \in E$ en anders slecht gericht.

snede
:	een snsede van een netwerk $G(V,E)$ met bron $a$ en put $z$is een tweetal $(P, \bar{P})$ zodanig dat $a \in P, z \in \bar{P}, P\cup \bar{P} = V$ en $P\cap \bar{P} = \emptyset$

capaciteit van een snede
:	de capaciteit van een snede $(p, \bar{P})$ is $C(P, \bar{P}) = \sum\limits_{i\in P} {\sum\limits_{j \in \bar{P}} {C_{(i,j)}}}$.

Max flow, min cut
:	Voor een snede$(P, \bar{P})$ en stroming $F$ in een net $G(V,E)$ geldt dat als $C(P, \bar{P}) = F$, dan is de stroming maximaal en de snede minimaal. 

### Matching

matching
:	Voor een gerichte tweeledige graaf $G(V\cup W, E)$ waarbij $V\cap W = \emptyset$ en $E \subseteq V\times W$ is $M$ een overeenkomst of matching indien
- $M \subseteq E$
- $\forall(x,y), (i,j) \in M$: indien $(i,j) \neq (x,y)$ dan is $i \neq  x$ en $j \neq y$ (ttz in elke knoop komt hoogstens een boog aan en vertrekt er hoogstens een)

maximale matching
:	een maximale matching heeft een maximaal aantal bogen in M. Een matching is volledig indien $\forall v \in V, \exists w \in W: (v,w) \in M$

### Petrinetten

petrinet
:	een petrinet is een enkelvoudige gerichte graaf $G(V,E)$ waarbij $V = P\cup T, P\cap T = \emptyset$ en $E\subseteq P \times T \cup T\times P; P$ noemen we plaatsen en $T$ transities.

markering van een petrinet
:	een markering van een petrinet is een toekenning van een natuurlijk getal aan elke plaats van het petrinet.

bereikbare markering
:	een markering M' is bereikbaar vanuit een markering M indien er vertrekkend van M een salvo is dat M' als resultaat heeft.

levende markering
:	Een markering M van een petrinet is levend indien na elk salvo te beginnnen bij M er voor elke transitie t een salvo bestaat zodanig dat na dat salvo t actief wordt

begrensde markering
:	een markering M is begrensd indien er een n bestaat zodanig dat bij gelijk welk salvo geen enkele plaats ooit meer dan n tokes bevat. Een begrensde markering waarvoor $n=1$ wordt een veilige markering genoemd.

# Vastepuntstheorie

## Orderelaties

### Basisbegrippen

partiele orderelatie
:	Een relatie R op een verzameling S is een (partiele)orde(relatie) als en slechts als voldaan is aan de volgende drie voorwaarden
- R is reflexief: $\forall x \in S: xRx$
- R is antisymmetrisch: $\forall x, y \in S: xRy$ en $yRx \Rightarrow x=y$
- R is transitief: $\forall x, y, z \in S: xRy$ en $yRz \Rightarrow xRz$

boven -en ondergrens
:	zij S een verzameling met een partiele orde $leq$
- $q \in S$ is een bovengrens (of majorant) voor een deel $X\subseteq S \Leftrightarrow \forall x \in X: x \leq a$
- $b \in S$ is een ondergrens (of minorant) voor een deel $X\subseteq S \Leftrightarrow \forall x \in X: b \leq x$

sup en inf
:	zij $S, \leq$ een een geordende verzameling $X \subseteq S$
- $a \in S$ is een kleinste bovengrens van X of een supremum van X, notatie $a = sup(X)$ als en slechts als a een bovengrens is voor X en voor elke bovengrens a' vqn X geldt dat $a\leq a'$
- $b\in S$ is een grootste ondergrens van X of een infinum van X, notatie $b= inf(X)$ als en slechts als b een ondergrens is voor X en voor elke ondergrens b' van X gelt dat $b\geq b'$

complete tralie
:	Een partieel geordende verzameling $L, \leq$ is een complete tralie als sup(X) en inf(X) bestaan voor een niet-lege deelverzameling $X\subseteq L$

top-en bodemelement
:	In een complete tralie $L, \leq$ noemen we
- $\top$ = topelement = sup(L)
- $\bot$ = bodemelement = inf(L)

### Monotone en continue afbeeldingen

monotone afbeelding
:	zij $L, \leq$ een geordende verzameling. Een afbeelding $T: L \rightarrow L$ noemen we monotoon als uit $x \leq y$ volgt dat $T(x) \leq T(Y)$

gerichte verzameling
:	Beschouw een willekeurige deelverzameling X van een complete tralie $L, \leq$. X is gericht $\Leftrightarrow$ elke eindige deelverzameling van X heeft een bovengrens in X

continue afbeelding
:	een afbeelding $T: L\rightarrow L$ op een complete tralie $L, \leq$ wordt een continue afbeelding genoemd indien $T(sup(X)) = sup(T(X))$ voor elke gerichte deelverzameling X van L.$(T(X)= \{t(x)| x\in X\})$

## De stellingen van Tarski en Kleene

### de stelling van Tarski

vaste punten
:	zij $L, \leq$ een complete tralie en beschouw afbeelding $T: L\rightarrow L$
- we noemen $a \in L$ een vast punt voor T als $T(a) = a$
- een kleinste vast punt voor T is een vast punt a voor T zodat elk ander vast punt b voor T geldt dat $a \leq b$
- een grootste vast punt voor T is een vast punt a voor T zodat voor elk ander vast punt voor T geldt dat $a \geq b$

### de stelling van Kleene

### voorbeeld: de transitieve sluiting van een relatie

