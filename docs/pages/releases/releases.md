---
title: GitHub Releases
nav_order: 5
---

# GitHub Releases

This document discusses what GitHub releases are, what they're useful for, and how they're made. 

Much of this information was taken from [this link](https://help.github.com/en/github/administering-a-repository/managing-releases-in-a-repository).

## What are GitHub Releases?

GitHub releases are convenient ways to create a notable checkpoint for your GitHub repository. The release is indicated with a version number and preserves the state of the code for the commit that you create the release with.

Additionally, you can include binary files with your release so that the users of your software don't have to worry about building the software themselves.

## When would I want to create a release?

Since GitHub releases snapshots the code base at a certain commit, I believe the best time to create releases is:

+ Any time you use a model in a publication. 
    + You can include the built binary along with all of the instruction files you need to reproduce the results. This leads to **highly** reproducible scientific computing, something that I believe computation has an advantage on compared to wet lab experiments that can be subject to forces outside of your control.
+ Any time you would like to provide a collaborator a version of the model. 
    + If a collaborator - especially one that is not Git-savvy - wishes to use one of the lab's numerical models, then providing a release will ensure that we know exactly what version of the code the collaborator is working with. This promotes consistency of results and decreases the likelihood of issues with unknowingly using different versions of the models between collaborators.

## How do I create a release?

Creating a release is extremely straightforward.

1. On GitHub, navigate to the main page of the repository.
2. Under your repository name, click **Releases**.
    ![releases example 1](https://help.github.com/assets/images/help/releases/release-link.png)
3. Click **Draft a new release**.
    ![releases example 2](https://help.github.com/assets/images/help/releases/draft_release_button.png)
4. Type a version number for your release. I recommend following a format similar to `vX.Y-Z` where `X` and `Y` are numbers and `Z` can be a very short description of what the release is for, such as the collaborators last name or a shortened version of the title of the paper that uses this release.
    ![releases example 3](https://help.github.com/assets/images/help/releases/releases-tag-version.png)
5. Use the drop-down menu to select the branch that contains the project you want to release.
    ![releases example 4](https://help.github.com/assets/images/help/releases/releases-tag-branch.png)
6. Type a title and description for your release.
    ![releases example 5](https://help.github.com/assets/images/help/releases/releases_description.png)
7. Include any binary files.
    ![binaries](https://help.github.com/assets/images/help/releases/releases_adding_binary.gif)
8. Publish the release or save the draft.
    ![publish or perish](https://help.github.com/assets/images/help/releases/release_buttons.png)

An example of a quick but effective release writeup is [shown here](https://github.com/jekyll/minima/releases/tag/2.4.0).

## Sharing releases

Once a release is created, sharing the release is as simple as sharing the link, `https://github.com/<YOUR_GITHUB_USERNAME>/<REPO_NAME>/releases/tag/<RELEASE_TAG>`.