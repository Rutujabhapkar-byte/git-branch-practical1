# Git Branch Practical1
Yes. This practical can be done completely from **Git Bash / VS Code terminal**. Here is the exact step-by-step procedure.

## Practical: GitHub Repository + Local Git + Branch

### 1. Create a new repository on GitHub

1. Open [GitHub](https://github.com/?utm_source=chatgpt.com)
2. Login to your account.
3. Click **+ → New repository**.
4. Repository name:

   ```text
   git-practical
   ```
5. Select **Public**.
6. **Do NOT** select “Add a README file”.
7. Click **Create repository**.

Keep the GitHub page open because we will copy its repository URL.

---

### 2. Create a local project

Open **Git Bash** and run:

```bash
mkdir git-practical
cd git-practical
```

Create a project file:

```bash
echo "GitHub Practical Project" > index.txt
```

Check the file:

```bash
ls
```

You should see:

```text
index.txt
```

---

### 3. Initialize the local Git repository

```bash
git init
```

Check status:

```bash
git status
```

You should see `index.txt` as an untracked file.

---

### 4. Add the file

```bash
git add index.txt
```

Or add everything:

```bash
git add .
```

Check:

```bash
git status
```

---

### 5. Commit the project

```bash
git commit -m "Initial project commit"
```

---

### 6. Connect local repository with GitHub

Copy your GitHub repository URL.

It will look like:

```text
https://github.com/YOUR_USERNAME/git-practical.git
```

Run:

```bash
git remote add origin https://github.com/YOUR_USERNAME/git-practical.git
```

Verify:

```bash
git remote -v
```

You should see:

```text
origin  https://github.com/YOUR_USERNAME/git-practical.git (fetch)
origin  https://github.com/YOUR_USERNAME/git-practical.git (push)
```

---

### 7. Push the committed project to GitHub

Rename the current branch to `main`:

```bash
git branch -M main
```

Push:

```bash
git push -u origin main
```

If GitHub asks you to sign in, complete the GitHub authentication.

Now refresh your GitHub repository.

You should see:

```text
git-practical
└── index.txt
```

---

# 8. Create a new branch

Create a branch named `feature`:

```bash
git branch feature
```

Switch to it:

```bash
git checkout feature
```

Or use the newer command:

```bash
git switch -c feature
```

Verify:

```bash
git branch
```

You should see:

```text
* feature
  main
```

The `*` means you are currently on the `feature` branch.

---

# 9. Make a change

Open `index.txt` and change:

```text
GitHub Practical Project
```

to:

```text
GitHub Practical Project
Branch Feature Added
```

Or directly run:

```bash
echo "Branch Feature Added" >> index.txt
```

Check the change:

```bash
cat index.txt
```

---

# 10. Commit the change

Check status:

```bash
git status
```

Add the changed file:

```bash
git add index.txt
```

Commit:

```bash
git commit -m "Added feature branch changes"
```

---

# 11. Push the new branch to GitHub

```bash
git push -u origin feature
```

This creates the `feature` branch on GitHub.

---

# 12. Verify the branch on GitHub

Go to your GitHub repository and click the **branch selector**.

You should see:

```text
main
feature
```

Select:

```text
feature
```

You should see the changed `index.txt` containing:

```text
GitHub Practical Project
Branch Feature Added
```

### Final Git command sequence

For your practical, the main commands are:

```bash
mkdir git-practical
cd git-practical

echo "GitHub Practical Project" > index.txt

git init
git add .
git commit -m "Initial project commit"

git branch -M main
git remote add origin https://github.com/YOUR_USERNAME/git-practical.git

git push -u origin main

git switch -c feature

echo "Branch Feature Added" >> index.txt

git add .
git commit -m "Added feature branch changes"

git push -u origin feature
```

**Practical result:** You will have **one GitHub repository with two branches (`main` and `feature`)**, and the change made on `feature` will be visible on GitHub.
