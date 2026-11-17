# Exactly

A design challenge generator. Press **Deal** and three card decks shuffle, deal and flip to give you a random **category**, **brand name** and **colour palette**. Then design that brand using only those five colours.

> *Design a funeral home brand called "Tuesday", using only colours from an airport carpet.*

There's no build step: it's one HTML page, a folder of fonts and Google Fonts for the logo.

## Files

| File | What it is |
| --- | --- |
| `index.html` | The whole website |
| `fonts/` | Urbane Rounded font files (Light, Medium, DemiBold, Bold) |
| `CHANGELOG.md` | Version history: changes and bug fixes |
| `README.md` | This file |
| `.nojekyll` | Tells GitHub Pages to serve the files as they are |

## Font licence: check before publishing

Urbane Rounded is a commercial font by Rian Hughes / Device Fonts ("All rights reserved"). Putting it on a public website usually needs a **webfont licence**, which is separate from a desktop licence. Make sure yours covers web use before the site goes public. If it doesn't, delete the `fonts` folder: the site still works and falls back to Trebuchet MS / Verdana.

## Put it on GitHub Pages (no coding needed)

1. **Open your repository** (for example `github.com/aismbx/exactly`), or create one: click **+** (top right), then **New repository**, name it `exactly`, set it to **Public**, and click **Create repository**.
2. **Upload the files.** Click **Add file**, then **Upload files**. Drag in `index.html`, `README.md`, `CHANGELOG.md` and the whole **`fonts` folder**, then click **Commit changes**.
   - Upload the `fonts` folder itself, not just the files inside it, so they end up at `fonts/urbane-rounded-500.woff2` and so on. Otherwise the font won't load.
   - Already uploaded the old version? Upload the new `index.html` over it. GitHub replaces files with the same name.
   - `.nojekyll` is a hidden file, so your computer may not show it. The site works without it. To add it anyway: click **Add file**, then **Create new file**, name it `.nojekyll`, leave it empty, and commit.
3. **Turn on Pages** (skip if it's already on). Go to **Settings**, then **Pages**. Under **Build and deployment**, choose **Deploy from a branch**, with branch **main** and folder **/ (root)**, then click **Save**.
4. **Wait a minute or two.** Your site is at `https://aismbx.github.io/exactly/`, or whatever name you gave the repository.

### Using the command line instead

```bash
cd exactly
git init
git add .
git commit -m "Exactly v2.0.0"
git branch -M main
git remote add origin https://github.com/aismbx/exactly.git
git push -u origin main
```

If the repository already has the old version, skip `git init` and `git remote add`. Just run `git add .`, `git commit` and `git push`.

## Updating the site

1. Edit `index.html`. The lists are near the top of the `<script>` section: `CATEGORIES`, `BRANDS` and `PALETTES`.
2. Add an entry to `CHANGELOG.md` with the new version number.
3. Upload the changed files again (or `git commit` and `git push`). GitHub Pages updates within a minute or two.

### Adding a palette

Each palette is a name, a one-line description and exactly 5 hex colours:

```js
{n:"Burnt Toast", d:"Toast left in one cycle too long.", c:["#2B1A10","#6B3E1F","#C8873E","#F2D6A2","#FFF7E6"]},
```

## Licence

The code has no licence yet. Add one if you want others to reuse it: [choosealicense.com](https://choosealicense.com) explains the options, and MIT is a common pick. This doesn't cover the Urbane Rounded font, which has its own licence (see above).
