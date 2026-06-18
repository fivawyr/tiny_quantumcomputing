## About this Repo 
- This repo contains german content about the fundamentals of QuantumComputing (QC). The documentation helps me with the deepdive/learning and tracking of my QC journey (&rarr; regarding future reaserch/academic progress)
- Feel free to use & correct content by forking 
- The mathemics Markdown Guide is to help you & myself for using the right equation and operators (Markdown is superior imo). The Cheat Sheet is mostly copy pace, checkout the original source: [Upyesp](https://www.upyesp.org/posts/makrdown-vscode-math-notation/)
## ⚛️ QC - Cheat Sheet

## Zustände

| Begriff | Notation | Bedeutung |
|---|---|---|
| Basis-Zustände | $\|0\rangle = \begin{pmatrix}1\\0\end{pmatrix},\quad \|1\rangle = \begin{pmatrix}0\\1\end{pmatrix}$ | klassische Bits als Vektoren |
| Superposition | $\|\psi\rangle = \alpha\|0\rangle + \beta\|1\rangle$ | $\|\alpha\|^2 + \|\beta\|^2 = 1$ |
| Messung | $P(0) = \|\alpha\|^2,\quad P(1) = \|\beta\|^2$ | kollabiert die Superposition |
| Hadamard-Basis | $\|+\rangle = \frac{\|0\rangle+\|1\rangle}{\sqrt{2}},\quad \|-\rangle = \frac{\|0\rangle-\|1\rangle}{\sqrt{2}}$ | Eigenvektoren von $H$ |
| Tensorprodukt | $\|\psi\rangle \otimes \|\phi\rangle = \|\psi\phi\rangle$ | kombiniertes $n$-Qubit-System |
| Bloch-Kugel | $\|\psi\rangle = \cos\frac{\theta}{2}\|0\rangle + e^{i\varphi}\sin\frac{\theta}{2}\|1\rangle$ | $\theta \in [0,\pi],\; \varphi \in [0,2\pi)$ |

&rarr; wird noch hinzugefügt
![q_state_notation]()
![3dimensional_units]()

## Gatter (Gates)

| Gate | Matrix | Wirkung |
|---|---|---|
| **X** | $\begin{pmatrix}0&1\\1&0\end{pmatrix}$ | $\|0\rangle \leftrightarrow \|1\rangle$ |
| **Z** | $\begin{pmatrix}1&0\\0&-1\end{pmatrix}$ | $\|1\rangle \to -\|1\rangle$ |
| **Y** | $\begin{pmatrix}0&-i\\i&0\end{pmatrix}$ | kombinierter Bit- + Phasenflip |
| **H** | $\frac{1}{\sqrt{2}}\begin{pmatrix}1&1\\1&-1\end{pmatrix}$ | $\|0\rangle \to \|+\rangle,\quad \|1\rangle \to \|-\rangle$ |
| **S** | $\begin{pmatrix}1&0\\0&i\end{pmatrix}$ | Phasendrehung um $\pi/2$ |
| **T** | $\begin{pmatrix}1&0\\0&e^{i\pi/4}\end{pmatrix}$ | Phasendrehung um $\pi/4$ |
| **CNOT** | $\begin{pmatrix}1&0&0&0\\0&1&0&0\\0&0&0&1\\0&0&1&0\end{pmatrix}$ | Flippt Target wenn Control $=\|1\rangle$ |
| **SWAP** | — | $\|\psi\rangle\|\phi\rangle \to \|\phi\rangle\|\psi\rangle$ |

> **Universalität:** $\{H, T, \text{CNOT}\}$ ist ein universeller Gattersatz.


## Bell-Zustände

| Zustand | Formel |
|---|---|
| $\|\Phi^+\rangle$ | $\frac{1}{\sqrt{2}}(\|00\rangle + \|11\rangle)$ |
| $\|\Phi^-\rangle$ | $\frac{1}{\sqrt{2}}(\|00\rangle - \|11\rangle)$ |
| $\|\Psi^+\rangle$ | $\frac{1}{\sqrt{2}}(\|01\rangle + \|10\rangle)$ |
| $\|\Psi^-\rangle$ | $\frac{1}{\sqrt{2}}(\|01\rangle - \|10\rangle)$ |

Schaltkreis: $H$ auf Qubit 1 → $\text{CNOT}(1 \to 2)$


## Algorithmen

| Algorithmus | Problem | Komplexität (klassisch → Quanten) |
|---|---|---|
| **Deutsch-Jozsa** | $f$ konstant oder balanced? | $O(2^{n-1})\ \to\ O(1)$ |
| **Grover** | Suche in $N$ Einträgen | $O(N)\ \to\ O(\sqrt{N})$ |
| **Shor** | Primfaktorzerlegung | $O(e^{n^{1/3}})\ \to\ O(n^3)$ |
| **QFT** | Quantum Fourier Transform | Subroutine in Shor & Phase Estimation |
| **VQE** | Grundzustandsenergie (Chemie) | Hybrid klassisch-quanten (NISQ) |

## Notation

| Symbol | Bedeutung |
|---|---|
| $\|\psi\rangle$ | Ket — Zustandsvektor |
| $\langle\psi\|$ | Bra — konjugiert transponiert |
| $\langle\phi\|\psi\rangle$ | Skalarprodukt (Amplitude) |
| $\|\psi\rangle\langle\phi\|$ | äußeres Produkt (Operator) |
| $\hat{U}^\dagger$ | hermitesch konjugiertes Gate |
| $\hat{U}\hat{U}^\dagger = \mathbb{I}$ | Unitaritätsbedingung |
