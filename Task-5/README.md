# 📘 Git Task 05 – Interactive Rebasing for Clean Commit History

---

## 🎯 Objective

The objective of this task is to understand and apply **interactive rebasing** in Git to maintain a clean and meaningful commit history. This task focuses on learning how to tidy up multiple commits before merging changes into the main branch.

---

## 🛠️ Task Requirements

- Create multiple commits with minor changes or simple commit messages
- Use interactive rebase to:
  - Squash commits
  - Reorder commits
  - Edit commit messages
- Understand how squashing improves commit history before merging

---

## 🧪 Steps Performed

### 1. Create a Feature Branch

A separate feature branch was created to safely perform interactive rebasing:


git checkout -b rebase-demo

## 2. Create Multiple Commits

Several small commits were made by:

- Updating project content
- Fixing minor issues
- Adding small improvements

This resulted in a messy commit history suitable for cleanup.

## 3. View Commit History

The commit history was reviewed using:

    git log --oneline

## 4. Start Interactive Rebase

Interactive rebase was initiated to clean up the last few commits:

    git rebase -i HEAD~n

n represents the number of recent commits selected for rebasing.

## 5. Squash, Reorder, and Edit Commits

In the interactive rebase editor:

- Multiple commits were squashed into one
- Commit order was rearranged
- Commit messages were edited for clarity

Common commands used:

- pick – keep the commit
- squash – combine commits
-reword – edit commit message

## 6. Verify Clean Commit History

After completing the rebase, the updated commit history was verified:

    git log --oneline

This confirmed that multiple commits were successfully combined into a single, clean commit.