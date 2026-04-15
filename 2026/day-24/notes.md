# Day 24 – Advanced Git: Merge, Rebase, Stash & Cherry Pick

---

## Task 1: Git Merge — Hands-On

### Observations

- When merging `feature-login` into `main`:
  - Git performed a **fast-forward merge**
  - No merge commit was created
  - `main` pointer simply moved forward

- When merging `feature-signup`:
  - A commit was added to `main` before merging
  - Git created a **merge commit**
  - History became non-linear

---

### Answers

#### What is a fast-forward merge?
A fast-forward merge happens when the target branch has no new commits, so Git simply moves the pointer forward without creating a new commit.

---

#### When does Git create a merge commit?
When both branches have new commits (diverged history), Git creates a merge commit to combine them.

---

#### What is a merge conflict?
A merge conflict occurs when the same file (or same lines) are modified in both branches and Git cannot automatically decide which version to keep.

---

##  Task 2: Git Rebase — Hands-On

### Observations

- Rebasing `feature-dashboard` onto `main`:
  - Replayed commits on top of latest `main`
  - History became **linear**
  - No merge commit created

---

### Answers

#### What does rebase actually do?
Rebase takes your commits, rewrites them, and places them on top of another branch.

---

#### How is history different from a merge?
- **Rebase** → linear history
- **Merge** → branch + merge commit (non-linear)

---

#### Why should you never rebase shared commits?
Because rebase rewrites commit history (changes commit IDs), which can break other developers' work.

---

#### When to use rebase vs merge?

- Use **rebase**:
  - For clean history
  - Before pushing
  - When working alone

- Use **merge**:
  - In team environments
  - When history should be preserved

---

## Task 3: Squash Commit vs Merge Commit

### Observations

- `git merge --squash feature-profile`:
  - Combined multiple commits into **one**
  - Only one commit added to `main`

- `git merge feature-settings`:
  - Performed **fast-forward merge** (no merge commit due to no divergence)

---

### Answers

#### What does squash merging do?
Squash merge combines all commits from a branch into a single commit before merging into the target branch.

---

#### When to use squash vs regular merge?

- Use **squash merge**:
  - For small or messy commits
  - To keep history clean

- Use **regular merge**:
  - To preserve full commit history
  - In collaborative projects

---

#### What is the trade-off of squashing?

- Pros:
  - Clean history
- Cons:
  - Loss of detailed commit history
  - Harder to debug step-by-step changes

---

##  Task 4: Git Stash — Hands-On

### Observations

- Could not switch branches with uncommitted changes
- Used `git stash` to save work-in-progress
- Retrieved changes using `git stash pop`
- Managed multiple stashes using `git stash list`

---

### Answers

#### Difference between `git stash pop` and `git stash apply`?

- `git stash pop`:
  - Applies changes AND removes stash

- `git stash apply`:
  - Applies changes BUT keeps stash

---

#### When to use stash?

- When switching context quickly
- When work is incomplete but you need to change branches
- Temporary storage of uncommitted work

---

##  Task 5: Cherry Picking

### Observations

- Created multiple commits in `feature-hotfix`
- Used `git cherry-pick <commit-hash>` to apply only one commit to `main`
- Only selected commit was added

---

### Answers

#### What does cherry-pick do?
Cherry-pick applies a specific commit from one branch onto another branch.

---

#### When to use cherry-pick?

- To apply a specific fix (e.g., bug fix) without merging full branch
- Hotfix scenarios

---

