# Sync This Vault to Your iPhone (No PC Required)

Everything here uses only the **Obsidian** app and the **Obsidian Git** community plugin. No computer, no extra apps required.

---

## Step 1 — Create a GitHub Personal Access Token

You need a token so Obsidian Git can authenticate to GitHub on your phone.

1. Open Safari and go to **github.com → Settings → Developer settings → Personal access tokens → Fine-grained tokens**.
2. Tap **Generate new token**.
3. Fill in:
   - **Token name:** `obsidian-iphone` (or anything you like)
   - **Expiration:** 1 year (or No expiration)
   - **Repository access:** Select only repositories → pick **NoamVardi18/Obsidian**
4. Under **Permissions → Repository permissions**, set:
   - **Contents:** Read and write
   - Everything else: No access
5. Tap **Generate token** and **copy it immediately** — you won't see it again.
   - Paste it somewhere safe (Notes app) until you need it in Step 4.

---

## Step 2 — Install Obsidian and Create a New Vault

1. Download **Obsidian** from the App Store.
2. Open Obsidian → tap **Create new vault**.
   - Vault name: `Obsidian` (matches the repo name, helps avoid confusion)
   - Location: leave as default (on-device)
3. Tap **Create**.

---

## Step 3 — Install the Obsidian Git Plugin

1. Inside your new vault, tap the **three-dot menu (⋮)** → **Settings**.
2. Scroll to **Community plugins** → turn off **Restricted mode** → tap **Turn on community plugins**.
3. Tap **Browse** → search for **Obsidian Git** → install and enable it.
4. Close Settings.

---

## Step 4 — Clone the Vault from GitHub

1. Open the **Command Palette** (tap the magnifying glass or swipe down, then search for "command palette").
2. Run: **Obsidian Git: Clone an existing remote repository**.
3. Enter:
   - **URL:** `https://github.com/NoamVardi18/Obsidian.git`
   - **GitHub username:** `NoamVardi18`
   - **Password / token:** paste the token you copied in Step 1
4. When asked where to clone into, choose the **root** of your current vault (or accept the default).
5. Obsidian will restart and reload with all the vault files.

> If Obsidian asks whether to trust the repository, tap **Trust**.

---

## Step 5 — Enable Auto-Sync

1. Go to **Settings → Community plugins → Obsidian Git → Options (gear icon)**.
2. Turn on **Pull on startup** — this pulls the latest notes every time you open Obsidian.
3. Set **Auto commit-and-sync interval** to **5** (minutes) — edits are backed up to GitHub every 5 minutes automatically.
4. Optional: set **Commit message** to something like `vault backup {{date}}` so you can tell commits apart.
5. Close Settings.

---

## Everyday Use

- **Open Obsidian** → it pulls the latest notes automatically.
- **Write notes** → they're committed and pushed every 5 minutes without any extra steps.
- **Manual sync** → open Command Palette → run **Obsidian Git: Commit all changes** or **Obsidian Git: Push**.

---

## Resolving a Merge Conflict (Rare)

A conflict can happen if you edited the same note on two devices at the same time (e.g., from the GitHub web editor and your phone).

1. Open Command Palette → run **Obsidian Git: Pull**.
2. Obsidian Git will flag the conflicted file in a notice.
3. Open the conflicted file — it will contain standard Git conflict markers:
   ```
   <<<<<<< HEAD
   your phone's version
   =======
   the incoming version
   >>>>>>> origin/main
   ```
4. Edit the file manually: delete the markers and keep the content you want.
5. Open Command Palette → run **Obsidian Git: Commit all changes** → then **Push**.

---

## Optional Alternatives

- **Working Copy** — a full-featured Git client for iOS. Useful if you want to manage the repo outside Obsidian or resolve complex conflicts in a proper Git UI.
- **iSH** — a Linux shell emulator for iOS. Lets you run `git` commands directly if you're comfortable with the command line. Not needed for normal use.

Neither is required for this setup.
