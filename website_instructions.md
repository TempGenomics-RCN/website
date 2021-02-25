# Guide for Temporal Genomics Working Group website

Uses Jekyl & GitHub pages to deploy the website.

## GitHub Pages set-up

1. Create the website repository on GitHub.
2. Create & checkout an orphan `gh-pages` branch from which the website will deploy.
  * An orphan branch is helpful here, as it is not connected to the other branches and commits, and its working tree has no files at all (so you only need to add files you want the website to have).

```git
#navigate to repository on local computer
git checkout --orphan gh-pages
git reset --hard
git commit --allow-empty -m "Initializing gh-pages branch"
git push origin gh-pages
git checkout main
```
