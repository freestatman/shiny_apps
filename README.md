
<!-- README.md is generated from README.Rmd. Please edit that file -->
My web applications <img src="http://logo-logos.com/wp-content/uploads/2016/10/Docker_logo_logotype.png" width=100 align="right" /> <img src="https://www.rstudio.com/wp-content/uploads/2014/04/shiny.png" width=100 align="right" /> <img src="http://www.unixstickers.com/image/cache/data/stickers/flask/Flask-text.sh-180x180.png" width=100 align="right" />
==================================================================================================================================================================================================================================================================================================================================================================

This repo contains code for building and deploying [web applications](https://en.wikipedia.org/wiki/Web_application) (e.g. [shiny](https://cran.r-project.org/package=shiny), [fiery](https://cran.r-project.org/package=fiery), and [flask](http://flask.pocoo.org/)) that I've developed for public consumption.

Run a single application
------------------------

Each app has it's own [Docker](https://www.docker.com/) container, as well as a [image tag on DockerHub](https://hub.docker.com/r/cpsievert/apps/builds/), so you can easily run apps on your local machine; for example, this will run the [zikar (shiny) app]() on <http://localhost:3838>

``` shell
docker run -p 3838:3838 cpsievert/apps:shiny-zikar
```

If you'd like to run a different app, you can get the image tag from the [`application.yml`](https://github.com/cpsievert/apps/blob/master/application.yml) file.

Run all the applications
------------------------

To run all the applications, a necessary first step is to build/pull all the docker images

``` shell
git clone https://github.com/cpsievert/apps.git
cd apps
make
```

The [`application.yml`](https://github.com/cpsievert/apps/blob/master/application.yml) can be used/modified to (securely) run all the applications as a service via [shinyproxy](https://www.shinyproxy.io/). See my blog post (coming soon)

``` shell
wget https://www.shinyproxy.io/downloads/shinyproxy-1.0.1.jar
wget https://raw.githubusercontent.com/cpsievert/apps/master/application.yml
java -jar shinyproxy-1.0.1.jar
```

Contributing
------------

Some notes on how to add an application:
