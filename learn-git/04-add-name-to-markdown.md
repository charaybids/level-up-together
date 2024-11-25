# How to Add Your Name Using a Pull Request

This guide will walk you through the process of adding your name to a markdown file using a pull request (PR).

## Prerequisites
- A GitHub account
- Git installed on your computer
- Basic familiarity with terminal/command line

## Step-by-Step Guide

### 1. Fork the Repository
1. Navigate to the repository on GitHub
2. Click the "Fork" button in the top-right corner
3. This creates a copy of the repository in your GitHub account

### 2. Clone Your Fork
```bash
# Replace USERNAME with your GitHub username
# Replace REPOSITORY with the repository name
git clone https://github.com/USERNAME/REPOSITORY.git
cd REPOSITORY
```

### 3. Create a New Branch
```bash
# Create and switch to a new branch
# Assuming your name is Alice A. and the topic is learn-git
git checkout -b add-alice-a-to-learn-git
```

### 4. Make Your Changes
1. Open the markdown file in your preferred text editor
2. Add your name to the file
   ```markdown
   - [Your Name](https://github.com/your-username)
   ```
3. Save the file

### 5. Commit Your Changes
```bash
# Stage your changes
git add .

# Commit with a descriptive message
git commit -m "chore: add [Your Name] to learners list"
```

### 6. Push Your Changes
```bash
# Push your branch to your fork
git push origin add-alice-a-to-learn-git
```

### 7. Create the Pull Request
1. Go to the original repository on GitHub
2. Click "Pull requests" > "New Pull Request" at https://github.com/ForStudentsByStudents-MITB/level-up-together/pulls
3. Click "compare across forks"
4. Select your fork and branch as the source
5. Add a title like "chore: add [Your Name] to learners list"
6. Click "Create pull request"

## Best Practices
- Follow any existing formatting in the file
- Make sure your name isn't already listed
- Use a clear commit message
- Respond to any feedback from maintainers

## Common Issues and Solutions
- **Can't push changes**: Make sure you have the correct permissions and are pushing to your fork
- **Merge conflicts**: Pull the latest changes from the main repository and resolve conflicts locally
- **PR shows other changes**: Make sure you're working on a clean branch with only your intended changes

## Need Help?
If you run into issues, you can:
- Check GitHub's documentation
- Ask in the repository's issues section
- Reach out to the maintainers