## Step 1 — Create a GitHub account

Go to [github.com](https://github.com) and create a free account. Send me your GitHub username so I can add you as a collaborator on both repositories. You'll get an email invite from GitHub — accept it before moving on.

---

## Step 2 — Install GitHub Desktop

Download and install **GitHub Desktop** from [desktop.github.com](https://desktop.github.com). Sign in with your GitHub account when prompted.

This is the app you'll use to sync files between your computer and GitHub — no terminal required.

---

## Step 3 — Set up the Obsidian vault (Northforge)

### 3a — Clone the vault

1. Open GitHub Desktop
2. Go to **File → Clone repository**
3. Click the **URL** tab and paste: `https://github.com/mstrand93/Northforge`
4. Choose where to save it on your computer, then click **Clone**

### 3b — Install Obsidian

Download Obsidian from [obsidian.md](https://obsidian.md) and install it.

### 3c — Open the vault

1. Open Obsidian
2. Click **Open folder as vault**
3. Select the `Northforge` folder you just cloned

### 3d — Install the Obsidian Git plugin

1. In Obsidian, go to **Settings → Community plugins**
2. Turn off Safe mode if prompted
3. Browse and search for **Obsidian Git**, install it, and enable it

This lets you pull and push note changes directly from within Obsidian, keeping our vault in sync.

---

## Step 4 — Set up the Unity project (EOG)

### 4a — Clone the Unity project

1. Open GitHub Desktop
2. Go to **File → Clone repository**
3. Click the **URL** tab and paste: `https://github.com/mstrand93/EOG`
4. Choose where to save it, then click **Clone**

### 4b — Install Unity Hub

Download Unity Hub from [unity.com/download](https://unity.com/download) and install it. Create a free Unity account if you don't have one.

### 4c — Install the correct Unity version

Open Unity Hub, go to **Installs**, and check with me which version to install before proceeding.

### 4d — Open the project

1. In Unity Hub, go to **Projects**
2. Click **Open → Add project from disk**
3. Select the `EOG` folder you cloned in step 4a

Unity will import the project on first open — this can take a few minutes.

---

## Staying in sync

**Always pull before you start working.** This fetches any changes the other person has made and prevents conflicts.

- **Obsidian vault:** Open GitHub Desktop, select the Northforge repository, and click **Pull origin**
- **Unity project:** Open GitHub Desktop, select the EOG repository, and click **Pull origin**

Do this every time before opening Obsidian or Unity for a work session.

### What if we edit the same note at the same time?

Git won't silently overwrite either version. The second person to push will be rejected and told to pull first. The conflicting note will then show both versions side by side like this:

```
<<<<<<< HEAD
Your version of the text
=======
Their version of the text
>>>>>>> origin/main
```

You manually pick the correct version, delete the marker lines, save, and push again. Since our notes are plain text, this is easy to read and fix — but the best way to avoid it is to not edit the same note at the same time, and to always pull first.

Let me know if you get stuck at any point.
