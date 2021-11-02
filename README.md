## How to Host a Resume with GitHub Pages

The purpose of this README is to describe how to host a resume online with various tools, such as GitHub Pages, Jekyll, Markdown, and a Markdown editor in Windows.

Prerequisites:

* Markdown editor (Typora, for example)
* Markdown formatted resume

### Formatting Your Resume

There are a lot of different Markdown flavors. Standard Markdown works, but is somewhat limited. It lacks certain features such as tables, so if you plan on using some fancier features, consider a flavor. Markdown is a great choice because it is easy to learn and offers a lot of flexibility, such as being able to be converted to HTML or XML. Check the [More Resources](# More Resources) section for a Markdown tutorial.

## Creating a GitHub Account

If you already have a GitHub Account, you can skip this section and sign in instead.

1. Go to [GitHub](https://github.com/).
2. Click the "Sign up for GitHub" Button.
3. Enter the details requested by the signup form.
4. Check your email address for the 6-digit code sent to it.
5. Specify how many people are working with you and that you are a student.
6. Select the features you are most interested in using.
7. Skip the next step by clicking the "Skip Personalization" button at the bottom unless you want to upgrade.

## Git Bash Setup

The following steps require Git Bash, Ruby, and RubyGems installed.

1. Download and install [Ruby](https://www.ruby-lang.org/en/downloads/).
2. Download and install [Git Bash](https://git-scm.com/downloads).
3. Open Git Bash.
4. Download and install [RubyGems](https://rubygems.org/pages/download#formats)
5. Install bundler with the command `gem install bundler`.
6. Install webrick with the command `gem install webrick`.<br>Note: This is needed to test your site locally.

Git is a Distributed Version Control System (DVCS). It more than does the job for hosting websites. Since this is what many developers use, it is good to be familiar with, and shows an ability to interface with modern systems. It allows for offline and remote work.

This environment allows you to work on your website locally. So, if you do not have access to an internet connection, you can still work on your website, and push your updates when you do.

### Initializing a Jekyll site

Jekyll sites come with a lot of advantages. All they need to do is store pages on a server, so they are relatively easy to set up. Andrew Etter points out that this means that the requisite hardware resources are very small.

Keep in mind that while you do these steps, GitHub Pages can take roughly 20 minutes to update your site. So if you do not see changes immediately, wait a bit.

1. Create a GitHub repository or use an existing one.

2. Navigate to where you want to store your site locally in Git Bash, using the `cd` command or by right clicking in the directory in the File Explorer and pressing "Git Bash Here."

3. Create a new repository with the `git init` command. This command takes a parameter for your repository name. So it looks like `git init NAME`. 

4. Enter the folder the previous command created with the chosen parameter as a name. 

5. Within your repository decide where you want your site to be located. If you want it in a directory titled "website," create that folder and enter it.

6. Choose a branch for your site. If you want to publish your site on the gh-pages branch, enter the command `git checkout --orphan gh-pages`.

7. Initialize the site with the command `jekyll new --skip-bundle .`<br>Note: the period is part of the command. This ensures the action takes place in your current directory. You can also specify a path.

8. Open the file labeled "Gemfile" in a text editor of your choice.

9. Comment out the line `gem "jekyll", "~> 4.2.1"` by placing a "#" at the beginning, which is how Ruby handles comments.

10. Uncomment the line `gem "github-pages", "~> GITHUB-PAGES-VERSION", group: :jekyll_plugins`.

11. Replace GITHUB-PAGES-VERSION in the uncommented line with the current github-pages version.<br>Note: The github-pages version at time of writing is 219. You can double check [here](https://pages.github.com/versions/). Make sure you look for github-pages, not Jekyll.

12. Run the command `bundle install` to build your new website.

    You did it! Now you need to move your work remotely.

    Make sure that if you make changes, you rebuild your entire site.

### Pushing Your Site to GitHub

1. Run the commands `git add .` which adds the current directory. 
2. Commit your work with `git commit -m 'Your message'`.
3. Set the remote repository you want to add to with the command `$ git remote add location https://github.com/USERNAME/REPOSITORY_NAME.git`where USERNAME is your GitHub username and REPOSITORY_NAME is the name of the remote repository on GitHub. The parameter "location" can be anything you want, just as long as it is the same as in the command in the next step.
4. Push your repository to GitHub with `git push -u location BRANCH-NAME` where BRANCH-NAME is the name of the branch in your local repository.
5. In your GitHub repository, go to the Settings page next to the gear icon. Then, select the Pages section.
6. Set the branch and directory in which you placed your website. So, if you pushed your site to the `docs` folder of the `main` branch, select those.
7. Check your site from the link given in the Pages section.<br>Note: If the box that contains your link is blue, the site has not finished updating.  Be patient. It sometimes takes a while. When it is green, you are good to go.

​	A link to a Markdown tutorial can be found in the "More Resources" section below. 

​	Then we will create a website with a static site generator known as Jekyll. Hosting you resume on an updatable format such as a website is important. Formats that cannot be updated, such as PDFs, have the problem of leaving people with out of date information on their end. When you update your PDF stored resume, yours is up to date, but anybody that was sent an older version is not. Storing you resume on a website can solve this. Your resume might look something like this.

![Animation](https://github.com/ungerj38/ungerj38.github.io/blob/main/Animation.gif)

### More Resources:

https://jekyllrb.com/docs/installation/

https://docs.github.com/en/pages/setting-up-a-github-pages-site-with-jekyll/creating-a-github-pages-site-with-jekyll

https://www.markdowntutorial.com/

https://www.amazon.ca/Modern-Technical-Writing-Introduction-Documentation-ebook/dp/B01A2QL9SS

### Authors and Acknowledgements

Gurtej Boparai 

Yucong Nie 

Tim Appleyard 

Jordan Unger 

Dean Pistorius

### FAQs

Q: Why are we using a Markdown editor instead of a word processor?

A: We are using a Markdown editor instead of a word processor because Markdown allows for interfacing with web development, despite being somewhat more complex than using a word processor. Markdown is easy to learn, especially when compared to HTML.

Q: Why is my resume showing up in basic HTML?

A: Your resume might be showing up in basic HTML if you do not rebuild your site when you make changes. Make sure you run the command `bundle install` when you make changes.
