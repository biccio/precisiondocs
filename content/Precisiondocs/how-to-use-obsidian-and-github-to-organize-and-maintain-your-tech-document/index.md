---
title: How to use Obsidian and Github to Organize and Maintain your Tech Documentation
date: 2024-08-23
summary: Obsidian is a powerful WYSIWYG markdown editor that makes it easy to write and organize your content. Paring it with Github is the perfect solution to develop and maintain technical documentation.
tags:
  - github
  - obsidian
  - hugo
  - jekyll
  - docusaurus
  - git
---
## Introduction: Managing Information Effectively

In today’s fast-paced technical environments, clear and well-organized documentation is key to ensuring smooth workflows and successful collaboration. Whether you’re working on API documentation, software architecture overviews, or development processes, managing this information effectively is essential. Two tools that offer a powerful solution for handling technical documentation are [Obsidian](https://obsidian.md/) and [GitHub](https://github.com/). Together, they provide an efficient system for writing, organizing, and sharing technical documents.

In this article, we’ll explore how to use Obsidian’s note-taking capabilities in combination with GitHub’s version control and collaborative features to streamline your technical documentation workflow.

## Obsidian and GitHub

Github is the most important git platform for code storage, continuous integration and version control, and it's also widely-used for tech documentation storage and collaborative editing, usually in addition with static site generators like [Hugo](https://gohugo.io), [Jekyll](https://jekyllrb.com/), [Docusaurus](https://docusaurus.io/). Obsidian is one of the best markdown editor around, with a great and very usable WYSIWYG interface, and some cool plugins that makes it the perfect all-in-one platform to manage tech documentation content. But how can we make the two tool work together?

## Setting Up Obsidian for Documentation

First of all you'll want to set up your workspace. After downloading and installing [Obsidian](https://obsidian.md/), you will create a dedicated vault for your documentation, and you'll start writing your documentation files. In terms of formatting, Obsidian supports markdown, so you can include headings, subheadings, code snippets, tables, and other essential elements for technical documentation. Tagging is another useful feature in Obsidian, allowing you to categorize your notes and easily find related content. By using **metadata and tags**, you can add context to your documentation and ensure it is well-organized.

## Integrating Obsidian with GitHub

Once your documentation is set up in Obsidian, the next step is to integrate it with GitHub to enable version control and collaboration. This process involves linking your Obsidian vault with a [GitHub repository](https://docs.github.com/en/get-started/quickstart/create-a-repo). If you haven’t already, [create a repository on GitHub](https://github.com/new) specifically for your documentation. 
Then, to link Obsidian with GitHub, you will use your terminal. 

Go to the folder where your Obsidian Vault is stored and use this command to initialize your local repo.

```bash
git init
```

Then, prepare and commit your files, add the Github repository as origin for your local one, and push to the main branch of the repository the content you created with Obsidian 

```bash
git add -A
git commit -m "first commit"
git remote add origin https://github.com/your_user/your_repo.git
git push -u origin main
```

Now your local Obsidian Vault is connected to your Github repository.
## Continuous integration within Obsidian

Now that your local and remote repos are aligned, how will you update your newly edited content directly within Obsidian? You can add to Obsidian a [Git plugin](https://github.com/Vinzent03/obsidian-git), to make it very easy to update your content without using your terminal.
1. Go to menu **Obsidian** → **Preferences** → **Community** plugin and turn them on (they're off by default).
2. Search "Git" in the plugin repository.
3. Install and enable the plugin.
4. You will notice a Git icon on the left hand sidebar. Press that button and on the right hand side of the interface you will notice the Git panel, with ```add```, ```commit``` and ```push``` commands ready to be used within Obsidian. 

You'll now ready to use Obsidian to edit your documentation content in a visual environment, with easy collaborative storage on Github
## Publish your Content

If you have your files on Github and you need to publish them in an easy way, you may want to choose [Github Pages](https://pages.github.com/). [Here's a tutorial](https://docs.github.com/en/pages/getting-started-with-github-pages/creating-a-github-pages-site#creating-your-site) that will easily guide you through all the steps needed.

