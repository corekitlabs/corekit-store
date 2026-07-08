# corekit-store

Modul-Verzeichnis für die corekit-Plattform. Pro Modul eine
Beschreibungsdatei unter `modules/<id>.json` mit den verfügbaren
Versionen; `index.json` ist das automatisch erzeugte
Gesamtverzeichnis.

## Module installieren

Gewünschte Module im Lockfile der Installation eintragen:

```yaml
# platform-config/modules.yaml
registry: https://raw.githubusercontent.com/corekitlabs/corekit-store/main
modules:
  - surveys@1.0.0
  - helpdesk@1.0.0
```

Der Index ist öffentlich; die Modul-Artefakte selbst sind
zugriffsgeschützt. Für die Installation braucht die Umgebung ein
Registry-Token (`MODULES_REGISTRY_TOKEN`).

Publizierte Versionen sind unveränderlich — Korrekturen erscheinen
als neue Version.
