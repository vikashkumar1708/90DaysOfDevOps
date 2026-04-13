# GIT BRANCHING & WORKING WITH GITHUB

---

##  Task 1: Understanding Branches

### 1. What is a branch in Git?

A branch is a movable pointer to a commit. It allows you to work on features or fixes independently without affecting the main code.

### 2. Why use branches?

* Keeps main branch stable
* Enables parallel development
* Prevents breaking production code

### 3. What is `HEAD`?

`HEAD` is a pointer to your current branch/commit.

### 4. What happens when switching branches?

Git updates your files based on that branch’s snapshot.

---

## Task 2: Branching Commands

### List branches

```bash
git branch
```

### Create a branch

```bash
git branch feature-1
```

### Switch branch

```bash
git switch feature-1
```

### Create + switch (best way)

```bash
git switch -c feature-2
```

### Make a commit on feature branch

```bash
echo "verifying" > file.txt
git add .
git commit -m "verifying file committed"
```

### Switch back to main

```bash
git switch main
```

### Delete branch

```bash
git branch -d feature-2
```

---

## Task 3: Push to GitHub

### Add remote 

```bash
git remote add origin git@github.com:vikashkumar1708/my-first-repo.git
```

### Verify remote

```bash
git remote -v
```

### Push main branch

```bash
git push -u origin main
```

### Push feature branch

```bash
git push -u origin feature-1
```

---

##  Task 4: Pull from GitHub

```bash
git pull origin main
```

### Fetch vs Pull

* `git fetch` → downloads changes only
* `git pull` → fetch + merge

---

##  Task 5: Clone vs Fork

### Clone repo

```bash
git clone https://github.com/user/repo.git
```

### Fork + clone

```bash
git clone https://github.com/your-username/repo.git
```

### Difference

* Clone → local copy
* Fork → GitHub copy

---



