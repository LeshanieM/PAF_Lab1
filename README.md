# PAF Lab 1 and 2

---

## Part 1

### 2. Clone the repository

```
git clone https://github.com/YOUR_USERNAME/git-practice-2026.git
cd git-practice-2026
```

### 3. Create a feature branch

Option i: Create branch then switch
```
git branch feature/yourname/awesome-feature
git checkout feature/yourname/awesome-feature
```

Option ii: Create and switch in one command (recommended)
```
git checkout -b feature/yourname/awesome-feature
```

### 4. Add files

```
echo "<h1>My Awesome Feature</h1>" > index.html
echo "Sample content" > readme.txt
```

Check status
```
git status
```

### 5. Stage, commit, and push

```
git add .
git commit -m "Add awesome feature files"
git push -u origin feature/yourname/awesome-feature
```

### 6. Verify on GitHub

Check under your feature branch to confirm files were pushed.

### 7–8. Create and merge Pull Request on GitHub

Go to the repository on GitHub → "Pull requests" tab → "New pull request"  
Select: base: main ← compare: your feature branch  
Create PR → Review → "Merge pull request"

---

## Part 2

### 1. Add collaborator on GitHub

Repository → Settings → Collaborators → Add person (by username/email)

### 2. Clone colleague's repository

```
git clone https://github.com/COLLEAGUE_USERNAME/their-repo.git
cd their-repo
```

### 3. Create a branch and make changes

```
git checkout -b feature/yourname/small-fix
echo "Fixing typo" >> readme.txt
```

### 4. Stage, commit, and push

```
git add .
git commit -m "Fix typo in documentation"
git push -u origin feature/yourname/small-fix
```

### 5–6. Create PR and merge on GitHub

Same process: PR → Review → Merge

### 7. Reverse roles

Your colleague does the same on your repo.

---

## Part 3

### As the contributor:

#### 1. Create a new feature branch from main

```
git checkout main
git pull origin main
git checkout -b feature/yourname/user-authentication
git switch -c feature/yourname/user-authentication
```

#### 2. Make several changes

Create feature files
```
mkdir src
echo "// User auth logic" > src/auth.js
echo "// Login component" > src/login.js
```

Stage and commit each logical change
```
git add src/auth.js
git commit -m "Add authentication service"

git add src/login.js
git commit -m "Add login component"
```

Push feature branch
```
git push -u origin feature/yourname/user-authentication
```

#### 3. Create Pull Request on GitHub

Click "Compare & pull request" button (appears after push), or manually: Pull requests → New → Select your branch.  
Add description: "Implements user authentication with login form"  
Assign reviewer: your colleague

### As the reviewer:

#### 4. Review and merge

Go to PR on GitHub → Review changes → Add comments or Approve  
Click "Merge pull request" when approved

#### 5. Delete feature branch (both remote and local)

After merging, delete on GitHub (button appears after merge), then locally:
```
git checkout main
git pull origin main
git branch -d feature/yourname/user-authentication
```

Optionally delete remote branch
```
git push origin --delete feature/yourname/user-authentication
```

#### 6. Reverse roles

Repeat with your colleague as contributor.

---

## Additional Commands

Check branches
```
git branch        # local branches
git branch -r     # remote branches
git branch -a     # all branches
```

Switch between branches
```
git checkout main
git checkout feature/branch-name
```

See differences
```
git diff
git diff main..feature/your-branch
```

Update main branch
```
git checkout main
git pull origin main
```

See commit history
```
git log --oneline --graph --all
```

Update feature branch with latest main
```
git checkout feature/your-branch
git merge main
```

Or rebase for cleaner history
```
git rebase main
```
