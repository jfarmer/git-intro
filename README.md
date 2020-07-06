# Intro Git

This isn't meant to be comprehsive. It won't answer every question you have.

Here's a quick video we made showing the steps involved when you are creating a fresh project: <https://youtu.be/1_yU0yHCcDo>

## Creating A New Repository

1. Go to <https://github.com> and click the **+** menu in the upper-right hand corner and thenc lick **New Repository**

   <https://share.getcloudapp.com/jkuQRrnQ>
1. Give your repository a name like `html-milestones` and a description then click the green **Create Repository** button

   <https://share.getcloudapp.com/Wnub6zA1>

   **Note**: You can name your repository anything. We're using `html-milestones` as an example name here. You'll have one repository per project, typically.
1. You should see a page that looks roughly like this, but containing the information *you* entered: <https://share.getcloudapp.com/lluJXmwX>

Next, you have two options depending on which scenario you're in:

1. You haven't done any local work on your project yet, so you have no code
1. You've already done some work on your project and you want to send that up to GitHub

## Fresh Project

If you haven't done any work yet, use `git clone` to get a copy of the remote repository on your computer, as follows:

```console
git clone https://github.com/githubUsername/repositoryName.git
```

**Note**: Replace `githubUsername` and `repositoryName` in the above command with the GitHub username and repository name of whatever you're trying to download. You can copy this from GitHub via the "Clone & Download" button.

Use `cd` to go into the newly-created directory. At this point the instructions are the same for both scenarios.

## Existing Project

If you've already done some work on a local project and want to create a new repository on GitHub to hold it, use `cd` to navigate to the project directory and do the following:

```console
git init
git remote add origin https://github.com/githubUsername/repositoryName.git
```

Replace `githubUsername` and `repositoryName` in the above sequence of commands with your GitHub username and the name of the repository you just created.

## Pushing Changes to GitHub

The basic idea is to package up all changes into something called a _commit_ and then push the commit to GitHub.

```console
git add .
git commit -m 'Initial commit'
git push
```

If `git push` complains about not having an _upstream_ branch, run the following command:

```console
git push --set-upstream origin master
```

You should only ever need to use `--set-upstream origin master` with `git push` once per repository. `git` will remember every time after that.


**Note**: In the line that reads

```console
git remote add origin https://github.com/githubUsername/repositoryName.git
```

make sure to replace `githubUsername` with **your** GitHub username and `repositoryName` with the name of your repository.

We'll learn how to create several commit later; normally you would want to group related changes into a single commit but keep unrelated changes in different commits. Likewise, the `'Initial commit'` message above is meant to be a description of what the changes are so other people can get an idea of what you've done without reading the code itself.

We won't worry about that for now. It's more important to get used to the flow of:

1. Pulling down new repositories using `git clone`
1. Making changes to a project and package them up into commits using `git add` and `git commit`
1. Pushing changes up to GitHub using `git push`

## Getting Changes

If you're working on a team and someone else made a change, you can use the following command to pull down any new changes:

```console
git pull
```

## Viewing Status

Before you run `git add` it's a good idea to run the following:

```console
git diff
```

This will show you all the changes you've made since the last commit. Press `q` to leave this interface (in general, any time you're on the command line and see a prompt that begins with `:` at the bottom of the screen, pressing `q` will quit).

You should also get used to running

```console
git status
```

which will tell you which files have changes, which ones have yet to be committed, etc. Using `git status` and `git diff` are the main ways to stay oriented with respect to what's going on in your repository.

You'll see more experienced programmers running them all the time to double check that they're doing what they expect to be doing, aren't accidentally committing code they didn't mean to, etc.
