## Einführung in das Quantum Computing (QC) - Notizen

### Einstiegszitat

> "Wir sind ungefähr da, wo klassische Computer in den 1950ern waren, die Theorie existiert, die Hardware steckt noch in den Kinderschuhen. Das volle Potential (z.B. Shor-Algorithmus zum Knacken von Verschlüsselungen) braucht Millionen fehlerkorrigierter Qubits" ~ Claude

- Differenzierung der bekannten Begriffe: Quantenphysik ist die Oberkategorie und schließt Quantenmechanik/-computing mit ein, wobei die Quantenmechanik die mathematische Grundlage ist. Sie beweist und beschreibt, wie Materie auf atomarer Ebene funktioniert, und liefert uns mithilfe der komplexen Zahlen jede Begründung, die für die Anwendung des Quantencomputings verwendet wird. Das Quantencomputing ist dabei die reine Ingenieurswissenschaft, welche Quantenmechanik-Phänomene (Superposition, Interferenz etc.) als Rechengrundlage verwendet. Die größte Überlappung mit meinem Interessensgebiet und Forschungsrelevanz liegt im `Quantum Chaos`. Es beschreibt das Verhalten von Systemen, deren klassisches Pendant chaotisch ist.

### Quantenbits

- Rekursive Operatoren wie Fibonacci oder Fakultät sind mathematische Konzepte, bei welchen unsere heutigen Computer an ihre Grenzen stoßen → exponentielles Wachstum
- Würde man bspw. ein ganz einfaches Problem wie die Sitzpositionsmöglichkeiten von 30 Gästen nehmen, so hat man eine hohe/exponentiell wachsende Kombinationsmöglichkeit, um ein Entscheidungskonzept (Dijkstra etc., kürzeste Wege) anzuwenden.

> Das Qubit hat vor der Messung keinen Zustand, der für uns auswertbar ist. Die Messung bringt das Qubit zum Kollabieren in einem der beiden Zustände ($0/1$)

- Ein Quantencomputer ist nicht per se schneller als ein herkömmlicher Computer, er löst algorithmische Probleme (durch die gegebene Linearität auch nicht alle) einfach mit weniger Operationen → solving `PDEs`, Encrypting und das Verhindern von Decrypting & Optimierung von Systemen (Entscheidungsmodelle / Energy Minimization, Decoded Quantum Interferometry)
- Quantencomputing ersetzt nicht einfach traditionelle Computer, sondern sollte (auch aus Kostengründen) aktuell nur für algorithmisch und numerisch komplexe Thematiken und Forschungsgebiete verwendet werden
- Die (m.E.) beste Beschreibung für den Zustand zwischen $0/1$ (`Superposition`) ist das Beispiel mit einer Kaffeebestellung: Wenn du dir unsicher bist, was du bestellen möchtest, und zwischen zwei (oder mehr, aber bleiben wir mal bei zwei) Optionen stehst, bist du in einer Art `Superposition`. Es wäre so, als würdest du eine Münze werfen, und solange sie in der Luft ist, ist nicht klar, welchen Zustand die Münze gerade hat

![Classic vs. Qubits](ressources/classic_vs_qubit.png)

- Der obere Vergleich fasst noch keine mathematische Begründung zusammen, daher:

$$
|\psi\rangle = \alpha|0\rangle + \beta|1\rangle
$$

- $\alpha$ und $\beta$ sind Amplituden und somit komplexe Zahlen, die beschreiben, wie stark die Basiszustände ($0/1$) in $\psi$ enthalten sind. Das Quadrat von $\alpha$ und $\beta$ gibt die Wahrscheinlichkeit an. Komplexe Zahlen besitzen eine Phase auf der komplexen Ebene, welche zur Interferenz führt (das Überlappen der Wellen zweier komplexer Zahlen auf der komplexen Ebene). Auf dem Konzept der `Interferenz` basiert die hohe Rechenleistung eines Quantencomputers
- Elektronenspins und Photonen zeigen das Konzept eines `Superpositionszustands`: Es gibt zwei Standardzustände (Up/Down bzw. vertikale/horizontale Polarisierung). Dabei ist der "dritte Zustand" genau das physische Konzept: Elektronenspins erhalten erst bei der Messung einen festen Wert (Wellenüberlappung), ebenso die diagonale Polarisierung von Photonen

