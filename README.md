# sunyounglee.com

Static site. No build step, no dependencies. The dark version is the site.

    index.html                     the page (dark)
    light.html                     the same page on a light ground
    work.html / approach.html /
    leadership.html / about.html   redirect to the matching section of index.html
    img/                           images (WebP)
    fonts/                         Switzer variable font (ITF licence)

## Replacing the current site

### If the domain stays on Vercel
1. Push this folder to a GitHub repo (see below).
2. Vercel -> the sunyounglee.com project -> Settings -> Git -> connect the new repo
   (or change the production branch). Framework preset "Other";
   leave the build command and output directory empty.
3. Deploy. DNS does not change. Roll back from the Deployments tab if needed.

### If you would rather host on GitHub Pages
1. Push this folder to a repo.
2. Settings -> Pages -> Deploy from a branch -> `main` -> `/ (root)`.
3. Settings -> Pages -> Custom domain -> `www.sunyounglee.com`, tick "Enforce HTTPS".
4. At your registrar point the `www` CNAME at `<username>.github.io`
   and remove the old Vercel records. Allow up to an hour.

## Pushing to GitHub
    git init
    git add .
    git commit -m "New portfolio"
    git branch -M main
    git remote add origin https://github.com/<username>/<repo>.git
    git push -u origin main

Or drag the files onto github.com -> Add file -> Upload files.
Upload the contents of this folder, not the folder itself: index.html sits at the repo root.

## Notes
- Keep the folder structure; the HTML uses relative paths (`img/...`, `fonts/...`).
- To make the light version the site instead, swap the two filenames.
- Preview locally: `python3 -m http.server` here, then open http://localhost:8000
