# Git Class - Our First Shared Repository

Welcome! This repository is shared by the whole class.
Each of you will add **one file about yourself** and send it with a **Pull Request (PR)**.

You do not need to understand everything yet. Type each command, press Enter,
and look at what Git prints.

---

## Step 1 - Get a copy of the repository (clone)

```
git clone https://github.com/Roeyhadad777/git-class.git
cd git-class
```

You now have the whole project on your computer.

## Step 2 - Make your own branch

A branch is your private workspace. Replace `your-name` with your first name:

```
git switch -c add-your-name
```

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

## Step 5 - Send it to GitHub (push)

```
git push
```

## Step 6 - Open a Pull Request

1. Open https://github.com/Roeyhadad777/git-class
2. Click the yellow **Compare & pull request** button
3. Click **Create pull request**

Done! The teacher will review it and merge it.

## Step 7 - Get everyone's files (pull)

After the teacher merges the PRs:

```
git switch main
git pull
ls students
```

You will see the files of the whole class.
