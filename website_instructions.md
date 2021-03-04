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


## Adding multiple pages

To add another page with information (using markdown files only):

1. Create a new markdown file in the `gh-pages` branch. (Ex: `contact.md`)
2. At the top of the file, add the following:

```git
---
title: CONTACT PAGE
template: #whatever Jekyll theme you chose for the first page (check _config.yml if you are unsure)
filename: contact.md
---
```

3. Link this `contact.md` page to your homepage (`index.md`):

```git
For contact information, visit [contact page](contact.md).
```

Push your changes and wait a few minutes for the website to be published (updated). Now, when you go to your GitHub pages website, you should see a link to a new page with the information in your `contact.md` file. You can also go directly to the newly created page with: `YOURGITHUBNAME.github.io/YOURREPOSITORYNAME/contact.md`.


## Customizing pages

### Theme

Customization starts with choosing a Jekyll theme. Currently, we are using the `Leap Day` [theme](https://github.com/pages-themes/leap-day) which has a simple layout with all the information contained in a single page with a link menu on the left side that takes you to desired heading. The best part of this theme is that you only have to modify a single markdown file to update your website. Other themes have different layouts - [change theme](https://docs.github.com/en/github/working-with-github-pages/adding-a-theme-to-your-github-pages-site-with-the-theme-chooser).

### Modifying the website

1. Go to the GitHub repository hosting the website and select the `gh-pages` brach from the drop-down menu.
2. Click the `index.md` file on the left (clicking on the message in the middle of the page shows commit info but does NOT open the index file).
3. Edit this file as you would edit a markdown document (see bellow).
4. Commit changes. The website will automatically update after a few minutes.

### Markdown

There is a lot online info about the markdown format (like how to include [emoji](https://github.com/ikatyang/emoji-cheat-sheet/blob/master/README.md#smileys--emotion) :wink: ) but everything you need to know to get started is already summirized by GitHub.

The basics

```git
Text:
**bold** , wrap word with two stars
*italic* , wrap word with one star
* Bullet point , a single star at the begging of line
   * sub-bullet point , indent once a single start

Headers
# First level header - 1 hashtag
## Second level header - 2 hashtag
###### 6th level header

Level 1-3 headers will appear as links on the left of the Leap Day layout
```
Read the [GitHub Markdown Guide](https://guides.github.com/features/mastering-markdown/) for **MANY** more details and tips




### Images 

There are different ways to insert pictures into a GitHub markdown file. It appears that there have been some recent changes in GitHub as the instructions from some online articles do not work anymore. The following should work for you:

Inserting images is a two-step process.

1. Uploading your image into GitHub to generate a source link
   * Start a new issue in your repository page (click `issues` and then click `New issue`)
   * Copy and paste or drag pictures from your local computer into the `Write` window. This will generate the code you will enter in the markdown file.
   * Copy the generated source link and cancel the issue by exiting the current page (for instance, clicking back to the repository page) 
   
2. Inserting link using HTML
Place this code where you want to insert your image
   ```git
   <img src="paste_your_source_link_here">
   ```
   
   Change the image size

   The above code will insert your image with the original size. You can control the size of your image by specifying the dimentions:
   ```git
   <img src="past_your_source_link_here" height="200" width="250">
   ``` 
   *200X250* is the current size of the speaker's image. 

   Few articles about inserting and controlling the size of images [inserting](https://ardalis.com/add-images-easily-to-github/) [size1](https://github.com/jgm/pandoc/issues/2554) [size2](https://stackoverflow.com/questions/14675913/changing-image-size-in-markdown) [size3](https://gist.github.com/uupaa/f77d2bcf4dc7a294d109)

