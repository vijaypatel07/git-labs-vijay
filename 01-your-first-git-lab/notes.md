# 01 — Your First Git Lab

## 🎯 What You'll Learn

In this lab, you'll learn the basic Git workflow:

* Create a Git repository with `git init`
* Check the state of your repository with `git status`
* Create and modify files
* Stage files with `git add`
* Save changes with `git commit`
* View your project history with `git log`

---

## 🕰️ Git as a Time Machine

Git is a **version control system** that keeps track of changes to your files.

Think of Git as a time machine for your project:

* **Commit** → Save a snapshot of your project
* **History** → See previous snapshots
* **Branch** → Create an alternate timeline
* **Checkout / Switch** → Move between timelines
* **Reset / Revert** → Undo or restore changes

Without Git, you might end up with files such as:

```text
project-final.zip
project-final-v2.zip
project-final-really-final.zip
project-final-final-2.zip
```

Git gives you a much better way to manage versions.

---

# 1. Create a Project Directory

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

You can verify your current location with:

```bash
pwd
```

---

# 2. Initialize a Git Repository

Initialize Git inside the project:

```bash
git init
```

You should see a message similar to:

```text
Initialized empty Git repository in /home/labex/project/my-time-machine/.git/
```

This creates a hidden `.git` directory.

The `.git` directory contains the information Git needs to track your project's history.

You can see it with:

```bash
ls -la
```

You should find:

```text
.git
```

> ⚠️ Don't manually modify or delete the `.git` directory unless you know exactly what you're doing. Removing it removes the Git repository's history and configuration.

---

# 3. Check Repository Status

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

`git status` is one of the most useful Git commands.

### 💡 Habit to Build

When you're unsure what's happening in Git, run:

```bash
git status
```

It's often the fastest way to understand what's going on.

---

# 4. Create a File

Create a file:

```bash
touch gitlab.txt
```

Check the status again:

```bash
git status
```

Git should report `gitlab.txt` as an **untracked file**.

An untracked file exists in your working directory, but Git isn't tracking it yet.

---

# 5. Stage the File

Tell Git that you want to include the file in the next commit:

```bash
git add gitlab.txt
```

Check the status:

```bash
git status
```

The file should now appear under **Changes to be committed**.

### Git's Three Important Areas

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

### Working Directory

Where you create and modify files.

### Staging Area

Where you prepare changes that should be included in the next commit.

### Repository

Where Git permanently records committed snapshots.

---

# 6. Create Your First Commit

Commit the staged file:

```bash
git commit -m "Add initial notes"
```

The `-m` option lets you provide a commit message.

A commit is essentially a **saved snapshot of your project at a particular point in time**.

Good commit messages describe what changed.

For example:

```bash
git commit -m "Add initial project files"
```

Avoid vague messages such as:

```bash
git commit -m "stuff"
git commit -m "changes"
git commit -m "update"
```

---

# 7. View Git History

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

In simple terms:

```text
EDIT → ADD → COMMIT → HISTORY
```

Or, in our time-traveler language:

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

| Concept           | Meaning                                  |
| ----------------- | ---------------------------------------- |
| Repository        | A project tracked by Git                 |
| `.git`            | Directory containing Git's internal data |
| Working Directory | Your current project files               |
| Untracked         | A file Git isn't tracking yet            |
| Staging Area      | Changes prepared for the next commit     |
| Commit            | A saved snapshot of your project         |
| Commit Hash       | Unique identifier for a commit           |
| History           | Record of previous commits               |

---

# 📝 Commands to Remember

### Initialize Git

```bash
git init
```

### Check status

```bash
git status
```

### Stage a file

```bash
git add filename
```

### Stage everything

```bash
git add .
```

### Commit changes

```bash
git commit -m "Your commit message"
```

### View history

```bash
git log
```

### View compact history

```bash
git log --oneline
```

---

# 🚀 What You Learned

You've completed the foundation of Git.

You now understand:

1. `git init` creates a Git repository.
2. `git status` shows what's happening in your repository.
3. `git add` moves changes into the staging area.
4. `git commit` creates a permanent snapshot.
5. `git log` lets you explore your project's history.

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

The core idea is simple:

> **Git lets you save meaningful checkpoints of your project so you can understand, compare, and recover its history.**

And this is only the beginning. 🚀