$$
|\psi\rangle = \alpha|\uparrow\rangle + \beta|\downarrow\rangle
$$

- Diese physischen Mechanismen sind *KEINE* Analogien. QC verwendet supraleitende Schaltkreise, in welchen exakt das beschriebene Verfahren verwendet wird. Bei photonikbasierten QCs sind die Photonen reale polarisierte Lichtteilchen

![Qubit Implementation]()

*Workflow:* Wir encoden binäre Input-Daten in den Quantenalgorithmus, auf welchem Quantenoperationen erfolgen. Am Ende transformieren wir die erhaltenen Qubits, um sie wieder in normale Bits zu übersetzen (cf. "Quantum Circuit Model"). Zusammengefasst: Input – Bits, Quantenoperationen – Qubits, Output – Bits

### Mathematische Grundlage

- Vektoroperationen sollten klar sein, wird hier übersprungen
- $\Re$ und $\Im$: Bei einer komplexen Zahl $z = a + bi$ ist $\Re(z) = a$ der *Realanteil* (messbare Amplitude, Wahrscheinlichkeit) und $\Im(z) = b$ der *Imaginäranteil* (Phase, steuert Interferenz). Im QC gilt: $|a|^2 = \Re(a)^2 + \Im(a)^2$ gibt die Messwahrscheinlichkeit, während das Verhältnis von $\Re/\Im$ die Phase bestimmt, die konstruktive oder destruktive Interferenz erzeugt

#### Komplexe Zahlen

- Sind Zahlen, die als reale Zahlen geschrieben werden und mit der imaginären Einheit `i` multipliziert werden
- $i^2 = -1$ dient als Ausgangslage, da dieser Zustand mit reellen Zahlen nicht erreichbar ist
- Komplexe Zahlen beinhalten somit eine reelle Zahl und eine imaginäre Komponente: $z = a + bi$
- $\theta$ ist der `phase angle` $\angle$ und beschreibt den Winkel eines Vektors

![Hier kommt das Bild vom Winkel rein]()

- Wir haben somit zwei unterschiedliche Arten, eine komplexe Zahl in einem 2-dimensionalen Koordinatensystem darzustellen:

$$
z = a + bi = re^{i\theta}
$$

→ wichtig ist hier zu sagen, dass $a$, $b$ und $r$, $\theta$ nicht äquivalent sind

#### Eulers Form

- Um die Verbindung der beiden Formate darzustellen, brauchen wir die Eulersche Formel:

$$
e^{i\theta} = \cos(\theta) + i \cdot \sin(\theta)
$$

→ mit der Magnitude $r$ multiplizieren:

$$
re^{i\theta} = r(\cos(\theta) + i \cdot \sin(\theta)) = r\cos(\theta) + ri \cdot \sin(\theta)
$$

→ hier ist $r\cos(\theta)$ die "reelle Komponente" und $ri \cdot \sin(\theta)$ die "imaginäre Komponente"

#### Absolute Values einer komplexen Zahl

- Distanz vom Ursprungspunkt, einfach der Betrag der Polarform:

$$
z = re^{i\theta} \Rightarrow |z| = r
$$

- Um einen Vektor zu transponieren, wird folgende Notation verwendet:
- "Transpose a vector and conjugate each of its elements"
- "The conjugate transpose of a vector `a` will be denoted as $a^\dagger$"

$$
a^\dagger = (a^*)^T = (a^T)^*
$$

$$
a = \begin{bmatrix} 2i \\ 13 \\ 6 - i \end{bmatrix} \Rightarrow a^\dagger = \begin{bmatrix} -2i & 13 & 6 + i \end{bmatrix}
$$

#### Conjugate Transpose ($\dagger$, "Dagger")

- Zwei Operationen in einem: Transponieren (Spaltenvektor → Zeilenvektor) + Konjugieren (jedes $i$ wird zu $-i$)
- Notation: $a^\dagger = (a^*)^T = (a^T)^*$ (→ die Reihenfolge, in welcher wir transponieren und konjugieren, ist für das Ergebnis egal)

