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

## A Static Site for Tech Documentation
Static site generation is a very popular solution in today's publishing environments, especially for technical documentation. The available frameworks are solid and easy to use, and the resulting website is blazing fast with no hiccups and zero render time. If you add Github to the workflow as a storage solution, and Netlify as deployment framework, you have a perfect solution to a fast and clean publishing process.
In this article, I'll describe all the steps you'll need to create a Tech Documentation website with Hugo using Github and Netlify for deployment.

## Framework: Hugo
As static site generator, I went for [Hugo](https://gohugo.io/). It's a solid framework, with good themes, and it's based on markdown files organized in a simple file system. To install the Hugo framework, you need to start by setting up Hugo on your machine. You can install Hugo via a package manager or download it directly. Hugo implements [themes](https://themes.gohugo.io/) to add ready made frontend to your website (or you can create a custom theme for yourself). For Hugo you can find a well known theme called Docsy, hosted on Google Github and unofficially supported, but for the purpose of this post we're going to use [Techdoc](https://github.com/thingsym/hugo-theme-techdoc), easier to manage if you're new to Hugo.

Here is a step-by-step guide to installing the Hugo framework, creating a new website, and installing Techdoc.

### Step 1: Install Hugo

For **macOS**:

```bash
brew install hugo
```

For **Linux**:

```bash
sudo apt-get install hugo
```

For **Windows**:
Download the binary from the [Hugo GitHub releases](https://github.com/gohugoio/hugo/releases) and add it to your PATH.

Once Hugo is installed, check if it’s working correctly by running:

```bash
hugo version
```

### Step 2: Create a New Website

Now that you installed Hugo, you need to create a new Hugo site by running the following command:

```bash
hugo new site my-website
```

This command will create a new folder `my-website` with the necessary Hugo folder structure.
At this point, you may want to move into the newly created website folder:

```bash
cd my-website
```

### Step 3: Install the Techdoc Theme

To install Techdoc you're going to use Git submodules. Run the following command to initialize ```git``` and to add the theme to ```themes``` folder:
```bash
git init
git submodule add https://github.com/thingsym/hugo-theme-techdoc.git themes/hugo-theme-techdoc
```

Now that the theme is installed, you will need to configure Hugo to use it at its best. Look for the [hugo.toml](https://github.com/thingsym/hugo-theme-techdoc/blob/master/exampleSite/hugo.toml) file in exampleSite folder of the theme and copy it in the root of your newly created website

Now you' re ready to launch the website using this command:

```bash
hugo server
```
   
   This will make your site available at `http://localhost:1313`. Hugo will automatically rebuild

## Repository: Github

Once your site is ready, you may want to create a repository on [Github](https://github.com) and put your website in it. This way you'll be able to easily push updates online, and - as we'll see - deploy the content.
First of all, you will create a repository on Github from your profile page, giving it a name of your choice and deciding for it to be ```public``` or ```private```. Then you'll go back to your terminal and initialize ```git``` using the commands provided from Github to connect your local repo to the online counterpart.  Git is already initalized in your folder so you won't need ```git init```

```bash
git remote add origin https://github.com/biccio/prova.git
git branch -M main
git push -u origin main
```

Now you're all set! Let's go to deployment!

## Deployment: Netlify

Netlify is a great solution to deploy a website from a variety of framework, providing a great interface to manage multiple websites and their build and deployment. Netlify offers a free starter package with **100 GB of bandwidth**, **300 build per minutes** for a single member seat.
The easiest way to create and manage a new website is *importing a new project* (other options are: *manually uploading your files* or *starting from a template*, a great solution if you need to start from scratch with backend and frontend).

### Step 1 - Create a new website importing a project

Assuming that you followed the previous steps, now you should have your content and framework stored in a repository on Github. 
1. **Create a new site**
   - Select **Add new site** → **Import an existing project**
   - Select **Github** and authenticate (or you may be already logged in)
   - Choose the repo where you stored your content
2. **Review your configuration**
   - Choose a name for your new website
   - Choose your branch (usually ``main``)
   - Leave blank *Base directory*
   - Write `hugo` as *Build Command*
   - `public` as *Publish Directory*
   - Leave default in *Functions Directory*
   - **important**: add *Hugo version* as *environmental variable*: key: `HUGO_VERSION` / value: `X.X.X` (you may find your hugo version with the terminal command `hugo version`)
   
### Step 2 - Deploy the website
Now you're ready to deploy, push the button and the magic will happen! Note that Netlify will choose for you a temporary subdomain: you'll be able to change it, or even set up a custom domain. If everything is ok, you'll be able to browse your new website in a couple of minutes!
