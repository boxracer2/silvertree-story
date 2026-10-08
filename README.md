# Every visit leaves a light · Silvertree Dental

The public "Every visit leaves a light" page: one hygiene chair's monthly visit counts, shown as a galaxy of stars.
It's a plain static site. Render serves the `site` folder as a free static site, `silvertree-story`, and redeploys
on every push to `main`.

## What's in it
- `site/` is the built page, and nothing else. It holds monthly counts only: no names, dollars, goals, or patient data.
- The source lives in `C:\Users\Brian\Projects\emma-hygiene-dashboard-immersive` (`client/public-story`). Don't edit
  the files in `site/` by hand.

## Monthly refresh (after the monthly report is in)
1. In the immersive folder, run `npm run public-story`. It writes the snapshot, builds the page, and fails if anything
   private reached the build.
2. Replace this repo's `site` folder with `dist/public-story`, for example
   `robocopy ..\emma-hygiene-dashboard-immersive\dist\public-story site /MIR`.
3. Commit and push. Render publishes it within a minute or two.
