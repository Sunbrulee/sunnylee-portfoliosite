# sunyounglee.com

Static site. No build step, no dependencies.

    index.html                     the page
    dark.html                      the same page on a dark ground
    work.html / approach.html /
    leadership.html / about.html   redirects to the matching section of index.html
    img/                           images (WebP)
    fonts/                         Switzer variable font (ITF licence)

## Replacing the current site

### If the domain stays on Vercel
1. Push this folder to a GitHub repo (see below).
2. Vercel dashboard -> the sunyounglee.com project -> Settings -> Git ->
   connect it to the new repo (or change the production branch).
   Framework preset: "Other". Build command: leave empty. Output directory: leave empty.
3. Deploy. The domain keeps pointing at Vercel, so nothing changes in DNS.
   Roll back from the Deployments tab if anything looks wrong.

### If you would rather host on GitHub Pages
1. Push this folder to a repo.
2. Settings -> Pages -> Deploy from a branch -> `main` -> `/ (root)`.
3. Settings -> Pages -> Custom domain -> `www.sunyounglee.com`, tick "Enforce HTTPS".
4. At your registrar, point the `www` CNAME at `<username>.github.io`
   and remove the old Vercel records. Allow up to an hour.

## Pushing to GitHub
    git init
    git add .
    git commit -m "New portfolio"
    git branch -M main
    git remote add origin https://github.com/<username>/<repo>.git
    git push -u origin main

Or drag these files onto github.com -> Add file -> Upload files.
Upload the contents of this folder, not the folder itself: index.html sits at the repo root.

## Notes
- Keep the folder structure; the HTML uses relative paths (`img/...`, `fonts/...`).
- Preview locally: `python3 -m http.server` here, then open http://localhost:8000
- The dark version is a second page, not a theme switch. Delete `dark.html` if you only want the light one.
