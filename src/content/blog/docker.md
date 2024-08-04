---
title: Docker
author: kobejk
pubDatetime: 2024-08-04
featured: false
draft: false
tags:
  - development
description: An intro to docker.
---

## Table of Contents

## Docker

Docker is the number 1 tool development tool. It helps developers build applications without configuration or environment setup.

It removes the "well, it works on my machine" problem many face when sharing code/dependencies.

### Containers

Docker uses containers. A container is a process running on a computer that is separate or isolated from all other processes.

They leverage software like `kernel namespaces and cgroups` available within the Linux operating system.

### Images

Containers run on filesystems provided by an image. These are configurations of everything needed to run an application including:

- the filesystem
- dependencies
- configurations
- scripts

and more.

Multiple containers can be "spun up" from a single image.

### Installation

Docker is made up of multiple components. The easiest way to install Docker is to run [Docker Desktop](https://docs.docker.com/desktop/).

This is a "batteries included" GUI program that enables users to run containers.

### Dockerfile

Everything in Docker runs off a single `Dockerfile`. This is the default filename and does not have an extension. Using this name allows you to run the `docker build` command without having to specify additional command flags.

This file contains instructions on how to build images.

The basic format is:

```dockerfile
# Comment
INSTRUCTION arguments
```

## Workflow

Below is a small Flask code snippet:

```python
from flask import Flask
app = Flask(__name__)

@app.route("/")
def hello():
    return "Hello World!"
```

To run this code, you would need to:

- install multiple different dependencies
- install python correctly
- make sure the correct versions of the software are installed
- the server starts your app

That's a lot of work.

This sample `Dockerfile` creates a container image with everything needed to run the app.

```dockerfile
# syntax=docker/dockerfile:1
FROM ubuntu:22.04

# install app dependencies
RUN apt-get update && apt-get install -y python3 python3-pip
RUN pip install flask==3.0.*

# install app
COPY hello.py /

# final configuration
ENV FLASK_APP=hello
EXPOSE 8000
CMD ["flask", "run", "--host", "0.0.0.0", "--port", "8000"]
```

To build the container, you would run the following command:

```bash
docker build -t test:latest .
```

And to run the container:

```bash
docker run -p 127.0.0.1:8000:8000 test:latest
```

This maps the container's port 8000 to http://localhost:8000 on the server.

## Resources

- https://www.docker.com/
- https://docs.docker.com/guides/docker-overview/
- https://docs.docker.com/reference/dockerfile/
- https://docs.docker.com/build/building/packaging/
