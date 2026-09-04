# Strome van Lewe · Church Studies

Bible resources for Strome van Lewe Gemeente, Boshof. Static HTML — no build step, no framework, no dependencies. Every page is a single file you can open and edit.

Live: **[stromevanlewe.netlify.app](https://stromevanlewe.netlify.app)** · mirror: [stromevanlewe.github.io/church-studies](https://stromevanlewe.github.io/church-studies/)

---

## Structure

```
index.html                      Landing page (logo embedded, no external assets)
assets/
  hero.jpg                      Linocut tree of life — the landing page artwork
  logo.png                      Church logo, transparent (not used by the pages)
bibleplans/3-month-plan/
  index.html                    90-day reading plan, 1 Sep – 30 Nov 2026
studies/offence/
  index.html                    "Om Aanstoot te Neem" — 8-session study
_redirects                      Netlify routing
netlify.toml.txt                ⚠ see Deployment notes
```

**Folder names are lower case and must stay that way.** See Deployment notes.

---

## The offence study

Eight sessions on offence, bilingual (Afrikaans / English), built for members to work through alone during the week and then discuss together in the Community Group.

| | Session | Key verse |
|---|---|---|
| **What it is** | 1. Die strik / The trap | Luke 17:1 |
| | 2. Die wortel / The root | Hebrews 12:15 |
| **The gospel** | 3. Die aanstoot van die Kruis / The offence of the Cross | 1 Corinthians 1:23 |
| | 4. Aanstoot teenoor Jesus self / Offence at Jesus Himself | Matthew 11:6 |
| **His example** | 5. Seer sonder aanstoot / Hurt without offence | 1 Peter 2:23 |
| **What to do** | 6. Gaan na jou broer / Go to your brother | Matthew 18:15 |
| | 7. Vergewe soos jy vergewe is / Forgive as you were forgiven | Colossians 3:13 |
| | 8. Leef vry / Living free | Psalm 119:165 |

Each session has: key verse in five translations · plain-language summary · teaching · a story · extra verses with paraphrases · one practical step · personal questions · separate group questions · a prayer.

Plus a standing self-check panel ("Sit my voet in die strik?" / "Is my foot in the trap?") reachable from every session, and collapsible leader notes at the foot of the page.

**Navigation:** sessions are `#s1` … `#s8` in the URL. *(These replaced the old `#week-1` … `#week-6` anchors — old links land on session 1.)*

**Language:** the page opens in Afrikaans. Add `?lang=en` for a direct English link, e.g. `/studies/offence/?lang=en#s3`.

---

## Editing the content

All eight sessions live in one readable `DATA` object near the top of `studies/offence/index.html`, before the rendering code. Change the text there and save — nothing to rebuild.

Scripture references written in the body text are **linked automatically**. If the verse is explained elsewhere in the study, the link jumps to that session; otherwise it opens bible.com in whichever translation the reader has selected. You don't have to write the links.

### Bible translation IDs (YouVersion)

| Abbrev | Translation | ID |
|---|---|---|
| AFR83 | Afrikaans 1983 | **6** |
| AFR53 | Afrikaans 1933/1953 | **5** |
| NLV | Nuwe Lewende Vertaling | **117** |
| ESV | English Standard Version | 59 |
| NIV | New International Version | 111 |

⚠ Earlier versions of this site used ID **2** for AFR83. That is wrong — **ID 2 is ABA (Bybel vir almal)**, a simplified paraphrase. All AFR83 links were pointing at the wrong Bible.

All eight key verses were verified word for word against each translation before publishing.

---

## Deployment notes

**Case sensitivity.** Netlify resolves paths case-insensitively; **GitHub Pages does not.** A link to `BiblePlans/` will work on Netlify and 404 on GitHub Pages, where the folder is `bibleplans/`. Keep every folder and file name lower case, and always test on the GitHub Pages URL before trusting a link.

**Relative links only.** No path starts with `/`. GitHub Pages serves this repo from the `/church-studies/` subdirectory, so an absolute path leaves the site. `./bibleplans/…` and `../../` work on both hosts.

**`netlify.toml.txt` is ignored by Netlify.** The file must be named `netlify.toml` exactly. Whatever it configures has never been applied. Rename it or delete it.

**`DEPLOY_x5f_GUIDE.md`** has an escaped underscore in its name; it was probably meant to be `DEPLOY_GUIDE.md`.

**If Netlify stops updating:** check Site configuration → Build & deploy — that it is connected to this repo, that the branch is `main`, and that auto publish is on.

---

## Scripture copyright

Quotations are used with acknowledgement:

- **AFR83** © 1983 Bybelgenootskap van Suid-Afrika
- **AFR53** © 1933, 1953 Bybelgenootskap van Suid-Afrika
- **NLV** © 2006 Christelike Uitgewersmaatskappy
- **ESV** © 2001 Crossway
- **NIV** © 1973, 1978, 1984, 2011 Biblica, Inc.

Key verses are quoted in full; extra verses are given as paraphrases with a link to the text.

---

## Still to come

- Leader's guide — extra explanation per session and possible answers to both sets of questions
- Further sections on the landing page: Boodskappe · Vir die huis · Hulpbronne vir leiers
