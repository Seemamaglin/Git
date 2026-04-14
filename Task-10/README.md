# Task 10 – Comprehensive Git Workflow with Forced Push & Recovery

## 📌 Objective
The objective of this task is to understand advanced Git workflows involving:
- Multiple branches
- History rewriting using rebase and reset
- Forced pushes (`git push --force`)
- Recovering lost commits using `git reflog`
- Best practices when collaborating in a team

This task demonstrates how mistakes can happen in real projects and how Git provides tools to safely recover from them.

---

## 🛠️ Branch Strategy Used
- `master` – Main stable branch
- `feature/task-10` – Feature branch for Task 10
- Other feature branches were used in earlier tasks to simulate collaboration

---

## 📂 Working Location
All operations were performed **inside the existing Git repository**.  
Documentation and outputs related to this task are stored inside the `Task-10` folder.

---

## 🔄 Step-by-Step Workflow

### 1️⃣ Create a Feature Branch

        git checkout -b feature/task-10

## 2️⃣ Make Commits

- Files related to Task-10 were added and committed normally.

        git add .
        git commit -m "Task-10 initial commit"

## 3️⃣ Rewrite History (Simulating a Real Scenario)

- To simulate history rewriting, a hard reset was performed:

        git reset --hard HEAD~1

⚠️ This removed the latest commit from the branch history.

## 4️⃣ Forced Push to Remote

- Since history was rewritten, a normal push was rejected.
- A forced push was required:

        git push --force origin feature/task-10

- This updated the remote branch to match the rewritten local history.

❌ Problem Faced: Lost Commit

After the hard reset and forced push:

The removed commit was no longer visible in git log
The commit appeared to be lost

This simulates a common real-world mistake during rebasing or force pushing.

🔍 Solution: Recovering the Lost Commit using git reflog

## 5️⃣ Locate the Lost Commit

        git reflog

Sample output:

c736105 HEAD@{0}: reset: moving to HEAD~1
16709e8 HEAD@{1}: push --force
18d11c8 HEAD@{2}: commit: Task-10 changes

➡️ The commit 18d11c8 was identified as the lost commit.

## 6️⃣ Recover the Commit 

        git reset --hard 18d11c8

This restored the commit locally.

## 7️⃣ Push the Recovered Commit

        git push --force

The recovered commit was successfully restored on the remote branch.