Here’s the **step-by-step to install Git for Windows** and configure VS Code so you can use Git Bash as your default terminal.

---

# 🛠 Step 1 — Download & Install Git for Windows

1. Go to 👉 [https://git-scm.com/download/win](https://git-scm.com/download/win).
   (It will auto-start the download of the `.exe` installer.)
2. Run the installer.

   * When asked **“Adjusting your PATH environment”**, choose:
     ✅ *Git from the command line and also from 3rd-party software*.
   * For terminal emulator, select:
     ✅ *Use MinTTY (the default terminal of MSYS2)*.
   * Keep other defaults unless you have strong preferences.
3. Finish installation.

---

# 🛠 Step 2 — Verify Git installed

Open **Command Prompt** or **PowerShell** and type:

```bash
git --version
```

You should see something like:

```
git version 2.47.0.windows.1
```

---

# 🛠 Step 3 — Launch Git Bash

After installation, you’ll have **Git Bash** in your Start Menu.
Or, right-click in any folder → **Git Bash Here**.
This is your dedicated Git terminal.

---

# 🛠 Step 4 — Configure Git (first time only)

In Git Bash, run:

```bash
git config --global user.name "Watson"
git config --global user.email "your@email.com"
```

This makes sure commits are tied to your identity.

---

# 🛠 Step 5 — Set Git Bash as default terminal in VS Code

1. Open **VS Code**.
2. Press **Ctrl+Shift+P** → type **“Preferences: Open User Settings (JSON)”**.
3. Add this snippet to your settings:

```json
"terminal.integrated.profiles": {
    "Git Bash": {
        "path": "C:\\Program Files\\Git\\bin\\bash.exe"
    }
},
"terminal.integrated.defaultProfile.windows": "Git Bash"
```

4. Save & restart VS Code.

Now, when you press **Ctrl+`** inside VS Code, it opens **Git Bash** by default! 🎉

---

# 🛠 Step 6 — (Optional) Test cloning a repo

In VS Code terminal (Git Bash):

```bash
git clone https://github.com/githubtraining/hellogitworld.git
cd hellogitworld
ls
```

You’ll see files appear in your folder, proving Git + VS Code + Git Bash are working together.

---

✅ At this point, you’re ready to:

* Use Git commands inside VS Code with color syntax highlighting.
* Install the extensions I listed earlier.
* Create & clone your own GitHub private repo for Odoo customizations.
