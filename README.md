# Intro to Python

Dieses Projekt enthält eine Konfiguration für ein Starter-Projekt für den Einstieg in die Python-Entwicklung.

## Verwendete Werkzeuge

1. **[pyenv]()** (Management der Python-Version, .python-version): 
2. **[poetry]()** (Management von Abhängigkeiten: `pyproject.toml`, `poetry.lock`. Verzeichnis `.venv`)
3. **[Development Containers](https://containers.dev/)** (Konsistente Entwicklungsumgebungen in der Cloud via [CodeSpaces](https://github.com/features/codespaces) oder lokal mit [Docker](https://www.docker.com/products/docker-desktop/)) `.devcontainer`, [`.devcontainer/devcontainer.json`](./.devcontainer/devcontainer.json), [`.devcontainer/Dockerfile`](./.devcontainer/Dockerfile) 
4. **[VS Code](https://code.visualstudio.com/)**

## Abhängigkeiten

siehe `.python-version`, `pyproject.toml`, `poetry.lock`

## Verwendung

### Voraussetzungen

1. [VS Code](https://code.visualstudio.com/) + [Docker](https://www.docker.com/products/docker-desktop/)-Installation oder [CodeSpaces](https://github.com/features/codespaces)

Im Dev Container bereits installiert:

2. [Python 3.12](https://www.python.org/) 
3. [Poetry](https://python-poetry.org/docs/)


### 1. Git-Checkout

```
git clone  ...
```

### 2. Abhängigkeiten installieren

Wir benutzen [Poetry](https://python-poetry.org) für das Management der Abhängigkeiten (3rd Party Packages). Dazu wollen wir im Projektverzeichnis ein Verzeichnis `.venv` nutzen, welches eine virtuelle Python-Umgebung für unser jeweiliges Projekt beinhaltet. Auf diesem Wege kommen sich ggf. verschiedene Versionen von Packages oder Python nicht in die Quere.

Die Poetry-Konfiguration lässt sich abfragen:

```shell
poetry config --list
```

Die Poetry-Konfiguration sollte folgende Einstellungen enthalten:

```shell
...
virtualenvs.create = true
virtualenvs.in-project = true
virtualenvs.prefer-active-python = true
...
```

Die Einstellungen lassen sich setzen mit:

```shell
poetry config virtualenvs.create true
poetry config virtualenvs.in-project true
poetry config virtualenvs.prefer-active-python true
```

Die Einstellungen sollten im Dev Container bereits korrekt gesetzt sein.

Nach dem `git clone ...` aus dem Git-Repository können die Abhängigkeiten mit 

```
poetry install
```

installiert werden.

### 3. Jupyter Notebooks öffnen und bearbeiten

...