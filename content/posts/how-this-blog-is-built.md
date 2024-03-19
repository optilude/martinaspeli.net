+++
title = "How this blog is built"
date = 2024-03-19T21:03:00.000Z
draft = false
+++
This blog is hosted for free using [GitHub](https://github.com) Pages, [Hugo,](https://gohugo.io) and the free tier of [CloudCannon](https://cloudcannon.com) CMS. Everything was built and configured in the browser. Here are some instructions for how to set up something similar.

## Creating a Hugo site on GitHub

First, create an account (if necessary) and then a new repository on [GitHub,](https://github.com) initially with an empty [README.md](http://README.md) file.

Then, create a new Codespace on GitHub based on this repository. We’ll use this as a virtual machine to run Hugo locally and get the basic site set up. A Codespace is like a Visual Studio Code editor in the browser with a builtin terminal that runs on a small local machine. You need only the most basic VM for these purposes, and we’ll not need it for long.

The [instructions for creating a new Hugo site](https://gohugo.io/getting-started/quick-start/) should apply, and Hugo ought to be already installed in the Codespaces environment. So open a new terminal inside the Codespaces editor (if not open already) and it should already be in the folder for your repository. Then run:

```
$ hugo new site --force .
```

This will create a new site. Next install a theme. I used the [Anatole](https://themes.gohugo.io/themes/anatole/)one. **Note**: Using git “submodules” might not work reliably with Cloudcannon, so it is likely better to install a theme using Hugo modules. For Anatole this was done with:

```
$ hugo mod init github.com/<username>/<repository>
$ hugo mod get github.com/lxndrblz/anatole
```

Next edit `hugo.toml` to add the theme, per the instructions for the theme:

```
[module]
  [[module.imports]]
    path = "github.com/lxndrblz/anatole"
    disable = false

theme = "anatole"
```

Create a first post:

```
$ hugo new content posts/my-first-post.md
```

Create a `.gitignore` file at the root of the repository to avoid committing the built file to Git:

```
public/
.hugo_build.lock
```

Then commit and push the changes. You can now shut down the Codespaces virtual machine.

## Setting up GitHub Pages hosting

[This guide](https://gohugo.io/hosting-and-deployment/hosting-on-github/)contains the basic instructions. Essentially, you will set up Pages hosting for your repository, and use a workflow in GitHub Actions to trigger a Hugo build each time there is a change to the repository.

You can trigger the build manually under GitHub’s Actions screens to create the site. The GitHub Pages documentation and guidance on the Settings screens provide further information.

## Setting up CloudCannon as a CMS

You can now create new content and deploy your site entirely in GitHub using its web interface or the github.dev editor (which is like Codespaces just without the attached terminal and virtual machine), or offline with a git client. Each time you commit and push a change, the workflow should rebuild your site and deploy it within a minute or two.

However, you can go one better using CloudCannon as a CMS. There is a free personal tier if you only need a single user, and paid tiers with more power. CloudCannon [natively supports Hugo](https://cloudcannon.com/hugo-cms/) and understands its structure.

The basic approach is:

* Log into CloudCannon, perhaps using GitHub as a login provider
* Connect CloudCannon to GitHub under Settings -&gt; Org Settings
* Create a new Site in CloudCannon that is linked to the repository you used earlier. CloudCannon will guide you through picking a repository and branch and link things up. Afterwards you can find this in Site Settings -&gt; Source Syncing.
* CloudCannon will locally build a test version of your site by running its own version of Hugo, and deploy it to a test URL for you. This is not the same as GitHub Pages, which has its own build triggers. It is possible to use CloudCannon as your deployment and hosting solution, too, but my preference is to keep this inside GitHub Pages and Actions and only use CloudCannon for editing and preview.
* You can now find and edit your first post in the CloudCannon CMS, or add new content.. When saved, it will push data to GitHub, which will trigger your build there (as well as the preview build in CloudCannon itself), updating your deployed site.