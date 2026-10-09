# Every visit leaves a light · Silvertree Dental

The public "Every visit leaves a light" page: one hygiene chair's monthly visit counts, shown as a galaxy of stars.
It's a plain static site. Render serves the `site` folder as a free static site, `silvertree-story`, and redeploys
on every push to `main`.

## What's in it
- `site/` is the built page, and nothing else. It holds monthly counts only: no names, dollars, goals, or patient data.
- The source lives in `C:\Users\Brian\Projects\emma-hygiene-dashboard-immersive` (`client/public-story`). Don't edit
  the files in `site/` by hand.

## Numbers refresh on their own
- The page loads `/data.json` on every visit.
- Render rewrites that request to the dashboard's public counts route, `/api/public/story`, which returns counts only
  and is cached 10 minutes. The rule is set in the Render dashboard under Redirects/Rewrites.
- A monthly report uploaded to the dashboard shows up here within about 10 minutes. Nothing needs rebuilding.
- If the dashboard doesn't answer, or its reply doesn't check out, the page shows the numbers it was built with.
- Never add a real `data.json` file to `site`, because Render skips the rule when a file exists.

## Changing the page's look
1. Build it with `npm run public-story` in the project that holds the source. The build fails if anything private
   reached it.
2. Replace this repo's `site` folder with `dist/public-story`, for example with `robocopy <project>\dist\public-story site /MIR`.
3. Commit and push. Render publishes it within a minute or two.
