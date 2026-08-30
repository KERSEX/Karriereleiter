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
Vibration; Joystick und Knöpfe am Automatengehäuse bewegen sich mit. Auf
Touchgeräten erscheint automatisch ein Bildschirm-Steuerkreuz. Sämtliche Menüs
— auch das Cheat-Terminal mit seiner Bildschirmtastatur — lassen sich
vollständig mit dem Controller bedienen.

**Der Automat lässt sich anfassen:** den Joystick am Gehäuse kann man mit Maus
oder Finger in alle Richtungen ziehen — er kippt dabei räumlich um seinen Fuß
und schnappt beim Loslassen zurück. Die Knöpfe **A** (springen) und **B**
(Start) sind anklickbar. Tastatur, Controller und Gehäuse steuern dasselbe
Spiel; der Joystick zeigt immer die aktuelle Eingabe.

**Klettern:** einfach ↑ gedrückt halten. Wer bis zu ~25 px neben einer heilen
Leiter steht, rutscht automatisch hin und steigt ein; die erreichbare Leiter
leuchtet weiß auf und ein blinkender Pfeil zeigt den Einstieg. Sprünge haben
Kojotenzeit (kurz nach der Kante zählt noch) und einen Sprungpuffer (kurz vor
der Landung gedrückt zählt auch).

**Kaputte Leitern** sind rostbraun statt blau, haben eine sichtbare Lücke mit
Warnband und enden nach kurzer Zeit — die Einstieghilfe fasst sie gar nicht
erst an. Und mit dem Espresso-Hammer in der Hand klettert niemand: erst
austrinken.

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
- **Arcade-Automat als Rahmen** — Marquee, Bezel, Bedienfeld mit mitlaufendem
  Joystick, Münzeinwurf. Abschaltbar unter Optionen → *Automat anzeigen*, dann
  füllt das Spielbild mehr Fläche.
- CRT-Look mit Scanlines, Blendreflex, Bildschirmbeben, Chiptune-Musik und -Effekten.
- Alle Einstellungen und Tastenbelegungen frei konfigurierbar und dauerhaft gespeichert.

## Cheat-Terminal

Codes lassen sich **jederzeit einfach eintippen** — im Titelbild, mitten im
Spiel, egal wo. Wer `KAOS` tippt, bekommt sofort das Cheat-Terminal aufgeklappt
und den Chaos-Modus eingeschaltet; das gilt für jeden Code der Liste. Wer lieber
klickt: Pausemenü oder **F1** öffnet das Terminal, dort tippt man den Code über
die Tastatur oder gibt ihn mit dem Controller auf der Bildschirmtastatur ein und
bestätigt mit `OK`. Gefundene Codes bleiben gespeichert. Mit Cheats erspielte
Punkte kommen nicht in die Bestenliste.

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
  Das Automatengehäuse ist in derselben Einheit gebaut (CSS-Variable `--u`) und
  skaliert deshalb pixelgenau mit.
- Eigene 5×7-Bitmapschrift, gerendert als echte Pixelrechtecke und pro Text
  zwischengespeichert — kein Antialiasing, keine Schriftdatei.
- Feste Physik-Schrittweite (60 Hz) mit Akkumulator — gleiche Sprungweiten auf jedem Monitor.
- Plattformen sind Strecken mit Steigung; Tassen rollen immer bergab und nehmen
  zufällig Leitern nach unten.
- Sound komplett synthetisiert (Rechteck/Dreieck/Rauschen), Musik über einen
  kleinen Step-Sequenzer.
