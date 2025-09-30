# Must-have VS Code extensions

* Python: `ms-python.python`
* Pylance (fast IntelliSense): `ms-python.vscode-pylance`
* Black (formatter): `ms-python.black-formatter`
* Ruff (lint + import sort, super fast): `charliermarsh.ruff`
* XML (for views/QWeb): `redhat.vscode-xml`
* Jinja (QWeb templating syntax): `samuelcolvin.jinjahtml`
* YAML (for manifests/CI): `redhat.vscode-yaml`
* ESLint (for JS/Owl): `dbaeumer.vscode-eslint`
* Prettier (JS/SCSS formatting): `esbenp.prettier-vscode`
* Docker (if you run Odoo/Postgres in containers): `ms-azuretools.vscode-docker`
* Git UI superpowers: `eamodio.gitlens`
* Live pair-coding: `ms-vsliveshare.vsliveshare`
* EditorConfig support: `EditorConfig.EditorConfig`
* Path autocomplete: `christian-kohler.path-intellisense`

Let’s install **one** extension — the **Python** extension for VS Code.

# Install via the GUI (easiest)

1. Open **Visual Studio Code**.
2. Go to **Extensions**: left sidebar icon with four squares (or press **Ctrl+Shift+X** on Windows/Linux, **Cmd+Shift+X** on Mac).
3. In the search box, type **Python**.
4. Click **Python** (publisher: **Microsoft**) → click **Install**.
5. If prompted, click **Reload**. If it offers **Pylance**, accept/install.

### Verify it worked

* Open any `*.py` file: you should see **syntax colors** immediately.
* In the bottom status bar, click **“Python 3.x”** or **“Select Interpreter”** and choose your environment (e.g., your `.venv`).
* Try a quick run: add `print("hello")`, then click **Run ▶** (top-right) or right-click → **Run Python File in Terminal**.

---

# (Optional) Install via command line

* Make sure the `code` command is in your PATH (on macOS: **Cmd+Shift+P** → “**Shell Command: Install 'code' command in PATH**”).
* Then run:

```bash
code --install-extension ms-python.python
```

Perfect, Watson ⚡ Here’s the exact shell command for each extension (assuming you have the `code` command in your PATH — if not, I can show you how to enable it).

```bash
# Python
code --install-extension ms-python.python

# Pylance (IntelliSense)
code --install-extension ms-python.vscode-pylance

# Black (Python formatter)
code --install-extension ms-python.black-formatter

# Ruff (linting + import sort)
code --install-extension charliermarsh.ruff

# XML (for Odoo views/QWeb)
code --install-extension redhat.vscode-xml

# Jinja (QWeb templating syntax)
code --install-extension samuelcolvin.jinjahtml

# YAML (for manifests / configs)
code --install-extension redhat.vscode-yaml

# ESLint (for JS / Owl)
code --install-extension dbaeumer.vscode-eslint

# Prettier (JS / SCSS formatter)
code --install-extension esbenp.prettier-vscode

# Docker (Odoo/Postgres in containers)
code --install-extension ms-azuretools.vscode-docker

# GitLens (Git superpowers)
code --install-extension eamodio.gitlens

# Live Share (pair programming)
code --install-extension ms-vsliveshare.vsliveshare

# EditorConfig (respect .editorconfig)
code --install-extension EditorConfig.EditorConfig

# Path Autocomplete
code --install-extension christian-kohler.path-intellisense
```

---

👉 You can copy-paste them **one by one** into your terminal, or run them all at once:

```bash
code --install-extension ms-python.python \
&& code --install-extension ms-python.vscode-pylance \
&& code --install-extension ms-python.black-formatter \
&& code --install-extension charliermarsh.ruff \
&& code --install-extension redhat.vscode-xml \
&& code --install-extension samuelcolvin.jinjahtml \
&& code --install-extension redhat.vscode-yaml \
&& code --install-extension dbaeumer.vscode-eslint \
&& code --install-extension esbenp.prettier-vscode \
&& code --install-extension ms-azuretools.vscode-docker \
&& code --install-extension eamodio.gitlens \
&& code --install-extension ms-vsliveshare.vsliveshare \
&& code --install-extension EditorConfig.EditorConfig \
&& code --install-extension christian-kohler.path-intellisense
```

---


# Recommended workspace settings

Create `.vscode/settings.json` in your repo:

```json
{
  "editor.formatOnSave": true,
  "[python]": {
    "editor.defaultFormatter": "ms-python.black-formatter",
    "editor.codeActionsOnSave": {
      "source.fixAll.ruff": true,
      "source.organizeImports.ruff": true
    }
  },
  "ruff.lint.args": ["--line-length=100"],
  "python.analysis.typeCheckingMode": "basic",
  "python.testing.pytestEnabled": true,
  "python.defaultInterpreterPath": "${workspaceFolder}/.venv/bin/python",
  "files.eol": "\n",
  "xml.format.splitAttributes": true,
  "xml.format.joinContentLines": false,
  "xml.preferences.quoteStyle": "double",
  "yaml.validate": true,
  "editor.tabSize": 4,
  "editor.rulers": [100],
  "git.confirmSync": false
}
```

# Launch Odoo from VS Code (debuggable)

`.vscode/launch.json`:

```json
{
  "version": "0.2.0",
  "configurations": [
    {
      "name": "Odoo 19 (dev)",
      "type": "python",
      "request": "launch",
      "program": "${workspaceFolder}/odoo/odoo-bin",
      "python": "${workspaceFolder}/.venv/bin/python",
      "args": [
        "-c", "${workspaceFolder}/dev/odoo.conf",
        "-d", "dev",
        "--addons-path", "${workspaceFolder}/addons,${workspaceFolder}/odoo/addons"
      ],
      "console": "integratedTerminal",
      "justMyCode": true
    }
  ]
}
```

# Optional tasks (run DB/services)

`.vscode/tasks.json`:

```json
{
  "version": "2.0.0",
  "tasks": [
    { "label": "Compose up", "type": "shell", "command": "docker compose up -d" },
    { "label": "Compose down", "type": "shell", "command": "docker compose down" },
    { "label": "Init venv", "type": "shell", "command": "python3 -m venv .venv && . .venv/bin/activate && pip install -U pip wheel && pip install -r requirements.txt" }
  ]
}
```

# Pre-commit (keep the repo clean automatically)

Add `.pre-commit-config.yaml`:

```yaml
repos:
  - repo: https://github.com/astral-sh/ruff-pre-commit
    rev: v0.6.9
    hooks:
      - id: ruff
        args: [--fix, --unsafe-fixes]
      - id: ruff-format
  - repo: https://github.com/psf/black
    rev: 24.8.0
    hooks:
      - id: black
```

Then:

```bash
pip install pre-commit
pre-commit install
```

# Nice-to-have files

`.editorconfig` (consistent tabs/line endings):

```
root = true
[*]
end_of_line = lf
insert_final_newline = true
charset = utf-8
indent_style = space
indent_size = 4
```

`.gitignore` (Python + Odoo basics):

```
.venv/
__pycache__/
*.pyc
.vscode/
.env
.idea/
*.log
.odoo_*
/addons/*/static/*/lib/
/dist/
/build/
```

# How you’ll work day-to-day

* You both open the repo in **VS Code** → enjoy full **color syntax** for Python/XML/QWeb/JS.
* Use the **Source Control** panel for commits/push/pull.
* Start a **Live Share** session when you want to edit the same files together in real time.
* Hit **Run → “Odoo 19 (dev)”** to debug with breakpoints, watches, call stacks.
