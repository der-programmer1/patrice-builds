# Bananenblick: Was ein Modelltest sichtbar macht

**11. November 2026 · Computer Vision, lokale KI und Modellbewertung**

[Öffentlichen Prototyp ausprobieren ↗](https://der-programmer1.github.io/Bananenblick/) · [Quellcode](https://github.com/der-programmer1/Bananenblick) · [Zur Journal-Übersicht](../README.md)

## Die Frage

Kann eine Web-App die sichtbare Reife von Bananen im Kamerabild einschätzen und dabei die Bilder auf dem Gerät verarbeiten?

Bananenblick erkundet diese Idee mit einem trainierten ONNX-Modell im Browser. Die öffentliche Version 0.1.0 ist als Prototyp verfügbar. Die neuere Arbeit beschäftigt sich mit einzelnen Bananen in dichten, überlappenden Büscheln.

## Woran gearbeitet wurde

Im [Update-Entwurf](https://github.com/der-programmer1/Bananenblick/pull/1) bekommen erkannte Früchte eigene Nummern. Rahmen, Ergebnisliste und Auswahl verwenden dieselbe Zuordnung. Eine Empfehlung soll erst nach drei sicheren Bestätigungen erscheinen und bei Unsicherheit oder verschwundenen Treffern entfallen.

Zur Software gehören außerdem Modell-Hashprüfungen, getrennte Zeitlimits und die Behandlung des Wechsels zwischen WebGPU und WebAssembly. Das sind überprüfbare Teile der Anwendung – die Qualität der Erkennung muss zusätzlich am Modell geprüft werden.

## Was der weitere Modellversuch gezeigt hat

Der Bericht zum Kandidaten 0.4 dokumentiert einen vor dem Training festgelegten Prüfbestand. Im ausgewerteten Test gab es 111 annotierte reife Einzelbananen:

| Beobachtung | Ergebnis |
| --- | --- |
| Richtige Empfehlungen | 2 |
| Falsche Empfehlungen | 0 |
| Ausgelassene reife Einzelbananen | 109 |
| Recall | 1,8 % |

Die Präzision betrug bei diesen nur zwei Empfehlungen rechnerisch 100 %. Gleichzeitig wurde fast alles ausgelassen. Die festgelegten Ziele von mindestens 95 % Präzision und 80 % Recall wurden damit verfehlt. Der Kandidat ersetzte die bisherigen App-Gewichte nicht.

Der frühere Fototest verwendete einen anderen Bestand. Seine Ergebnisse lassen sich deshalb nicht als direkter Vorher-/Nachher-Vergleich mit diesem Versuch lesen.

## Die wichtige Erkenntnis

Der aktuelle Update-Stand besteht seine Softwareprüfungen. Das Modell bleibt dennoch unter den Freigabezielen. Für das Gesamtprojekt müssen Anwendung, Modell und echte Geräte jeweils passende Nachweise liefern.

Die bislang beschriebenen Browserprüfungen verwenden unter anderem mobile Linux-Emulation und kontrollierte Zustände. Physische Tests auf Android/Chrome und iPhone/Safari sowie der Nachweis von drei vollständigen Kameraauswertungen pro Sekunde stehen aus.

Deshalb bleibt die neue Version ein offener Entwurf. Öffentlich erreichbar ist weiterhin der bestehende Prototyp.

## Die Arbeit nachvollziehen

- [Update-Entwurf mit Ergebnissen und Prüfstand](https://github.com/der-programmer1/Bananenblick/pull/1)
- [Bericht des Modellversuchs 0.4](https://github.com/der-programmer1/Bananenblick/blob/codex/numbered-individual-bananas/public/evaluation/experiment-v4/report.md)
- [Gespeicherte Ausgaben und Beispiele](https://github.com/der-programmer1/Bananenblick/blob/codex/numbered-individual-bananas/public/evaluation/experiment-v4/examples.md)

Dieser Beitrag beschreibt den verlinkten Stand vom 11. November 2026. Entwicklung und Dokumentation erfolgen auch mit KI-Unterstützung. Im Versuchsbericht sind die Datenherkunft, Grenzen der Annotationen und fehlende unabhängige Expertenprüfung dokumentiert.

---

[Öffentlichen Prototyp öffnen ↗](https://der-programmer1.github.io/Bananenblick/) · [Zurück zum Journal](../README.md)