$$
A = \begin{bmatrix} a & b \\ c & d \end{bmatrix} \Rightarrow A^T = \begin{bmatrix} a & c \\ b & d \end{bmatrix} \Rightarrow A^\dagger = \begin{bmatrix} a^* & c^* \\ b^* & d^* \end{bmatrix}
$$

- Im QC: $|\psi\rangle$ (Ket) ist der Spaltenvektor, $\langle\psi| = |\psi\rangle^\dagger$ (Bra) ist der Zeilenvektor → `Bra-Ket-Notation`
- Wahrscheinlichkeit: $\langle\psi|\psi\rangle = |\alpha|^2 + |\beta|^2 = 1$
- Quantengatter $U$ müssen $U^\dagger U = I$ erfüllen (unitär) → sichert die Normierung des Zustands

#### Hermitische Matrix

- Eine Matrix ist hermitisch, wenn $H = H^\dagger$ (gleich ihrer eigenen Conjugate Transpose) gilt
- Hermitische Matrizen haben immer reelle Eigenwerte → Messergebnisse im QC sind immer reelle Zahlen, daher müssen Observablen hermitisch sein

#### Computational Basis State

$$
|0\rangle = \begin{bmatrix} 1 \\ 0 \end{bmatrix}
\qquad
|1\rangle = \begin{bmatrix} 0 \\ 1 \end{bmatrix}
$$

- Wenn wir die Wahrscheinlichkeit $\psi$, ob wir 1 oder 0 bekommen, betrachten, können wir anhand des 2-dimensionalen Vektors sehen, wie hoch diese ist
- $\langle\psi|$ ist der konjugiert-transponierte Vektor von $|\psi\rangle = \begin{bmatrix} \alpha \\ \beta \end{bmatrix} \Rightarrow \langle\psi| = |\psi\rangle^\dagger = \begin{bmatrix} \alpha^* & \beta^* \end{bmatrix}$

![Visualisation Graph 2D]()

- Die **globale Phase** ist einfach eine mathematische Darstellung, die wir brauchen, um Quantenzustände darzustellen. Wir können diese nicht beobachten (→ in einer Sphäre darstellen), wodurch wir sie einfach ignorieren. Sie existiert einfach und wird nicht weiter bearbeitet/verwendet
- Die **relative Phase** beeinflusst die Herleitung und die gezeigte Darstellung der Sphäre im Notebook, daher gehe ich nicht weiter darauf ein. Die **relative Phase** ist die Differenz der zwei Phasenwinkel unserer zwei Amplituden
- Wir formen die klassische Schreibweise $|\psi\rangle = \alpha|0\rangle + \beta|1\rangle$ in die Polarform ($re^{i\theta}$) um → ich überspringe hier einmal die Umformung (ist eigentlich nur eine klassische $r \cdot e^{i\theta}$-Umformung)

$$
|\psi\rangle = r_\alpha|0\rangle + r_\beta e^{i\Phi}|1\rangle
$$

> Hintergrund: $\Phi$ ist einfach eine Zusammenfassung von $\theta_\beta - \theta_\alpha = \Phi$, somit ist diese Differenz $\Delta$ hier die **relative Phase**!

- Wir haben somit 3 reale (reell & imaginär) Variablen, welche wir sehr gut im 3-dimensionalen Raum darstellen können

#### Multiple Qubits

- The first position by the first bit is on the right $|01\rangle$, in this case the `1`. The basis states are:

$$
|00\rangle = \begin{bmatrix} 1 \\ 0 \\ 0 \\ 0 \end{bmatrix}
\qquad
|01\rangle = \begin{bmatrix} 0 \\ 1 \\ 0 \\ 0 \end{bmatrix}
\qquad
|10\rangle = \begin{bmatrix} 0 \\ 0 \\ 1 \\ 0 \end{bmatrix}
\qquad
|11\rangle = \begin{bmatrix} 0 \\ 0 \\ 0 \\ 1 \end{bmatrix}
$$

#### Applied multiple qubits - Superposition of two qubits

$$
|\psi\rangle = a|00\rangle + b|01\rangle + c|10\rangle + d|11\rangle = \begin{bmatrix} a \\ b \\ c \\ d \end{bmatrix}
$$

