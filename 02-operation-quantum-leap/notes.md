# ⚡ 02 — Operation Quantum Leap

> **Git Learning Journey**

This lesson covers the **basic Git workflow**: creating a project, initializing Git, staging changes, committing them, and verifying Git history.

The core flow is:

```text
Create → Initialize → Add → Stage → Commit → Verify
```

---

## 🎯 Objective

Practice the basic Git workflow:

* 📁 Create a project directory
* 🧰 Initialize a Git repository
* 📄 Create a file with specific content
* ➕ Stage changes
* 💾 Create a commit
* 📜 Check Git history
* ✅ Verify your work

---

# 🔑 Key Takeaways

### 📌 Essential Git Commands

| Command                           | Purpose                               |
| --------------------------------- | ------------------------------------- |
| `mkdir <directory>`               | 📁 Create a directory                 |
| `cd <directory>`                  | 🚶 Move into a directory              |
| `pwd`                             | 📍 Show current location              |
| `git init`                        | 🧰 Initialize a Git repository        |
| `ls -la`                          | 👀 Show files, including hidden files |
| `echo "content" > file.txt`       | 📄 Create/write content to a file     |
| `cat file.txt`                    | 📖 Display file contents              |
| `git status`                      | 🔍 Check repository status            |
| `git add <file>`                  | ➕ Stage a file                        |
| `git commit -m "message"`         | 💾 Create a commit                    |
| `git log`                         | 📜 View Git history                   |
| `git log --oneline`               | 📜 View compact Git history           |
| `git log --oneline -1`            | 🔎 View the latest commit             |
| `git commit --amend -m "message"` | ✏️ Correct the latest commit message  |

### 🧠 Most Important Concept

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

> **`git add` prepares changes. `git commit` saves them to Git history.**

---

# 1️⃣ Create the Project Directory

Move to the project directory:

```bash
cd ~/git-labs-vijay
```

Create the project:

```bash
mkdir 02-operation-quantum-leap
```

Enter the directory:

```bash
cd 02-operation-quantum-leap
```

Verify your location:

```bash
pwd
```

Expected location:

```text
~/git-labs-vijay/02-operation-quantum-leap
```

---

# 2️⃣ Initialize the Git Repository

Initialize Git:

```bash
git init
```

Git creates a hidden `.git` directory containing the repository's internal data.

Verify it:

```bash
ls -la
```

You should see:

```text
.git
```

### 💡 Key Idea

`git init` turns an existing directory into a Git repository.

---

# 3️⃣ Create the Classified File

Create `classified.txt` with the required content:

```bash
echo "The flux capacitor requires 1.21 gigawatts of power." > classified.txt
```

Check the contents:

```bash
cat classified.txt
```

Expected:

```text
The flux capacitor requires 1.21 gigawatts of power.
```

### 💡 Shell Concept — `>`

The `>` operator redirects command output into a file.

For example:

```bash
echo "Hello" > example.txt
```

creates `example.txt` containing:

```text
Hello
```

---

# 4️⃣ Check Git Status

Run:

```bash
git status
```

Git should show `classified.txt` as an **untracked file**.

### 🧠 What Does "Untracked" Mean?

An untracked file:

* 📁 Exists in your project directory
* ❌ Is not being tracked by Git yet

---

# 5️⃣ Stage the File

Stage the file:

```bash
git add classified.txt
```

Check the status:

```bash
git status
```

The file should now appear under:

```text
Changes to be committed
```

### 🧠 Git Workflow

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

> ⚠️ `git add` does **not** create a commit.
> It prepares changes for the next commit.

---

# 6️⃣ Create the Commit

Create the commit using the **exact required message**:

```bash
git commit -m "Add top-secret flux capacitor information"
```

A commit creates a snapshot of the staged changes.

The commit will have a unique hash, for example:

```text
abc1234
```

The actual hash will be different on your system.

---

# 7️⃣ Verify the Commit

Check the repository:

```bash
git status
```

You should see:

```text
nothing to commit, working tree clean
```

View the latest commit:

```bash
git log --oneline -1
```

Expected:

```text
abc1234 Add top-secret flux capacitor information
```

