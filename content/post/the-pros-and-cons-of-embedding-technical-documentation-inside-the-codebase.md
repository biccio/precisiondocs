---
title: How to Build and Deploy a Tech Documentation Static Site with Hugo
date: 2024-08-23
tags: ["hugo", "netlify", "staticsitegenerator", "frameworks", "github", "deployment", "techdoc", "docsy"]
summary: Hugo is a powerful static site generator functioning as a complete framework. Along with Github as storage repository and Netlify as deployment tool, it makes a perfect platform to run and mantain a fast and lightweight documentation website.
featured: true
image : "/img/posts/img-1.png"
schema:
  "@context": https://schema.org
  "@type": HowTo
  name: "How to Build and Deploy a Tech Documentation Static Site with Hugo"
  datePublished: "2024-08-23"
  image: /img/posts/img-1.png
  description: "A guide on how to create, store, and deploy a documentation website using Hugo, GitHub, and Netlify."
  tool:
    - "@type": SoftwareApplication
      name: "Hugo"
    - "@type": SoftwareApplication
      name: "GitHub"
    - "@type": SoftwareApplication
      name: "Netlify"
  step:
    - "@type": HowToStep
      name: "Install Hugo"
      text: "Install the Hugo framework on your machine using a package manager like Homebrew, apt-get, or by downloading the binary."
    - "@type": HowToStep
      name: "Create a New Website"
      text: "Use the 'hugo new site' command to create a new folder with the necessary Hugo structure."
    - "@type": HowToStep
      name: "Install the Theme"
      text: "Add a theme like Techdoc to your site using Git submodules and configure the hugo.toml file."
    - "@type": HowToStep
      name: "Set up GitHub Repository"
      text: "Create a new repository on GitHub and push your local website files to it."
    - "@type": HowToStep
      name: "Deploy with Netlify"
      text: "Import the GitHub project into Netlify, configure the build settings (build command 'hugo', publish directory 'public'), and deploy the site."
---

## Choosing the Best Place for Documentation
If you’ve ever worked with code and tech documentation, you may have asked yourself, “Where should all that essential information go?” Embedding documentation directly in the codebase versus keeping it separate (like in a standalone knowledge base) each comes with pros and cons, along with specific use cases where one approach may work better than the other. Here, we’ll examine the arguments for both options to help you decide which method best fits your project.
## Why choose to embed documentation
For developers who spend most of their time in an [IDE](https://en.wikipedia.org/wiki/Integrated_development_environment), having documentation alongside the code itself makes a huge difference. With embedded documentation, developers avoid hunting through separate tools, finding essential information—function descriptions, parameters, tricky logic explanations—all integrated into the code. This ease of access saves time and reduces context-switching, especially valuable in fast-paced or Agile environments.

Furthermore, **embedded documentation is often more accurate**. When a method or function changes, it's easy for developers to quickly update the related docstring and comment, to prevent outdated documentation. Keeping the code and documentation close together is a huge help, especially for small teams that may not have time or resources to maintain a separate workflow for tech writing.
### Some Drawbacks of Embedded Documentation
While embedded comments and [docstrings](https://it.wikipedia.org/wiki/Docstring) work for specific, isolated explanations, **they can clutter the code if overused.** Readability may suffer, especially when sections are filled with verbose documentation that obscures the actual code logic. There’s also limited formatting flexibility—comments in code are generally plain text, which doesn’t allow for rich formatting like tables, images, or structured examples
### Use case for embedded documentation
Embedded documentation is most effective when projects focus on technical use cases that benefit directly from inline clarification. For example, if you’re building an API, inline docstrings make each function’s purpose, parameters, and output clear. Combined with tools like [Sphinx](https://www.sphinx-doc.org/) or [JSDoc](https://jsdoc.app/), these inline comments can even auto-generate documentation pages, making them accessible without the need for manual upkeep.

## Why Use Separate Documentation?

In contrast, keeping documentation separate from code can be a great choice, **especially for larger, cross-functional teams or complex projects**. With dedicated documentation tools like [Confluence](https://www.atlassian.com/software/confluence), [Notion](https://www.notion.so/), or [GitBook](https://www.gitbook.com/), you can create comprehensive guides, tutorials, and high-level overviews that surpass the limitations of inline comments. Separate documentation allows you to include multimedia elements like tables, diagrams, and step-by-step user flows, making it ideal for non-developers or anyone who might be intimidated by the codebase.

Keeping documentation separate from the codebase also makes it more accessible to **non-developer stakeholders** like product managers or customer support. Many documentation platforms include advanced search and organizational features, making it easier to find specific information than if it were buried in code comments.

### Potential Downsides of Separate Documentation
One common challenge with separate documentation is that it’s prone to getting out of sync with the actual code. Without a rigorous update process, changes to the code may not always reflect in the documentation, leading to potential confusion. Separate documentation also requires more upkeep, often involving additional workflow steps like reviews or approvals, which can slow down development and add maintenance overhead.

### Use Cases for Separate Documentation
Separate documentation is essential for larger, more complex projects where high-level overviews, architectural diagrams, or tutorials are common. For onboarding, a structured knowledge base that provides an overview of architecture, workflows, and team processes is more accessible than embedded comments alone. High-level architectural diagrams, setup instructions, or step-by-step tutorials for feature implementations are often better suited to a dedicated documentation platform.

## A Common Middle Ground: Combining Embedded and Separate Documentation

For many teams, a balanced approach is often the best solution. Smaller projects or those primarily managed by developers might benefit from embedded documentation for its simplicity. In contrast, larger, cross-functional projects typically require a dedicated documentation platform to support collaboration, onboarding, and in-depth guides.

A middle-ground approach could be to use **embedded documentation for lower-level details**—method descriptions, parameters, and inline clarifications of complex logic—while using a separate documentation tool for **higher-level overviews, architecture diagrams, and tutorials**. This method allows the code to stay readable and uncluttered, while higher-level information remains accessible, flexible, and easy to maintain.
