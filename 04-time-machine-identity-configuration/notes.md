# 04 — Time Machine Identity Configuration

## Objective

Learn how to set your Git identity globally and override it for a specific repository.

---

## 1. Lab Setup

Create the lab directory and initialize it as a Git repository:

```bash
cd ~/git-labs-vijay
mkdir 04-time-machine-identity-configuration
cd 04-time-machine-identity-configuration
git init
```

Check the repository:

```bash
git status
```

---

## 2. Set Global Git Identity

Set your global Git username:

```bash
git config --global user.name "vijay patel"
```

Set your global email:

```bash
git config --global user.email "vijay@timestream.com"
```

Verify:

```bash
git config --global user.name
git config --global user.email
```

Expected:

```text
vijay patel
vijay@timestream.com
```

These settings apply to your Git repositories by default.

---

## 3. Set Local Git Identity

Now set a different username only for the `04-time-machine-identity-configuration` repository:

```bash
git config user.name "Temporal Agent Bob"
```

Verify the local username:

```bash
git config user.name
```

Expected:

```text
Temporal Agent Bob
```

Notice that we did **not** change the local email.

The repository will therefore use:

```text
Username: Temporal Agent Bob
Email:    vijay@timestream.com
```

---

## 4. Global vs Local Configuration

Check the global configuration:

```bash
git config --global --list
```

You should see:

```text
user.name=vijay patel
user.email=vijay@timestream.com
```

Check the local configuration:

```bash
git config --local --list
```

You should see:

```text
user.name=Temporal Agent Bob
```

The local configuration overrides the global username for this repository.

---

## 5. Check the Effective Identity

Run:

```bash
git config user.name
git config user.email
```

Expected:

```text
Temporal Agent Bob
alice@timestream.com
```

This shows the identity Git will use in the current repository.

---

## 6. Useful Configuration Commands

View all configuration:

```bash
git config --list
```

View only global configuration:

```bash
git config --global --list
```

View only local configuration:

```bash
git config --local --list
```

Check the current repository's username:

```bash
git config user.name
```

Check the current repository's email:

```bash
git config user.email
```

---

## Beginner Troubleshooting

### `fatal: not a git repository`

Make sure you are inside the lab:

```bash
cd ~/git-labs-vijay/04-time-machine-identity-configuration
```

Then check:

```bash
git status
```

### The username is not what you expected

Check both global and local values:

```bash
git config --global user.name
git config user.name
```

Remember:

```text
Local setting → takes priority
Global setting → used when no local setting exists
```

### The local email is missing

Check:

```bash
git config user.email
```

If it returns:

```text
vijay@timestream.com
```

then Git is using the global email, which is what we want for this lab.

Do **not** run:

```bash
git config user.email "..."
```

because the lab specifically requires that the local email remain unchanged.

---

## Quick Verification

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
vijaye@timestream.com

Temporal Agent Bob
vijay@timestream.com
```

---

## Mental Model

Think of Git identity like this:

```text
Global Git Identity
├── user.name  → vijay patel
└── user.email → vijay@timestream.com

04-time-machine-identity-configuration
└── Local override
    └── user.name → Temporal Agent Bob
```

So the `04-time-machine-identity-configuration` repository uses **Temporal Agent Bob**, while other repositories can continue using **vijay patel**.

## Key Takeaways

* `git config --global` sets user-wide Git settings.
* `git config` inside a repository sets local settings.
* Local settings override global settings.
* You can override only one part of your identity, such as `user.name`.
* `git config --local --list` shows repository-specific settings.
* `git config --global --list` shows global settings.
