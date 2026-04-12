# Day 22 – Git Notes & Commands



###  Setup & Config

```bash
git --version
```

Check installed Git version

```bash
git config --global user.name "your-name"
git config --global user.email "your-email"
```

Set global username and email

```bash
git config --list
```

View all Git configurations

---

### Basic Workflow

```bash
git init
```

Initialize a new Git repository

```bash
git status
```

Check current state of files

```bash
git add <file>
```

Stage a specific file

```bash
git add .
```

Stage all changes

```bash
git commit -m "message"
```

Save staged changes

---

### Viewing Changes

```bash
git log
```



## Concepts

### 1. Difference between git add and git commit

* `git add` moves changes to staging area
* `git commit` saves them permanently

---

### 2. What is Staging Area?

Staging area allows you to prepare changes before committing.
It helps you select only required changes instead of committing everything.

---

### 3. What does git log show?

* Commit ID
* Author
* Date
* Commit message

---

### 4. What is .git folder?

.git folder stores:

* Commit history
* Branches
* Configuration

If deleted → Git tracking is lost

---

### 5. Git Areas

| Area              | Description                |
| ----------------- | -------------------------- |
| Working Directory | Where files are edited     |
| Staging Area      | Where changes are prepared |
| Repository        | Where commits are stored   |

---

