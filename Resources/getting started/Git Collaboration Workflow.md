## Overview

This note covers the day-to-day GitHub workflow for collaborating on Unity and Obsidian projects. For initial setup, see [[Setting up GitHub]].

The same workflow applies to both repositories: Unity and Obsidian.

---

## The basic loop

1. **Pull**: fetch any changes others have pushed before you start
2. **Work**: make your changes in Unity or Obsidian
3. **Save**: save the file/scene in Unity; Obsidian auto-saves
4. **Commit**: label what you changed
5. **Push**: upload your changes to GitHub

---

## Step by step

### 1: Pull before you start

Open GitHub Desktop, select the relevant repository, and click **Fetch origin**, then **Pull origin** if there are new changes. Always do this before opening Unity or editing notes.

### 2: Make your changes

Work as normal in Unity or Obsidian.

### 3: Commit your changes

1. Open GitHub Desktop: you'll see all modified files listed
2. Write a short commit message describing what you changed (e.g. *Add player movement script* or *Update session notes*)
3. Click **Commit to main** (or your branch name)

### 4: Push your changes

Click **Push origin**. This uploads your committed changes to GitHub so others can see and pull them.

---

## Using branches (recommended for Unity features)

Branches let you work on a feature or fix in isolation without touching the main project until it's ready.

### Create a branch

1. In GitHub Desktop, go to **Branch → New Branch**
2. Name it something descriptive (e.g. `player-combat`, `ui-redesign`)
3. Click **Create Branch**

Work and commit as normal; changes stay on your branch.

### Publish the branch

Click **Publish branch** in GitHub Desktop to upload it to GitHub.

### Merge via pull request

When your work is ready to go into main:

1. Go to the repository on [github.com](https://github.com)
2. Click the **Pull requests** tab → **New pull request**
3. Set the right side to your branch, left side to `main`
4. Review the changes, then click **Create pull request**
5. Add a comment if needed, then submit
6. Either collaborator can click **Merge pull request → Confirm merge**
7. Delete the branch if it's no longer needed

### Owner pulls the merged changes

After a merge, the owner needs to sync locally:

1. Open GitHub Desktop
2. Click **Fetch origin** → **Pull origin**
3. Reopen the Unity project if needed to see the changes

---

## Adding a new collaborator

1. Go to the repository on GitHub → **Settings → Collaborators → Add people**
2. Enter their GitHub username or email
3. They accept the invitation via email
4. They clone the repository in GitHub Desktop (**File → Clone repository**)
5. They open the project from disk in Unity Hub (**Open → Add project from disk**)

---

## Quick reference

| Action | GitHub Desktop |
|---|---|
| Get latest changes | Fetch origin → Pull origin |
| Save your work to GitHub | Commit → Push origin |
| Start isolated work | Branch → New branch → Publish |
| Bring work into main | Pull request → Merge |

---

## Notes

- **Always pull before you start.** The most common source of problems is pushing without pulling first.
- **Unity gitignore:** The `.gitignore` file must be inside the Unity project folder (not just the repo root) to work correctly. Drag it in if it ends up in the wrong place. On Mac, use **Cmd+Shift+.** to show hidden files.
- **Same Unity version:** All collaborators should use the same Unity version to avoid compatibility issues.
