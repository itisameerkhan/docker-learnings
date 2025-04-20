# What is Docker 

![demo](https://www.docker.com/app/uploads/2023/08/logo-guide-logos-1.svg)

Docker is a platform that lets you package up your app — along with everything it needs to run (code, dependencies, configs) — into a container.

Think of a container like a mini virtual machine — but lighter, faster, and made just for your app.

Docker is a set of platform as a service products that use OS-level virtualisation to deliver software in packages called containers. Containers are isolated from one another and bundle their own software, libraries and configuration files; they can communicate with each other through well-defined channels. All containers are run by a single operating-system kernel and are thus more lightweight than virtual machines.

## ⭐ Why Use Docker?

*  "It works on my machine" problem — solved.

* Run apps consistently across dev, staging, prod.

* No more “install Node, Mongo, Python…” — it’s all inside the container.

* Spin up/down environments fast — clean and disposable.


## ⭐ Key concepts 

### ⚡ Image

* A snapshot of your app and its environment. Built from a Dockerfile.

* Like a template.

### ⚡ Container 

* A running instance of an image.

* Like a live, isolated mini computer for your app.


### ⚡ Dockerfile 

* A script with instructions to build your image.

```
Copy
Edit
FROM node:18
WORKDIR /app
COPY . .
RUN npm install
CMD ["npm", "start"]
```

### ⚡ Docker Hub 🌐

A registry (like GitHub for images) where you can push/pull images.


## ⭐ Container 

A container is a lightweight, portable, isolated environment that runs your application and everything it needs to work — like the code, libraries, dependencies, environment variables, and even runtime (Node, Python, etc.).

You can think of a container as a box where you put your app, zip it up with everything it depends on, and send it to any computer or server. That computer doesn’t need to have Node, MongoDB, Python, or anything installed — just Docker. Once the box (container) is opened, your app runs exactly the same everywhere.


-- 