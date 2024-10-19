# **Git Commands and Workflows**

---

## **1. Introduction to Git**  
Git is a **distributed version control system** (DVCS) used to manage source code and track changes efficiently. It allows for **collaborative development** and **version control**, keeping every modification documented, and enabling developers to roll back to previous states when needed.

---

## **2. Initial Setup and Configuration**  
Before using Git, you need to configure it for your system.

```bash
git config --global user.name "Your Name"
git config --global user.email "your.email@example.com"
```
- Use **`git config --list`** to display all configurations.
- **Alias common commands**:
  ```bash
  git config --global alias.st 'status'
  git config --global alias.co 'checkout'
  ```

---

## **3. Repository Initialization and Cloning**  
### **Create a New Repository**:
```bash
git init
```
This command initializes a **new Git repository** in your current directory.

### **Clone a Remote Repository**:
```bash
git clone <repository_url>
```
- To clone a specific branch:
  ```bash
  git clone --branch <branch_name> <repository_url>
  ```

---

## **4. Staging, Committing, and Status Check**  
### **Track Changes**:
```bash
git add <file>        # Stage a specific file
git add .             # Stage all changes
```
### **Commit Changes**:
```bash
git commit -m "Commit message"
```
To modify the last commit without changing the message:
```bash
git commit --amend --no-edit
```

### **Check Repository Status**:
```bash
git status
```

---

## **5. Branching and Merging**  
### **Create and Switch Branches**:
```bash
git branch <branch_name>    # Create a new branch
git switch <branch_name>    # Switch to the branch
git checkout -b <branch_name>   # Create and switch simultaneously
```

### **Merge Branches**:
```bash
git merge <branch_name>     # Merge a branch into the current one
git merge --no-ff           # Ensure a merge commit is created
```
- **Abort a merge**:
  ```bash
  git merge --abort
  ```

---

## **6. Rebasing and Cherry-picking**  
### **Rebase**:
```bash
git rebase <branch>       # Move your branch onto the target branch
git rebase --continue     # Continue rebasing after conflict resolution
```

### **Cherry-pick**:
```bash
git cherry-pick <commit_hash>   # Apply specific commits from another branch
```

---

## **7. Stashing Changes**  
### **Basic Stash Commands**:
```bash
git stash              # Save uncommitted changes
git stash list         # View stashed items
git stash apply        # Reapply the latest stash without removing it
git stash pop          # Apply and delete the stash
```
- **Stash untracked files**:
  ```bash
  git stash --include-untracked
  ```

---

## **8. Inspecting Commits and Logs**  
### **View Commit History**:
```bash
git log --graph --oneline --decorate
```
- **View a specific commit**:
  ```bash
  git show <commit_hash>
  ```
### **Blame: Find Line Changes**:
```bash
git blame <file_name>
```

---

## **9. Remote Repositories and Collaboration**  
### **Adding and Fetching Remote Repositories**:
```bash
git remote add origin <url>    # Link to a remote repository
git fetch origin               # Fetch updates without merging
```

### **Pushing and Pulling Changes**:
```bash
git push origin <branch_name>   # Push changes to the remote branch
git pull origin <branch_name>   # Fetch and merge in one step
```

---

## **10. Git Reset and Reflog for Recovery**  
### **Reset Commits**:
```bash
git reset --soft <commit>   # Keep changes staged
git reset --hard <commit>   # Discard all changes
```

### **Reflog**:
```bash
git reflog                  # View all `HEAD` changes
git reset --hard HEAD@{1}   # Recover from previous state
```

---

## **11. Clean Up and Organize**  
```bash
git clean -f      # Remove untracked files
git clean -fd     # Remove untracked files and directories
```

---

## **12. Git Bisect: Debugging with Binary Search**  
```bash
git bisect start
git bisect bad       # Mark the current commit as faulty
git bisect good <commit>   # Mark a known good commit
```

---

## **13. Tags and Releases**  
### **Create and Push Tags**:
```bash
git tag -a v1.0 -m "Version 1.0"
git push origin --tags
```

---

## **14. Submodules and Worktrees**  
### **Submodules**:
```bash
git submodule add <repo_url> <path>   # Add a submodule
git submodule update --init           # Initialize and update submodules
```

### **Worktrees**:
```bash
git worktree add ../new-branch <branch_name>
```

---

## **15. Aliases for Efficiency**  
Create aliases to simplify frequently used commands:
```bash
git config --global alias.stsh 'stash --all'
git config --global alias.shorty 'status --short --branch'
```

---

## **16. Git Hooks**  
Automate tasks using **hooks**:
- Create scripts in the `.git/hooks/` directory.
- Example: A **pre-commit** hook to enforce coding standards.

---

## **17. `git am` and `git format-patch`**  
### **Apply Patch Files**:
```bash
git am <patch_file>
```
### **Create Patch Files**:
```bash
git format-patch -1 <commit_hash>
```

---

## **18. Helpful Git Flags and Tricks**  
- **`git push --force-with-lease`**: Safer force-pushing to avoid overwriting upstream changes【21†source】.
- **`git log --stat`**: View commit statistics (lines added/removed).
- **`git shortlog`**: Group commits by author.

---

## **19. Git GUI Tools and Visual Helpers**  
Use GUI tools like **SourceTree** or **GitKraken** for visual Git management. You can also use `git log --graph` to view your commit history graphically in the terminal.

---

For further reading and examples, refer to:
- [Pro Git Book](https://git-scm.com/book/en/v2)
- [Advanced Git Commands on HackerNoon](https://hackernoon.com/lesser-known-git-commands-151a1918a60)【20†source】.
- [Freek's Blog on Git](https://freek.dev/586-lesser-known-git-commands)【22†source】.

