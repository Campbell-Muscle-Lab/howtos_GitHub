---
Title: Best Practices
nav_order: 2
parent: GitHub Pages
---

# Best Practices
{:.no_toc}

* TOC
{:toc}

## Overview

This page discusses the conventions and best practices that we use in the Campbell Muscle Lab to build our GitHub Pages websites.

## Structuring Your GitHub Pages Website

1. All pages of your website go in the pages folder.
    + This is a rather simple rule to follow, but important nonetheless. All pages that you create for your website need to go in the folder located at `docs/pages`.
2. Each new page goes in a new folder.
    + This convention is pretty self explanatory, but every new page is placed in a new folder. This helps with organizing images and the structural layout of your website.
3. Nest pages and folders that go together.
    + To keep things organized both on your website and in your `docs` folder, it helps to nest pages that are related. For example, look to the left of this page at the navigation bar. There are multiple topics written about GitHub Pages. To organize this, we have grouped these concepts together. You can see how we've organized the pages in this GitHub repository by visiting [this link](https://github.com/Campbell-Muscle-Lab/howtos_GitHub/tree/master/docs/pages/github_pages).
4. Include any inkscape source files for your page in a subdirectory of that page's folder titled, `SVG_files`.
    + This allows us to keep the editable file format of the inkscape image that you upload so that if we ever need to change it, it will be simpler than redoing the entire image.

## Structure of Individual Pages

1. The `index.md` page serves as the main page of the repository and the title should almost always be the name of the repository or project.
2. Pages should always be set up in this format:

    ```md
    ---
    title: YOUR TITLE HERE
    nav_order: Put the order in which the link on the nav bar to the left should appear here
    has_children: (`True` if the page has sub-pages under it or `False` if this page does not)
    parent: Title of Parent if it has a parent page (is a sub-page of another page)
    grand_parent: Title of grand parent page if it has one (is a sub-page of a sub-page)
    ---

    # YOUR TITLE HERE
    {:.no_toc}

    * TOC
    {:toc}
    ```

      + The header (the portion between the two `---`) describes where the page will be in the built site. The GitHub Pages template that we use builds our site hierarchy for us and handles the linking between pages automatically.
      + The `title`, and `nav_order` members of the header should always be present on every page.
          + The other members are not necessary and should only be used when they apply.
      + The `TOC` portion of this page template describes where to put the table of contents.
          + Putting `{:.no_toc}` under the title header designates that the title should not be included in the table of contents. 
3. When linking between pages, like when you want to [link to the Getting Started page](../getting_started/getting_started.md), use relative referencing instead of absolute referencing for file paths.
    + For example:
        + When linking to the Getting Started page like I did above, do the following:
            ```md
            [link to Getting Started page]( ../getting_started/getting_started.md)
            ```
            (Without the space between the open parenthesis and the `../`.)

            NOT

            ```md
            [link to Getting Started page](/pages/github_pages/getting_started/getting_started.md)
            ```

            The latter can lead to broken links.

## The Configuration File

1. Links in the configuration file should use the `http` protocol for accessing websites, not the `https` protocol.
    + For example:
        + Use `http://www.github.com` instead of `https://www.github.com`.
    + Not following this rule can lead to broken links in your website.

## General

1. When you encounter an issue with a GitHub Pages site or with a tutorial site such as this one, submit an issue for that site's repository. We can't fix problems with our websites if we don't know about them!