- A uniform superposition is a superposition where all outcomes have the exact same probability
- Ein Byte kann $2^8$ Zustände besitzen (Größe eines `int`, 256 mögliche Kombinationen), wodurch wir nur einen `int` brauchen. Durch die Superposition erhalten wir neben den "normalen" Bit-Kombinationen 256 komplexe Zahlen ($a, b, c, ...$):

$$
a|00000000\rangle + b|00000001\rangle + c|00000010\rangle + \dots
$$

- Durch das Hinzufügen der komplexen Zahlen müssen wir zusätzliche Informationen abdecken, die ein einzelner `int` nicht abdecken kann. Für ein Byte bräuchte man 512 `floats`. Das Problem ist aber, dass es ein exponentielles Wachstum gibt, wodurch man bei 32 Bits (4 Bytes) knapp 8,6 Millionen Floats braucht (~34 GB)

#### Quanten-Algorithmus

- Um die unterschiedlichen Prozesse zu visualisieren, wird ein `Quantum Circuit Model` verwendet

![Quantum Circuit]()

- In dem Fall werden die 3 klassischen Bits (`meas`) nur dafür genutzt, die Ergebnisse zu speichern. Daher ist diese als Measuring Line dargestellt. Die Zeit vergeht von links nach rechts, und am Ende werden die Measurement-Elemente (die "Tacho"-Symbole) verwendet, um die Werte aus den Qubits auszuwerten
- Eine unitäre Matrix erfüllt, wenn man sie mit ihrer Conjugate Transpose multipliziert ($U^\dagger U$), dass man die Identitätsmatrix erhält:

$$
\begin{bmatrix}
1 & 0 & 0 & 0 \\
0 & 1 & 0 & 0 \\
0 & 0 & 1 & 0 \\
0 & 0 & 0 & 1
\end{bmatrix}
$$

wodurch $U^\dagger U = U U^\dagger = I$ gilt. Das bedeutet, dass wenn wir eine unitäre Matrix $U$ mit $\psi$ multiplizieren, die Magnitude des Ergebnisses äquivalent zur Magnitude von $\psi$ ist:

$$
\| U|\psi\rangle \| = \| |\psi\rangle \|
$$

### Gate logic differences

- Quantum logic gates sind `reversible`, das bedeutet, man kann eine inverse Operation auf das Qubit durchführen und erhält den ursprünglichen Zustand, bevor das Qubit durch das Gate ging

#### Pauli Gates

- Alle drei Pauli-Gates operieren auf einem einzelnen Qubit und rotieren um $\pi$ um die jeweilige Hauptachse auf der Bloch-Sphäre der drei Achsen X, Y, Z und werden als $\sigma$ beschrieben

$$
X = \sigma_x = \begin{bmatrix} 0 & 1 \\ 1 & 0 \end{bmatrix}
\qquad
Y = \sigma_y = \begin{bmatrix} 0 & -i \\ i & 0 \end{bmatrix}
\qquad
Z = \sigma_z = \begin{bmatrix} 1 & 0 \\ 0 & -1 \end{bmatrix}
$$

#### Pauli X Gate (NOT)

- Single-Qubit-Gate, welches $|0\rangle$ und $|1\rangle$ vertauscht, somit ist es einfach `NOT` → wird als Fadenkreuz dargestellt
- Als Hilfestellung kann man sich vorstellen, dass die Bloch-Sphäre um 180° gedreht wird (bzw. der Punkt, der auf der Sphäre liegt). Dadurch, dass es immer 180° sind, springen wir immer von 0 auf 1 und andersherum. Beispiel:

$$
|\psi\rangle = \alpha|0\rangle + \beta|1\rangle
\quad \xrightarrow{X} \quad
X|\psi\rangle = \alpha|1\rangle + \beta|0\rangle
$$

- Da wir nicht immer einen festen Winkel von $\theta = \pi$ haben, verwenden wir neben den Pauli-Gates auch `Rotation Gates`. Diese verwenden einen beliebigen Winkel und können kontinuierlich rotiert werden (keine Flip-Operationen wie bei Pauli):

