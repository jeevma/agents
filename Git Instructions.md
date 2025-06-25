To contribute to a **community GitHub repository** (e.g., an open-source project), and **keep your fork updated** while pushing your changes to your **own GitHub account**, follow these steps:

---

## ✅ Use Case:

* You cloned a community repo (e.g., `https://github.com/community-org/project`)
* You made some changes
* Now, you want to:

  * Push your version to your GitHub account (e.g., `https://github.com/yourusername/project`)
  * Keep pulling updates from the **original community repo**

---

## 🧭 Step-by-Step Guide

### 🔁 1. **Fork the community repository on GitHub**

* Go to the repo on GitHub (e.g., `https://github.com/community-org/project`)
* Click **Fork** (top-right) → Select your GitHub account

Now you have:
✅ Your fork: `https://github.com/yourusername/project`
✅ Original repo: `https://github.com/community-org/project`

---

### 💻 2. **Set up your local repo**

If you already cloned from the community repo:

```bash
git clone https://github.com/community-org/project.git
cd project
```

---

### 🔄 3. **Change the origin to your fork**

```bash
git remote set-url origin https://github.com/yourusername/project.git
```

✅ Now `origin` points to **your fork**.

---

### ➕ 4. **Add the original repo as `upstream`**

```bash
git remote add upstream https://github.com/community-org/project.git
```

✅ Now:

* `origin` → your GitHub repo
* `upstream` → original community repo

---

### 📂 5. **Check remote setup**

```bash
git remote -v
```

Expected output:

```bash
origin    https://github.com/yourusername/project.git (fetch)
origin    https://github.com/yourusername/project.git (push)
upstream  https://github.com/community-org/project.git (fetch)
upstream  https://github.com/community-org/project.git (push)
```

---

### 🚀 6. **Push your changes to your fork**

```bash
git push origin main
```

*(Replace `main` with your branch name if different)*

---

### 🔁 7. **Pull future updates from the community repo**

When you want to sync your local copy with the original repo:

```bash
git fetch upstream
git checkout main
git merge upstream/main
```

If you want to rebase instead of merge:

```bash
git rebase upstream/main
```

---

### 📤 8. **(Optional) Push merged changes to your GitHub fork**

```bash
git push origin main
```

---

## 💡 Tip: Keep your fork always in sync

You can create a script or use GitHub CLI to periodically sync your fork with `upstream`.

---

Would you like a **Git alias script** or a **GitHub Action** to automate syncing your fork with upstream?
