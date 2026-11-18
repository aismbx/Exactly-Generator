# Exactly

A design challenge generator. Press **Deal** to get a random **category**, **brand name** and **colour palette**, then design that brand using only those five colours.

> *Design a yoga studio brand called "Dolly", using only colours from a ski jacket 1989.*

There's no build step: it's one HTML page. The only outside file is the Arimo font from Google Fonts, which is free and open-source.

## Files

| File | What it is |
| --- | --- |
| `index.html` | The whole website |
| `CHANGELOG.md` | Version history: changes and bug fixes |
| `README.md` | This file |
| `.nojekyll` | Tells GitHub Pages to serve the files as they are |

## Put it on GitHub Pages (no coding needed)

1. **Open your repository** (for example `github.com/aismbx/exactly`), or create one: click **+** (top right), then **New repository**, name it `exactly`, set it to **Public**, and click **Create repository**.
2. **Upload the files.** Click **Add file**, then **Upload files**. Drag in `index.html`, `README.md` and `CHANGELOG.md`, then click **Commit changes**. GitHub replaces any older files with the same names.
   - `.nojekyll` is a hidden file, so your computer may not show it. The site works without it. To add it anyway: click **Add file**, then **Create new file**, name it `.nojekyll`, leave it empty, and commit.
3. **Turn on Pages** (skip if it's already on). Go to **Settings**, then **Pages**. Under **Build and deployment**, choose **Deploy from a branch**, with branch **main** and folder **/ (root)**, then click **Save**.
4. **Wait a minute or two.** Your site is at `https://aismbx.github.io/exactly/`, or whatever name you gave the repository.

### Upgrading from version 2 (the pink design)

Version 3 no longer uses the `fonts` folder. If you uploaded it before, it does no harm, but you can delete it. Open each font file on GitHub, click the **⋯** menu, then **Delete file**, and commit. The folder disappears when it's empty.

### Using the command line instead

```bash
cd exactly
git init
git add .
git commit -m "Exactly v3.0.0"
git branch -M main
git remote add origin https://github.com/aismbx/exactly.git
git push -u origin main
```

If the repository already has an older version, skip `git init` and `git remote add`. Run `git rm -r fonts` to remove the old fonts, then `git add .`, `git commit` and `git push`.

## Updating the site

1. Edit `index.html`. The lists are near the top of the `<script>` section: `CATEGORIES`, `BRANDS` and `PALETTES`.
2. Add an entry to `CHANGELOG.md` with the new version number.
3. Upload the changed files again (or `git commit` and `git push`). GitHub Pages updates within a minute or two.

### Adding a palette

Each palette is a name, a one-line description and exactly 5 hex colours:

```js
{n:"Burnt Toast", d:"Toast left in one cycle too long.", c:["#2B1A10","#6B3E1F","#C8873E","#F2D6A2","#FFF7E6"]},
```

If the name is plural or uncountable (like "Burnt Toast" or "Tinned Peaches"), the challenge sentence should read "colours from burnt toast", not "from a burnt toast". Names ending in "s" or containing "'s" are handled automatically. For others, add the name to the `MASS` list in the script.

## Licence

The code has no licence yet. Add one if you want others to reuse it: [choosealicense.com](https://choosealicense.com) explains the options, and MIT is a common pick. Arimo is open-source (Apache 2.0) and free to use on websites.