$$
\begin{bmatrix}
\cos(\frac{\theta}{2}) & -i\sin(\frac{\theta}{2}) \\
-i\sin(\frac{\theta}{2}) & \cos(\frac{\theta}{2})
\end{bmatrix}
$$

#### Pauli Y Gate

- Rotiert um $\pi$ um die Y-Achse auf der Bloch-Sphäre. Im Vergleich zum X-Gate werden zum einen die Qubits geflippt, zum anderen wird ein Phasenfaktor von `i` hinzugefügt:

$$
Y|\psi\rangle = \begin{bmatrix} 0 & -i \\ i & 0 \end{bmatrix}
\begin{bmatrix} \alpha \\ \beta \end{bmatrix}
= \begin{bmatrix} -i\beta \\ i\alpha \end{bmatrix}
= i \begin{bmatrix} -\beta \\ \alpha \end{bmatrix}
= i(\alpha|1\rangle - \beta|0\rangle)
$$

- Für Pauli Y entspricht das `Rotation Gate`:

$$
\begin{bmatrix}
\cos(\frac{\theta}{2}) & -\sin(\frac{\theta}{2}) \\
\sin(\frac{\theta}{2}) & \cos(\frac{\theta}{2})
\end{bmatrix}
$$

#### Pauli Z Gate

- Rotiert um $\pi$ um die Z-Achse auf der Bloch-Sphäre. Im Vergleich zum X-Gate bleiben die Basiszustände erhalten, es wird lediglich die Phase von $|1\rangle$ um $\pi$ gedreht (Vorzeichenwechsel):

$$
Z|\psi\rangle = \begin{bmatrix} 1 & 0 \\ 0 & -1 \end{bmatrix}
\begin{bmatrix} \alpha \\ \beta \end{bmatrix}
= \begin{bmatrix} \alpha \\ -\beta \end{bmatrix}
= \alpha|0\rangle - \beta|1\rangle
$$

- Für Pauli Z entspricht das `Rotation Gate`:

$$
\begin{bmatrix}
e^{-i\frac{\theta}{2}} & 0 \\
0 & e^{i\frac{\theta}{2}}
\end{bmatrix}
$$

#### Hadamard Gate

