---
Title: Building Locally
nav_order: 3
parent: GitHub Pages
---

# Building Locally
{:.no_toc}

* TOC
{:toc}

## Overview

This document walks through the process of building your pre-existing GitHub Pages repo on your local machine. This is advantageous as this allows you to preview changes instantly instead of committing and pushing the changes, then waiting on GitHub to build the site for you.

## Installation of Dependencies

There are several pieces of software that you will need to get your repo up and running locally. You will need:

  + Git for Windows.
      + Note: Having the Git Desktop application installed on your Windows machine isn't sufficient!
  + A version of the Ruby programming language.
  + The `Bundler` package manager for Ruby.
  + The `Jekyll` Ruby package.

### Installing Git for Windows

To install Git for Windows, click the download link [at this site](https://gitforwindows.org/) and run the installer once downloaded. There are quite a few options that you can choose to customize your experience with using Git. However, we recommend keeping everything default except for the editor of choice for Git (the first option you are presented to change). Using Visual Studio Code as your editor of choice is much easier than using the default Vim editor.

This installs Git along with the 'Git Bash' shell that allows us to build the website locally.

### Installing The Ruby Language

To install the Ruby programming language, visit [this site](https://rubyinstaller.org/downloads/) to download the Ruby installer. There are many options on which installer to download but they keep their updated recommended installer to the right of the installer links under the "Which Version to Download?" section.
+ Note, As of 9/17/2023, Ken could not get this to work with the latest Ruby. It did work with the 2.7 version.

Once the installer has downloaded, run it and follow the prompts. On the last step of the installation wizard, be sure to run the `ridk install` step. This is important for installing the Ruby packages we need.

### Installing Bundler

Ruby packages come as "gems" much like how Python packages come as modules. A convenient package manager for the Ruby language is [Bundler](https://bundler.io/).

Per `Bundler`'s website, to install `Bundler`:

1. Open a Git Bash window on your local machine. To do this:
    1. Click the Windows icon on the lower left of your screen to open the Start Menu.
    2. Search for "Git Bash" and hit <kbd>Enter</kbd>.
2. Type the following in the Git Bash window:
    ```
    gem install bundler
    ```
    Ruby will install `Bundler` for you and notify you when it has finished. Keep the Git Bash window open for the next step.

### Installing Jekyll

`Jekyll` is a Ruby gem that converts markdown files into HTML pages for websites. To install `Jekyll`, type the following into a Git Bash window:

```
gem install jekyll
```

As with `Bundler`, Ruby will notify you when the installation has finished.

Finally, verify that `Jekyll` has installed correctly by typing, `jekyll -v` in the Git Bash window.

## Setting Up The Repo to Build Locally

Now that the installation of all the dependencies are taken care of, we can focus on constructing the additional file we need to build our GitHub Pages website locally. 

### The Gem File

This additional file is named `Gemfile` and is how we tell Ruby that we need the GitHub Pages gem before we can build the website.

To construct this file, open your favorite text editor, create a new file named `Gemfile` (no file extension), and type the following:

```
source 'https://rubygems.org'
gem "github-pages", group: :jekyll_plugins
```

Save the `Gemfile` in the same directory as the `_config.yml` and `index.md` file of your GitHub Pages repository.

## Building the Repo Locally

Now that we have all of the dependencies installed and the `Gemfile` made, we can finally build our website locally. To do so:

1. Open a Git Bash window. To do this:
    1. Click the Windows icon on the lower left of your screen to open the Start Menu.
    2. Search for "Git Bash" and hit <kbd>Enter</kbd>.
2. Navigate to the directory that contains your `_config.yml`, `index.md`, and `Gemfile` files.
3. If this is your first GitHub Pages site that you are building locally, type the following in your Git Bash window:
    ```
    bundle install
    ```
    This installs all of the gems necessary to build your site locally (these were specified via the Gemfile).

    If this is not your first GitHub Pages site that you are building locally, you can skip this step.
4. Type the following in your Git Bash window:
    ```
    bundle exec jekyll serve
    ```
    This will initiate the build process for your website and will inform you what port the website is located at. This is nearly always `localhost:4000`.
4. Open an internet browser and type in the address bar `localhost:XXXX` where `XXXX` is the port number you were given in the previous step. If everything has gone right, you should now see your GitHub Pages website just like how it is built when pushed to GitHub.
