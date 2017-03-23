# Deploying a Website with Github Pages

When you want to put your website on the internet for the world to see, you'll need to **deploy** it. THere are many services to do this, and there is a whole career (devOps) dedicated to deployment and maintenance of websites and apps. To keep it simple though, we're going to use GitHub's gh-pages feature that allows you to turn any repository into a deployed website.

## Instructions

### Step 1: Create a Github Repository for your site.

Go to Github and click on the '+' button on the top right of the screen. Select 'New Repository', and follow the next instructions by giving it a name.

Copy the commands to add the remote origin

### Step 2: Initialize git inside your project directory and connect to Github

In your command line, navigate to the folder with your project files. Type `git init` to initialize git on that repository.

Paste in the `git remote add origin ....` line to connect to github

### Step 3: Commit your changes

`git add .`
`git commit -m "a message about your work"`

### Step 4: Create and Switch to a new branch called gh-pages

`git checkout -b gh-pages`

### Step 5: Push up your changes to GitHub

`git push origin gh-pages`

### Step 6: Enjoy your website!

https://yourusername.github.io/repositoryname/

Make sure you have an index.html file!!!
