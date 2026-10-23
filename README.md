# Persönliche Projekt-Website

Quellcode meiner bestehenden Webseite, die auf eigenem VPS läuft.

## Deployment-Aufbau

Die Docker- und Nginx-Konfiguration bildet den Produktivaufbau dieser Website nach: Nginx läuft im Host-Netzwerk auf Port `63251`; Traefik leitet die Domain `info.fbawidamannserver.cloud` an diesen Port weiter. Die Compose-Datei enthält die Traefik-Labels für den bestehenden Proxy und Sie eine Traefik-Installation samt Middleware `secure-headers@file` voraus und ist nicht als alleinstehender lokaler Compose-Stack gedacht.

Die Website-Dateien werden read-only nach Nginx eingebunden. Nginx-Logs werden separat in `logs/` geschrieben; Logdateien sind nicht Bestandteil dieses Repositories und werden durch `.gitignore` ausgeschlossen.

## Aufbau

- `site/` – HTML-Seiten sowie CSS, Bilder und Schriftdateien
- `Dockerfile` und `nginx.conf` – Nginx-Image und Konfiguration
- `docker-compose.yml` – Compose-Aufbau mit den dazugehörign Traefik-Labels

## Geändert und angepasst hier für GitHub

Persönliche Angaben in den HTML-Seiten sind durch Platzhalter ersetzt worden. Das VPS-Diagramm jedoch zeigt hier die Darstellung meines Servers.
