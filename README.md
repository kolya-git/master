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
- **Lesestand abgleichen** zwischen iPad und iPhone über eine Datei in iCloud Drive (optional mit Büchern)
- Auf dem iPhone automatisch schmale Ränder und linksbündiger Text

## Zwischen Geräten wechseln

1. Auf dem einen Gerät „Sync“ (Bibliothek) bzw. das Pfeilsymbol (Lesemodus) → **In Dateien sichern** → iCloud Drive → vorhandene Datei ersetzen.
2. Auf dem anderen Gerät „Sync“ → **Stand laden …** → `buecherfach-stand.json` wählen → „Weiterlesen“.

Pro Buch gewinnt der neuere Stand. Abgeglichen werden Leseposition, Schrift, Zeilenabstand, Absatzstil, Silbentrennung, Farbschema, Lesemodus und Verlagsformatierung. Schriftgröße, Ränder, Ausrichtung und Doppelseite bleiben je Gerät. Einen Hintergrund-Sync gibt es nicht, weil Web-Apps unter iOS nicht selbst in iCloud Drive schreiben dürfen.

## Datenschutz und Sicherheit

- Bücher und Lesepositionen werden nur lokal im Browser des Geräts gespeichert (IndexedDB). Es wird nichts hochgeladen.
- Eine Content Security Policy erlaubt nur die eigenen Skripte (per SHA-256-Prüfsumme) und Google Fonts. Skripte, Event-Handler, `javascript:`-Links und Inhalte von fremden Servern aus E-Books werden entfernt bzw. blockiert.
- Nachgeladen werden nur die Schriften von Google Fonts.

## Technik

Eine einzige HTML-Datei ohne Build-Schritt und ohne externe Bibliotheken. EPUB wird mit `DecompressionStream` entpackt (Safari ab iOS 16.4), MOBI (PalmDOC) wird selbst dekodiert. `sw.js` macht die App offline nutzbar.
