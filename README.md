# Persönliche Projekt-Website

Statischer Quellcode der Projekt- und Portfolio-Website. Die Website besteht aus HTML, CSS und lokal gespeicherten Bildern und Schriftarten.

## Deployment-Aufbau

Die Docker- und Nginx-Konfiguration bildet den Produktivaufbau dieser Website nach: Nginx läuft im Host-Netzwerk auf Port `63251`; Traefik leitet die Domain `info.fbawidamannserver.cloud` an diesen Port weiter. Die Compose-Datei enthält die Traefik-Labels für den bestehenden Proxy. Sie setzt also eine passende Traefik-Installation samt Middleware `secure-headers@file` voraus und ist nicht als alleinstehender lokaler Compose-Stack gedacht.

Die Website-Dateien werden read-only nach Nginx eingebunden. Nginx-Logs werden separat in `logs/` geschrieben; Logdateien sind nicht Bestandteil dieses Repositories und werden durch `.gitignore` ausgeschlossen.

## Lokal testen

Ohne Traefik kann der Webinhalt mit einem beliebigen statischen Webserver ausgeliefert werden. Für den originalen Docker-Aufbau sind Host-Netzwerk und die beschriebene Traefik-Umgebung erforderlich.

## Aufbau

- `site/` – HTML-Seiten sowie CSS, Bilder und Schriftdateien
- `Dockerfile` und `nginx.conf` – Nginx-Image und Konfiguration
- `docker-compose.yml` – produktiver Compose-Aufbau mit Traefik-Labels

## Vor einer Veröffentlichung anpassen

Persönliche Angaben in den HTML-Seiten sind durch Platzhalter ersetzt. Das VPS-Diagramm in diesem Repository entspricht der öffentlichen Live-Konfiguration und zeigt deren öffentliche IP und Domain.

Die Datei `site/mc/starwars.zip` und Server-Logs sind nicht enthalten.

Bitte vor Veröffentlichung prüfen, dass alle verwendeten Bilder, Diagramme und Schriftdateien veröffentlicht werden dürfen. Ein Repository-Lizenztext ist bewusst nicht vorgegeben.
