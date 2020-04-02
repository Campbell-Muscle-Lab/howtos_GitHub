---
title: Git Ignore Instructions
has_children: True
nav_order: 2
---

# Git Ignore Instructions

The following pages discuss how to set up the `.gitignore` file in a GitHub repository.

## What is a `.gitignore` file?

A `.gitignore` file is how we tell Git to ignore certain files or folders in a repository. The `.gitignore` file is essentially just a list of all of the files and folders in a repository that aren't necessary to keep track of. 

As an extreme example, consider a situation where we have a model in a repository that generates 500 MB of results, status files, etc for every simulation. This repository would become very large very quickly if we did not tell Git to ignore these generated files.

We ignore those generated files with the `.gitignore` file in the root folder of the repository.

## How do I update the `.gitignore` file?

The `.gitignore` file is just a plain text file so it can be updated in any text editor that you would like.

The following links provide instructions for updating `.gitignore` files for specific projects.