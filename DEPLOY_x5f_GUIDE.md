# Deploy Guide — GitHub + Netlify (English & Afrikaans)

## What you have in this folder
- index.html = main library page
- studies/offence/index.html = the 6-week study (final bilingual Grade 10 version)
- _redirects + netlify.toml = makes Netlify work perfectly
- This folder is ready to drag-and-drop.

---

## OPTION A — EASIEST: Netlify Drop (no GitHub needed) — 60 seconds
1. Go to https://app.netlify.com/drop
2. Drag THIS ENTIRE FOLDER (church-final-bilingual-bundle) onto the page
3. Netlify gives you a link like https://amazing-fox-123.netlify.app
4. Share that link on WhatsApp: add #week-1 at end for direct Week 1: .../studies/offence/#week-1
5. To update later, drag the folder again to same site (or use Netlify Deploys tab → Drag & drop)

**Custom domain (optional):** Netlify → Domain settings → Add custom domain → e.g. studies.yourchurch.org.za → follow DNS instructions.

## OPTION B — BEST LONG TERM: GitHub + Netlify connected (recommended)

### Step 1: Create GitHub repo
1. Go to github.com → New repository → Name: church-studies → Public → Create
2. Click "uploading an existing file" → drag ALL files from this bundle into GitHub → Commit

### Step 2: Enable GitHub Pages (optional backup)
- GitHub repo → Settings → Pages → Source: Deploy from a branch → Branch: main / root → Save
- You will get https://yourusername.github.io/church-studies/ as backup link

### Step 3: Connect to Netlify (auto-deploy)
1. Go to app.netlify.com → Add new site → Import an existing project → GitHub → Authorize → Choose church-studies repo
2. Build settings: leave empty (this is static). Publish directory: . (dot)
3. Deploy site → You get netlify.app link
4. From now on: every time you push a new study to GitHub, Netlify auto-updates.

### How to add your next study
1. Duplicate studies/offence/ → studies/forgiveness/ (or studies/vergiffenis/)
2. Replace the index.html inside with your new study (keep same structure)
3. Edit the main index.html landing page — copy the card and link to studies/forgiveness/
4. Push to GitHub (or drag to Netlify Drop again)

---

## AFRIKAANS — Vinnige Gids

### Opsie A — Maklikste: Netlify Drop
1. Gaan na https://app.netlify.com/drop
2. Sleep hierdie HELE VOUER daarop
3. Jy kry dadelik 'n skakel soos https://...netlify.app — deel op WhatsApp

### Opsie B — Beste langtermyn: GitHub + Netlify gekoppel
1. Skep GitHub repo: church-studies → laai alle lêers op
2. Gaan na app.netlify.com → Import from GitHub → kies jou repo → Deploy
3. Elke keer as jy nuwe studie na GitHub laai, publiseer Netlify outomaties

**Volgende studie byvoeg:** Dupliseer studies/offence/ → studies/nuwe-studie/ → vervang index.html → verander hoof index.html om nuwe kaart by te voeg.

---

## Scripture links explained
We use bible.com search which never breaks:
- ESV: https://www.bible.com/search/bible?query=Romans%2014:13&version=59
- NIV: https://www.bible.com/search/bible?query=Romans%2014:13&version=111 → also works as https://www.bible.com/bible/111/ROM.14.13 (your example format)
- AFR83: version=5
- AFR53: version=2

On bible.com, user can switch translation at top.

## Troubleshooting
- Page shows Week 5 not Week 1? Hard refresh (Ctrl+F5) — new version forces #week-1 if no hash.
- Back button goes to Week 1? Fixed — we now store #week-1...#week-6 in URL via pushState + hashchange listener.
- Low data? The study is <500KB, works offline after first load. bible.com links need data.

Blessings on the small groups!
