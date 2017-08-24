---
title: Docker on Windows
excerpt_separator: "<!--more-->"
categories:
  - Post Formats
tags:
  - Post Formats
  - readability
  - standard
---

## Jekyll / Github

Jekyll has always been a pain in the arse to get working on Windows, from installing Ruby and the million gem packages and broken builds..... Welcome Docker for Windows!

Docker allows fully contained applications to be run in an isolated container as if it was a VM except much smaller and less cpu and memory intensive. There are many containers for running lots of applications especially for Linux.

### Running standard Jekyll

One such container is for the Jekyll blogging engine uses ruby and numerous other packages.

```cs
// Create blog
docker run --rm -v="$PWD":/srv/jekyll -it -p 4000:4000 jekyll/jekyll jekyll new myblog

// Serve blog
cd myblog
docker run --rm -v="$PWD":/srv/jekyll -it -p 4000:4000 jekyll/jekyll jekyll serve
```

### Running standard Github pages

A docker image for github pages can be found at [starefossen/github-pages](https://github.com/Starefossen/docker-github-pages)

*TODO I could not get this container to work properly. Listens on the port but does not render the site?!*

```cs
docker run --rm -v="$PWD":/usr/src/app -it -p 4000:4000 starefossen/github-pages jekyll new gblog

docker run --rm -v="$PWD":/usr/src/app -it -e JEKYLL_GITHUB_TOKEN=my-github-token -p 4000:4000  starefossen/github-pages bundle exec jekyll serve
```

### Run Jekyll using the Bash shell running on Windows

If you like the feel of installing Ruby and all the other componants youself can check out bash running on Windows. You heard right Windows can now run bash shell (under the hood is Ubuntu)

[Running Jekyll on Windows](http://www.jamessturtevant.com/posts/Running-Jekyll-in-Windows-using-Docker/)

