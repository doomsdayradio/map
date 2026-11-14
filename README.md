# Doomsday Landkarte

Eine interaktive Karte der Doomsday-Welt. Sie stellt das Kartenraster als SVG dar und zeigt Landschaften, Fraktionen, Orte und Handelsrouten.

Die Karte ist unter [doomsday.radio/story/map](https://doomsday.radio/story/map/) erreichbar.

## Karte erkunden

- Die Karte lässt sich durch Ziehen verschieben und per Mausrad oder Schaltflächen zoomen.
- Die Ansichten **Karte**, **Einfluss**, **Relief** und **Bevölkerung** zeigen unterschiedliche Aspekte der Welt.
- Ebenen wie Routen, Orte, Wetter, Wolken und Raster können ein- und ausgeblendet werden. Ein Klick auf Orte oder Flächen zeigt weitere Informationen; für ausgewählte Orte gibt es Links zur Lore.
- Das Raster reicht von X00 bis X111 und Y00 bis Y111. Eine Koordinateneinheit entspricht laut Kartendaten 10 km Luftlinie.

## Projektdateien

- `site/index.html`: Aufbau und Bedienelemente der Karte.
- `site/map.js` und `site/map.css`: Darstellung, Interaktion und Gestaltung.
- `site/layout.json`: Kartendaten für die Darstellung.
- `site/map.txt`: ASCII-Karte und ergänzende Angaben zur Welt.

## Lokal ansehen

Im Projektverzeichnis einen lokalen HTTP-Server starten, beispielsweise mit Python:

```shell
python -m http.server 8000
```

Anschließend `http://localhost:8000/site/` im Browser öffnen. Die Karte lädt ihre Daten per HTTP; direktes Öffnen der HTML-Datei kann deshalb fehlschlagen. Das gemeinsame Stylesheet, Lore-Inhalte und weitere Ressourcen der Doomsday-Website sind in diesem Repository nicht enthalten und stehen lokal möglicherweise nicht zur Verfügung.

## Veröffentlichung

Der GitHub-Workflow veröffentlicht `site/` bei Änderungen auf `main` oder bei manuellem Start nach `map/` im Bunny-S3-Bucket. Dafür benötigt er die Repository-Secrets `WEBSITE_S3_ENDPOINT_URL`, `WEBSITE_S3_PW`, `WEBSITE_S3_ZONE_ID` und `WEBSITE_S3_ZONE_NAME`. Optional aktiviert `NTFY_DOOMSDAY_BUILDS` die Benachrichtigungen.
