This is a minimal example of a book based on R Markdown and **bookdown** (https://github.com/rstudio/bookdown). Please see the page "Get Started" at https://bookdown.org/ for how to compile this example.

Here's how I deployed this bad boy:

1. wrote my book in a new project cloned from GitHub (`bookdown:::bookdown_skeleton(getwd())`)
1. committed and pushed README (critical for netlify connection- cannot be empty repo)
1. made `.travis.yml` (can't use usethis b/c adds a `.RBuildIgnore`)
1. made `DESCRIPTION` (can't use usethis b/c not relevant fields)
1. update `.gitignore` (used usethis)
1. from netlify, got token
1. on travis, stored netlify token as an env variable
1. back to netlify, new site from git, connect it, left all defaults to deploy from master
1. copied netlify site `API ID`, and pasted back into my `.travis.yml` as env `NETLIFY_SITE_ID`

--> push to GitHub, this should deploy to Netlify

--> then I will make a small change and push to GitHub again and the site should GO DOWN while Travis builds the book.

