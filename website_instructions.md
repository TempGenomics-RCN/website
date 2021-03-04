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


## Customizing your page

### Theme

Customization starts with choosing a Jekyll theme. Currently, we are using the `Leap Day` theme which has a simple layout with all the information contained in a single page with a link menu in the left side of the page that take you to desired heading. The best part of this theme is that you only have to modify a single markdown file to update your website (other themes have separate files for pages).

#### Modifying the website

1. Go to the GitHub repository hosting the website and select the `gh-pages` brach from the drop-down menu.
2. Click the `index.md` file on the left (clicking on the message in the middle of the page shows commit info but does NOT open the index file).
3. Edit this file as you would edit a markdown document (see bellow).
4. Commit changes. The website will automatically update after a few minutes.

#### Markdown

There is a lot online info about the markdown format but everything you need to know to get started is already summirized by GitHub [here](https://guides.github.com/features/mastering-markdown/)

Mainly:

```git
Text:
**bold** - wrap word with two stars
*italic* - wrap word with one star
* Bullet point - a single star at the begging of line
   * - indent a single start for a sub-bullet point 

Headers
# First level header - 1 hashtag
## Second level header - 3 hashtag
###### 6th level header
```

Images 

There are different ways to insert pictures into a GitHub markdown file. It appears that there have been some recent changes in GitHub as the instructions from some online articles do not work anymore. The following should work for you:

Inserting images is a two-step process.

1. Uploading your image into GitHub to generate a source link
   * Start a new issue in your repository page (click `issues` and then click `New issue`)
   * Copy and paste or drag pictures from your local computer into the `Write` window. This will generate the code you will enter in the markdown file.
   * Copy the generated source link and cancel the issue by exiting the current page (for instance, clicking back to the repository page) 
   
2. Inserting link using HTML
   ```<img src="past_your_source_link_here">
   ```
   
Change the image size

The above code will insert your image with the original size. You can control the size of your image by specifying the dimentions:
```<img src="past_your_source_link_here" height="200" width="250">
``` 
*200X250* is the current size of the speaker's image


   
 Text:
**bold** - wrap word with two stars
*italic* - wrap word with one star
* Bullet point - a single star at the begging of line
   * - indent a single start for a sub-bullet point 

Headers
# First level header - 1 hashtag
## Second level header - 3 hashtag
###### 6th level header
   
 
   
   

5. 
6. The website will automatically update after a few minutes of committing changes in GitHub

