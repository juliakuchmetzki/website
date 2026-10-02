# Design-Präferenzen — johanneskuchmetzki.de & flipupde.de

Diese Datei fasst die Design- und Content-Vorlieben zusammen, die sich aus der
bisherigen Zusammenarbeit ergeben haben. Gedacht als Referenz für zukünftige
Anpassungen, damit der Stil über beide Websites konsistent bleibt.

## Referenz-Vorbild

**AccuBooked** (accubooked.de o.ä.) ist das wiederkehrende Stil-Vorbild für
Layout-Entscheidungen — bei Unsicherheit dort orientieren.

## Typografie & Schrift

- Selbst gehostete Fonts (Inter, Space Grotesk, Caveat) — **keine** externen
  Font-CDNs (Google Fonts etc.), aus Datenschutzgründen.
- `Caveat` (Script-Font) nur sparsam für 1–2 Akzentwörter pro Seite, in
  Akzentfarbe mit dicker farbiger Unterstreichung (`.accent-script`).
- Keine Gedankenstriche (—) in Fließtext/Headlines — gilt als KI-Indiz.
  Stattdessen Punkt oder Komma verwenden.
- Direkter, selbstbewusster, umgangssprachlicher Ton auf Deutsch. Kurze,
  prägnante Sätze statt Marketing-Floskeln.
  Beispiel-Headline: *"Ich habe Reselling zum Kinderspiel gemacht. Und zeig
  dir wie."*

## Farben

- CSS-Custom-Properties pro Seite, eigene Akzentfarbe je Marke:
  - FlipUp: Rot `#e3402a`
  - johanneskuchmetzki.de: Grün `#1f6f5c`
- Body-Hintergrund: mehrere gestapelte `radial-gradient()`-Layer in der
  Akzentfarbe über die ganze Seitenhöhe verteilt — keine flachen
  `.section.alt`-Farbbänder.

## Navigation

- "Floating Pill Nav": am Seitenanfang flach/transparent, wird beim Scrollen
  zur kleineren abgerundeten Pille mit Blur + Schatten (`.scrolled`-Klasse
  via Scroll-Listener). Im gescrollten Zustand etwas dünner (weniger
  Padding).

## Sections & Layout

- Kleiner, zentrierter `.section-divider` (ca. 44×2px, Akzentfarbe) als
  erstes Element jeder Section — trennt Abschnitte visuell, unabhängig von
  der sonstigen Ausrichtung.
- **Keine weißen Boxen/Karten mit Rahmen und Schatten** um Feature-/Prozess-
  Listen — wirkt "KI-mäßig". Stattdessen freistehende Listen mit dünner
  vertikaler Akzentlinie.
- Prozess-/Feature-Listen (z. B. "Vom Deal zum Verkauf", "Warum unter 15
  Mitglieder"):
  - Überschrift + Label der Section zentriert, der Listenblock selbst als
    Gruppe zentriert, aber linksbündiger Text innerhalb.
  - Icon sitzt **neben** der Überschrift jedes Punkts (nicht darüber).
  - Direkt darunter eine dünne (1px) vertikale Akzentlinie, die nur den
    Absatztext einrahmt (nicht die Überschrift) und deren horizontale
    Position genau unter der **Mitte** des Icons liegt.
- Footer: dunkel, mehrspaltig (Brand/Tagline, Link-Spalten, Bottom-Bar mit
  Copyright + Adresse), Social-Icons wo passend.

## Icons

- **Keine** Standard-Emojis und keine einfachen Duotone-/Linien-Icons (wurden
  als "langweilig" bzw. "KI-mäßig" abgelehnt).
- **Kein** Checkmark-Badge auf Icons.
- Gewählter Stil: **streamline-emojis** (Iconify-Set) — flach, bunt, mit
  einheitlicher schwarzer Outline, nicht zu glänzend/3D (wie noto/fluent-
  emoji), nicht zu reduziert (wie flat-color-icons). Bei neuen Icons zuerst
  mehrere Stil-Alternativen als Vergleichsgrafik zeigen, dann erst
  einbauen.
- Icon-Größe in Listen: 32px.

## Fotos

- Echte, selbst gemachte Fotos (Lager, Pakete, Arbeit) statt Stock- oder
  KI-wirkender Bilder — baut Vertrauen/Authentizität auf.
- Foto-Collagen: mehrere überlappende, leicht rotierte Fotos (Polaroid-
  artig). **Wichtig:** Mehrere Collagen auf derselben Seite müssen
  unterschiedliche Layouts haben (andere Anzahl Bilder, andere Positionen/
  Rotationen) — nicht das gleiche Muster kopieren.
- "Proof"-Fotostreifen (scrollende Bilderreihe) wird bei neuen authentischen
  Fotos gerne erweitert.

## Technisches / Workflow

- Vor jedem Push: lokal mit Playwright (Chromium headless) screenshotten und
  visuell prüfen.
- Nach jeder CSS-/Bild-Änderung: Cache-Busting-Query (`?v=N`) auf
  `style.css` und betroffene Bild-`src` hochzählen (GitHub Pages/Browser-
  Caching ist unzuverlässig).
- Rechtliche Seiten (Impressum, Datenschutz, AGB, Widerruf) immer mit
  gleichem Nav-/Footer-Stil wie die Hauptseite synchron halten.
- Bei größeren Stilentscheidungen (z. B. Icon-Stil) immer zuerst mehrere
  konkrete visuelle Optionen zeigen und auswählen lassen, bevor
  implementiert wird. Bei kleinen Text-/Layout-Anpassungen direkt umsetzen.
