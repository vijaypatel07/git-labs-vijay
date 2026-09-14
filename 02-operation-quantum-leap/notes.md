# 02 — Operation Quantum Leap

## 🎯 Objective

Practice the basic Git workflow:

```text
Create → Initialize → Add → Stage → Commit → Verify
```

You'll practice:

* Creating a project directory
* Initializing a Git repository
* Creating a file with specific content
* Staging changes
* Creating a commit
* Checking Git history
* Verifying your work

---

# 1. Create the Project Directory

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

# 2. Initialize the Git Repository

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

### Key idea

`git init` turns an existing directory into a Git repository.

---

# 3. Create the Classified File

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

### 💡 Shell concept

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

# 4. Check Git Status

Run:

```bash
git status
```

Git should show `classified.txt` as an **untracked file**.

An untracked file exists in your project directory, but Git isn't tracking it yet.

---

# 5. Stage the File

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

### Git workflow

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

`git add` does **not** create a commit. It prepares changes for the next commit.

---

# 6. Create the Commit

Create the commit using the exact required message:

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

# 7. Verify the Commit

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

# 🧠 Important Concepts

| Concept           | Meaning                              |
| ----------------- | ------------------------------------ |
| Repository        | A directory managed by Git           |
| `.git`            | Git's internal repository data       |
| Working Directory | Your current project files           |
| Untracked         | A file Git doesn't track yet         |
| Staging Area      | Changes prepared for the next commit |
| Commit            | A saved snapshot of staged changes   |
| Commit Hash       | Unique identifier for a commit       |
| Git History       | Collection of commits                |

---

# 📝 Commands to Remember

### Create a directory

```bash
mkdir 02-operation-quantum-leap
```

### Move into it

```bash
cd 02-operation-quantum-leap
```

### Initialize Git

```bash
git init
```

### Check status

```bash
git status
```

### Create a file

```bash
echo "content" > filename.txt
```

### Stage a file

```bash
git add filename.txt
```

### Commit changes

```bash
git commit -m "Commit message"
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

# 🎯 Exact Commit Messages

When a challenge specifies an exact commit message, match it character-for-character.

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

## `git: command not found`

Check whether Git is installed:

```bash
git --version
```

If Git isn't available, follow your environment's instructions for installing it.

---

## `fatal: not a git repository`

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

## `nothing to commit, working tree clean`

This is **not an error**.

It means Git has no new changes waiting to be committed.

Check your history:

```bash
git log --oneline
```

---

## File is untracked

If `git status` shows:

```text
Untracked files:
    classified.txt
```

stage it:

```bash
git add classified.txt
```

Then verify:

```bash
git status
```

---

## Changes are not staged

If Git shows:

```text
Changes not staged for commit
```

stage the file again:

```bash
git add classified.txt
```

Then commit:

```bash
git commit -m "Add top-secret flux capacitor information"
```

Remember: if you modify a file **after** `git add`, the new modification needs to be staged again.

---

## Git asks for your name and email

Configure your Git identity:

```bash
git config --global user.name "Your Name"
git config --global user.email "you@example.com"
```

Then retry the commit.

---

## Commit message is incorrect

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

* You're inside `~/git-labs-vijay/02-operation-quantum-leap`
* `classified.txt` contains the expected text
* The working tree is clean
* The latest commit has the required message

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

Remember:

> **`git add` prepares changes. `git commit` saves them to Git history.**

You've now completed another step in your Git journey. 🕰️⚡
