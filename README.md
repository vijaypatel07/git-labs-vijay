# CONTENTS


| | | | |
|---|---|---|---|
| [Chapter_01](./01-your-first-git-lab/notes.md) | [Chapter_02](./02-operation-quantum-leap/notes.md) | [Chapter_03](./03-git-config-management/notes.md) | [Chapter_04](./04-time-machine-identity-configuration/notes.md) |
| [Chapter_05](./05-working-with-files-and-staging-area/notes.md) | [Chapter_06](./06-the-time-travelers-suitcase/notes.md) | [Chapter_07](./07-git-branch-basic-operations/notes.md) | [Chapter_08](./08-the-time-travelers-dilemma/notes.md) |
| [Chapter_09](./09-advanced-git-commit-operations/notes.md) | [Chapter_10](./10-rewriting-history/notes.md) | [Chapter_11](./11-saving-work-in-progress/notes.md) | [Chapter_12](./12-the-time-traveling-developer/notes.md) |
| [Chapter_13](./13-marking-important-milestones/notes.md) | [Chapter_14](./14-tagging-your-projects-history/notes.md) | [Chapter_15](./15-git-history-and-log-management/notes.md) | [Chapter_16](./16-git-time-detective/notes.md) |
| [Chapter_17](./17-git-diff-deep-dive/notes.md) | [Chapter_18](./18-uncover-the-secret-code-changes/notes.md) | [Chapter_19](./19-git-reset-and-reflog/notes.md) | [Chapter_20](./20-recover-the-lost-files/notes.md) |




# Setting up things: <br>
📁 **git-labs-vijay** folder created on Desktop <br>
💻 VS Code installed <br>
🔧 Git installed <br>


## Step 1 ✅— Open the folder in VS Code
Open VS Code → File → Open Folder... → Desktop → git-labs-vijay → Select Folder

## Step 2 ✅— Open VS Code Terminal
> In VS Code,
> * Terminal → New Terminal <br>
> * You should see a path ending roughly like: <br>
> ...\Desktop\git-labs-vijay> <br>
> * Verify Git <br>
In that terminal, run only this: `git --version` <br>

You should get something like:<br>
`git version 2.x.x`
`

## Step 3 ✅— Tell Git who you are
> Before making commits, Git needs your name and email. <br>
In the same VS Code terminal, run: <br>
`git config --global user.name "Vijay"`

Then:
`git config --global user.email "your-email@example.com"`

👉 For the email, use the same email address you use on GitHub.for user.name keep anything

>Then verify both with:
`git config --global --list` <br>
 You should see something like: <br>
 user.name=Vijay Patel <br>
user.email=your-email@example.com

## Step 4 ✅- Git identity is set. Initialize Git in git-labs-vijay

```text
Initialize Git in git-labs-vijay
Your VS Code terminal should already be inside: Desktop\git-labs-vijay
Now run just this:
git init

You should see something similar to: <br>
Initialized empty Git repository in .../Desktop/git-labs-vijay/.git/
What just happened?
Git created a hidden .git folder inside git-labs-vijay.
Think of it like:
git-labs-vijay/
└── .git/    ← Git's internal tracking area *

Don't touch .git manually. Git manages it for us. 
```

> ✅ Your local Git setup is complete: <br>
git-labs-vijay
      │
      ├── README.md


## Step 5 ✅— Create the GitHub repository
Now connect this local project to GitHub.
Go to GitHub in your browser and create a new repository.

Name it exactly:
git-labs-vijay
For now:
✅ Repository name: git-labs-vijay
❌ Don't add a README
❌ Don't add .gitignore
❌ Don't add a license

Keep it essentially empty, because we already have our local Git repository.
copy url:

## Final
 👍 Now we connect your local repo to the GitHub repo. <br>
 * VS Code terminal, make sure you're still inside: Desktop\git-labs-vijay <br>
 * run `git remote add origin YOUR_GITHUB_URL`

 > For example: <br>
`git remote add origin https://github.com/your-username/git-labs-vijay.git`

 > * 🔗 Local repo is now connected to GitHub. <br>
 Verify the connection `git remote -v` <br>
 You should see something like:<br>
origin  https://github.com/your-username/git-labs-vijay.git (fetch) <br>
origin  https://github.com/your-username/git-labs-vijay.git (push)

<br>


## Perfect! ✅
``` text
Perfect! ✅ That means the connection is correct.

You now have:
Local PC                         GitHub
git-labs-vijay
      │
      │ origin
      └──────────────────────→  git-labs-vijay
Step 15 — One last setup command

Before pushing, let's make sure our branch is called **main**.
Run:
git branch -M main 

This doesn't upload anything. It simply renames your current branch to main.
```

## Push your first commit to GitHub

Run this one command in the same terminal:

`git push -u origin main`

What it does: <br>
**push** → uploads your local commits to GitHub <br>
**origin** → your GitHub repository <br>
**main** → the branch we're uploading <br>
**-u** → remembers this connection, so future pushes can simply be *git push*