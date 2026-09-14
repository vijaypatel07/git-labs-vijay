# Setting up things: <br>
📁 **git-labs-vijay** folder created on Desktop <br>
💻 VS Code installed <br>
🔧 Git installed <br>


## Step 1 — Open the folder in VS Code
Open VS Code → File → Open Folder... → Desktop → git-labs-vijay → Select Folder

## Step 2 — Open VS Code Terminal
> In VS Code,
> * Terminal → New Terminal <br>
> * You should see a path ending roughly like: <br>
> ...\Desktop\git-labs-vijay> <br>
> * Verify Git <br>
In that terminal, run only this: `git --version` <br>

You should get something like:<br>
`git version 2.x.x`
`

## Step 3 — Tell Git who you are
> Before making commits, Git needs your name and email. <br>
In the same VS Code terminal, run: <br>
`git config --global user.name "Vijay"`

Then:
`git config --global user.email "your-email@example.com"`

👉 For the email, use the same email address you use on GitHub.

>Then verify both with:
`git config --global --list` <br>
 You should see something like: <br>
 user.name=Vijay Patel <br>
user.email=your-email@example.com

## Step 3 ✅ Git identity is set. Initialize Git in git-labs-vijay

```
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
