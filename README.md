# Mundara Monorepo

This repository hosts all technical parts of the **Mundara project** in a unified monorepo using public Git submodules. It includes frontend, backend, infrastructure, and shared code.

---

## 🧰 Requirements

- Git ≥ 2.25
- Unix-like shell (Linux, macOS, WSL)

---

## 📦 Clone Everything

```bash
# Clone the monorepo with all submodules recursively
git clone --recurse-submodules https://github.com/nak0x/mundara.git
cd mundara
```

If you already cloned the repo without submodules:

```bash
git submodule update --init --recursive
```

## 🔄 Pull Latest Changes
```bash
# Pull latest changes for the monorepo and all submodules
git pull --recurse-submodules
git submodule update --recursive --remote
```

## 🧹 Reset & Clean All Projects
```bash
# Reset main repo and all submodules to latest clean state
git reset --hard
git submodule foreach --recursive git reset --hard
git clean -fdx
git submodule foreach --recursive git clean -fdx
```

## 📁 Project Structure
```text
mundara/
├─*─ Website/         # Frontend (Nuxt, Vercel)
├─*─ Unity/         # Unity experience
├─*─ Track/       # 3D Tracking with OpenCV
├─*─ Doc/      # Documentation for the project
├─── Models/      # 3D models used during the projects
└─── README.md
```
Each starred subfolder is a standalone Git repository (submodule) with its own README and setup instructions.

## 📝 Committing Submodule Updates
If a submodule is updated (e.g., new commits in web/), do the following:

```bash
# Inside the submodule
cd web
git pull origin main

# Back in root
cd ..
git add web
git commit -m "Update web submodule"
git push
```

## ✅ Notes
No authentication required (all submodules are public).

Use git status to track any submodule changes.

Always use --recurse-submodules for operations involving pull/clone.