The hash will differ, but the commit message should match exactly.

---

# 🧠 Important Git Concepts

| Concept              | Meaning                              |
| -------------------- | ------------------------------------ |
| 📦 Repository        | A directory managed by Git           |
| ⚙️ `.git`            | Git's internal repository data       |
| 📁 Working Directory | Your current project files           |
| ❓ Untracked          | A file Git doesn't track yet         |
| 📋 Staging Area      | Changes prepared for the next commit |
| 💾 Commit            | A saved snapshot of staged changes   |
| 🔑 Commit Hash       | Unique identifier for a commit       |
| 📜 Git History       | Collection of commits                |

---

# 📝 Commands to Remember

### 📁 Create a Directory

```bash
mkdir 02-operation-quantum-leap
```

### 🚶 Move Into It

```bash
cd 02-operation-quantum-leap
```

### 🧰 Initialize Git

```bash
git init
```

### 🔍 Check Status

```bash
git status
```

### 📄 Create a File

```bash
echo "content" > filename.txt
```

### ➕ Stage a File

```bash
git add filename.txt
```

### 💾 Commit Changes

```bash
git commit -m "Commit message"
```

### 📜 View History

```bash
git log
```

### 📜 View Compact History

```bash
git log --oneline
```

---

# 🎯 Exact Commit Messages

When a challenge specifies an exact commit message, match it **character-for-character**.

Correct:

```bash
git commit -m "Add top-secret flux capacitor information"
```

Different capitalization, wording, or punctuation may fail an automated check.

For example, these are different messages:

```text
add top-secret flux capacitor information
Add Top-Secret Flux Capacitor Information
Add top-secret flux capacitor information.
```

---

# 🛠️ Beginner-Friendly Troubleshooting

## ❌ `git: command not found`

Check whether Git is installed:

```bash
git --version
```

If Git isn't available, follow your environment's instructions for installing it.

---

## ❌ `fatal: not a git repository`

You're probably outside the repository.

Check your location:

```bash
pwd
```

Then check for `.git`:

```bash
ls -la
```

Make sure you're inside:

```text
~/git-labs-vijay/02-operation-quantum-leap
```

If this is the correct project and Git hasn't been initialized:

```bash
git init
```

---

## ℹ️ `nothing to commit, working tree clean`

This is **not an error**.

It means Git has no new changes waiting to be committed.

Check your history:

```bash
git log --oneline
```

---

## ❓ File Is Untracked

If `git status` shows:

```text
Untracked files:
    classified.txt
```

Stage it:

```bash
git add classified.txt
```

Then verify:

```bash
git status
```

---

## ❓ Changes Are Not Staged

If Git shows:

```text
Changes not staged for commit
```

Stage the file again:

```bash
git add classified.txt
```

Then commit:

```bash
git commit -m "Add top-secret flux capacitor information"
```

### ⚠️ Important

If you modify a file **after** `git add`, the new modification needs to be staged again.

---

## 👤 Git Asks for Your Name and Email

Configure your Git identity:

```bash
git config --global user.name "Your Name"
git config --global user.email "you@example.com"
```

Then retry the commit.

---

## ✏️ Commit Message Is Incorrect

Check the latest commit:

```bash
git log --oneline -1
```

If you need to correct the latest commit before sharing it:

```bash
git commit --amend -m "Add top-secret flux capacitor information"
```

> ⚠️ Be careful with `--amend` once a commit has already been shared with others.

---

# 🧪 Final Verification

Run these commands:

```bash
pwd
git status
cat classified.txt
git log --oneline -1
```

Verify that:

* 📍 You're inside `~/git-labs-vijay/02-operation-quantum-leap`
* 📄 `classified.txt` contains the expected text
* ✅ The working tree is clean
* 📜 The latest commit has the required message

---

# 🏆 Key Takeaway

The basic Git workflow is:

```text
Create or modify files
        ↓
   git status
        ↓
      git add
        ↓
   git status
        ↓
     git commit
        ↓
git log --oneline
```

### ⭐ Remember

> **`git add` prepares changes. `git commit` saves them to Git history.**

⚡ You've now completed another step in your Git learning journey.
