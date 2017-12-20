---
title: "Wiki Editing"
date: 2017-12-19T11:13:10Z
draft: true
---

This document describes how to edit the project wiki (this site), it is intended for those who contribute to Polydigital projects and want to post public information about their work.

## Summary

* We publish this site to [Github Pages](https://pages.github.com/), essentially we are using github to host our static site.  
* We generate the site using [Hugo](https://gohugo.io/) that builds Markdown into our static site.
* We use Github to maintain versions of both our [markdown source](https://github.com/polydigital/polydigital.githubpages) and for the [public generated site.](https://github.com/polydigital/polydigital.github.io)
* This guide describes how to create/edit new content, build the site locally and publish it to the web.  For more info on that read the [Hugo docs.](https://gohugo.io/documentation/)

## Set Up Local Machine

* [Install Hugo](https://gohugo.io/getting-started/installing/) which is used for site generation
* Clone the git repo that has all the source content in it:

~~~
$ git clone https://github.com/polydigital/polydigital.githubpages.git
~~~

* Change into the working (cloned) directory
* Create a new content item:

~~~
$ hugo new team/about-tom-broughton.md
~~~

* This will create a new markdown file in the content directory
* The path/filename will be represented like this in the public site once built
* Edit the newly created file and save
* In the root of the cloned dir run a hugo server locally with the build drafts flag

~~~
$ hugo server --buildDrafts
~~~

* Browse to the URL for the server specified in the terminal
* Add on the path and name of file (without the .md file extension) to preview content
* Any saved updates to content will immediately be reflected in the browser
* when happy with changes/edit commit changes to git and push to repo

~~~
$ git add team/about-tom-broughton.md
$ git commit -m "created content page: about tom broughton"
$ git push origin master
~~~

## Publishing

* To generate static site with new content first remove the draft:true flag at the top of the markdown and commit and push the change to the source repo
* Change directory to public and add all changes to git, commit and push to origin master

~~~
$ cd public
$ git add --all
$ git commit -m "publishing new page: about tom broughton"
$ git push origin master
$ cd ..
~~~
