# 🔁 n8n_Backup_on_GitHub

Automagically back up your **n8n workflows** to your **GitHub repo** — because even your automation deserves a safety net 😌

---

## 🧠 What it does

Every day (or whenever you like — you're the boss), this n8n workflow will:

- 🔍 Check which workflows have changed
- 📦 Save only the modified ones (no spam commits!)
- 🏷️ Also manage their tags (optional)
- ☁️ Push them to your GitHub repository

Yes, it’s like version control for your automation empire 🏛️

---

## 🧱 How it works

This project consists of **two workflows**:
1. **Main Workflow** – Loops through all your workflows and handles the scheduling
2. **Subworkflow** – Handles file comparison and GitHub upload (create or update)

You’ll need to import **both** into n8n.

---

## ⚙️ Setup instructions

### 1. GitHub Access

You'll need:
- A **GitHub account**
- A **personal access token** (PAT) with `repo` scope (for private repos)

Create it [here](https://github.com/settings/tokens) — and don’t forget to copy it (because GitHub won’t remind you 😬)

Then, create a credential in n8n called **`GitHub account`** (or another name, but match it in the workflow).

---

### 2. GitHub Repo Structure

The subworkflow pushes `.json` files to your repo. The default path is:
name_ID.json