- Rotiert um die Bloch-Sphäre mit dem Vektor $\begin{bmatrix} 1 \cr 0 \cr 1 \end{bmatrix}$ und ist mit einem blauen H Block dargestellt 
$$
H = \begin{bmatrix} \frac{1}{\sqrt{2}} & \frac{1}{\sqrt{2}} \cr \frac{1}{\sqrt{2}} & -\frac{1}{\sqrt{2}} \end{bmatrix} = \frac{1}{\sqrt{2}} \begin{bmatrix} 1 & 1 \cr 1 & -1 \end{bmatrix}
$$
#### CNOT Gate
- Um Interaktionen zwischen mehreren Qubits zu erhalten, brauchen wir andere Gates wie das `Controlled NOT Gate`
![]()
- Flipt das Ziel-Qubit `nur` wenn bereits $|1\rangle$ ist
$$
CNOT|00\rangle = \begin{bmatrix} 1 & 0 & 0 & 0 \cr 0 & 1 & 0 & 0 \cr 0 & 0 & 0 & 1 \cr 0 & 0 & 1 & 0\end{bmatrix} \begin{bmatrix} 1 \cr 0 \cr 0 \cr 0 \end{bmatrix} = \begin{bmatrix} 1 \cr 0 \cr 0 \cr 0 \end{bmatrix} = |00\rangle 
$$
- den Unterschied sieht man, wenn man 10/11 mit CNOT verbindet und sich das flippen betrachetet 
$$
CNOT|11\rangle = \begin{bmatrix} 1 & 0 & 0 & 0 \cr 0 & 1 & 0 & 0 \cr 0 & 0 & 0 & 1 \cr 0 & 0 & 1 & 0\end{bmatrix} \begin{bmatrix} 0 \cr 0 \cr 0 \cr 1 \end{bmatrix} = \begin{bmatrix} 0 \cr 0 \cr 1 \cr 0 \end{bmatrix} = |10\rangle 
$$
&rarr; hier sieht man sehr gut, dass wir 1 als Ausgangssituation benötigen, wenn wir CNOT verwenden
#### Toffoli Gate (CCNOT)
- flips only if both (target & controlled qubits are 1). Wenn wir drei Qubits haben und den State 111 erreichen &rarr; wird das letzte Bit geflipped
$$
CCNOT|111\rangle = 
\begin{bmatrix} 
1 & 0 & 0 & 0 & 0 & 0 & 0 & 0 \cr 
0 & 1 & 0 & 0 & 0 & 0 & 0 & 0 \cr 
0 & 0 & 1 & 0 & 0 & 0 & 0 & 0 \cr 
0 & 0 & 0 & 1 & 0 & 0 & 0 & 0 \cr 
0 & 0 & 0 & 0 & 1 & 0 & 0 & 0 \cr 
0 & 0 & 0 & 0 & 0 & 1 & 0 & 0 \cr 
0 & 0 & 0 & 0 & 0 & 0 & 0 & 1 \cr 
0 & 0 & 0 & 0 & 0 & 0 & 1 & 0 \cr 
\end{bmatrix} \begin{bmatrix} 0 \cr 0 \cr 0 \cr 0 \cr 0 \cr 0 \cr 0 \cr 1 \end{bmatrix} \begin{bmatrix} 0 \cr 0 \cr 0 \cr 0 \cr 0 \cr 0 \cr 1 \cr 0\end{bmatrix} = |110\rangle
$$
#### SWAP Gate & Fredkin
- tauscht immer dann, wenn es eine Differenz der Qubits gibt und verwedet dafür die Identitätsmatrix top left 
![]()
$$
CSW AP = 
\begin{bmatrix} 
1 & 0 & 0 & 0 & 0 & 0 & 0 & 0 \cr 
0 & 1 & 0 & 0 & 0 & 0 & 0 & 0 \cr 
0 & 0 & 1 & 0 & 0 & 0 & 0 & 0 \cr 
0 & 0 & 0 & 1 & 0 & 0 & 0 & 0 \cr 
0 & 0 & 0 & 0 & 1 & 0 & 1 & 0 \cr 
0 & 0 & 0 & 0 & 0 & 0 & 0 & 0 \cr 
0 & 0 & 0 & 0 & 0 & 1 & 0 & 0 \cr 
0 & 0 & 0 & 0 & 0 & 0 & 0 & 1 \cr 
\end{bmatrix} 
$$
![]()

### Quantenverschränkung
- zwei Qubits sind verschränkt wenn der Zustand des einen nicht unabhängig vom anderen Qubit ist 
$$
|\Psi\rangle = \frac{1}{\sqrt{2}}(|00\rangle + |11\rangle)
$$ 
- Die Korrelation ist sofort, die Messergebnisse von A korrelieren sofot mit B, wodurch sich diese sofort den gleichen Zustand teilen
- Nach Einsteins Fernwirkungsfestellung ("spukhafte Fernwirkung") &rarr; Einstein ging damals davon aus, dass seine Relativitätstheorie durch die Annahme (ERP Paradoxon), dass die Informationsübertragung schneller als Lichtgeschwindigkeit erfolge. Heutzutage weiß man, dass die Relativitätstheorie nicht gestört wird, das es sich um keine Informationsübertragung handel
- Auch wenn wir die Verschränkung nicht für Kommunikation nutzen können, können wir mit der Verschränkung mehr Zustände representieren als mit isolierten Qubits 
- 
### Bell States 
- beschreibt die unterschiedlichen States von verschränkten Qubits. Wir haben zwei States wo jeweils die Qubits die gleich-gemessten Werte besitzen: 
$$
|\Psi^+\rangle = \frac{|00\rangle + |11\rangle}{\sqrt{2}}
$$
$$
|\Psi^-\rangle = \frac{|00\rangle - |11\rangle}{\sqrt{2}}
$$
- und wir haben die zwei States, wo die Qubits beim messen beide den umgekehrten Output besitzen: 
$$
|\Psi^+\rangle = \frac{|01\rangle + |10\rangle}{\sqrt{2}}
$$
$$
|\Psi^-\rangle = \frac{|01\rangle - |10\rangle}{\sqrt{2}}
$$
- wenn man ein drittes Qubit mit zwei verbinden will, wählt man einfach 