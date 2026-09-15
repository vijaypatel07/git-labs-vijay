# ⏳ 04 — Time Machine Identity Configuration

In this lab, we learn how to configure a **Git identity globally** and then **override that identity locally** for a specific repository.
This helps you understand how Git decides which `user.name` and `user.email` to use when creating commits.

---

## 🔑 Key Takeaways

* 🌍 `git config --global` sets **user-wide Git settings**.
* 📁 `git config` inside a repository sets **local repository settings**.
* ⚡ **Local settings override global settings.**
* 🎯 You can override only one part of the identity, such as `user.name`.
* 🔍 `git config --local --list` shows repository-specific settings.
* 🌍 `git config --global --list` shows global settings.
* 🧠 `git config user.name` and `git config user.email` show the **effective values** Git will use in the current repository.

---

## 🎯 Objective

Learn how to:

1. Set your Git identity **globally**.
2. Set a different identity value **locally** for a specific repository.
3. Understand how **local configuration overrides global configuration**.
4. Check the effective Git identity for the current repository.

---

# 🧪 1. Lab Setup

Create the lab directory and initialize it as a Git repository:

```bash
cd ~/git-labs-vijay
mkdir 04-time-machine-identity-configuration
cd 04-time-machine-identity-configuration
git init
```

### ✅ Check the repository

```bash
git status
```

You should now be inside a Git repository.

---

# 🌍 2. Set Global Git Identity

A **global Git identity** applies to your Git repositories by default.

### 👤 Set global username

```bash
git config --global user.name "vijay patel"
```

### 📧 Set global email

```bash
git config --global user.email "vijay@timestream.com"
```

### 🔍 Verify

```bash
git config --global user.name
git config --global user.email
```

Expected:

```text
vijay patel
vijay@timestream.com
```

### 🧠 What does this mean?

These settings become your **default Git identity**.

```text
Global Git Identity
├── user.name  → vijay patel
└── user.email → vijay@timestream.com
```

Other repositories will use these values unless they have local overrides.

---

# 📁 3. Set Local Git Identity

Now set a different username **only for this repository**.

```bash
git config user.name "Temporal Agent Bob"
```

> 💡 Because we are inside the repository and did not use `--global`, this creates a **local repository setting**.

### 🔍 Verify the local username

```bash
git config user.name
```

Expected:

```text
Temporal Agent Bob
```

Notice that we **did not change the local email**.

Therefore, this repository will use:

```text
Username: Temporal Agent Bob
Email:    vijay@timestream.com
```

The username comes from the **local configuration**, while the email comes from the **global configuration**.

---

# ⚖️ 4. Global vs Local Configuration

## 🌍 Check global configuration

```bash
git config --global --list
```

You should see:

```text
user.name=vijay patel
user.email=vijay@timestream.com
```

## 📁 Check local configuration

```bash
git config --local --list
```

You should see:

```text
user.name=Temporal Agent Bob
```

### ⚡ Important Rule

The local configuration overrides the global configuration for this repository.

```text
Local setting
      ↓
   takes priority
      ↓
Global setting
```

---

# 🪪 5. Check the Effective Identity

The following commands show the identity Git will use in the **current repository**:

```bash
git config user.name
git config user.email
```

Expected:

```text
Temporal Agent Bob
vijay@timestream.com
```

### 🧠 Why?

Git checks for a local value first.

For `user.name`:

```text
Local user.name
→ Temporal Agent Bob
```

So the local value wins.

For `user.email`:

```text
No local user.email
→ use global user.email
→ vijay@timestream.com
```

---

# 🛠️ 6. Useful Configuration Commands

## 🔎 View all configuration

```bash
git config --list
```

Shows configuration available to Git, including applicable global and local settings.

---

## 🌍 View only global configuration

```bash
git config --global --list
```

Shows your global Git settings.

---

## 📁 View only local configuration

```bash
git config --local --list
```

Shows settings specifically configured for the current repository.

---

## 👤 Check current repository's username

```bash
git config user.name
```

---

## 📧 Check current repository's email

```bash
git config user.email
```

---

# 🐛 Beginner Troubleshooting

## ❌ `fatal: not a git repository`

Make sure you are inside the lab:

```bash
cd ~/git-labs-vijay/04-time-machine-identity-configuration
```

Then check:

```bash
git status
```

---

## 🤔 The username is not what you expected

Check both global and effective values:

```bash
git config --global user.name
git config user.name
```

Remember:

```text
Local setting  → takes priority
Global setting → used when no local setting exists
```

---

## 📧 The local email is missing

Check:

```bash
git config user.email
```

If it returns:

```text
vijay@timestream.com
```

then Git is using the **global email**, which is what we want for this lab.

### ⚠️ Do NOT run:

```bash
git config user.email "..."
```

The lab specifically requires that the local email remain unchanged.

---

# ✅ Quick Verification

From inside `04-time-machine-identity-configuration`, run:

```bash
git config --global user.name
git config --global user.email

git config user.name
git config user.email
```

Expected:

```text
vijay patel
vijay@timestream.com

Temporal Agent Bob
vijay@timestream.com
```

---

# 🧠 Mental Model — Quick Revision

Think of Git identity as a **default + override** system:

```text
🌍 GLOBAL GIT IDENTITY
├── user.name  → vijay patel
└── user.email → vijay@timestream.com
          │
          │ default
          ▼
📁 04-time-machine-identity-configuration
└── LOCAL OVERRIDE
    └── user.name → Temporal Agent Bob
```

### ⭐ The Golden Rule

```text
LOCAL  >  GLOBAL
```

If a local value exists, Git uses it.
If no local value exists, Git falls back to the global value.

### 🎯 Final Effective Identity

```text
Repository:
04-time-machine-identity-configuration

user.name  → Temporal Agent Bob   ← local override
user.email → vijay@timestream.com ← global default
```

**Remember:** You don't have to override the entire identity. You can override just `user.name` or just `user.email`.
