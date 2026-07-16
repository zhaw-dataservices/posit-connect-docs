# Daten aus REDCap laden

Apps auf Posit Connect können Daten direkt aus [ZHAW-REDCap](https://redcap.zhaw.ch/) lesen. Diese Seite beschreibt, wie das eingerichtet wird.

## Beispiel-Repositories

Wir stellen zwei Beispiel-Repositories bereit, die zeigen, wie man Records über die REDCap-API abruft und als Data Frame weiterverwendet:

- [redcap-api-r](https://github.zhaw.ch/service-research-data/redcap-api-r) – für R
- [redcap-api-py](https://github.zhaw.ch/service-research-data/redcap-api-py) – für Python

Beide sind primär als Anleitung fürs lokale Arbeiten gedacht (z. B. in RStudio oder Jupyter), eignen sich aber genauso als Vorlage, um Daten für ein Dashboard zu laden, das später auf Posit Connect veröffentlicht wird – siehe [Lokal arbeiten & Posit Connect](#lokal-arbeiten-posit-connect) unten.

## Voraussetzungen

Du benötigst einen REDCap-API-Token für dein Projekt. Diesen findest du in REDCap unter **Applications > API**; falls noch keiner existiert, bei einer REDCap-Admin-Person anfragen.

## Verbindung herstellen (R)

Siehe [redcap-api-r](https://github.zhaw.ch/service-research-data/redcap-api-r): ein minimales R-Skript mit der Funktion `get_redcap_data()`, das Records aus REDCap als Data Frame liefert – inklusive Anleitung, wie der Export bei Änderungen im REDCap-Projekt über den API Playground aktualisiert wird.

## Verbindung herstellen (Python)

Siehe [redcap-api-py](https://github.zhaw.ch/service-research-data/redcap-api-py): dieselbe Vorgehensweise für Python (`get_redcap_data()`, liefert ein pandas-DataFrame), inklusive Jupyter-Notebook zur Dateninspektion.

## Lokal arbeiten & Posit Connect

Beide Repositories sind in erster Linie dafür gedacht, Daten lokal auf deinem Gerät abzurufen und weiterzuverarbeiten – über eine lokale `secrets.yml`, die nie committet wird. Dasselbe Muster empfehlen wir auch für Dashboards, die später auf Posit Connect deployt werden: `get_redcap_data()` liest die Credentials dort automatisch aus Umgebungsvariablen (Tab **Vars** der App auf Posit Connect) statt aus der Datei, der Code bleibt dabei unverändert.

## API-Token sicher speichern

Tokens gehören nie in den Code oder ins Repository. Lokal in `config/secrets.yml` (gitignored), auf Posit Connect als Umgebungsvariable im Tab **Vars**. Details dazu in den READMEs der beiden Repositories oben.

## Hinweise zum Datenschutz

<!-- TODO: Was ist bei REDCap-Daten besonders zu beachten? -->
