# Bücherfach

E-Book-Reader im Browser, gebaut für das iPad. Funktioniert offline und ohne Installation aus dem App Store.

**App öffnen:** https://kolya-git.github.io/master/

## Auf dem iPad einrichten

1. Die Adresse oben in **Safari** öffnen.
2. „Teilen“ → **„Zum Home-Bildschirm“**. Danach startet das Bücherfach wie eine App, auch offline.
3. „Bücher hinzufügen“ → „Durchsuchen“ → **Downloads** → Dateien auswählen.

## Funktionen

- Formate: **EPUB, MOBI/PRC/AZW** (ohne Kopierschutz), **FB2, TXT, HTML**
- Blättern per Tipp oder Wischen, alternativ Scrollen; Doppelseite im Querformat
- Schriftgröße, Schrift (Literata, Iowan, Atkinson Hyperlegible, System, Georgia, Verlag), Zeilenabstand, Ränder, Blocksatz, Einzug oder Absatzabstand, Silbentrennung
- Farbschemata: Automatisch, Hell, Sepia, Grau, Dunkel, Schwarz
- Inhaltsverzeichnis, Positionsregler, Leseposition wird automatisch gemerkt
- Bibliothek mit Covern, Suche und Sortierung

## Datenschutz

Bücher und Lesepositionen werden nur lokal im Browser des Geräts gespeichert (IndexedDB). Es wird nichts hochgeladen. Nachgeladen werden nur die Schriften von Google Fonts.

## Technik

Eine einzige HTML-Datei ohne Build-Schritt und ohne externe Bibliotheken. EPUB wird mit `DecompressionStream` entpackt (Safari ab iOS 16.4), MOBI (PalmDOC) wird selbst dekodiert. `sw.js` macht die App offline nutzbar.
