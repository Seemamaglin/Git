# 📘 Git Task 04 – Simulating and Resolving Merge Conflicts

## 🎯 Objective
The objective of this task is to understand how **merge conflicts occur in Git** and how to **identify and resolve them manually** using Git commands.

This task demonstrates:
- Creating multiple branches from the same commit
- Modifying the same file in different branches
- Triggering a merge conflict
- Resolving the conflict correctly
- Verifying the final merged result

---

## 🛠️ Steps Performed

### 1️⃣ Create a Base Commit
- Started from the `master` branch
- Used a common file (`index.html`) as the base
- Committed the initial version of the file

        git add index.html
        git commit -m "Initial welcome message"

2️⃣ Create Two Branches from the Same Commit

        git checkout -b branch-a
        git checkout master
        git checkout -b branch-b

-Now, both branch-a and branch-b point to the same commit.

## 3️⃣ Modify the Same Line in Both Branches

- Changes in branch-a
- Modified the welcome message in index.html

        git checkout branch-a
        git add index.html
        git commit -m "Update welcome message in branch-a"

- Changes in branch-b
- Modified the same welcome message differently

        git checkout branch-b
        git add index.html
        git commit -m "Update welcome message in branch-b

## 4️⃣ Merge Branches and Observe Conflict

- Switched to master and attempted a merge:

        git checkout master
        git merge branch-a
        git merge branch-b

⚠️ Git detected a merge conflict because the same line was modified in both branches.