# Kimsia's Git Workflow Guide

## 📍 Start of Coding Session

### 1. Get Latest Changes (Must do at start of session)
```bash
# Make sure you're on your feature branch
git checkout your-feature-branch

# Fetch latest changes
git fetch origin

# Rebase on latest main
git rebase origin/main
```

### 2. Restore Your Work-in-Progress (if you have any stashes you want to continue)
```bash
# List your saved stashes
git stash list

# Apply most recent stash
git stash apply stash@{0}
# OR apply and remove it from stash list
git stash pop

# If you have multiple stashes, you can apply specific ones
git stash apply stash@{1}  # applies the second most recent stash
```

### 3. Handle Any Conflicts (if any conflicts occur)
```bash
# If you get conflicts, check status
git status

# After resolving conflicts in your editor
git add <resolved-files>
git rebase --continue   # if during rebase
# OR
git stash pop --continue   # if during stash pop
```

## 🏁 End of Coding Session

### Option 1: Stash Work-in-Progress (if you don't feel like committing)
```bash
# Save all changes including untracked files
git stash -u

# Add a descriptive message
git stash push -m "WIP: user authentication feature"

# Verify your stash
git stash list
```

### Option 2: Commit Your Changes (where possible try to aim to commit something, but don't force it)
```bash
# Check what you're about to commit
git status

# Stage and commit
git add <files>
git commit -m "feat: add user authentication logic"

# Push if ready (use force-with-lease if you rebased)
git push --force-with-lease origin your-feature-branch
```

## 💡 Pro Tips

1. **Stash Naming Convention**
   ```bash
   git stash push -m "WIP: <feature>: <brief description>"
   ```

2. **View Stash Contents**
   ```bash
   git stash show -p stash@{0}
   ```

3. **Partial Stashing**
   ```bash
   # Stash only specific files
   git stash push -m "specific files only" path/to/file1 path/to/file2
   ```

4. **Clean Up Old Stashes**
   ```bash
   # Remove specific stash
   git stash drop stash@{1}

   # Clear all stashes
   git stash clear
   ```