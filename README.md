# Exactly

A design challenge generator. Press **Generate** to get a random **category**, **brand name** and **colour palette**, then design it using only those colours.

> *Design a funeral home brand called "Hiccup", using only colours from a disco ball.*

It's one HTML file with no build step and no dependencies apart from Google Fonts.

## Files

| File | What it is |
| --- | --- |
| `index.html` | The whole website |
| `CHANGELOG.md` | Version history: changes and bug fixes |
| `README.md` | This file |
| `.nojekyll` | Tells GitHub Pages to serve the files as they are |

## Put it on GitHub Pages (no coding needed)

1. **Make a GitHub account** at [github.com](https://github.com) if you don't have one.
2. **Create a repository.** Click **+** (top right), then **New repository**. Name it `exactly`, set it to **Public**, and click **Create repository**.
3. **Upload the files.** On the new repository page, click **uploading an existing file**. Drag in `index.html`, `README.md` and `CHANGELOG.md`, then click **Commit changes**.
   - `.nojekyll` is a hidden file, so your computer may not show it. Without it the site still works. To add it anyway: click **Add file**, then **Create new file**, name it `.nojekyll`, leave it empty, and commit.
4. **Turn on Pages.** Go to **Settings**, then **Pages** (left sidebar). Under **Build and deployment**, set **Source** to **Deploy from a branch**. Set the branch to **main** and the folder to **/ (root)**, then click **Save**.
5. **Wait a minute or two**, then refresh the Pages settings screen. Your site's address appears at the top:
   `https://YOUR-USERNAME.github.io/exactly/`

### Using the command line instead

```bash
cd exactly
git init
git add .
git commit -m "Exactly v1.4.0"
git branch -M main
git remote add origin https://github.com/YOUR-USERNAME/exactly.git
git push -u origin main
```

Then do step 4 above.

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

Add one if you want others to reuse the code. [choosealicense.com](https://choosealicense.com) explains the options. MIT is a common pick.
