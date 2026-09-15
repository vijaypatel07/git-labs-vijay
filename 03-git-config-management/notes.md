# 🔧 03 — Git Config Management

> **Git Learning Journey 🚀**

Git configuration controls how Git behaves on your system and inside individual repositories.
In this lab, we’ll learn how to configure **identity, editor, colors, line endings, aliases, and repository-specific settings**.

---

## 🎯 Objective

Learn how to configure Git for:

* 👤 User identity
* 🎨 Git colors
* ✍️ Default editor
* 📄 Line endings
* ⚡ Git aliases
* 📦 Repository-specific settings

---

# 1. 🧪 Lab Setup

Create the lab directory and initialize it as a Git repository:

```bash
cd ~/git-labs-vijay
mkdir 03-git-config-management
cd 03-git-config-management
git init
```

Check that Git is initialized:

```bash
git status
```

You should see that you are on a Git branch and that there are no commits yet.

---

# 2. 🔍 View Git Configuration

See all available Git settings:

```bash
git config --list
```

Check your Git username:

```bash
git config user.name
```

---

# 3. 🏗️ Git Configuration Levels

Git has three main configuration levels:

| Level         | Applies to                  |
| ------------- | --------------------------- |
| 🌐 **System** | Everyone on the machine     |
| 👤 **Global** | Your user account           |
| 📦 **Local**  | Only the current repository |

### Priority

```text
System → Global → Local
```

> ⭐ A **local** setting overrides a **global** setting.

---

# 4. 👤 Set Your Git Identity

Git uses your name and email when creating commits.

### Set your name globally

```bash
git config --global user.name "Your Name"
```

### Set your email globally

```bash
git config --global user.email "your.email@example.com"
```

### Verify them

```bash
git config --global user.name
git config --global user.email
```

---

# 5. 🎨 Enable Git Colors

Enable colored Git output:

```bash
git config --global color.ui auto
```

Check the setting:

```bash
git config --global color.ui
```

---

# 6. ✍️ Set the Default Editor

For example, use **Nano**:

```bash
git config --global core.editor nano
```

Check it:

```bash
git config --global core.editor
```

### 📝 When Nano opens

```text
Ctrl + X
Y
Enter
```

---

# 7. 📄 Configure Line Endings

On Ubuntu/Linux, a common setting is:

```bash
git config --global core.autocrlf input
```

Check it:

```bash
git config --global core.autocrlf
```

This helps Git handle files created on different operating systems.

---

# 8. ⚡ Create Git Aliases

Aliases let you create shorter Git commands.

## 🔹 Alias for `git status`

Create a shortcut:

```bash
git config --global alias.st status
```

Now you can use:

```bash
git st
```

---

## 🔹 Alias for Graphical Log

Create a shortcut:

```bash
git config --global alias.lg "log --color --graph --pretty=format:'%Cred%h%Creset -%C(yellow)%d%Creset %s %Cgreen(%cr) %C(bold blue)<%an>%Creset' --abbrev-commit"
```

Use it with:

```bash
git lg
```

### 🔎 Check your aliases

```bash
git config --global alias.st
git config --global alias.lg
```

---

# 9. 📦 Repository-Specific Configuration

Git allows you to configure settings only for the current repository.

Make sure you are inside the lab repository:

```bash
cd ~/git-labs-vijay/03-git-config-management
```

### Set a local username

```bash
git config user.name "Lab User"
```

### Check the local value

```bash
git config user.name
```

### Compare it with your global username

```bash
git config --global user.name
```

> ⭐ The **local value takes priority** inside this repository.

---

# 10. 🛠️ Useful Git Config Commands

### 📋 View all configuration

```bash
git config --list
```

### 🌐 View global configuration

```bash
git config --global --list
```

### 📦 View local configuration

```bash
git config --local --list
```

### 🔎 Check where a setting comes from

```bash
git config --show-origin --list
```

### 🎯 Get a specific setting

```bash
git config user.name
git config user.email
```

---

# 🆘 Beginner Troubleshooting

## ❌ `git: command not found`

Git may not be installed.

On Ubuntu:

```bash
sudo apt update
sudo apt install git
```

---

## ❌ `fatal: not a git repository`

You are probably outside the Git repository.

Check your location:

```bash
pwd
```

Then move into the lab:

```bash
cd ~/git-labs-vijay/03-git-config-management
```

---

## ⚠️ Global and Local Names Are Different

This is expected.

Check both:

```bash
git config --global user.name
git config user.name
```

The **local setting wins** inside the repository.

---

## ❌ Alias Does Not Work

Check whether the alias exists:

```bash
git config --global alias.st
```

Then try:

```bash
git st
```

---

# ✅ Quick Configuration Check

Run these commands to review your setup:

```bash
git config user.name
git config user.email
git config --global color.ui
git config --global core.editor
git config --global core.autocrlf
git config --global alias.st
```

---

# 🧠 Mental Model

Think of Git configuration as your Git **control panel** 🎛️:

```text
Git
├── 👤 Identity
│   ├── user.name
│   └── user.email
│
├── 🎨 Appearance
│   └── color.ui
│
├── ✍️ Editor
│   └── core.editor
│
├── 📄 File handling
│   └── core.autocrlf
│
└── ⚡ Shortcuts
    ├── alias.st
    └── alias.lg
```

Most settings can be configured **globally**, while repository-specific settings can **override them locally**.

---

# 🔑 Key Takeaways

### ⭐ Important Commands

| Command                                   | Purpose                                   |
| ----------------------------------------- | ----------------------------------------- |
| `git config --list`                       | 📋 View all Git configuration             |
| `git config user.name`                    | 👤 Get current repository username        |
| `git config user.email`                   | 📧 Get current repository email           |
| `git config --global user.name "Name"`    | 👤 Set global username                    |
| `git config --global user.email "Email"`  | 📧 Set global email                       |
| `git config --global color.ui auto`       | 🎨 Enable Git colors                      |
| `git config --global core.editor nano`    | ✍️ Set Nano as editor                     |
| `git config --global core.autocrlf input` | 📄 Configure line-ending handling         |
| `git config --global alias.st status`     | ⚡ Create `git st` alias                   |
| `git config --global alias.lg "..."`      | 📊 Create graphical log alias             |
| `git config --global --list`              | 🌐 View global configuration              |
| `git config --local --list`               | 📦 View repository-specific configuration |
| `git config --show-origin --list`         | 🔎 Show where settings come from          |

### 🧠 Remember

```text
System → Global → Local
                    ↑
              Highest priority
```

* 🔧 `git config` controls Git's behavior.
* 🌐 `--global` applies settings to your user account.
* 📦 Local settings apply only to the current repository.
* ⭐ Local configuration overrides global configuration.
* 👤 Git identity is stored with your commits.
* ⚡ Aliases make frequently used commands shorter.
* 🔍 `git config --list` is useful for checking your setup.

---

## 📌 Quick Revision

```text
Git Config
│
├── 👤 Identity
│   ├── user.name
│   └── user.email
│
├── 🎨 Appearance
│   └── color.ui
│
├── ✍️ Editor
│   └── core.editor
│
├── 📄 Line Endings
│   └── core.autocrlf
│
├── ⚡ Aliases
│   ├── alias.st → status
│   └── alias.lg → graphical log
│
└── 📦 Configuration Levels
    ├── System
    ├── Global
    └── Local ⭐
```

**Core idea:** Configure Git globally for your normal workflow, and use **local repository configuration** when a project needs different behavior.
