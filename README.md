Essential Git Commands: A Step-by-Step Guide

This guide will walk you through the fundamental Git commands you'll use daily, from cloning an existing project to pushing your changes back to a remote repository.

1. Cloning a Repository

To start working on an existing project, you first need to get a copy of it onto your local machine. This is called "cloning."

Command: git clone <repository_url>

Purpose: Downloads a complete copy of a Git repository from a remote server (like GitHub, GitLab, Bitbucket) to your local computer.

Example:

git clone https://github.com/your-username/your-project.git

This will create a new directory named your-project (or whatever the repository's name is) in your current location, containing all the project files and its entire Git history.

2. Navigating into the Repository

After cloning, you need to move into the newly created project directory to start working with its Git features.

Command: cd <repository_name>

Purpose: Changes your current directory in the terminal to the cloned repository's folder.

Example:

cd your-project

Your terminal prompt might change to indicate you're inside a Git repository (e.g., (main) or master).

3. Checking the Status

Before making changes or after making some, it's good practice to check the current state of your working directory and staging area.

Command: git status

Purpose: Shows you which files have been modified, which are staged for commit, and which are untracked. It also tells you what branch you're on and if your local branch is ahead or behind the remote.

Example Output (you'll see different messages depending on your changes):

On branch main
Your branch is up to date with 'origin/main'.

Untracked files:
  (use "git add <file>..." to include in what will be committed)
    new-file.txt

Changes not staged for commit:
  (use "git add <file>..." to update what will be committed)
  (use "git restore <file>..." to discard changes in working directory)
    modified-file.txt

nothing added to commit but untracked files present (use "git add" to track)

4. Making Changes (Implicit)

This step involves you actually editing, adding, or deleting files in your project using your code editor or IDE. Git doesn't have a command for this; it just tracks the results of your work.

5. Staging Changes

After you've made changes, you need to tell Git which specific changes you want to include in your next commit. This is called "staging."

Command (to stage specific files): git add <file_name>

Command (to stage all changes in the current directory): git add .

Command (to stage all changes, including deletions, across the repository): git add -A

Purpose: Moves changes from the "working directory" to the "staging area" (also known as the "index"). Only staged changes will be included in the next commit.

Example:

git add index.html style.css  # Stage specific files
git add .                     # Stage all new/modified files in current directory
git add -A                    # Stage all changes (new, modified, deleted) in repo

6. Committing Changes

Once your changes are staged, you "commit" them. A commit is a snapshot of your repository at a specific point in time, along with a message describing the changes.

Command: git commit -m "Your descriptive commit message"

Purpose: Records the staged changes permanently into the repository's history. The commit message is crucial for understanding the purpose of the changes later.

Example:

git commit -m "Add header and basic styling to homepage"

If you omit -m, Git will open a text editor (like Vim or Nano) for you to write a longer commit message. See previous answers on how to exit these editors.

7. Viewing History

You can review the project's commit history to see who made what changes and when.

Command: git log

Purpose: Displays a list of all commits in the current branch, showing the commit hash, author, date, and commit message.

Example Output:

commit 7b1c3d9aef0f4e2b8c9d0a1b2c3d4e5f6a7b8c9d (HEAD -> main, origin/main)
Author: Your Name <your.email@example.com>
Date:   Mon Jul 22 14:30:00 2025 -0500

    Add header and basic styling to homepage

commit abcdef1234567890abcdef1234567890abcdef12
Author: Another User <another.user@example.com>
Date:   Fri Jul 19 10:00:00 2025 -0500

    Initial project setup

If the log is long, it will open in a pager. Press q to exit.

8. Pulling Latest Changes

If you're collaborating with others, they might have pushed changes to the remote repository. You need to "pull" those changes to keep your local copy up-to-date.

Command: git pull

Purpose: Fetches changes from the remote repository and automatically merges them into your current local branch.

Example:

git pull

It's a good habit to git pull before you start working and before you git push your own changes.

9. Pushing Changes

Once you've committed your changes locally, you need to "push" them to the remote repository so others can see and access them.

Command (for current branch): git push

Command (explicitly specifying remote and branch, especially useful when working with multiple branches or for clarity): git push origin <branch_name>

Purpose: Uploads your local commits to the remote repository.

Example:

git push
# Or, if you're on a branch named 'feature/my-feature' and want to push it to origin:
git push origin feature/my-feature

If it's the first time you're pushing a new local branch, Git might tell you to set an "upstream" branch, like: git push --set-upstream origin <branch_name>.

10. Branching (Optional but Recommended)

Branching allows you to work on new features or bug fixes in isolation without affecting the main codebase.

Create a new branch:

git branch <new_branch_name> (creates the branch)

Example: git branch feature/new-login

Switch to a branch:

git checkout <branch_name> (older command)

Newer, recommended command: git switch <branch_name>

Example: git switch feature/new-login

Shortcut to create and switch:

git checkout -b <new_branch_name> (older command)

Newer, recommended command: git switch -c <new_branch_name>

List branches: git branch (shows local branches, current branch highlighted)

git branch -a (shows all branches, local and remote)

Merge a branch: After finishing work on a feature branch, you merge its changes back into another branch (e.g., main).

Switch to the target branch: git switch main (or git checkout main)

Merge the feature branch: git merge feature/new-login

Delete a branch (after merging): git branch -d <branch_name>

Example: git branch -d feature/new-login

This covers the most essential Git commands for a typical workflow. Practice these regularly, and you'll become comfortable with Git in no time!



Starting a New Project (Initializing a Repository)

If you're starting a new project from scratch on your local machine and want to add Git version control to it, you'll "initialize" a new Git repository.

From the Terminal

Command: git init

Purpose: Creates a new, empty Git repository in the current directory. This adds a hidden .git folder, which is where Git stores all its tracking information.

Example:

# Navigate to your project folder
cd ~/Documents/MyNewProject
git init

After running this, your project folder is now a Git repository, but it doesn't have any commits yet. To make your first commit and start tracking your project:

Stage your initial files:

git add .

This command stages all the files in your current directory, preparing them for the first commit.

Make your initial commit:

git commit -m "Initial project setup"

This creates the very first snapshot of your project's history.