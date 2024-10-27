---
title: How to use Obsidian and Github to organize and maintain your tech documentation
date: 2024-09-30
summary: Obsidian is a powerful WYSIWYG markdown editor that makes it easy to write and organize your content. Paring it with Github is the perfect solution to develop and maintain technical documentation.
---
## Introduction

In today’s fast-paced technical environments, clear and well-organized documentation is key to ensuring smooth workflows and successful collaboration. Whether you’re working on API documentation, software architecture overviews, or development processes, managing this information effectively is essential. Two tools that offer a powerful solution for handling technical documentation are **[Obsidian](https://obsidian.md/)** and **[GitHub](https://github.com/)**. Together, they provide an efficient system for writing, organizing, and sharing technical documents.

In this article, we’ll explore how to use Obsidian’s note-taking capabilities in combination with GitHub’s version control and collaborative features to streamline your technical documentation workflow.

## Why Obsidian and GitHub?

Github is a well known go-to tool for code storage, continuous integration and version control. Github is also widely-used for tech documentation, usually in addition with static site generators like Astro, Hugo, Jekyll. So you may want to choose Github to store and evolve all your markdown content. Obsidian on the other end is one of the best markdown editor around. Its realtime WYSIWYG interface makes it a very usable editing tool, but the most important feature that makes it the perfect companion for Github, is the Git integration, that makes it very easy to seamlessly push newly edited content to Github.

## Setting Up Obsidian for Documentation

The first step in using Obsidian for technical documentation is setting up your workspace. After downloading and installing [Obsidian](https://obsidian.md/), you will create a dedicated vault for your documentation, and you'll start writing your documentation files. In terms of formatting, Obsidian supports markdown, so you can include headings, subheadings, code snippets, tables, and other essential elements for technical documentation. Tagging is another useful feature in Obsidian, allowing you to categorize your notes and easily find related content. By using **metadata and tags**, you can add context to your documentation and ensure it is well-organized.

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

Now your local Obsidian Vault is connected to your Github repository



In a collaborative environment, GitHub makes it easy for teams to review and contribute to documentation. You can create **[branches](https://guides.github.com/introduction/flow/)** for specific documentation tasks, such as updating API references or adding new sections, and submit **[pull requests](https://docs.github.com/en/pull-requests)** for review. This ensures that documentation changes are carefully reviewed before being merged into the main documentation repository.

## Managing Documentation Changes with GitHub

GitHub’s powerful version control capabilities make it an ideal platform for managing technical documentation in a professional setting. Using a **branching strategy** for documentation, similar to how code is managed, allows multiple contributors to work on different parts of the documentation simultaneously without causing conflicts. For instance, if one team member is updating the API documentation and another is refining the architecture overview, they can work in separate branches and merge their changes once approved.

Automating documentation checks through **[Continuous Integration (CI)](https://docs.github.com/en/actions/automating-builds-and-tests/about-continuous-integration)** is another best practice. **[GitHub Actions](https://github.com/features/actions)**, for example, can be used to run markdown linting, check for broken links, or even spell-check your documentation every time changes are pushed. This helps maintain high-quality documentation and prevents errors from slipping through the cracks.

For large projects, you can also use **[GitHub Pages](https://pages.github.com/)** or other static site generators like **[Jekyll](https://jekyllrb.com/)**, **[MkDocs](https://www.mkdocs.org/)**, or **[Docusaurus](https://docusaurus.io/)** to automatically publish your documentation as a static website. This makes the documentation accessible to non-technical stakeholders while keeping it updated with every push to the repository.

## Structuring Technical Documentation Effectively

Maintaining a clear structure is critical for technical documentation. Start by organizing your documentation into logical sections, such as API references, project architecture, and development processes. Each section should follow a consistent template, with headings for an overview, use cases, code examples, and versioning information.

As your documentation grows, leveraging Obsidian’s **Graph View** can be incredibly helpful for identifying gaps or unclear relationships between sections. This visual representation of your notes enables you to keep track of how different documents relate to one another, ensuring that your knowledge base remains well-structured and easy to navigate.

## Keeping Documentation Up-to-Date

One of the key advantages of using GitHub to manage documentation is that it encourages the practice of keeping documentation close to the codebase. This means that whenever the code is updated, the corresponding documentation can be updated as part of the same workflow. By integrating documentation into the development process, you ensure that it remains accurate and relevant throughout the project lifecycle.

## Backups and Accessibility

Storing your documentation in GitHub also provides **[automatic backups](https://docs.github.com/en/repositories/creating-and-managing-repositories/backing-up-a-repository)**. If anything happens to your local files, the latest version of your documentation is always safe and accessible in your GitHub repository. If your repository is private, you can also maintain confidentiality for sensitive information.

Additionally, **Obsidian** is an offline-first application, so you can work on your documentation even when you don’t have internet access. This is especially useful for remote work or when traveling.