## 📘 Git Task 06 – Stashing Changes for Context Switching
## 🎯 Objective

    The objective of this task is to understand and use Git stash to temporarily save uncommitted changes. This allows switching branches or handling urgent work without losing progress in the current working directory.

## 🛠️ Task Requirements
- Make changes without committing them
- Store those changes using git stash
- Switch branches and perform other tasks
- Reapply the stashed changes using git stash pop
- Learn how to view and manage stashes

## 🧪 Steps Performed
1. Make Uncommitted Changes

- Changes were made to the following files without committing:

index.html
style.css

-The working directory status was checked using:

        git status
2. Stash the Changes

- The uncommitted changes were saved temporarily using:

        git stash

- This removed the changes from the working directory and stored them safely in a stash.

3. View Available Stashes

- The list of stashed changes was viewed using:

        git stash list

    Example output:

    - stash@{0}: WIP on master: Add output screenshots and readme file to task-5

4. Switch Context and Reapply Stash

- After completing other work, the stashed changes were reapplied using:

        git stash pop

- The changes were restored to the working directory
- The stash entry was automatically removed after applying

5. Verify Stash Removal

- The stash list was checked again:

        git stash list

- No entries were found, confirming the stash was successfully applied and cleared.

