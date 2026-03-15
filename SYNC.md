# Keeping Cursor + Claude Code in Sync

This repo is the **single source of truth**. Both Cursor and Claude Code should work from the same clone and sync via **Git + GitHub**.

---

## Option A: One folder, two editors (recommended)

Use **one local clone** and open it in whichever tool you’re using.

1. **Clone once** (already done in this workspace):
   ```bash
   git clone https://github.com/vlad0326-png/nouri.git
   cd nouri
   ```

2. **In Cursor:** Open the folder that contains this repo  
   - e.g. `.../nouri/repo` or wherever you keep the clone.

3. **In Claude Code:** Open the **same folder** (same path on your machine).

4. **Sync workflow:**
   - Before starting work in either tool: `git pull`
   - After making changes: `git add .` → `git commit -m "message"` → `git push`
   - Then pull in the other tool before making more changes.

---

## Option B: Two clones, sync via GitHub

If you use one folder in Cursor and a different one in Claude Code (e.g. different projects):

1. **Cursor:** Work in clone A (e.g. this workspace).
2. **Claude Code:** Work in clone B (e.g. `~/Projects/nouri`).
3. **Sync:**
   - When switching to Cursor: in clone A run `git pull`.
   - When switching to Claude Code: in clone B run `git pull`.
   - After changes in either: commit and `git push`, then `git pull` in the other clone before editing.

---

## Quick checklist

- [ ] **Before editing:** `git pull` (get latest from GitHub).
- [ ] **After editing:** `git add .` → `git commit -m "what you did"` → `git push`.
- [ ] **Tell the AI** which tool you’re in: “I’m in Cursor” or “I’m in Claude Code” so it can remind you to pull/push if needed.

---

## Remote

- **GitHub:** https://github.com/vlad0326-png/nouri  
- **Branch:** `main`
