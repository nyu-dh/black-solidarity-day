# Black Solidarity Day [![Build Status](https://travis-ci.com/nyu-dss/black-solidarity-day.svg?branch=main)](https://travis-ci.com/nyu-dss/black-solidarity-day)

## Prerequisites 
- [Git](https://git-scm.com/book/en/v2/Getting-Started-Installing-Git)
- [Docker](https://docs.docker.com/get-docker/)

## Serve locally using Docker

To use Wax in a container, make sure you are familiar with Docker and have [Docker installed](https://docs.docker.com/get-docker/).

1. Clone the repo and change directory into it 
```
$ cd ~/Desktop
$ git clone https://github.com/nyu-dss/black-solidarity-day.git
$ cd black-solidarity-day
```

2. Next, build the `wax_image` base image:
```
$ docker build -t ubuntu/wax .
```

3. You will run all of the Wax tasks and commands within an interactive bash container, which you can create and access by running:
```
$ docker run -it --rm -v "$PWD":/wax --name wax -p 4000:4000 ubuntu/wax bash
```

4. To serve the site, you can run the following command in the guest container and view it in your host browser:
```
$ bundle exec jekyll serve --host 0.0.0.0 --verbose
```

You can exit the container at any time with `$ exit`, which will automatically stop and remove the container.
