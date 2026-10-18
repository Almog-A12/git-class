# Git Class - Our First Shared Repository

Welcome! This repository is shared by the whole class.
Each of you will add **one file about yourself** and send it with a **Pull Request (PR)**.

You do not need to understand everything yet. Type each command, press Enter,
and look at what Git prints.

---

## Why do we work on a branch?

`main` is the **official version** of the project. It is locked:
nobody can change it directly - not you, not your classmates.

So the way to add something is always:

```
main      ●───────────────────────●   ← the official version
           \                     /
add-dana    ●── your file ── PR ─●     ← your branch, merged back by the teacher
```

1. Make a **branch** - your own private workspace
2. Do your work and **commit** it on that branch
3. **Push** the branch to GitHub
4. Open a **Pull Request** - "please merge my branch into main"
5. The teacher reviews it and **merges** it into `main`

This is exactly how teams work in real companies.

---

## Step 0 - Make your own copy on GitHub (fork)

1. Log in to https://github.com (no account? **Sign up** - it is free)
2. Open https://github.com/Roeyhadad777/git-class
3. Click **Fork** (top right), then **Create fork**

You now have your own copy, with your name at the top left of the page.
You will push to **your copy**, and send the Pull Request from there.

## Step 1 - Get your copy on your computer (clone)

On **your copy** on GitHub: click the green **Code** button → **HTTPS** → copy the link.

```
cd ~
git clone <paste the link here>
cd git-class
```

You now have the whole project on your computer.

## Step 2 - Make your own branch

A branch is your private workspace. Replace `your-name` with your first name:

```
git switch -c add-your-name
git branch
```

The `*` shows the branch you are on.

## Step 3 - Create your file

Replace `your-name` with your first name (small letters, no spaces):

```
echo "# Hi, I am Your Name" > students/your-name.md
echo "I am learning Git today." >> students/your-name.md
```

## Step 4 - Save it in Git (add + commit)

```
git status
git add students/your-name.md
git status
git commit -m "Add your-name to the class"
```

`git status` before and after shows you what changed.

## Step 5 - Send your branch to GitHub (push)

```
git push -u origin add-your-name
```

The first time, GitHub asks you to log in:

- **Windows:** a browser window opens - log in and approve.
- **Mac or Linux:** Git asks for a username and password - but GitHub does **not** accept
  your account password. Do this once:

  **Option A - Mac with Homebrew** (a browser login opens, like on Windows):

  ```
  brew install --cask git-credential-manager
  git push -u origin add-your-name
  ```

  **Option B - a token instead of a password** (Linux, or Mac without `brew`):

  0. **Linux only** - so Git remembers your token for a day instead of asking every push:

     ```
     git config --global credential.helper "cache --timeout=86400"
     ```

  1. On GitHub: your avatar (top right) → **Settings** → **Developer settings**
     (bottom of the left menu) → **Personal access tokens** → **Tokens (classic)**
     → **Generate new token (classic)**
  2. Note: `git class`, Expiration: `30 days`, tick only **public_repo**
  3. Click **Generate token** and **copy it now** - GitHub shows it only once
  4. Run `git push -u origin add-your-name` again:
     - **Username:** your GitHub username (not your email)
     - **Password:** paste the token (nothing shows on screen while you paste - that is normal)

  A Mac remembers it for good; Linux remembers it for a day (step 0).
  Treat the token like a password - never share it or post it in the class chat.

## Step 6 - Open a Pull Request

1. Open **your copy** on GitHub (refresh the page)
2. Click the yellow **Compare & pull request** button
3. Check the top line: `Roeyhadad777/git-class` ← your copy
4. Click **Create pull request**

Done! The teacher will review it and merge it.

## Step 7 - Get everyone's files (pull)

After the teacher merges the PRs. The first command is only needed once -
it tells Git where the class repository is:

```
git remote add upstream https://github.com/Roeyhadad777/git-class.git
git switch main
git pull upstream main
ls students
```

You will see the files of the whole class.
