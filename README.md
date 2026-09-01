# KARRIERELEITER

Ein Arcade-Kletterspiel im Stil der Automaten von ca. 1981 — nur dass hier nicht
eine Prinzessin gerettet wird, sondern die eigene **Beförderungsurkunde**.
Der Chef sitzt oben, wirft Kaffeetassen die Rampen hinunter und du kletterst
vom Praktikanten bis in die Chefetage.

**Alles steckt in einer einzigen Datei:** `index.html` — kein Build, keine
Abhängigkeiten, keine externen Assets. Grafik, Sound, Musik, Menüs und Cheats
werden zur Laufzeit erzeugt (Canvas 2D + WebAudio + Gamepad API).

## Spielen

**Direkt im Browser: https://kersex.github.io/Karriereleiter/**

Oder lokal: `index.html` im Browser öffnen. Doppelklick genügt (`file://`
reicht aus) — das Spiel lädt nichts nach.

Die Seite wird von GitHub Pages ausgeliefert. Der Workflow
`.github/workflows/pages.yml` veröffentlicht sie bei jedem Push auf den
Standardbranch neu.

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

**Der Automat lässt sich anfassen:** den Kugelgriff am Gehäuse kann man mit
Maus oder Finger in alle Richtungen ziehen. Der Stick ist als SVG gebaut —
Montageplatte, Staubkappe, Chromschaft und Kugel bewegen sich einzeln, eine
gedämpfte Feder zieht ihn beim Loslassen mit leichtem Überschwingen zurück.
Am Griff folgt er der Hand ohne Verzug, ein Achteck-Gatter begrenzt ihn wie
eine echte Restriktorplatte, und bei jedem Richtungswechsel klickt ein
Mikroschalter. Die Knöpfe **A** (springen) und **B** (Start) sind anklickbar.
Tastatur, Controller und Gehäuse steuern dasselbe Spiel; der Stick zeigt immer
die aktuelle Eingabe.

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
| 75 m | **Serverraum** | Acht Netzstecker ziehen, dann stürzt der Chef mitsamt Serverschrank ab. Die Urkunde hilft hier nicht — solange ein Stecker steckt, läuft der Server. Offene Stecker blinken, das HUD zählt mit, und es gibt entsprechend mehr Zeit. Umherziehende Deadlines. |
| 100 m | **Chefetage** | Förderbänder schieben dich weg, Meeting-Einladungen fahren darauf. Der Chef wirft schneller. |

Nach der Chefetage beginnt Runde 2 — schneller, mehr Gegner, mehr Bonus.

## Features

- **Espresso-Hammer** — kurzzeitig alles zerschlagen, was rollt (dafür kein Klettern).
- **Sprung-Kombos** — mehrere Gegner in einem Sprung: 100 → 300 → 500 → 800 Punkte.
- **Bonus-Uhr**, Extraleben bei 20.000 Punkten, Bonusgegenstände (Aktentasche, Krawatte, Diensthandy).
- **Karriere-Titel** im HUD, der mit der Punktzahl mitwächst: Praktikant → … → CEO → Legende.
- **Auftragsanzeige**: Das Zwischenbild sagt vor jeder Etage, was dort zu tun ist.
- **Bestenliste** mit Kürzel-Eingabe, lokal gespeichert.
- **Kaputte Leitern**, Abkürzungen, Alternativrouten.
- Vier Schwierigkeitsgrade (Praktikant / Normal / Manager / Burnout).
- **Arcade-Automat als Rahmen** — Marquee, Bezel, Bedienfeld mit mitlaufendem
  Joystick, Münzeinwurf. Abschaltbar unter Optionen → *Automat anzeigen*, dann
  füllt das Spielbild mehr Fläche.
- CRT-Look mit Scanlines, Blendreflex, Bildschirmbeben, Chiptune-Musik und -Effekten.
- Alle Einstellungen und Tastenbelegungen frei konfigurierbar und dauerhaft gespeichert.

## Cheat-Terminal

Die Figur lässt sich auch ohne Code wechseln: **Pause → Figur wechseln**.

Codes lassen sich **jederzeit einfach eintippen** — im Titelbild, mitten im
Spiel, egal wo. Wer `KAOS` tippt, bekommt sofort das Cheat-Terminal aufgeklappt
und den Chaos-Modus eingeschaltet; das gilt für jeden Code der Liste. Wer lieber
klickt: Pausemenü oder **F1** öffnet das Terminal, dort tippt man den Code über
die Tastatur oder gibt ihn mit dem Controller auf der Bildschirmtastatur ein und
bestätigt mit `OK`. Gefundene Codes bleiben gespeichert. Mit Cheats erspielte
Punkte kommen nicht in die Bestenliste.

| Code | Wirkung |
|---|---|
| `KAOS` | **Chaos-Modus** — siehe unten |
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
| `TEMU` | **Billig-Klempner** — tauscht die Spielfigur gegen eine sehr günstig wirkende Fälschung: grüne Mütze mit schiefem Emblem, einseitiger Schnauzer, orangefarbenes Hemd, türkise Latzhose mit genau einem Knopf, zwei verschiedene Schuhe und ein Preisschild, das noch dranhängt. Reine Optik — die Punkte zählen normal. |

Und natürlich: **↑ ↑ ↓ ↓ ← → ← → B A** schaltet alles auf einmal frei.

### Chaos-Modus

`KAOS` schaltet einen Modus ein, in dem **immer** ein Ereignis läuft: läuft
eines aus, startet sofort das nächste. Im HUD blinkt dauerhaft ein
regenbogenfarbenes `KAOS`, darunter steht, was gerade los ist:

| Ereignis | Was passiert |
|---|---|
| Steuerung vertauscht | links und rechts sind getauscht |
| Mondgravitation | Sprünge werden schwerelos |
| Alle hektisch | Gegner und Spieler laufen deutlich schneller |
| Kaffeeregen | Tassen prasseln von oben herein |
| Mini-Modus | der Held schrumpft |
| Büro-Disco | die Palette rotiert durch alle Farben |
| Erdbeben | der Bildschirm wackelt dauerhaft |
| Spiegelverkehrt | das ganze Bild ist gespiegelt |
| Alles steht Kopf | das Bild steht auf dem Kopf |
| Stromausfall | nur noch ein Lichtkegel um den Helden |
| Betriebsfeier | Konfettiregen |
| Aktenflut | der Chef wirft fünf Tassen auf einmal |
| Neue Deadline | ein zusätzliches Feuer erscheint |

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
