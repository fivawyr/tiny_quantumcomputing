#### Overview
- Quantum Cryptography (QC) ist die Anwendung von quantenmechanischen Prinzipien auf die sichere Kommunikation.
- Im Gegensatz zur klassischen Kryptographie basiert die Sicherheit nicht auf der Schwierigkeit mathematischer Probleme, sondern auf physikalischen Gesetzen der Quantenmechanik.
- Das bekannteste Anwendungsgebiet ist der **Quantenschlüsselaustausch (Quantum Key Distribution, QKD)**, bei dem zwei Kommunikationspartner einen gemeinsamen geheimen Schlüssel erzeugen können.
- Ein Angreifer kann den Schlüssel nicht unbemerkt abhören, da jede Messung eines Quantenzustands diesen verändert.
- Quantum Cryptography dient **nicht** der Verschlüsselung der Daten selbst, sondern dem sicheren Austausch kryptographischer Schlüssel.
- Nach erfolgreichem Schlüsselaustausch werden die eigentlichen Daten weiterhin mit klassischen Verfahren wie **AES-256** verschlüsselt.
- Der Shor-Algorithmus zeigt, dass leistungsfähige Quantencomputer klassische Public-Key-Verfahren wie RSA oder ECC in Zukunft brechen könnten. Quantum Cryptography ist eine mögliche Antwort auf dieses Problem.

---

#### Cyber Security Kontext

In der Cyber Security beschäftigt sich Quantum Cryptography mit der Frage, wie Kommunikation auch gegen zukünftige Angreifer mit Quantencomputern abgesichert werden kann.

Aktuelle Public-Key-Verfahren wie:

- RSA
- Diffie-Hellman (DH)
- Elliptic Curve Cryptography (ECC)

basieren auf mathematischen Problemen, deren Lösung für klassische Computer praktisch unmöglich ist. Ein ausreichend leistungsfähiger Quantencomputer könnte diese Verfahren jedoch mithilfe des **Shor-Algorithmus** in realistischer Zeit brechen.

Quantum Cryptography verfolgt daher einen anderen Ansatz:
Statt auf mathematische Komplexität zu vertrauen, nutzt sie fundamentale Gesetze der Quantenmechanik, wodurch ein Abhörversuch physikalisch nachweisbar wird.

---

#### Wichtige Eigenschaften

| Eigenschaft | Beschreibung |
|-------------|--------------|
| Physikalische Sicherheit | Sicherheit basiert auf Naturgesetzen statt Mathematik |
| Abhörerkennung | Jeder Messversuch verändert den Quantenzustand und wird erkannt |
| Kein Ersatz für AES | QC liefert lediglich den Schlüssel |
| Zukunftssicher | Schutz gegen Angriffe durch Quantencomputer |
| Spezielle Hardware | Benötigt Quantenkanäle (z. B. Glasfaser oder Satelliten) |

---

#### Funktionsprinzip (vereinfacht)

1. Alice erzeugt zufällige Qubits.
2. Die Qubits werden über einen Quantenkanal an Bob gesendet.
3. Bob misst die empfangenen Qubits.
4. Alice und Bob vergleichen öffentlich die verwendeten Basen.
5. Stimmen genügend Messungen überein, entsteht ein gemeinsamer geheimer Schlüssel.
6. Wird eine ungewöhnlich hohe Fehlerrate festgestellt, deutet dies auf einen Abhörversuch hin und der Schlüssel wird verworfen.

---

#### Vorteile

- Abhörversuche werden erkannt.
- Sicherheit ist unabhängig von der Rechenleistung des Angreifers.
- Schutz gegen zukünftige Quantencomputer.
- Geeignet für besonders kritische Kommunikationskanäle.

---

#### Nachteile

- Hohe Kosten für spezielle Hardware.
- Begrenzte Übertragungsreichweite.
- Geringere Datenraten als klassische Netzwerke.
- Ersetzt keine bestehende Verschlüsselung, sondern ergänzt sie.
- Noch keine breite Verfügbarkeit im Unternehmensumfeld.

---

#### Quantum Key Distribution (QKD)

QKD ist die bekannteste praktische Anwendung der Quantum Cryptography.

Bekannte Protokolle:

- BB84 (1984)
- E91 (Ekert-Protokoll)
- B92

Der erzeugte Schlüssel wird anschließend beispielsweise für:

- AES-256
- One-Time Pad (OTP)

verwendet.

---

#### Zusammenhang mit Post-Quantum Cryptography (PQC)

Quantum Cryptography und Post-Quantum Cryptography werden häufig verwechselt.

| Quantum Cryptography | Post-Quantum Cryptography |
|----------------------|---------------------------|
| Nutzt Quantenmechanik | Nutzt klassische Mathematik |
| Benötigt spezielle Hardware | Läuft auf heutiger Hardware |
| Erkennt Abhörversuche | Erkennt keine Abhörversuche |
| Hauptanwendung: QKD | Ersatz für RSA und ECC |
| Noch wenig verbreitet | Aktuell Standardisierungsprozess durch NIST |

---

#### Typische Einsatzgebiete

- Militärische Kommunikation
- Regierung und Behörden
- Banken und Finanzinstitute
- Rechenzentren
- Satellitenkommunikation
- Kritische Infrastruktur (KRITIS)

---

#### Merksätze

> Quantum Cryptography verschlüsselt keine Daten, sondern ermöglicht den sicheren Austausch kryptographischer Schlüssel.

> Die Sicherheit basiert auf den Gesetzen der Quantenmechanik und nicht auf schwer lösbaren mathematischen Problemen.

> In der Praxis wird Quantum Cryptography meist mit klassischen Verschlüsselungsverfahren wie AES kombiniert.