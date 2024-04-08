# DevOps Engineer Beginner's Guide to GitHub

Welcome to your first steps towards becoming a DevOps Engineer. This guide is designed to introduce you to the basics of using GitHub, a vital tool in the world of software development and operations. By the end of this guide, you will know how to set up your environment for secure communication with GitHub, clone repositories, manage files with VS Code, and maintain your projects with version control.

## Prerequisites

- A GitHub account. If you don't have one, sign up at [GitHub](https://github.com/).
- Visual Studio Code (VS Code) installed on your computer. Download it from [Visual Studio Code](https://code.visualstudio.com/).

## Table of Contents

1. Setting Up SSH Keys
2. Adding SSH Keys to GitHub
3. Cloning a Repository
4. Using VS Code
5. Making Changes and Committing
6. Pushing Changes to GitHub
7. Pulling Updates from GitHub

## 1. Setting Up SSH Keys

SSH keys serve as a means to securely communicate with GitHub without needing to use your password each time.

- Open a terminal or command prompt.
- Enter `ssh-keygen -t ed25519 -C "your_email@example.com"`, replacing `your_email@example.com` with your GitHub email.
- Press enter to accept the default file location.
- (Optional) Enter a passphrase for additional security when prompted.
- Your SSH key is now generated.

## 2. Adding SSH Keys to GitHub

- Navigate to your SSH directory (usually `~/.ssh`) and open the file named `id_ed25519.pub` in a text editor to copy your SSH public key.
- Go to GitHub -> Settings -> SSH and GPG keys -> New SSH key.
- Paste your SSH key, give it a descriptive title, and click "Add SSH key".

## 3. Cloning a Repository

- Find a repository on GitHub that you want to clone.
- Click the "Code" button and select the "SSH" option to copy the SSH URL.
- In your terminal, enter `git clone <SSH_URL>`, replacing `<SSH_URL>` with the URL you copied.

## 4. Using VS Code

- Open VS Code.
- Go to File -> Open Folder, and select the repository folder you cloned.
- You can now edit files, add new files, and explore the repository in VS Code.

## 5. Making Changes and Committing

- Make changes to a file or create a new file in your repository folder using VS Code.
- Open the terminal in VS Code (Terminal -> New Terminal).
- Use `git add .` to stage your changes.
- Commit your changes with `git commit -m "Your commit message"`, replacing `Your commit message` with a description of your changes.

## 6. Pushing Changes to GitHub

- Push your committed changes to GitHub with `git push`.
- If you set a passphrase for your SSH key, enter it when prompted.

## 7. Pulling Updates from GitHub

- To make sure you have the latest changes from your GitHub repository, use `git pull` in your terminal.

Congratulations! You've covered the basics of managing projects on GitHub using SSH for secure communication, VS Code for editing, and git for version control. Keep practicing these steps to become more familiar with the process.


### Exercise 1: Set Up Your Workspace

**Objective:** Learn how to create a directory structure and initialize a Git repository.

1. **Create a Directory for Your Project:**
   - Open the Terminal.
   - Create a new directory with `mkdir DevOpsPractice`.
   - Navigate into it with `cd DevOpsPractice`.

2. **Initialize a New Git Repository:**
   - Within the `DevOpsPractice` directory, run `git init` to initialize a new Git repository.

3. **Create a README File:**
   - Still in the terminal, create a README file by running `echo "# DevOps Practice Repository" > README.md`.
   - Stage the README file with `git add README.md`.
   - Commit it with `git commit -m "Initial commit with README"`.

### Exercise 2: Working with Files and Directories

**Objective:** Practice basic file and directory manipulation commands.

1. **Create a New Directory and File:**
   - Create a directory named `scripts` with `mkdir scripts`.
   - Inside `scripts`, create a file named `setup.sh` with `touch scripts/setup.sh`.
   - Edit `setup.sh` with `open -a TextEdit scripts/setup.sh` and add `echo "Setting up DevOps environment"` as its content.

2. **Stage and Commit Changes:**
   - Use `git add scripts/setup.sh` to stage the new file.
   - Commit this addition with `git commit -m "Add setup script"`.

### Exercise 3: Interacting with GitHub

**Objective:** Practice pushing changes to GitHub and observing the result.

1. **Create a New Repository on GitHub:**
   - Go to [GitHub](https://github.com/) and create a new repository named `DevOpsPractice`. Do not initialize it with a README, .gitignore, or license.

2. **Link Your Local Repository to GitHub:**
   - Follow the instructions on GitHub to add a remote origin for your local repository, typically with `git remote add origin <REPO_SSH_URL>`.

3. **Push Your Local Commits to GitHub:**
   - Push your commits with `git push -u origin master` (or `main`, depending on your default branch name).

### Exercise 4: Modifying Content and Pushing Changes

**Objective:** Learn how to modify files, delete files, and see the effect of those changes on GitHub.

1. **Update and Remove Files:**
   - Add a new line to `README.md` with `echo "\nThis is a practice repository for basic DevOps skills." >> README.md`.
   - Remove the `setup.sh` script with `rm scripts/setup.sh`.

2. **Commit Your Changes:**
   - Stage changes with `git add -A`.
   - Commit with `git commit -m "Update README and remove setup script"`.

3. **Push Changes to GitHub:**
   - Push with `git push`.
   - Go to your GitHub repository page to see the updated `README.md` and the removal of `setup.sh`.

### Exercise 5: Cloning and Collaborating

**Objective:** Learn how to clone repositories and understand the basics of collaboration.

1. **Clone a Repository:**
   - Find a public repository on GitHub that you're interested in.
   - Clone it to your local machine with `git clone <REPO_SSH_URL>`.

2. **Explore the Repository:**
   - Navigate into the cloned repository directory.
   - Explore its content using `ls`, `cd`, and `open` commands.

### Exercise 6: Branching with Git

**Objective:** Learn how to create and manage branches in Git.

1. **Create a New Branch for a Feature:**
   - Create a new branch with `git branch feature-awesome`.
   - Switch to the new branch with `git checkout feature-awesome`.

2. **Add a New Feature:**
   - In the `DevOpsPractice` directory, create a new file `feature.txt` and add some content to it.
   - Stage and commit this new file to the `feature-awesome` branch.

3. **Merge the Feature Branch:**
   - Switch back to the master (or main) branch with `git checkout master`.
   - Merge the feature branch with `git merge feature-awesome`.
   - Push the changes to GitHub.

### Exercise 7: Explore Merge Conflicts

**Objective:** Understand how to resolve merge conflicts.

1. **Create Conflict:**
   - On the `master` branch, modify `README.md` and commit the change.
   - Switch to `feature-awesome` (or create another branch) and make a different change to `README.md`.
   - Attempt to merge this branch back into `master` with `git merge feature-awesome` and observe the conflict.

2. **Resolve the Conflict:**
   - Open the conflicted file(s) and choose which changes to keep.
   - Stage the resolved file(s) with `git add`.
   - Complete the merge with `git commit`.
   - Push the resolution to GitHub.

### Exercise 8: Tagging and Releases

**Objective:** Practice creating tags for releases.

1. **Create a Tag for Your Project:**
   - Ensure all changes are committed and pushed.
   - Create a tag with `git tag -a v1.0 -m "First release"`.
   - Push the tag to GitHub with `git push origin v1.0`.

2. **Explore Releases on GitHub:**
   - Go to your GitHub repository, navigate to the "Releases" section, and see your new tag.
   - Create a release note for your tag directly on GitHub.

### Exercise 9: Stashing Changes

**Objective:** Learn how to stash changes temporarily.

1. **Make Changes and Stash:**
   - Make changes to any file but don't commit them.
   - Run `git stash` to stash the changes.
   - Check the status with `git status` to see a clean working directory.

2. **Apply Stashed Changes:**
   - Retrieve stashed changes with `git stash pop`.
   - Stage, commit, and push these changes as practiced before.

### Exercise 10: Collaborating on GitHub

**Objective:** Practice collaborating by working on issues, pull requests, and reviewing code.

1. **Work on an Issue:**
   - Go to your GitHub repository and create a new issue, describing a feature or bug.
   - On your local machine, create a branch named after the issue, make the necessary changes to address the issue, and push the branch to GitHub.

2. **Open a Pull Request:**
   - On GitHub, open a pull request for your branch.
   - Describe the changes and link the pull request to the issue it resolves.

3. **Review and Merge the Pull Request:**
   - Review the changes on GitHub, comment if necessary.
   - Merge the pull request and close the issue.

### Bonus Challenge: Explore GitHub Actions

**Objective:** Gain a basic understanding of CI/CD with GitHub Actions.

1. **Read GitHub Actions Documentation:**
   - Visit the [GitHub Actions documentation](https://docs.github.com/en/actions) and familiarize yourself with the basics.

2. **Create a Simple Workflow:**
   - In your repository, create a new `.github/workflows` directory.
   - Add a new file named `ci.yml` and set up a simple workflow that runs on every push, performing tasks like installing dependencies or running scripts.

3. **Observe the Workflow:**
   - Make a change to trigger the workflow.
   - Go to the "Actions" tab on your GitHub repository to see the workflow run.

### Exercise 11: Initialize a New Project with VS Code

**Objective:** Set up a new project and open it in VS Code from the terminal.

1. **Create a New Directory for the Project:**
   - In the Terminal, use `mkdir MySecondProject` to create a new directory.
   - Navigate into it with `cd MySecondProject`.

2. **Initialize a Git Repository and Open VS Code:**
   - Run `git init` to initialize a new Git repository.
   - Open the project in VS Code by running `code .`.

3. **Create a New File in VS Code:**
   - Use the File Explorer in VS Code to create a new file named `index.html`.
   - Add basic HTML boilerplate code to `index.html`.
   - Save your changes.

4. **Commit Your File to Git:**
   - Use the Source Control panel in VS Code to stage your changes.
   - Commit the changes with a meaningful message.

### Exercise 12: Working with Multiple Files and Directories

**Objective:** Practice managing a more complex project structure with VS Code.

1. **Set Up Project Structure:**
   - Inside `MySecondProject`, create a directory structure with `mkdir css js assets`.
   - Navigate into each directory (`cd css`, etc.) and create a `.gitkeep` file in each (use `touch .gitkeep`).

2. **Open Project in VS Code:**
   - From the root of `MySecondProject`, run `code .` to reopen the project in VS Code.

3. **Add Content and Commit:**
   - Add a new CSS file under `css/` and a new JavaScript file under `js/`.
   - Use the Source Control panel in VS Code to stage, commit, and push your changes.

### Exercise 13: Branching and Merging with VS Code

**Objective:** Use VS Code's built-in Git support for branching and merging.

1. **Create a Feature Branch in VS Code:**
   - Use the Source Control panel to create a new branch named `feature-enhancement`.
   - Switch to the `feature-enhancement` branch.

2. **Make Changes in Your Feature Branch:**
   - Add or modify files as part of your new feature.
   - Stage, commit, and push your changes using the Source Control panel.

3. **Merge Your Feature Branch:**
   - Switch back to your `master` or `main` branch in VS Code.
   - Merge `feature-enhancement` into `master` using the terminal or VS Code's built-in Git features.

### Exercise 14: Resolving Merge Conflicts in VS Code

**Objective:** Learn how to handle merge conflicts using VS Code.

1. **Create Conflicting Changes:**
   - On the `master` branch, modify `index.html` and commit your changes.
   - Switch to or create a new branch and make different modifications to `index.html`.
   - Try to merge this branch back into `master` and note the conflict.

2. **Resolve the Conflict in VS Code:**
   - VS Code will highlight the conflicting changes.
   - Manually edit the file to resolve the conflicts, or use the built-in conflict resolution tools in VS Code.
   - After resolving, commit and push the changes.

### Exercise 15: Utilizing Git Stash in VS Code

**Objective:** Practice stashing changes directly from VS Code.

1. **Make Changes and Stash:**
   - Make some changes in your working directory but don't commit them.
   - Open the Source Control panel, right-click your changes, and select "Stash Changes".

2. **Apply Stashed Changes:**
   - Make additional changes and commit them.
   - Go back to the Source Control panel, right-click on your stash, and select "Pop Stash".
   - Resolve any conflicts, then stage and commit the changes.

### Bonus Challenge: Explore VS Code Extensions

**Objective:** Enhance your VS Code setup with extensions that improve productivity.

1. **Discover and Install Extensions:**
   - Open the Extensions view in VS Code (or press `Cmd+Shift+X`).
   - Search for and install extensions relevant to your development work, such as GitLens, Live Server, or Prettier.

2. **Configure and Use an Extension:**
   - After installing an extension, configure it as needed from the settings.
   - Use the extension in your project workflow. For instance, use GitLens to explore Git history, or use Live Server to preview an HTML file in real-time.

---

**Objective:** Practice initializing a repository and setting up essential files.

- Create a new directory called `ProjectInit`.
- Inside `ProjectInit`, run `git init` to initialize a new Git repository.
- Open this project in VS Code by running `code .` from within the directory.
- Create a `README.md` file and add a brief description of the project.
- Create a `.gitignore` file and add `.DS_Store` to ignore Mac system files.
- Stage and commit both files.

---

**Objective:** Learn branching and basic file operations.

- Ensure you are in the `ProjectInit` directory.
- Create a new branch named `update-readme` with `git checkout -b update-readme`.
- Modify the `README.md` in VS Code to include more project details.
- Add a section about contributing to the project.
- Stage the changes and commit them with a descriptive message.
- Merge `update-readme` back into the master/main branch.

---

**Objective:** Practice cloning and working with an existing repository.

- Clone an existing GitHub repository you have access to using `git clone <repository-SSH-URL>`.
- Navigate into the cloned repository's directory.
- Open the directory in VS Code using `code .`.
- Create a new branch named `cleanup`.
- Look for any unnecessary files or outdated information in `README.md` and make appropriate updates or deletions.
- Add a `.gitignore` file if it doesn't exist and populate it with common patterns (like `node_modules/`, `.env`).
- Commit your changes and push the `cleanup` branch to GitHub.

---

**Objective:** Simulate a collaborative workflow with issues and pull requests.

- Within the GitHub interface for the cloned repository, open a new issue describing a fake bug or needed improvement in the `README.md`.
- Locally, switch to a new branch named `issue-fix` where you will work on resolving this issue.
- Make the necessary changes in VS Code to address the issue outlined.
- Commit your changes and push the `issue-fix` branch to GitHub.
- Open a pull request on GitHub from your `issue-fix` branch to the main branch, referencing the issue you created.
- Merge the pull request once satisfied with the changes.

---

**Objective:** Handling updates and conflicts.

- On GitHub, directly edit `README.md` in the main branch to add a new line at the end of the file.
- Locally, on the main branch, add a different line to the end of `README.md` without pulling the latest changes first.
- Attempt to push your local changes. Git should prevent it and suggest pulling the changes first.
- Pull the changes, and if a conflict arises, resolve it in VS Code. Keep both lines you and the remote version added.
- Once resolved, push the changes back to GitHub.

---
