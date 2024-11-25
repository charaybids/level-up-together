# Git Rebase Guide: Pulling Remote Changes

## Basic Workflow

```bash
# 1. First, make sure you're on your feature branch
git checkout your-feature-branch

# 2. Fetch the latest changes from remote
git fetch origin

# 3. Rebase your branch onto the updated main branch
git rebase origin/main
```

## Common Scenarios

### Scenario 1: Simple Rebase (No Conflicts)

```bash
# Starting from your feature branch
git checkout feature/user-auth
git fetch origin
git rebase origin/main

# If everything goes well, push your changes
git push --force-with-lease origin feature/user-auth
```

### Scenario 2: Handling Conflicts During Rebase

```bash
# If you encounter conflicts during rebase
# 1. Fix conflicts in your editor
# 2. Stage the resolved files
git add <resolved-files>

# 3. Continue the rebase
git rebase --continue

# 4. If you need to abort the rebase
git rebase --abort
```

## Best Practices

1. **Always backup your branch**

```bash
# Create a backup branch
git branch feature/user-auth-backup
```

2. **Check what commits will be rebased**

```bash
# See commits that will be rebased
git log origin/main..HEAD
```

3. **Use force-with-lease instead of force**

```bash
# Safer than git push --force
git push --force-with-lease origin your-branch
```

## Common Mistakes to Avoid

1. Never rebase commits that have been pushed to shared branches
2. Don't rebase without fetching latest changes first
3. Always confirm you're on the correct branch before rebasing

## Troubleshooting Tips

If something goes wrong:

```bash
# View current rebase status
git status

# Abort rebase and start over
git rebase --abort

# Return to previous state using reflog
git reflog
git reset --hard HEAD@{1}
```