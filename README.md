# csp-header-util

Kleine lokale Utility zum Parsen, Bearbeiten und Zusammenführen von **Content-Security-Policy**-Headern.

## Was die App macht

Die Anwendung besteht aus einer einzelnen Datei: **`index.html`**.
Sie läuft komplett lokal im Browser (auch direkt über `file://`, ohne Dev-Server, ohne Build-Step, ohne Framework, ohne externe Libraries).

Funktionen:

- Zwei Eingabefelder für **CSP A** und **CSP B**
- Akzeptiert entweder
  - eine komplette Header-Zeile wie
    `Header set Content-Security-Policy "..."`
  - oder einen reinen CSP-String
- Button **„Analysieren“**:
  - nur ein Feld befüllt → diese eine CSP wird geparst
  - beide Felder befüllt → beide CSPs werden gemerged
- Direktiven mit gleichem Namen werden zusammengeführt
- Einträge innerhalb einer Direktive werden dedupliziert (Reihenfolge bleibt möglichst erhalten)
- Gefundene Direktiven werden übersichtlich angezeigt
- Einträge können pro Direktive entfernt werden
- Neue Einträge können pro Direktive hinzugefügt werden
- Ausgabe wird bei jeder Änderung sofort neu generiert:
  - reiner CSP-String
  - vollständige `.htaccess`-Header-Zeile
- Für beide Ausgaben gibt es einen **Kopieren**-Button

## Nutzung

1. `index.html` im Browser öffnen
2. CSP in Feld A und optional Feld B einfügen
3. **Analysieren** klicken
4. Einträge bearbeiten (entfernen/hinzufügen)
5. Ergebnis kopieren
