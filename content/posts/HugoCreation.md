HugoCreation.md

---
title: "Creating This Website Using Hugo on Windows 10"
date: 2021-02-28T13:04:04+05:30
tags: ["Hugo", "website", "golang", "coding", "windows 10"]
author: "Me"
# author: ["Me", "You"] # multiple authors
showToc: true
TocOpen: false
draft: false
hidemeta: false
comments: false
#description: "Trying to make Frankin work on Windows 10"
#disableHLJS: true # to disable highlightjs
disableShare: false
disableHLJS: false
searchHidden: false
cover:
    image: "<image path/url>" # image path/url
    alt: "<alt text>" # alt text
    caption: "<text>" # display caption under cover
    relative: false # when using page bundles set this to true
    hidden: true # only hide on current single page
---



This post describes the creation process of this website. I have used the popular static site generator [Hugo](https://gohugo.io/). Hugo is based on the language *go*. Disclaimer: this is the second time I am creating my website using Hugo. But the last time I created this was in 2015, so a lot has changed.

## Installing Hugo on Windows 10
My recommendation is to use [Chocolatey](https://chocolatey.org/) to install Hugo although there are binaries available at [github](https://github.com/gohugoio/hugo/releases) for direct installation. If Chocolatey is installed on your system, open powershell by right clicking the start button. There type

```
chococ install hugo
```

to install Hugo. Now are ready to use Hugo commands from the powershell. To check if the installtion went well type `hugo version`. It will display the current version of Hugo.

## Using Hugo

One way to quickly learn how to use Hugo is to follow the [quickstart guide](https://gohugo.io/getting-started/quick-start/) over at the Hugo website. There is one problem, with the echo command, I encountered while applying it on Windows 10. For completeness I will describe all the steps involved.

We begin by creating a directory with the necessary structure for our website. I stated by creating a practice folder called quickstart using

```
hugo new site quickstart
```
Then type
```
cd quickstart
```
to move into the newly created directory.

Next we add a theme to our website. We will add the Ananke theme using git.

```
git init
git submodule add https://github.com/budparr/gohugo-theme-ananke.git themes/ananke
```
More themes are available at [themes.hugo.io](https://themes.gohugo.io/). If you don't have *git* installed you can also download the themes from there, and extract the compressed folder into the themes folder in your site's directory. Using [*git*](https://git-scm.com/downloads) is higly recommended.

Take a look in the `themes` folder in your site's directory. There should be a folder named `ananke` inside. Go back to the `quickstart` directory and open the `config.toml` file in your faourite text editor. I am using [Atom](). Add
```
theme = "ananke"
```
to the end of your config file.

Now your website is essentially ready. Let's add our first post. Type the following command on the powershell

```
hugo new posts/my-first-post.md
```
This will create a markdownfile named `my-first-post.md` in the `content>posts`. Open it in a text editor. You will notice that the file already contains the following:
```
---
title: "My First Post"
date: 2021-02-27T16:42:29+05:30
draft: true
---
```
The `title` is going to be the title of your blog post, `date` is the time when your file was created, and 'draft' represents whether or no your post is published. Change `draft` to false when you are happy with the content.

Even when `draft` is set to true, you can see how it will look on you website by typing the folloing in the powershell.

```
hugo server -D
```

**image**

Click on the link displayed to see the current status of your website. Make your changes. Once you are happy with your changes, build your site by typing the following in your powershell
```
hugo
```
Your website is published in the `public` folder in your website directory.

## Creating your Website
