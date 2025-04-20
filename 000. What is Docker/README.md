# What is Docker 

![demo](https://miro.medium.com/v2/resize:fit:1000/0*DEOunKcbHW0dRlS5)


## ⚡ `FROM`

The `FROM` directive specifies the base image for your Docker image. Every Dockerfile must start with a `FROM` instruction

* FROM is the starting point of your image.

* It inherits everything from the base image.

```
FROM <image>[:<tag>] [AS <name>]
```

```
FROM node:18
FROM ubuntu:20.04
FROM python:3.11-slim
```

## ⚡ `WORKDIR`

`WORKDIR` sets the working directory inside the Docker image for any following `RUN`, `CMD`, `COPY`, `ADD`, or `ENTRYPOINT` instructions.