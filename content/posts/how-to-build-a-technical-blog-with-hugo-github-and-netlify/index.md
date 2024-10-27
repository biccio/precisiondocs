---
title: How to Build and Deploy a Blog with Hugo, Github and Netlify
date: 2024-09-30
summary: Hugo is a powerful static site generator functioning as a complete framework. Along with Github as storage repository and Netlify as deployment tool, it makes a perfect platform to run and mantain a fast and lightweight documentation website.
---
## Introduction
Static site generation is a very popular solution in today's publishing environments, especially for technical documentation. The available frameworks are solid and easy to use, and the resulting website is blazing fast with no hiccups and zero render time. If you add Github to the workflow as a storage solution, and Netlify as deployment framework, you have a perfect solution to a fast and clean publishing process.
In this article, I'll describe all the steps I've taken to bring Precisiondocs online, and how I maintain the content in my publishing process.

## Framework: Hugo
As static site generator, I went for [Hugo](https://gohugo.io/). It's a solid framework, with good themes, and it's based on markdown files organized in a simple file system. To install the Hugo framework, you need to start by setting up Hugo on your machine. You can install Hugo via a package manager or download it directly

Here is a step-by-step guide to installing the Hugo framework, creating a new website, and installing the [Anubis2 theme](https://github.com/Junyi-99/hugo-theme-anubis2), the one I chose for this website.
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

### Step 3: Install the Anubis2 Theme
In any Hugo installation you will need to add a *theme* to provide a layout and a presentation layer  to your content. In my case I chose Anubis2. You can install this theme (as any other) using Git. Run the following command to add it as a submodule:
```bash
git init
git submodule add https://github.com/Mitrichius/hugo-theme-anubis.git themes/anubis2
```

Now that the theme is installed, you will need to let Hugo know. Look in the root for a file called `config.toml` file and add the following line to specify the Anubis2 theme:

```toml
theme = "anubis2"
```

Now you' re ready to launch the website using this command:

```bash
hugo server
```
   
   This will make your site available at `http://localhost:1313`. Hugo will automatically rebuild
## Repository: Github
Once your site is ready, you may want to create a repository on [Github](https://github.com) and put your website in it. This way you'll be able to easily push updates online, and - as we'll see - deploy the content.
First of all, you will create a repository on Github from your profile page, giving it a name of your choice and deciding for it to be ```public``` or ```private```. Then you'll go back to your terminal and initialize ```git``` using the commands provided from Github to connect your local repo to the online counterpart. 

```bash
git init
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
