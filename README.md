# configs

Meine persönlichen Konfigurationen für Dev-Tools.

## Codex CLI

- `codex/config.toml`: portable Codex CLI defaults.

**Installation:**
```bash
mkdir -p ~/.codex
cp codex/config.toml ~/.codex/config.toml
```

---

## Fish Shell

### ga / gd - Parallele Git-Entwicklung

Funktionen für Multi-Agent-Workflows, wo mehrere AI-Agents gleichzeitig arbeiten.

- `ga <name>`: Erstellt einen Clone mit `--reference` (schnell, platzsparend)
- `gd`: Löscht Clone mit Sicherheitschecks (warnt bei uncommitted/unpushed)

**Abhängigkeiten:**
```bash
brew install fzf gum
```

**Installation:**
```fish
mkdir -p ~/.config/fish/functions
cp fish/functions/*.fish ~/.config/fish/functions/
```

**Nutzung:**
```fish
cd ~/mein-projekt
ga feature-name    # → ../mein-projekt-feature-name auf branch agent/feature-name

cd ../mein-projekt-feature-name
gd                 # → löscht den Clone (mit Bestätigung)
```

---

## Hinweis

Nicht einfach kopieren - schau dir die Files genau an und nimm nur das, was für dich Sinn macht.
