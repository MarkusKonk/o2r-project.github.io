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

The most prominent effort in this area, the **Rocker-project**, was initiated by Dirk Eddelbuettel and Carl Boettiger. For an introduction, you may read their blog post [here](http://dirk.eddelbuettel.com/blog/2014/10/23/) or follow [this tutorial](http://ropenscilabs.github.io/r-docker-tutorial/) from rOpenSci. With a big choice of pre-build docker images, Rocker provides optimal solutions for those who want to run R from Docker containers. Explore it on [Github](https://github.com/rocker-org/) or [Docker Hub](https://hub.docker.com/u/rocker/), and soon you will find out that it takes just one single command to run instances of either [base R](https://hub.docker.com/r/rocker/r-base/), [R-devel](https://hub.docker.com/r/rocker/r-devel/) or [Rstudio Server](https://hub.docker.com/r/rocker/rstudio/). Moreover, you can run [previous versions of R](https://hub.docker.com/r/rocker/r-versioned/) or use one of the bundles with commonly used R packages and other software (e.g. bundles going back to [Hedley Wikham](https://hub.docker.com/r/rocker/hadleyverse/) and [rOpenSci](https://hub.docker.com/r/rocker/ropensci/)).
If you come from Bioinformatics or neighboring disciplines, you might be delighted that **Bioconductor** provides own R package bundles based on Rocker's images (see the [help page](http://bioconductor.org/help/docker/), [GitHub](https://github.com/Bioconductor/bioc_docker), and [Open Hub](https://hub.docker.com/u/bioconductor/) presences).

So why, apart from the incredibly easy and fast installation of R bundles, would you *really* want to combine R with Docker? Ben Marwick, Associate Professor at the University of Washington, explains in [this presentation](https://benmarwick.github.io/UW-eScience-docker-for-reproducible-research/) that it helps you manage dependencies. It gives a computational environment that is isolated from the host, and at the same time transparent, portable, extendable and reusable. Marwick uses Docker and R for **reproducible research** and thus bundles up his works to **research compendia**; an instance is available [here](https://github.com/benmarwick/1989-excavation-report-Madjebebe), and a template [here](https://github.com/benmarwick/researchcompendium).

The R package [**dockertest**](https://github.com/traitecoevo/dockertest) makes particular use of the isolated environment that Docker provides: R programmers can set up test environments for their R packages and R projects, in wich they can rapidly test their works on Docker containers that only contain R and the relevant dependencies. 

The platform [**R-hub**](https://github.com/r-hub) supports R programmers throughout the development process of a package and them solving issues prior to the submission of a package to CRAN. In particular, it provides services that build packages on all CRAN-supported platforms and checks them against the latest R release. The backends that perform regular builds also use Docker container - you can find details in the [project proposal](https://github.com/r-hub/proposal).


