📘 Git Task 08 – Pre-commit Hook for Clean Code

🎯 Objective

- The objective of this task is to understand Git Hooks, specifically the pre-commit hook, and use it to enforce clean code standards by blocking commits that contain console.log statements.

- This task demonstrates how automated checks can prevent unwanted code from entering the repository.

🧠 What are Git Hooks?

Git Hooks are scripts that Git automatically runs at certain points in the Git workflow.

🔑 Key Points:

- Hooks live inside the .git/hooks/ directory
- They are written as shell scripts
- They run automatically (no manual execution)
- If a hook exits with:

  - 0 → Git continues
  - 1 → Git stops the operation

=> Pre-commit Hook

- Runs before a commit is created
- Used to validate code, formatting, linting, etc.

📂 Task Description

Create a pre-commit hook that:

- Scans the project files
- Detects any usage of console.log
- Blocks the commit if found
- Allows the commit if the code is clean

🛠️ Implementation Steps

Step 1: Navigate to Hooks Directory

    cd .git/hooks

Step 2: Create the pre-commit File

    nano pre-commit

Step 3: Write the Pre-commit Script

    #!/bin/sh
    echo "Running pre-commit checks..."

    if grep -R "console.log" . --exclude-dir=.git; then
        echo "❌ console.log found. Commit blocked."
    exit 1
    fi

    echo "✅ Code is clean"
    exit 0

Step 4: Make the Hook Executable

    chmod +x .git/hooks/pre-commit

🧪 Testing the Hook

Case 1: Code Contains console.log

    console.log("debug message");
    git commit -m "Test commit"

❌ Output:

❌ console.log found. Commit blocked.

Commit is stopped.

Case 2: Clean Code (No console.log)

        git commit -m "Clean commit"

✅ Output:

Running pre-commit checks...
✅ Code is clean

Commit is successful.

⚠️ Issue Faced During Implementation

Even after deleting the file containing console.log, the commit was still blocked.

Error message:

./.git/hooks/pre-commit:if grep -R "console.log" .; then

🔍 Root Cause

The command:

grep -R "console.log" .

was scanning all directories, including:

    .git/hooks/pre-commit

Since the hook itself contained the word console.log, it detected itself, causing the commit to fail every time.

✅ Solution Applied

Excluded the .git directory from the search:

    grep -R "console.log" . --exclude-dir=.git

