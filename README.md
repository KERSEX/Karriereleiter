# KARRIERELEITER

Ein Arcade-Kletterspiel im Stil der Automaten von ca. 1981 — nur dass hier nicht
eine Prinzessin gerettet wird, sondern die eigene **Beförderungsurkunde**.
Der Chef sitzt oben, wirft Kaffeetassen die Rampen hinunter und du kletterst
vom Praktikanten bis in die Chefetage.

**Alles steckt in einer einzigen Datei:** `index.html` — kein Build, keine
Abhängigkeiten, keine externen Assets. Grafik, Sound, Musik, Menüs und Cheats
werden zur Laufzeit erzeugt (Canvas 2D + WebAudio + Gamepad API).

## Starten

`index.html` im Browser öffnen. Doppelklick genügt (`file://` reicht aus).

## Steuerung

| Aktion | Tastatur | Controller |
|---|---|---|
| Laufen | ← → / A D | D-Pad, linker Stick |
| Leiter hoch/runter | ↑ ↓ / W S | D-Pad, linker Stick |
| Springen | Leertaste / K / J | A oder X |
| Start / Bestätigen | Enter / F | Start, R1 |
| Pause & Menü | Esc / P | Options / Start |
| Zurück | Backspace | B, Select, L1 |
| Cheat-Terminal | F1 | Pausemenü → Cheat-Terminal |
| Optionen | F2 | Pausemenü → Optionen |

Controller werden automatisch erkannt (Standard-Gamepad-Mapping), inklusive
Vibration. Auf Touchgeräten erscheint automatisch ein Bildschirm-Steuerkreuz.
Sämtliche Menüs — auch das Cheat-Terminal mit seiner Bildschirmtastatur —
lassen sich vollständig mit dem Controller bedienen.

## Die vier Etagen

| Etage | Name | Mechanik |
|---|---|---|
| 25 m | **Großraumbüro** | Schräge Schreibtischreihen, der Chef rollt Kaffeetassen herunter, aus dem brennenden Papierkorb kriechen Deadlines. |
| 50 m | **Aufzugschacht** | Fahrende Aufzüge, springende Tacker. Aufzug B ist eine riskante Express-Abkürzung von ganz unten bis zur Zielebene. |
| 75 m | **Serverraum** | Acht Netzstecker ziehen, dann stürzt der Chef mitsamt Serverschrank ab. Umherziehende Deadlines. |
| 100 m | **Chefetage** | Förderbänder schieben dich weg, Meeting-Einladungen fahren darauf. Der Chef wirft schneller. |

Nach der Chefetage beginnt Runde 2 — schneller, mehr Gegner, mehr Bonus.

## Features

- **Espresso-Hammer** — kurzzeitig alles zerschlagen, was rollt (dafür kein Klettern).
- **Sprung-Kombos** — mehrere Gegner in einem Sprung: 100 → 300 → 500 → 800 Punkte.
- **Bonus-Uhr**, Extraleben bei 20.000 Punkten, Bonusgegenstände (Aktentasche, Krawatte, Diensthandy).
- **Karriere-Titel** im HUD, der mit der Punktzahl mitwächst: Praktikant → … → CEO → Legende.
- **Bestenliste** mit Kürzel-Eingabe, lokal gespeichert.
- **Kaputte Leitern**, Abkürzungen, Alternativrouten.
- Vier Schwierigkeitsgrade (Praktikant / Normal / Manager / Burnout).
- CRT-Look mit Scanlines, Bildschirmbeben, Chiptune-Musik und -Effekten.
- Alle Einstellungen und Tastenbelegungen frei konfigurierbar und dauerhaft gespeichert.

## Cheat-Terminal

Im Pausemenü oder mit **F1**. Code über Tastatur tippen oder mit dem Controller
auf der Bildschirmtastatur eingeben, dann `OK`. Gefundene Codes bleiben
gespeichert. Mit Cheats erspielte Punkte kommen nicht in die Bestenliste.

| Code | Wirkung |
|---|---|
| `KAOS` | **Chaos-Modus** — alle paar Sekunden ein neues Zufallsereignis: vertauschte Steuerung, Mondgravitation, Kaffeeregen, Erdbeben, Büro-Disco, Aktenflut, Mini-Modus … |
| `KAFFEE` | Endlos-Espresso |
| `HOMEOFFICE` | Geistmodus (unverwundbar) |
| `TURBO` | Überstunden — alles deutlich schneller |
| `SCHWEBEN` | Mondgravitation |
| `MINIME` | Mini-Praktikant |
| `URLAUB` | Betriebsferien — alle Gegner pausieren |
| `MAGNET` | Boni fliegen dir zu |
| `REGENBOGEN` | Farbwechselnde Palette |
| `DEBUG` | Hitboxen und FPS |
| `GEHALT` | +10.000 Punkte |
| `LEBEN` | 9 Leben |
| `CHEFETAGE` | Etagen-Auswahl im Pausemenü freischalten |
| `IDDQD` | Gruß an 1993 |

Und natürlich: **↑ ↑ ↓ ↓ ← → ← → B A** schaltet alles auf einmal frei.

## Technisches

- Interne Auflösung 224 × 272 Pixel, ganzzahlig hochskaliert (`image-rendering: pixelated`).
- Feste Physik-Schrittweite (60 Hz) mit Akkumulator — gleiche Sprungweiten auf jedem Monitor.
- Plattformen sind Strecken mit Steigung; Tassen rollen immer bergab und nehmen
  zufällig Leitern nach unten.
- Sound komplett synthetisiert (Rechteck/Dreieck/Rauschen), Musik über einen
  kleinen Step-Sequenzer.
