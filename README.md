# How I Got Here — Technical.ly Career Explorer

Search Technical.ly career profiles by location, experience and profession. This is the source of the private prototype, packaged for a standalone GitHub repository. The initial collection contains 24 stories researched on October 23, 2026.

## Files

- `index.html`: page structure
- `styles.css`: responsive layout and branding
- `app.js`: search, filters, sorting, classification notes and browser-local editing
- `articles.json`: the curated story collection
- `.nojekyll`: tells GitHub Pages to serve these static files directly

There is no installation or build step. No API keys or external JavaScript dependencies are needed. All four application files are identical to the prototype source commit `3936f5c017357336c3b9aa9f75b406e0c7546d67`. Platform hosting configuration, Git history, credentials and viewer email addresses are excluded.

## Put the code on GitHub

1. Create a repository. Choose **Private** if you want to keep the code restricted while the team reviews it.
2. Extract this ZIP and open the `how-i-got-here` folder.
3. Upload the **contents** of that folder to the repository root using **Add file → Upload files**, then commit. `index.html` should be at the root, rather than inside another folder. Alternatively, use GitHub Desktop to add and push the folder as a repository.
4. Invite your colleagues through the repository's access settings if you want them to review the source.

Uploading code does not publish a website or change the existing prototype.

## Run locally

From this folder, with Python 3 installed:

```bash
python -m http.server 8000
```

Open http://localhost:8000 in your browser. Some systems use `python3` instead of `python`. Use a local server: double-clicking `index.html` may block the JSON fetch. The VS Code Live Server extension is another option.

## Optional: host on GitHub Pages

Publishing is optional. The current prototype's email allowlist is provided by its hosting platform; it is **not** part of this code. Standard GitHub Pages publishing does not preserve those restrictions. A private repository alone does not make a Pages website private. If you need restricted visitors, keep the current private prototype or have your web team provide authenticated hosting.

When you are ready for a public website and your GitHub plan supports Pages for the repository:

1. Open the repository's **Settings → Pages**.
2. Under **Build and deployment**, choose **Deploy from a branch**.
3. Select the `main` branch and **/(root)**, then **Save**.
4. GitHub will display the published URL when deployment completes. Follow that returned URL rather than guessing it.

If the browser upload interface omits `.nojekyll`, add an empty file named `.nojekyll` at the root. No custom Actions workflow is required.

GitHub's current documentation: https://docs.github.com/en/pages/getting-started-with-github-pages/configuring-a-publishing-source-for-your-github-pages-site

## Update stories

Edit `articles.json` and commit the change. If Pages is configured to publish from that branch, GitHub republishes the site after the commit. This package does not automatically import new Technical.ly stories.

**Manage index** edits are stored only in the editing browser. They do not commit to GitHub or update anyone else's collection. To publish those edits:

1. Export JSON using Manage index.
2. Review the exported data and replace the repository's `articles.json` with it.
3. Commit the updated file.
4. Browsers with an older local edited copy may need **Manage index → Restore starting collection** to load the newly published dataset. Export any local edits first. “Starting collection” means the data currently shipped in `articles.json`.

Each record has a unique string `id`, `name`, descriptive `title`, original Technical.ly `url`, publication `date` (YYYY-MM-DD), `summary`, `regions`, `experience`, `professions`, `series`, `seriesEvidence`, `classificationNote`, `needsReview` boolean and `checked` date. Use supported label values from `app.js`. Empty classification arrays are allowed when evidence is insufficient. Keep `series` equal to `How I Got Here`, and include evidence of membership in the series.

## Editorial limits

This is a curated starting collection, not the complete archive. Some source pages returned access errors. No North Dakota story has been verified for this collection; a zero count does not establish that the full series contains none.

Display titles are condensed descriptions. Summaries are written for this index; the original articles remain linked on Technical.ly. No WordPress posts or tags were changed.

Experience and profession labels are editorial browsing aids, not necessarily formal job titles. They reflect the story's publication context. Founder can overlap with Senior. Some profession labels include a previous career, and location can reflect the article's market or a documented professional connection. Read each story's classification note. Amber markers flag suggested labels or incomplete review.

## Validation

Original prototype checks covered combined filters, Pennsylvania search, North Dakota empty results, classification notes, browser-local saving and persistence, chronological sorting, and desktop layout. Responsive CSS is included; physical mobile-device testing has not been performed.

## Rights

No open-source license has been selected for this export. Have the Technical.ly team choose an appropriate license before offering reuse rights. Article content, branding and any third-party rights remain with their respective owners.
