---
layout: post
title: Investigating Docker and R
categories:
  - introduction
  - overview
  - R
  - Docker
---

Docker and R, how does it combine? That is the question that we asked ourself in recent weeks. In this post, we are going to share our insights with you.

The most prominent effort in this area, the **Rocker-project**, was initiated by Dirk Eddelbuettel and Carl Boettiger. For an introduction, you may read their blog post [here](http://dirk.eddelbuettel.com/blog/2014/10/23/) or follow [this tutorial](http://ropenscilabs.github.io/r-docker-tutorial/) from rOpenSci. With a big choice of pre-build Docker images, Rocker provides optimal solutions for those who want to run R from Docker containers. Explore it on [Github](https://github.com/rocker-org/) or [Docker Hub](https://hub.docker.com/u/rocker/), and soon you will find out that it takes just one single command to run instances of either [base R](https://hub.docker.com/r/rocker/r-base/), [R-devel](https://hub.docker.com/r/rocker/r-devel/) or [Rstudio Server](https://hub.docker.com/r/rocker/rstudio/). Moreover, you can run [previous versions of R](https://hub.docker.com/r/rocker/r-versioned/) or use one of the bundles with commonly used R packages and other software (e.g. bundles going back to [Hedley Wikham](https://hub.docker.com/r/rocker/hadleyverse/) and [rOpenSci](https://hub.docker.com/r/rocker/ropensci/)).
If you come from Bioinformatics or neighboring disciplines, you might be delighted that [**Bioconductor**](http://bioconductor.org/) provides own R package bundles based on Rocker's images (see the [help page](http://bioconductor.org/help/docker/), [GitHub](https://github.com/Bioconductor/bioc_docker), and [Open Hub](https://hub.docker.com/u/bioconductor/) presences).

So why, apart from the incredibly easy and fast installation of R bundles, would you *really* want to combine R with Docker? Ben Marwick, Associate Professor at the University of Washington, explains in [this presentation](https://benmarwick.github.io/UW-eScience-docker-for-reproducible-research/) that it helps you manage dependencies. It gives a computational environment that is isolated from the host, and at the same time transparent, portable, extendable and reusable. Marwick uses Docker and R for **reproducible research** and thus bundles up his works to *Research Compendia*; an instance is available [here](https://github.com/benmarwick/1989-excavation-report-Madjebebe), and a template [here](https://github.com/benmarwick/researchcompendium).

The R package [**dockertest**](https://github.com/traitecoevo/dockertest) makes particular use of the isolated environment that Docker provides: R programmers can set up test environments for their R packages and R projects, in wich they can rapidly test their works on Docker containers that only contain R and the relevant dependencies.

Some works are dedicated to *dockerizing* R extensions. The liftr (REF) package for R help lets users enhance Rmd files with YAML-metadata, wich enables rendering R Markdown documents in Docker containers. Liftr also supports  [Rabix](https://www.rabix.org/), a Docker-based toolkit for portable bioinformatics workflows. That means that users can have Rabix workflows run inside the container and have the results integrated directly into the final document. Another extension you may want to *dockerize* is Shiny. Flavio Barros dedicated two articles on R-bloggers to this topic: [Dockerizing a Shiny App](https://www.r-bloggers.com/dockerizing-a-shiny-app/) and [Share Shiny apps with Docker and Kitematic](https://www.r-bloggers.com/share-your-shiny-apps-with-docker-and-kitematic/).

Rather than running R inside Docker containers, it can be beneficial to call Docker containers from inside R. This is what the packages RSelenium and googleComputeEnginer do. [**Selenium**](http://www.seleniumhq.org/) provides tools for browser automation, which are also [available as Docker images](https://hub.docker.com/u/selenium/). They can be used, amongst others, for testing web applications or controlling a headless web browser from your favorite programming language..In this tutorial, you can see how and why you should use RSelenium to interact with your Selenium containers. 
[**googleComputeEnginer** provides an R interface to the Google Cloud Compute Engine API. It includes a function called _docker_run that starts a Docker container in a Google Cloud VM and executes R code in it. Read this article for details and examples. googleComputeEngineR usees functions from the **harbor package** for R. You should have a look at it, because it may help you to control your own Docker containers that run either locally or in remote.

The platform [**R-hub**](https://github.com/r-hub) supports R programmers throughout the development process of a package and them solving issues prior to the submission of a package to CRAN. In particular, it provides services that build packages on all CRAN-supported platforms and checks them against the latest R release. The backends that perform regular builds also use Docker container. Read the [project proposal](https://github.com/r-hub/proposal) for details.



