# Academic website

Built on the **Kelly** template (BootstrapMade), rebuilt around five pages:
`Home · Publications · Teaching · CV · Contact`.

Plain HTML and CSS — no build step, no Ruby, no Node. Edit a file, push, done.

---

## Files

```
index.html          Home — position, interests, skills strip, experience, links
publications.html   Publications / Working Papers / Work in Progress
teaching.html       Courses, each title linking to its materials
cv.html             Download button + inline PDF preview + short summary
contact.html        Email, department, address, map, profile links
assets/css/custom.css   ← ALL your colour and style changes go here
assets/css/main.css     ← template base; don't edit
assets/cv/cv.pdf        ← overwrite with your CV, keep the filename
assets/papers/          ← paper PDFs
assets/img/profile-img.jpg  ← replace with your photo
```

`custom.css` loads after `main.css`, so anything you set there wins. To change the
whole colour scheme, edit `--accent-color` at the top of `custom.css` — one line
retints the entire site.

---

## Before you publish — replace these

Search for each string across all files and replace it.

### 1. Identity (do this first — it appears everywhere)

| Find | Replace with |
|---|---|
| `Mahla [Last Name]` | your full name (27 places) |
| `mahla.lastname@atu.ac.ir` | your real academic email (14 places) |

### 2. Profile links

| Find | Where to get it |
|---|---|
| `YOUR_SCHOLAR_ID` | the `user=` value in your Google Scholar URL |
| `0000-0000-0000-0000` | your ORCID iD |
| `YOUR-PROFILE` | your ResearchGate profile slug |
| `YOUR_USERNAME` | your GitHub / LinkedIn username |

If you don't have one of these yet, delete that whole `<li>` from the
`academic-links` list rather than leaving a dead link. ORCID is free and takes two
minutes — worth registering before you apply anywhere.

### 3. Home page (`index.html`)

- `[Supervisor Name]` and `https://example.com/supervisor`
- `[one line: what the project is about]`
- `[project topic]`, `[Second project or research group]`, `[Institution]`
- `[year]` — the intake you're applying for
- The three research interests: **rewrite these in your own words.** They are the
  most-read three lines on the site. Be specific — "forecasting inflation under
  structural breaks" tells a reader far more than "time series".
- The toolkit strip: delete anything you can't defend in an interview.

### 4. Publications (`publications.html`)

Entries follow the standard economics format:

```
Title                                    ← links to the PDF
with Coauthor A and Coauthor B
Journal Name, 2026, 41(2): 215–240.
Pdf | Journal | Data & R Code | Abstract
```

Delete the groups you don't need. **An honest short list beats a padded one** — if
you have no publications yet, keep only *Work in Progress*, or remove the page from
the navbar until you do. Reviewers notice padding.

To remove a page from the navbar, delete its `<li>` from the `<nav>` block in all
five files.

### 5. Teaching (`teaching.html`)

The three courses and their links are already in. Still to fill: `[Institution]`
and `[Term, Year]` on each.

Note the three URLs currently point at `gsme.sharif.edu` — check each one opens the
material you intend before publishing.

### 6. CV (`cv.html`)

Overwrite `assets/cv/cv.pdf` with your own, **keeping the filename**. The download
button and preview then keep working with no HTML edit. Update `[Month Year]` in two
places. Re-export it every time your CV changes — a stale CV is worse than none.

### 7. Photo

Replace `assets/img/profile-img.jpg`. A square headshot around 600×600 works best.

---

## Publishing to GitHub Pages

1. Create a **public** repo named exactly `yourusername.github.io`.
2. From this folder:

```bash
git init
git add .
git commit -m "Initial site"
git branch -M main
git remote add origin https://github.com/yourusername/yourusername.github.io.git
git push -u origin main
```

3. Repo **Settings → Pages → Source: Deploy from a branch → main / (root)**.
4. Live at `https://yourusername.github.io` in a minute or two.

To update anything afterwards:

```bash
git add .
git commit -m "Update CV"
git push
```

`.nojekyll` is included so GitHub serves the files as-is.

---

## Notes

- The contact form was **removed on purpose**. It needed PHP, and GitHub Pages
  serves static files only — the form would have silently discarded every message.
  A `mailto:` link is honest and actually works.
- Unused template pages (portfolio, services, resume) and their libraries were
  deleted. The site is ~1 MB instead of ~10 MB.
- The BootstrapMade credit in the footer is required by the template licence.
- Checked: valid HTML, all links resolve, responsive to mobile, keyboard focus
  visible, reduced-motion respected.
