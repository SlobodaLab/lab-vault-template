# Detailed Setup Guide

Step-by-step instructions for getting this vault running on your machine.

## 1. Download and Install Obsidian

1. Go to [obsidian.md/download](https://obsidian.md/download)
2. Download for your operating system (Windows, Mac, or Linux)
3. Install and open Obsidian

Obsidian is free for personal use.

## 2. Get This Vault

**Option A — Download from GitHub (no GitHub account needed):**
1. On the GitHub page, click the green **Code** button
2. Click **Download ZIP**
3. Extract the ZIP to a location on your computer (e.g., `Documents/MyVault`)

**Option B — Use as a template (GitHub account required):**
1. Click **Use this template** → **Create a new repository**
2. Name your repo and set it to Private
3. Clone it to your computer: `git clone https://github.com/YOUR-USERNAME/YOUR-REPO.git`

**Option C — Fork it (GitHub account required):**
1. Click **Fork** on the GitHub page
2. Clone your fork to your computer

## 3. Open as a Vault

1. In Obsidian, click **Open folder as vault**
2. Navigate to the folder you downloaded/cloned
3. Select it and click Open
4. Obsidian will ask about trusting this vault — click **Trust author and enable plugins**

## 4. Install Community Plugins

Obsidian needs a few community plugins for the templates and queries to work.

1. Go to **Settings** (gear icon, bottom-left) → **Community plugins**
2. Click **Turn on community plugins** if prompted
3. Click **Browse** and install each of the following:

### Required Plugins

| Plugin | What it does | Why you need it |
|--------|-------------|----------------|
| **Templater** | Powerful template engine | Powers all the templates (daily notes, projects, etc.) |
| **Dataview** | Database-like queries | Drives the automatic task lists, paper lists, and project rollups |
| **TaskNotes** | Task management as files | Individual tasks as markdown files with a board view |
| **Journals** | Periodic notes (daily/weekly/monthly) | Auto-creates daily notes on vault open |

### Recommended Plugins

| Plugin | What it does |
|--------|-------------|
| **Homepage** | Opens a specific note when you open the vault (set to `VAULT-INDEX.md`) |
| **Tag Wrangler** | Rename, merge, and manage tags in bulk |
| **Minimal Theme** + **Minimal Theme Settings** | Clean, customizable theme |

4. After installing, **enable** each plugin (toggle it on in the Community plugins list)

## 5. Configure Plugins

### Templater
- Settings → Templater → **Template folder location**: `__templates`
- Enable **Trigger Templater on new file creation**

### Journals (Daily Notes)
- Settings → Journals → Configure your daily note:
  - **Date format**: `YYYY-MM-DD`
  - **New file location**: `01-Daily Notes`
  - **Template**: `__templates/Daily Note template`
- Set up weekly notes similarly:
  - **Date format**: `gggg-[W]ww`
  - **New file location**: `01-Daily Notes/01-Weekly Notes`
  - **Template**: `__templates/Weekly Note template`

### Homepage (if installed)
- Settings → Homepage → **Homepage file**: `VAULT-INDEX`

## 6. Create Your First Project

1. Create a new folder in `02-Projects/` with your project name
2. Inside it, create a note and apply the **Project template**
3. Create a `STATUS.md` and apply the **STATUS template**
4. Add the project to `VAULT-INDEX.md`

## 7. Optional: Claude Code Integration

If you want to use Claude Code with this vault, see `claude-integration/README.md` for setup instructions.

## 8. Optional: Time Tracking

If you want passive time tracking, see `04-Methods/Vault workflows/Time tracking (optional).md` for how to set up ActivityWatch.

---

## Syncing Across Devices

If you want the vault on multiple devices:

- **Obsidian Sync** (paid, built-in, end-to-end encrypted) — the simplest option
- **iCloud / OneDrive / Google Drive** — works but can cause sync conflicts with Obsidian's config files
- **Git** — works well for text, but requires comfort with git

Choose one method. Don't mix them.
