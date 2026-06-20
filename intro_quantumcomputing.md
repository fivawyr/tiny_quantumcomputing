## Einführung in das QuantumComputing (QC) - Notizen
### Einstiegszitat
> "Wir sind ungefähr da, wo klassicsche Computer in den 1950ern waren, die Theorie existiert, die Hardware steckt noch in den Kinderschuhen. Das volle Potential (z.B. Short Algorithmus zu knacken von Verschlüsselungen) braucht millionen-fehlerkorrigierten Qubits" ­~ Claude 
- Differenzierung der bekannten Begriffe: Quantenphysik ist die Oberkategorie und schließt Quantenmechanik/-computing mit ein. Wobei die Quantenmechanik die mathematische Grundlage ist. Sie beweist und beschreibt wie Materie auf atomarer Ebene funktioniert und gibt uns mithilfe der komplexen Zahlen jede Begründung die für die Anwendung des Quantencomputings verwendet wird. Das Quantencomputing ist dabei die reine-/Ingenieurswissenschaft, welche Quantenmechanik Phänomene (Superposition, Inferenz etc.) Rechengrundlage verwendet. Die größte Überlappung mit meinem Interessensgebiet + Forschungs Relevantheit liegt im `Quantum Chaos`. Es beschreibt das Verhalten von klassischen Pendant chaotisch ist. 
### Quantenbits
- rekursive Operatoren wie Fibonacci oder Fakultät sind mathematische Konzepte, bei welchen unseren heutigen Computer an ihre Grenzen stoßen &rarr; exponentielles Wachstum
- Würde man bspw. ein ganz einfaches Problem wie die Sitzpositionsmöglichkeiten von 30 Gästen nehmen, so hat man eine hohe/exponentiell wachsende Kombinationsmöglichkeit, um ein Entscheidungskonzept (Dijkstra etc., kürzeste Wege) anzuwenden. 
> Das Qubit hat vor der Messung keinen Zustand, der für uns auswertbar ist. Die Messung bringt das Qubit zum kollabieren in einem der beiden Zustände ($1/2$)
- Ein Quantencomputer ist nicht per se schneller als ein herkömmlicher Computer, er löst algorihtmitische Probleme (durch die gegebene Linearität auch nicht alle) einfach mit weniger Operationen &rarr; solving `PDE's`, Encrypting und das Verhindern von Decrypting & Optimierung von Systemen (Entscheidungsmodelle / Energy Minimuzation, Decoded Quantum Inferferometry)
- Quantencomputing ersetzt nicht einfach tradionelle Computer, sondern sollte (auch aus Kostengründen) aktuell nur für algorithmische und numerische komplexe Thematiken und Forschungsgebiete verwendet werden
- die (ino) beste Beschreibung für den Stand zwischen $0/1$ (`Superposition`) ist das Beispiel mit einer Kaffeebestellung. Wenn du dir unsicher bist was du bestellen möchtest und zwischen zwei (oder mehr aber bleiben wir mal bei zwei) Optionen stehst, bist du in einer Art `Superposition`. Es wäre so, als würdest du eine Münze werfen und in der Luft nicht klar ist, welchen Zustand die Münze gerade hat
![Classic vs. Qubits](ressources/classic_vs_qubit.png)
- Der obere Vergleich fasst noch keine mathematische Begründung zusammen, daher: 
$$
\|\psi\rangle = \alpha\|0\rangle + \beta\|1\rangle
$$
- $\alpha$ und $\beta$ sind Aplituden und somit komplexe Zahlen (hier die Wurzel aus der Annahme, wenn sich der Zustand eines Systems ändert) die beschreiben, wie stark die Basiszustände ($0/1$) für $\psi$ am Ende enthält das Quadrat von $\alpha$ und $\beta$. Komplexe Zahlen besitzen eine Phase auf der komplexen Ebene, welche zur Interferenz führt (das Überlappen der Wellen zweier komplexen Zahlen und komplexer Ebene). Auf dem Konzept der `Interferenz` basiert die hohe Rechenleistung eines Quantencomputers
- Elektronen Spins und Phototen zeigen das Konzept eines `Superpositionszustandens`, es gibt zwei Standard Zustände (Up/Down || Vertikal/-Horizontale Polarisierung). Dabei ist der "dritte Zustand" genau das physische Konzept: Elektronen Spins enthalten erst bei der Messung einen festen Wert (Wellen Überlappung) und diagonale Polarisierung von Phototen
$$
\|\psi\rangle = \alpha\|\uparrow + \beta\|\downarrow\rangle 
$$
- diese physischen Mechanismen sind *KEINE* Analogien. QC verwendet supraleitende Schaltkreise, in welchen exakt das beschriebene Verfahren verwendet wird. Die Photonen sind photonikbasiert QC's reale polarisierte Lichtteilen 
![Qubit Implementation]()
*Workflow:* wir encoden binary input data in den Quantenalgorithmus, auf welchem Quantum Operationen erfolgen. Am Ende transformieren wir die erhalten Qubits, um sie wieder in normale Bits zu übersetzen (cf. "Quantum Circuit Model"). Zusammengefasst: Input - Bits, Quantum Operationen . Qubits, Output - Bits
### Mathematische Grundlage
- Vektor Operationen sollte klar sein, wird hier übersprungen
- $\Re$ und $\Im$: Bei einer komplexen Zahl $z = a + bi$ ist $\Re(z) = a$ der *Realanteil* (messbare Amplitude, Wahrscheinlichkeit) und $\Im(z) = b$ der *Imaginäranteil* (Phase, steuert Interferenz). Im QC gilt: $\|a\|^2 = \Re(a)^2 + \Im(a)^2$ gibt die Messwahrscheinlichkeit, während das Verhältnis von $\Re/\Im$ die Phase bestimmt, die konstruktive oder destruktive Interferenz erzeugt
#### Komplexe Zahlen
- sind imaginäre Zahlen, welche als reale Zahlen geschrieben werden und mit der imaginären Einheit `i` multipliert 
- $i^2 = -1$ dient als Ausgangslage, da dieser Zustand mit reelen Zahlen nicht erreichbar ist
- Komplexe Zahlen beeinhalten somit eine reele Zahl und eine imaginäre Komponenente §z = a + bi§
- $\theta$ ist der `phase angle` $\angle$ und beschreibt den Winkel eines Vectors  
![Hier kommt das Bild vom Winkel rein]()
- wir haben somit zwei unterschiedliche Arten einer komplexen Zahl in einem 2-Dimensionalen Koordinatensystem dazustellen: 
$z = a + bi = re^{i\theta}$ &rarr; wichtig ist hier zu sagen, dass $a$, $b$ und $re$ und $\theta$ nicht äquivalent sind
#### Eulers Form 
- um die Verbindung von den beiden Formaten dazustellen, brauchen wir die eulische Formel:
$$
e^{i\theta} = cos(\theta) + i \cdot sin(\theta)
$$
&rarr; mit der magnitude $r$ multiplizieren
$$
re^{i\theta} = r(cos(\theta) + i \cdot sin(\theta) = rcos(\theta) + ri\cdot sin(\theta))
$$
&rarr; hier ist $rcos(\theta)$ die "reele Komponente" und $ri\cdot sin(\theta$ die "imaginäre 
#### Absolute Values einer komplexen Zahl 
- Distanz von dem Ursprungspunkt, einfach den Betrag der Polar Form nehmen:
$$
z = re^{i\theta} = \|z\| = r
$$
- um einen Vektor zu transposen, wird folgende Notation verwendet:
- "Transpose a vector and conjugate each of its elements"
- "the conjugate transpose of a vector `a` will be denoted as $a^\dag$
$$
a^\dag = (a^\ast)^T = (a^T)^\ast
a = \begin{bmatrix}2i \cr 13 \cr 6 - i\end{bmatrix} \rarr a^\dag = \begin{bmatrix} -2i & 13 & 6 + i\end{bmatrix}
$$
