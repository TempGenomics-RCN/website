# Guide for Temporal Genomics Working Group website

Uses Jekyll & GitHub pages to deploy the website.

## GitHub Pages set-up

[Here](https://jiafulow.github.io/blog/2020/07/09/create-gh-pages-branch-in-existing-repo/) is more example code on how to make `gh-pages` branches.
[Here](https://guides.github.com/features/pages/) is another example of deploying a GitHub page website.

1. Create the website repository on GitHub.
2. Create & checkout an orphan `gh-pages` branch from which the website will deploy.
    * An orphan branch is helpful here, as it is not connected to the other branches and commits, and its working tree has no files at all (so you only need to add files you want the website to have).

```git
#navigate to repository on local computer
git checkout --orphan gh-pages
git reset --hard
git commit --allow-empty -m "Initializing gh-pages branch"
git push origin gh-pages
git push --set-upstream origin gh-pages #sets /remote as the upstream branch
```

3. Once the branch is pushed, then go to the repository Settings page. Scroll down until you find the section on "GitHub Pages" and make sure `gh-pages` is selected as the branch, and `/root` is selected as the source. Click `Save`.
    * If you have done this right, you should see the line above turn green, with a message saying *Your site is published at ....*
4. Choose a Jekyll theme (can always choose different themes later on).
5. Exit out of Settings and move back to the `gh-pages` branch on GitHub.
6. Create a file called `index.md` and populate it with some text. Commit your changes.
7. Wait a few minutes, then refresh the page and see if a file called `_config.yml` has been created. If it has, congratulations! You have officially made a website with GitHub pages.
    * The `index.md` file contains text for the main page of your website. Edit it as you would a markdown file.
    * The `_config.yml` has the configuration settings for your website (Jekyll theme, website name, etc.).
