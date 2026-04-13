# 🍒 Git Task 07 – Cherry-Picking Commits Between Branches

## 🎯 Objective
The objective of this task is to selectively apply a specific commit from one branch to another using **git cherry-pick**, without merging the entire branch.

---

## 🛠️ Task Description
Two separate branches were created with independent commits.  
A specific commit from one branch was identified and cherry-picked into another branch to demonstrate selective commit transfer.

---

## 🌿 Branches Used
- `branch-A`
- `branch-B`

---

## 🚀 Steps Followed

### 1️⃣ Switched to Branch A and Made a Commit
- A new file was created and committed in `branch-A`.

        echo "Add text in branch-A" >> branch-A.txt
        git add branch-A.txt
        git commit -m "Add text in branch-A.txt"

2️⃣ Switched to Branch B and Made a Separate Commit

- A different file was created and committed in branch-B.

    git checkout branch-B
    git add branch-B.txt
    git commit -m "Add new file in branch-B"

3️⃣ Identified Commit to Cherry-Pick

- The commit from branch-A that needed to be applied to branch-B was identified using:

        git log --oneline

- Commit selected for cherry-pick:
- d2b44c4 Add text in branch-A.txt

- The selected commit from branch-A was applied to branch-B.

        git cherry-pick d2b44c4

5️⃣ Verified Commit History

- The commit history was verified to confirm that the cherry-picked commit was successfully added.

        git log --oneline