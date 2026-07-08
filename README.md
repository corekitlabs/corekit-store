# corekit-store

Kuratierter Modul-Index für corekit (SPECS/module-store.md §4).

- **Eine Datei pro Modul** unter `modules/<id>.json` — PRs kollidieren nicht.
- CI aggregiert bei jedem Push ein `index.json` (Konsumenten-Komfort;
  der corekit-Fetcher liest die per-Modul-Dateien direkt).
- Aufnahme/Update = PR mit Review. Der `digest` je Version ist der
  sha256 des tar.gz-Layers und kommt aus dem Release-Workflow des
  Modul-Repos (Step „Store-Index-Snippet ausgeben").

## Nutzung im Lockfile

```yaml
# platform-config/modules.yaml
registry: https://raw.githubusercontent.com/corekitlabs/corekit-store/main
modules:
  - surveys@1.0.0
  - helpdesk@1.0.0
```

Privat gehostete Artefakte (ghcr) brauchen auf dem Pod
`MODULES_REGISTRY_TOKEN`; ein öffentlicher Store/öffentliche Pakete
laufen anonym.
