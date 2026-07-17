# Baum des Wissens

Eine interaktive 3D-Erfahrung: ein leuchtender Baum, dessen Krone in eine Galaxie übergeht und dessen Wurzeln durch die Erde bis zu einem glühenden Lavakern reichen. Beim ersten Klick oder starkem Hineinzoomen reist man durch einen Zeittunnel — vorbei an schwebenden Formeln, Sternenstreifen und Lichtringen — und landet automatisch auf einer zweiten, eigenständigen Seite: „Tree of Knowledge".

**Live-Demo (nach Veröffentlichung über GitHub Pages):** `https://<dein-benutzername>.github.io/<repo-name>/`

## Struktur

```
Repository-Hauptverzeichnis/
├── README.md
├── index.html                      ← Startseite (GitHub Pages öffnet das automatisch)
├── Tree of Knowledge/
│   └── index.html                  ← Zielseite, öffnet sich nach der Zeittunnel-Reise
└── varianten/                      ← frühere Entwicklungsstufen (siehe unten)
```

**Wichtig:** `index.html` und der Ordner `Tree of Knowledge/` müssen im selben Verzeichnis bleiben und genau so heißen (Groß-/Kleinschreibung beachten), sonst funktioniert die Weiterleitung am Ende nicht.

## Wie es funktioniert

1. **Intro** — ein Nietzsche-Zitat erscheint (automatisch auf Englisch oder Arabisch, je nach Gerätesprache), bevor die Szene startet
2. **3D-Szene** — frei navigierbarer Raum mit Baum, Galaxie, Erde und Krater, auf Basis eines Fotos als geschichtete Tiefenebenen
3. **Zeittunnel** — erster Klick oder starkes Zoomen lösen eine ~3-sekündige Reise aus: Spiralflug, Lichtringe, Sternenstreifen, schwebende physikalische Formeln
4. **Übergang** — automatischer Wechsel zu `Tree of Knowledge/index.html`

## Steuerung

| Eingabe | Wirkung |
|---|---|
| Maus ziehen / ein Finger (Touch) | Umsehen |
| W A S D | Frei fliegen |
| Shift halten | Doppeltes Tempo |
| Mausrad / Pinch (Touch) | Zoomen |
| Klick auf Erde / Kern / Galaxie | Kamera fliegt automatisch dorthin |
| **Erster Klick irgendwo** oder **starkes Hineinzoomen** | Löst den Zeittunnel-Effekt aus |

## Veröffentlichung über GitHub Pages

1. Dieses Repository (mit exakt der obigen Ordnerstruktur) zu GitHub hochladen
2. Im Repository: **Settings → Pages**
3. Unter „Branch" den Branch (z. B. `main`) und Ordner `/ (root)` auswählen, speichern
4. Nach kurzer Zeit ist die Seite unter `https://<dein-benutzername>.github.io/<repo-name>/` erreichbar

## Technik

- Reines HTML/CSS/JavaScript, Three.js (r128) direkt eingebettet — keine Installation, kein Build-Schritt nötig
- Bildmaterial als Base64 in die Datei eingebettet (daher die Dateigröße)
- Kein externes Bildgenerierungs-Tool verwendet; alle Texturen/Effekte sind prozedural oder aus deinen bereitgestellten Fotos aufgebaut

## `/varianten` — frühere Entwicklungsstufen

Eigenständige, frühere Versionen aus dem Entwicklungsprozess. Sie funktionieren unabhängig voneinander und sind nicht mit den Hauptseiten verlinkt — als Referenz, falls dir ein früherer Stil besser gefällt.

| Datei | Beschreibung |
|---|---|
| [`varianten/digital_tree.html`](./varianten/digital_tree.html) | Die allererste Version: schlichter, filigraner Baum mit Leiterbahn-Boden, scrollbar von Wurzeln bis Krone |
| [`varianten/baum_schlicht.html`](./varianten/baum_schlicht.html) | Ruhiges Poster-Motiv: große Sonne hinter dem Baum, Erde am Wurzelgrund |
| [`varianten/baum_galaxie_krater.html`](./varianten/baum_galaxie_krater.html) | Prozedural erzeugte Version mit generierten Texturen für Sonne, Galaxie und Krater |
| [`varianten/baum_lebendig.html`](./varianten/baum_lebendig.html) | Das erste Referenzfoto als flaches Bild, mit animierten Lichtpulsen darüber |
| [`varianten/baum_3d.html`](./varianten/baum_3d.html) | Erste vollständig 3D-prozedurale Baum-Szene (Three.js), ohne Foto-Grundlage |

---

*„Aber es ist mit dem Menschen wie mit dem Baume. Je mehr er hinauf in die Höhe und Helle will, um so stärker streben seine Wurzeln erdwärts, abwärts, ins Dunkle, Tiefe — ins Böse."* — Friedrich Nietzsche
