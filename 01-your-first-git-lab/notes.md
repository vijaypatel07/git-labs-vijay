# 🚀 01 — Your First Git Lab

> **Git Learning Journey — Foundation**

## 👋 Introduction

In this lab, we’ll learn the **basic Git workflow**: creating a repository, checking its status, staging changes, committing snapshots, and viewing project history.

Git can be thought of as a **time machine for your project** — it helps you save meaningful checkpoints and explore your project's history.

---

# 🎯 Objective

By the end of this lab, you will understand how to:

* 📁 Create a Git repository with `git init`
* 🔍 Check repository state with `git status`
* 📝 Create and modify files
* 📦 Stage files with `git add`
* 💾 Save changes with `git commit`
* 📜 View project history with `git log`

---

# 🔑 Key Takeaways

### 🛠️ Commands Used

| Command                   | Purpose                                   |
| ------------------------- | ----------------------------------------- |
| `git init`                | Initialize a Git repository               |
| `git status`              | Check the current state of the repository |
| `git add filename`        | Stage a specific file                     |
| `git add .`               | Stage all changes                         |
| `git commit -m "message"` | Create a commit with a message            |
| `git log`                 | View commit history                       |
| `git log --oneline`       | View compact commit history               |

### ⭐ Core Workflow

```text
EDIT → ADD → COMMIT → HISTORY
```

Or:

```text
Working Directory
       │
       │ git add
       ▼
Staging Area
       │
       │ git commit
       ▼
Git Repository
```

---

# 🕰️ Git as a Time Machine

Git is a **version control system** that keeps track of changes to your files.

Think of Git as a time machine for your project:

* 💾 **Commit** → Save a snapshot of your project
* 📜 **History** → See previous snapshots
* 🌿 **Branch** → Create an alternate timeline
* 🔄 **Checkout / Switch** → Move between timelines
* ↩️ **Reset / Revert** → Undo or restore changes

Without Git, you might end up with files such as:

```text
project-final.zip
project-final-v2.zip
project-final-really-final.zip
project-final-final-2.zip
```

Git gives you a much better way to manage versions.

---

# 1️⃣ Create a Project Directory

First, move to your project directory:

```bash
cd ~/Desktop
```

Create a directory for the Git project:

```bash
mkdir 01-your-first-git-lab
```

Enter the directory:

```bash
cd 01-your-first-git-lab
```

Verify your current location:

```bash
pwd
```

---

# 2️⃣ Initialize a Git Repository

Initialize Git inside the project:

```bash
git init
```

You should see a message similar to:

```text
Initialized empty Git repository in /home/labex/project/my-time-machine/.git/
```

This creates a hidden **`.git`** directory.

The `.git` directory contains the information Git needs to track your project's history.

You can see it with:

```bash
ls -la
```

You should find:

```text
.git
```

> ⚠️ **Important:** Don't manually modify or delete the `.git` directory unless you know exactly what you're doing. Removing it removes the Git repository's history and configuration.

---

# 3️⃣ Check Repository Status

Use:

```bash
git status
```

This shows the current state of your repository.

For a newly initialized repository, you'll typically see something like:

```text
On branch main

No commits yet
nothing to commit
```

### 💡 Habit to Build

When you're unsure what's happening in Git, run:

```bash
git status
```

It's often the fastest way to understand what's going on.

---

# 4️⃣ Create a File

Create a file:

```bash
touch gitlab.txt
```

Check the status again:

```bash
git status
```

Git should report `gitlab.txt` as an **untracked file**.

### 📌 What Does "Untracked" Mean?

An untracked file exists in your working directory, but Git isn't tracking it yet.

---

# 5️⃣ Stage the File

Tell Git that you want to include the file in the next commit:

```bash
git add gitlab.txt
```

Check the status:

```bash
git status
```

The file should now appear under:

```text
Changes to be committed
```

---

# 🧩 Git's Three Important Areas

A simple way to understand the basic Git workflow is:

```text
Working Directory
       │
       │ git add
       ▼
Staging Area
       │
       │ git commit
       ▼
Git Repository
```

## 📂 Working Directory

Where you create and modify files.

## 📦 Staging Area

Where you prepare changes that should be included in the next commit.

## 🗄️ Repository

Where Git permanently records committed snapshots.

---

# 6️⃣ Create Your First Commit

Commit the staged file:

```bash
git commit -m "Add initial notes"
```

The `-m` option lets you provide a commit message.

A commit is essentially a **saved snapshot of your project at a particular point in time**.

### ✅ Good Commit Messages

Good commit messages describe what changed.

For example:

```bash
git commit -m "Add initial project files"
```

### ❌ Avoid Vague Messages

```bash
git commit -m "stuff"
git commit -m "changes"
git commit -m "update"
```

---

# 7️⃣ View Git History

To see your commits:

```bash
git log
```

You'll see information similar to:

```text
commit abc123...
Author: Your Name <you@example.com>
Date:   ...

    Add initial notes
```

The commit contains a unique identifier called a **commit hash**.

### 📜 Compact History

For a shorter and easier-to-read history:

```bash
git log --oneline
```

Example:

```text
abc1234 Add initial notes
```

---

# 🔄 The Basic Git Workflow

The most important workflow from this lab is:

```bash
# Check the repository
git status

# Make changes
touch file.txt

# Stage changes
git add file.txt

# Save a snapshot
git commit -m "Add file.txt"

# View history
git log --oneline
```

### 🧠 In Simple Terms

```text
EDIT → ADD → COMMIT → HISTORY
```

### 🕰️ Time-Traveler Version

```text
Make changes
     ↓
Pack the changes
     ↓
Save a checkpoint
     ↓
Travel through your history
```

---

# 🧠 Key Git Concepts

| Concept                  | Meaning                                  |
| ------------------------ | ---------------------------------------- |
| 📁 **Repository**        | A project tracked by Git                 |
| ⚙️ **`.git`**            | Directory containing Git's internal data |
| 📂 **Working Directory** | Your current project files               |
| ❓ **Untracked**          | A file Git isn't tracking yet            |
| 📦 **Staging Area**      | Changes prepared for the next commit     |
| 💾 **Commit**            | A saved snapshot of your project         |
| 🔑 **Commit Hash**       | Unique identifier for a commit           |
| 📜 **History**           | Record of previous commits               |

---

# 📝 Commands to Remember

## ⚙️ Initialize Git

```bash
git init
```

## 🔍 Check Status

```bash
git status
```

## 📦 Stage a File

```bash
git add filename
```

## 📦 Stage Everything

```bash
git add .
```

## 💾 Commit Changes

```bash
git commit -m "Your commit message"
```

## 📜 View History

```bash
git log
```

## ⚡ View Compact History

```bash
git log --oneline
```

---

# 🚀 What You Learned

You've completed the foundation of Git.

You now understand:

1. ⚙️ `git init` creates a Git repository.
2. 🔍 `git status` shows what's happening in your repository.
3. 📦 `git add` moves changes into the staging area.
4. 💾 `git commit` creates a permanent snapshot.
5. 📜 `git log` lets you explore your project's history.

These commands form the foundation of almost every Git workflow.

---

# 🧭 Quick Mental Model

Remember this:

```text
                Git Repository
                     │
                     │ git commit -m
                     ▲
                     │
              Staging Area
                     ▲
                     │
                     │ git add
                     │
              Working Directory
                     ▲
                     │
                  You edit
```

## ⭐ Core Idea

> **Git lets you save meaningful checkpoints of your project so you can understand, compare, and recover its history.**

And this is only the beginning. 🚀
