**step-by-step guide** to set you and your collaborator up with a **GitHub private repo** for your Odoo code.

---

# 🛠 Step 1 — Create your GitHub account

1. Go to [github.com](https://github.com).
2. Create a free account (choose a username, email, password).
3. Verify your email.

💡 On the **free plan**, you already get unlimited **private repositories** with unlimited collaborators.

---

# 🛠 Step 2 — Create a private repository

1. Once logged in, click the **+** in the top-right corner → **New repository**.
2. Name it something like `odoo-addons` or `odoo-snippets`.
3. **Description**: “Private repo for Odoo custom modules and code snippets.”
4. Select **Private** (important).
5. Initialize with:

   * ✔️ a README file
   * ✔️ a `.gitignore` (choose “Python”)
6. Click **Create repository**.

---

# 🛠 Step 3 — Invite your collaborator

1. In your new repo → go to **Settings** → **Collaborators**.
2. Click **Add people**, enter your collaborator’s GitHub username or email.
3. Choose **Write access** (so they can push changes).

They’ll receive an email invitation — once they accept, you’re linked.

---

# 🛠 Step 4 — Install Git locally

On each of your computers:

* [Download Git](https://git-scm.com/downloads) and install.
* Verify install:

  ```bash
  git --version
  ```

Optional but recommended: set your name/email globally:

```bash
git config --global user.name "Watson"
git config --global user.email "your@email.com"
```

---

# 🛠 Step 5 — Clone the repo locally

In a folder where you want your code to live:

```bash
git clone https://github.com/<your-username>/odoo-addons.git
cd odoo-addons
```

Now you both have a **local copy** of the repo.

---

# 🛠 Step 6 — Work on your code

Example: add a Python file for an Odoo model.

```bash
echo "# My Odoo customization" > models.py
```

Then save it into Git:

```bash
git add models.py
git commit -m "Add first customization snippet"
git push
```

Your collaborator runs:

```bash
git pull
```

…and they’ll see your changes.

---

# 🛠 Step 7 — Optional: Pair programming (real-time)

If you want to edit code together **live** (like Google Docs):

1. Install [Visual Studio Code](https://code.visualstudio.com/).
2. Install the **Live Share extension** (free, from Microsoft).
3. Open your repo in VS Code → click “Live Share” → copy the invite link.
4. Your collaborator clicks the link and joins your session.

Now you’re both typing in the **same files in real time**, while the repo still keeps everything under Git.

---

✅ That’s it!
Now you have:

* A **secure private repo** to store and share your Odoo customizations/snippets.
* A workflow to either work **async** (push/pull with Git) or **sync** (pair coding with Live Share).


