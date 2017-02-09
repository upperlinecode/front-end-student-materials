# Cloning a Repository from Github
Github is the "Google Docs of Code" - it allows developers to store their code in the cloud and share it with people around the world. In this lesson, we're going to learn how to download a repository (or "Repo") from Github using `git` in the command line. Git is a version control system that allows us to save our work at different times.

## What are Repositories?
A Repository is just a directory with a collection of files and folders that are "tracked" by github. You can think of a repository as a code project.

## From the Cloud to your Computer (Cloning)
1. Navigate to the github repo you want to clone. [Here is an example repo for you to practice with](https://github.com/upperlinecode/command-line-refrigerator-lab)
2. Click the "Fork Button" on the top right and choose your profile to make a copy to. A fork is an identical copy of a repository, but that belongs to you.
![Fork Button](https://s3.amazonaws.com/upperline/curriculum-assets/command-line/8+fork+button.gif)
3. Click the green "Clone or Download" link on the right side and copy the address.
![Clone Button](https://s3.amazonaws.com/upperline/curriculum-assets/command-line/9-clone-button.gif)
4. In your terminal, navigate to your development directory (so you have all of your work in the same place)
5. Enter `git clone link_name` where link_name is the link that you copied and run. This will download the github repo to your local machine.
![git clone](https://s3.amazonaws.com/upperline/curriculum-assets/command-line/9.git-clone.gif)
6. `cd` into the directory that you just downloaded.

## More Resources
