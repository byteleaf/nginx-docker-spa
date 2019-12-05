# Nginx docker image for a SPA (Single page application)

## Introduction

To run a SPA (single page application) like a normal angular or react
app you need to configure your nginx.

Static files should be resolved normally like
**_http://localhost:7000/favicon.ico_** or
**_http://localhost:7001/main.94e6abcc6275689efbf2.js_**

All routes should be redirected (if no static file for this route was
found) to the **_index.html_** of the SPA. Examples are routes like
**_http://localhost:7000_** or **_http://localhost:7000/start_**. The
angular router is resolving the route internal!! Be careful if some
static file won't be found, for example a image, the nginx config will
return the index.html!!

## Explanation

+ the **_/content_** folder contains the SPA, in this example its a simple angular 7 application

+ the **_/conf_** folder contains the nginx configuration

## How to run with docker

Open cmd in the root level of the project:

+ Build the docker image

    >docker image build -t nginx-docker-spa .

+ Take a look at your local docker images

    >docker images

+ Create & start a container

    >docker container run -p 7000:80 nginx-docker-spa
 
 + You can run app in your browser via **_http://loclahost:7000_**
