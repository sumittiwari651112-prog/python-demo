 # Git Push — Class Notes

**Goal:** Save a small project with Git and upload it to GitHub.

**Git** keeps a history of changes on your computer. **GitHub** hosts a copy online. A **repository**, or **repo**, is a project with its Git history.

## Before the demo

- Install Git and sign in to your GitHub account.
- On GitHub, create an empty repository called `git-demo`. Do not add a README, license, or `.gitignore` there for this demo.
- On your computer, create a folder called `git-demo`. Inside it, create `hello.txt` containing `Hello students!`.
- Open a terminal inside that folder. Run the commands below one at a time.

If this is your first time making a Git commit, set your author details once:

```bash
git config --global user.name "Your Name"
git config --global user.email "YOUR_EMAIL"
```

### Why do we set a name and email?

Git records an author name and email with every commit so the project history shows **who made each saved change**.

- `user.name` sets the author name shown on your commits. Use your name; it does not have to be your GitHub username.
- `user.email` sets the author email recorded in your commits.
- `--global` makes these the default details for all Git repositories used by your user account on this computer. A repository can override them with its own settings.

Replace `"Your Name"` and `"YOUR_EMAIL"` with your details. You normally set them once on each computer. If no author identity is available, Git may refuse to create a commit and ask you to configure it.

These commands label your commits. They do not log you in to GitHub or give you permission to push.

## 1. `git init` — Start Git in this folder

```bash
git init
```

This turns your current folder into a Git repository. Git creates a hidden `.git` folder to store its history and settings.

Run this once when starting a new local repository. It does not create a repository on GitHub.

## 2. `git add` — Choose changes to save

```bash
git add hello.txt
```

This puts the current changes in `hello.txt` into the **staging area**. The staging area is the collection of changes selected for your next commit.

To stage all changes under the current folder, you can use:

```bash
git add .
```

For this demo, adding just `hello.txt` is enough. If you edit a file again after adding it, run `git add` again to include the latest edits. Never stage passwords or access tokens.

## 3. `git commit` — Save a version locally

```bash
git commit -m "Add greeting file"
```

This records the staged changes as a **commit**: a saved point in the project's history.

- `-m` lets you provide a message.
- `"Add greeting file"` describes what changed.

The commit is on your computer. It has not been uploaded to GitHub yet.

## 4. `git branch -M main` — Name this branch `main`

```bash
git branch -M main
```

A **branch** is a named line of development in the project's history. This command renames the current branch to `main`.

- `branch` works with branches.
- `-M` means force-rename.
- `main` is the new name.

In this fresh demo repository, we use it to make the branch name predictable before pushing. In an existing project, `-M` can replace an existing branch name, so do not use it blindly.

### Why use the `main` branch?

`main` is a common name for a project's primary branch. It gives everyone a clear name to use for the central version of the project.

Git does not require this name. Older projects may use `master`, and teams can choose another name. The word `main` does not automatically make the code correct or ready for release.

We use `main` here so our branch name matches the name in `git push origin main`.

## 5. `git remote add origin` — Save the GitHub address

```bash
git remote add origin https://github.com/YOUR_USERNAME/git-demo.git
```

Replace `YOUR_USERNAME` with your GitHub username, or copy your repository's HTTPS URL from GitHub.

- **Remote:** An address for another copy of the repository.
- **`add`:** Save a new remote.
- **`origin`:** The nickname we give that address.
- **URL:** The address of your GitHub repository.

`origin` is a common nickname, not a special GitHub account or branch. This command saves the connection details; it does not upload files. Run it once for this repository.

## 6. `git push origin main` — Upload the saved commits

```bash
git push origin main
```

- `push`: Send local commits to the remote repository.
- `origin`: Use the GitHub address saved earlier.
- `main`: Push the local `main` branch to the remote `main` branch.

A push sends commits. Edits that you have not committed are not included.

After a successful push, refresh the repository page on GitHub. You should see `hello.txt` and the commit message.

## 7. Access tokens — Why choose a classic token?

A **personal access token (PAT)** is a secret used to authenticate to GitHub. For HTTPS Git authentication, use the token in the password field if prompted, not your GitHub account password. A credential manager may handle sign-in instead.

**You do not have to choose a classic token for this demo.** GitHub recommends fine-grained tokens whenever possible. They let you limit access to selected repositories and specific permissions.

Choose a classic token only when your required workflow is unsupported by fine-grained tokens and the repository's policies allow it. Some tutorials demonstrate classic tokens for compatibility; that does not make them the preferred choice for every project.

A token does not grant permissions your account lacks. Set an expiry, keep it private, and never paste it into code, a commit, or a screenshot.

## Complete command sequence

Run inside the local `git-demo` folder after creating `hello.txt` and the empty GitHub repository:

```bash
git init
git add hello.txt
git commit -m "Add greeting file"
git branch -M main
git remote add origin https://github.com/YOUR_USERNAME/git-demo.git
git push origin main
```

Replace `YOUR_USERNAME` before running the remote command.

For the next change, edit and save `hello.txt`, then run:

```bash
git add hello.txt
git commit -m "Update greeting"
git push origin main
```

`add` selects changes, `commit` saves them locally, and `push` uploads the commits.
