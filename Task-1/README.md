Git Task 1 - Innitialize,Commit, and Branching

Objective:
    1.Initializing a Git repository
    2.Creating and committing files
    3.Creating and switching between branches
    4.Merging a feature branch into the default branch
    5.Verifying commit history

Steps Performed:

1. Initialize Repoitory:
        git init
    Uses ,aster as default branch

2. Create and commit files

    Basic project files created: index.html,style.css

        git add .
        git commit -m "Add index.html and style.css"

3. Create and work on Feature branches

        git checkout -b feature-update
    
    The following actions were performed:
        1. Create a new branch named "feature-update".
        2. Switch to the "feature-update" branch.
        3. updated content in html
        4. Add the "update.html" file to the staging area.

        git add index.html
        git commit -m "Update content in feature branch"

4. Merge feature branch into master

        git checkout master
        git merge feature-update


5. Verify Commit history

        git log 
        git log --oneline
        h=git log --oneline --graph

6. Push repoditory to GitHub

        git remote add origin <>
        git push -u origin master
        git push origin feature-update
