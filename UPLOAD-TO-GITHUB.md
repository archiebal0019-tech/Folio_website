# Putting this site on GitHub Pages

Everything in this folder is the finished website. There is nothing to build and nothing to install.

## What has to end up in the repository

Eight items, all at the **top level** of the repo, not inside a folder:

```
index.html
resume.html
resume-data.js
404.html
.nojekyll
README.md
UPLOAD-TO-GITHUB.md
images/          (49 files)
```

If your repository's front page shows a folder called `folio wbe 1` that you have to click into, the site will 404. GitHub Pages looks for `index.html` at the root and nothing else will do.

## Uploading through the website

1. On github.com, create a new repository. **Public**, and do not tick "Add a README".
2. On the empty repo page, click **uploading an existing file**.
3. Open this folder on your PC. Press **Ctrl+A** to select everything *inside* it, including the `images` folder.
4. Drag that selection into the browser window. Wait for all of it to finish, `images` included.
5. Click **Commit changes**.

Two things people miss here:

- **`.nojekyll` may be invisible.** Windows hides files that start with a dot. In File Explorer turn on **View → Show → Hidden items** before you select everything. Without it GitHub Pages may ignore some files.
- **The `images` folder must go too.** Drag the folder itself; GitHub keeps the structure. If you only upload the HTML files, the site loads with every picture broken.

## Switching Pages on

Repository → **Settings** → **Pages** in the left sidebar.

- Source: **Deploy from a branch**
- Branch: **main**, folder: **/ (root)**
- **Save**

Give it a minute or two. The Actions tab shows a green tick when the build is done, and the Pages settings page then shows a banner with your live address.

## Your address

```
https://<username>.github.io/<repo-name>/
```

The repository name is part of the URL. Opening `https://<username>.github.io/` on its own gives a 404 unless you named the repository exactly `<username>.github.io` — which is worth doing, because then the site lives at that short address with nothing after it.

## If you get a 404

Work down this list:

1. Does the repo's front page list `index.html`, or a folder? A folder is the problem.
2. Does Settings → Pages show a green "Your site is live at…" banner? If not, Pages is not switched on.
3. Are you opening the exact URL from that banner, including the repo name and the trailing slash?
4. Is the repository **Public**? Private repos need a paid plan for Pages.
5. Has the Actions tab finished? A build in progress serves a 404 in the meantime.

## If the site loads but pictures are missing

The `images` folder did not upload. Add it: **Add file → Upload files**, then drag the `images` folder in on its own.

## If the CV's Download PDF button does nothing

Check the repo has `resume-data.js` spelled with the hyphen. If it arrived as `resumedata.js`, rename it in GitHub — click the file, then the pencil icon, and correct the name.

## Updating the site later

Change the files in this folder, then in the repo use **Add file → Upload files** and drag the changed ones in. Same filenames overwrite the old versions. The live site updates about a minute after you commit.
