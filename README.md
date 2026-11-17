# Future Justice System website

Node.js (Astro) website for **futurejusticesystem.com**. Mobile responsive, auto-deploys to GitHub Pages.

---

## 1. One-time setup on your computer

1. Install **Node.js 22** (LTS) from https://nodejs.org
2. Install **Git** from https://git-scm.com
3. Open a terminal in this folder and run:

```bash
npm install
npm run dev
```

4. Open http://localhost:4321 to see the site. It reloads automatically while you edit.

---

## 2. Put it on GitHub

1. On GitHub create a new **public** repository, e.g. `futurejusticesystem` (leave it empty, no README).
2. In this folder run (replace `YOUR-USERNAME`):

```bash
git init
git add .
git commit -m "Future Justice System website"
git branch -M main
git remote add origin https://github.com/YOUR-USERNAME/futurejusticesystem.git
git push -u origin main
```

3. On GitHub open the repo: **Settings › Pages › Build and deployment › Source** and choose **GitHub Actions**.
4. Open the **Actions** tab. The "Deploy to GitHub Pages" job runs. When it shows a green tick, the site is live at `https://YOUR-USERNAME.github.io/futurejusticesystem/` temporarily.

---

## 3. Connect futurejusticesystem.com

1. GitHub repo: **Settings › Pages › Custom domain** and enter `futurejusticesystem.com`, then Save. (The `public/CNAME` file already contains the domain.)
2. In **Hostinger hPanel › Domains › futurejusticesystem.com › DNS / Nameservers**:
   - Delete the existing **A** records for `@`.
   - Add 4 **A** records, name `@`:
     - `185.199.108.153`
     - `185.199.109.153`
     - `185.199.110.153`
     - `185.199.111.153`
   - Add (or edit) a **CNAME** record: name `www` → `YOUR-USERNAME.github.io`
3. Wait for DNS (usually minutes, up to a few hours). When GitHub shows the domain check as green, tick **Enforce HTTPS**.

Done: https://futurejusticesystem.com is live.

---

## 4. Make changes

### Everyday edits (no design code needed)

| What to change | File |
|---|---|
| Headline, mission, vision, founder message, contact info, next session date | `src/data/site.json` |
| Panels, topics, panelists | `src/data/panels.json` |
| Team members and photos | `src/data/team.json` + `public/images/team/` |
| Gallery photos | `src/data/gallery.json` + `public/images/gallery/` |
| Colours, spacing, fonts | `src/styles/global.css` |

Then publish:

```bash
git add .
git commit -m "Update team"
git push
```

GitHub rebuilds and the live site updates in about 1 minute.

### Change things by giving commands (Claude Code)

1. Install: `npm install -g @anthropic-ai/claude-code`
2. In this folder run: `claude`
3. Type what you want in plain words, for example:
   - `Add a new team member: Ali Raza, Media Director, photo is ali.jpg`
   - `Change the email to info@futurejusticesystem.com`
   - `Add a Panel 4 called "AI in Courts" with these panelists: ...`
   - `Make the hero headline bigger on mobile`
   - `Add a News page in the same style`
4. Claude Code edits the files, runs the build, and can commit and push for you. `CLAUDE.md` in this folder tells it the brand rules.

---

## 5. Contact form (one-time)

1. Sign up free at https://formspree.io and create a form with the email that should receive messages.
2. Copy the form ID (the part after `/f/`, e.g. `xyzabcd`).
3. Paste it into `src/data/site.json` → `"formspreeId": "xyzabcd"`, then push.

## 6. Teaser video on the Gallery page (optional)

Upload the teaser to YouTube, then put the embed link in `src/data/site.json`:
`"teaserVideo": "https://www.youtube.com/embed/VIDEO_ID"`

---

## Commands

| Command | What it does |
|---|---|
| `npm run dev` | Local preview at http://localhost:4321 |
| `npm run build` | Builds the final site into `dist/` |
| `npm run preview` | Preview the built site |
