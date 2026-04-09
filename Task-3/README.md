Task 3- Undoing Changes and Reverting Commits

## 🎯 Objective

1. Undo uncommitted changes using `git checkout` or `git restore`
2. Undo committed changes safely using `git revert` or `git reset`
3. Understand the differences between `git checkout`, `git restore`, `git reset`, and `git revert`

## Steps to Complete
1. Undoing uncommitted changes:

    A tracked file (`index.html`) was modified accidentally in the working directory.

    The file status was checked using:
        
        git status

    To discard the uncommitted changes and restore the file to the last committed state, the following command was used:

        git checkout -- index.html

2. Make a commit 

    A new commit was made with the message "Added index.html".

        git add index.html
        git commit -m "Added index.html"

3. Undo a commit safely using revert:

        git revert HEAD

    The commit history was verified using:

        git log --oneline

4. Difference between `git checkout`, `git restore`, `git reset`, and `git revert`:

    - `git checkout` is used to discard changes in the working directory and restore the file to the last committed state.
    - `git restore` is used to discard changes in the staging area and restore the file to the last committed state.
    - `git reset` is used to discard changes in the working directory and staging area and restore the file to the last committed state.
    - `git revert` is used to undo a commit safely by creating a new commit that reverses the changes made in the commit.
