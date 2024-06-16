---

# GithubDemo Repository

**Welcome to the GithubDemo repository!** This repository serves as a documentation of my journey learning and practicing Git, GitHub, and various Git commands. The journey began with downloading Git from [git-scm.com](https://git-scm.com) and configuring it on a Windows system.

## Initial Configuration

After installing Git, I configured my username and email using the following commands:

```bash
git config --global user.name "Your Name"
git config --global user.email "your_email@example.com"
```

These commands set up my identity in Git, which is used in every commit.

## Creating a Project Directory

On the desktop, I opened the command prompt and used the `dir` command to list directories. Then, I navigated to the desktop using:

```cmd
cd Desktop
```

Once on the desktop, I created a new folder named "Vishal Project" with:

```cmd
mkdir "Vishal Project"
```

*Note: To create a folder with spaces in its name, use quotes around the folder name.*

## Initializing a Git Repository

I navigated into the newly created folder:

```cmd
cd "Vishal Project"
```

Inside this folder, I initialized a new Git repository:

```bash
git init
```

To confirm the creation of the `.git` directory (which might be hidden), I used:

```cmd
dir /a
```

## First Commit

I created a new text file named `01-NAME.txt`:

```cmd
type nul > 01-NAME.txt
```

Then, I checked the status of the repository with:

```bash
git status
```

I added the new file to staging:

```bash
git add 01-NAME.txt
# or to add all untracked or unstaged changes:
git add .
```

After staging the changes, I made my first commit:

```bash
git commit -m "Added 01-NAME.txt"
```

I verified that there were no staged or unstaged changes with another `git status`, followed by viewing the commit log:

```bash
git log
```

## Editing Files

I opened `01-NAME.txt` in Notepad, added my name, saved, and closed it. To view the contents of the file from cmd, I used:

```cmd
type 01-NAME.txt
```

After making changes to the file, I staged them again and then decided to unstage using:

```bash
git restore --staged 01-NAME.txt
```

I re-staged and committed the changes with an updated message:

```bash
git add 01-NAME.txt
git commit -m "Updated 01-NAME.txt with name"
```

## Adding More Files

I continued by adding more files like `02-Address.txt`, `03-ContactDetails.txt`, and `04-MoreInformation.txt`. During this process, I demonstrated how to delete files and undo changes using commands like:

```cmd
del /F 01-NAME.txt # Delete a file forcefully.
```

```bash
git reset <commit_id> # Unstage all changes after a specific commit.
```

After adding files to staging, I showed how to unstage all changes at once:

```bash
git restore --staged .
```

## Stashing Changes

To temporarily store changes without committing them, I used stashing commands:

```bash
git stash # Store current changes.
git stash pop # Apply stored changes.
git stash list # List all stashes.
git stash clear # Clear all stashes.
```

## Connecting to GitHub

After creating a public repository named GithubDemo on GitHub, I connected my local repository to it with:

```bash
git remote add origin <repository_link>
git remote -v # Verify remote URLs.
```

I pushed my local master branch to GitHub with:

```bash
git push origin master
```

## Branching and Merging

I created a new branch named `feature1` and switched to it:

```bash
git branch feature1
git checkout feature1
# Make some changes...
git add .
git commit -m "Feature1 updates"
git push origin feature1 # Push branch to GitHub.
```

On GitHub, I was prompted to create a pull request (PR), review it, and choose between merging or squashing commits.

Alternatively, from cmd after switching back to the master branch, I merged `feature1`:

```bash
git checkout master
git branch # Check current branch.
git merge feature1 # Merge feature1 into master.
```

During the merge, if there are conflicts, you might need to enter the interactive editor. Here's how to exit it:

- To save and exit: Press `i` (insert mode), make your changes, press `Esc`, type `:wq`, and press `Enter`.
- To exit without saving: Press `Esc`, type `:q!`, and press `Enter`.

After merging, I pushed the updated master branch to GitHub:

```bash
git push origin master
```

## Additional Commands

I also learned about various other commands and configurations:

- To make Git case-sensitive on Windows:
  
  ```bash
  git config core.ignorecase false
  ```

- To reset the repository to a specific commit and discard all changes:
  
  ```bash
  git reset --hard <commit_id>
  ```

- To add and commit changes in one command:
  
  ```bash
  git add .; git commit -m "Commit message"
  ```

- To understand the difference between fetching and pulling from a remote repository:
  
  ```bash
  git fetch # Fetches updates from remote.
  git pull # Fetches updates and merges them.
  ```

This README documents all the steps, commands, and explanations of my learning process with Git and GitHub. It serves as a guide for anyone starting their journey with version control.

---
