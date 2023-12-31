**AYO: Don't get mad, you don't have to write code to modify this. This is a free static site so you might have to put a little bit of work into figuring it out; that's why it's free. You can do it! I believe in you!**

Deployment Status
| Environment | Status |
| - | - |
| [Production](https://leah.frederick.work) | [![pages-build-deployment](https://github.com/frederick-work/leah.frederick.work/actions/workflows/pages/pages-build-deployment/badge.svg)](https://github.com/frederick-work/leah.frederick.work/actions/workflows/pages/pages-build-deployment) |
| [Development](https://dev.leah.frederick.work) | [![pages-build-deployment](https://github.com/frederick-work/dev.leah.frederick.work/actions/workflows/pages/pages-build-deployment/badge.svg)](https://github.com/frederick-work/dev.leah.frederick.work/actions/workflows/pages/pages-build-deployment) |

Pending new reviews: [![GitHub issues](https://img.shields.io/github/issues/frederick-work/leah.frederick.work?label=new%20review)](https://github.com/frederick-work/leah.frederick.work/labels/new%20review)


#### Table of Contents
- [Overview](#overview)
- [Managing automated review posting system](#managing-automated-review-posting-system)
- [Editing site with Github Codespaces](#editing-site-with-github-codespaces)
- [Adding reviews](#adding-reviews)
- [Local Development](#local-development)
- [Dependencies](#dependencies)


# Overview
[This site](https://leah.frederick.work) was created using Youssef Raafat's [portfolYOU](https://github.com/YoussefRaafatNasry/portfolYOU/tree/master) Jekyll template. It's a simple, responsive, and portfolio-focused theme that's perfect for showcasing your work and skills.

Jekyll is a static site generator that allows you to create a website without having to write HTML, CSS, or JavaScript. You can learn more about Jekyll [here](https://jekyllrb.com/). It's what powers [GitHub Pages](https://pages.github.com/), which is where this site is hosted.

To modify the site you only need to be able to edit Markdown files. Markdown is a lightweight markup language that's easy to learn. You can learn more about Markdown [here](https://www.markdownguide.org/).

# Managing automated review posting system
When a new review is submitted a new issue will be created [here](https://github.com/frederick-work/leah.frederick.work/labels/new%20review). If you want to approve the review, add the `review approved` label to the issue , remove the `new review` label, and close it. The site will automatically be updated with the new review.

## Links
- [Google Apps Script](https://script.google.com/u/0/home/projects/1d4EQ3b3rAjj-Cck1z3Dcpx1PPvBXL31UNmqbPED-lQP6UilWwFsgbrPu/edit)
- [Google Sheets Review Database](https://docs.google.com/spreadsheets/d/1bS30eDES4LTxzarj2mK8ARuiLirTPhnQS_0Q1X7Vx1c/edit?resourcekey#gid=2048581759)
- [Google Forms Review Submission](https://docs.google.com/forms/d/1Ml41FKG77zkvw9xZtzm_5_Iw7TH4JYvEDQjfFxu4ER4/edit)

# Editing site with Github Codespaces
1. If you don't have an active codespace, create one [here](https://github.com/codespaces/new?hide_repo_select=true&ref=development&repo=669187073&skip_quickstart=true&machine=basicLinux32gb&geo=UsEast).
2. Open the codespace in your browser.
3. Make your changes.
4. Commit and push your changes to Github:
```bash
git add .
git commit -m "describe your changes here"
git push
```

This will deploy the site to [dev.leah.frederick.work](https://dev.leah.frederick.work/). If you're happy with your changes, create a pull request [here](https://github.com/frederick-work/leah.frederick.work/compare/master...frederick-work:leah.frederick.work:development) to merge your changes into the master branch. Once this is completed the site will be redeployed to [leah.frederick.work](https://leah.frederick.work/).

# Adding reviews manually

To add a review, copy the following text and paste it in a new file in the `_posts` directory. The name of the file should be in the format `YYYY-MM-DD-review-title.md`. For example, `2021-04-27-date-night-savior.md`. You can then customize the content to your liking.

```markdown
---
title: "Leah's Babysitting Services: Making Date Nights Stress-Free and Fun!"
tags: [Babysitting]
style: border
color: info
description: Looking for a reliable and caring babysitter to enjoy those much-needed date nights with your spouse? Look no further than Leah's Babysitting Services!
---

I can't speak highly enough of Leah's babysitting services! My husband and I have been using her help for our date nights twice a month, and she has been an absolute lifesaver. Leah is not only incredibly reliable and punctual, but her genuine love and care for our children are evident from the moment she walks through the door.

blah blah bla...
```

The information between the --- is called the front matter. It contains the information that will be displayed on the review card. The information below the --- is the review content. You can add as much content as you like.

Once you've added the review, you'll need to commit and push the changes to GitHub. You can do this by running the following commands in a bash shell.
```bash
# add the new file to the staging area
git add _posts/<your-post-name-here>.md

# commit the changes
git commit -m "added new review"

# push the changes to GitHub
git push
```

This will trigger [this Github action](https://github.com/frederick-work/leah.frederick.work/actions/workflows/pages/pages-build-deployment) that will update the live site at [leah.frederick.work](https://leah.frederick.work/).

# Local Development

To run the site locally, run the following commands in a bash shell. You'll need to install [the dependencies](#dependencies) first.
```bash
# clone the repository to your local machine
git clone git@github.com:frederick-work/leah.frederick.work.git 
cd leah.frederick.work

# open VS Code in the current directory
code .

# -- run these in the VS Code terminal --
# install dependencies
bundle install

# run site locally with hot reload at localhost:4000
bundle exec jekyll serve --livereload
```
The site should now be running at [localhost:4000](http://localhost:4000/).

Check out [this template's documentation](https://youssefraafatnasry.github.io/portfolYOU/docs/) if you want to customize the site beyond [adding a review](#adding-reviews).

# Dependencies

To run this site locally, you'll need to install the following dependencies:
- [Git](https://git-scm.com/downloads) - Source control for the code that makes up the site
- [Ruby](https://www.ruby-lang.org/en/downloads/) - The runtime environment for the site (Programming language that you don't need to know)
- [RubyGems](https://rubygems.org/pages/download) - Ruby's package manager
- [Bundler](https://bundler.io/) - A dependency manager for Ruby

You'll probably also want to install a text editor or IDE. I recommend [Visual Studio Code](https://code.visualstudio.com/).

You can use the bash shell that's included with the [Git for Windows](https://gitforwindows.org/) installation to run [the commands above to run the site locally](#local-development). In order to push code to Github to update the live site, you'll need to [add an SSH key to your Github account](https://docs.github.com/en/authentication/connecting-to-github-with-ssh/adding-a-new-ssh-key-to-your-github-account).