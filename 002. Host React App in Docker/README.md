# Docker Simple Commands 

> hello-docker 
```cmd
FROM node:20-alpine

WORKDIR /app

COPY . . 

CMD node index.js
```

### ⚡ Build docker from app 

```cmd
docker build -t docker-image-name .
```

### ⚡ to check images 

```cmd
docker images
```

### ⚡ run 

```cmd
docker run -it docker-image-name
```

### ⚡ run in shell

```cmd
docker run -it docker-image-name sh
```

---

## ⭐ React app in docker 

1. install vite + react in local machine 

```cmd
npm create vite@latest
```

2. create dockerfile in folder 

3. add this commands 

```cmd
FROM node:20-alpine

WORKDIR /app

COPY package*.json ./

RUN npm install 

COPY . . 

EXPOSE 5173

CMD npm run dev
```

4. in packages json change this scripts `--host`

```cmd
"scripts": {
    "dev": "vite --host",             <---- add "--host"
    "build": "vite build",
    "lint": "eslint .",
    "preview": "vite preview"
  },
```

5. export this one in `vite.config.js`

```js
import { defineConfig } from 'vite'
import react from '@vitejs/plugin-react'

// https://vite.dev/config/
export default defineConfig({
  plugins: [react()],
  server: {              <-------
    watch: {
      usePolling: true,
    },
    host: true,
    port: 5173
  }
})                       <--------

```

6. build this app


```cmd
docker build -t react-docker . 
```

7. run the docker app in `powershell`

open powershell

```cmd
docker run -p 5173:5173 -v "${pwd}:/app" -v /app/node_modules react-docker
```


---


# 🐋 How to publish docker image 

#### 1. docker login 

```cmd
docker login
```

### 2. tag

```cmd
docker tag react-docker itisameerkhan/react-docker-2
```

### 3. push 

```cmd
docker push itisameerkhan/react-docker-2
```


---


# 🐋 DOCKER COMPOSE 

#### 1. docker init

```cmd
docker init
```

#### 2. add this in `compose.yaml`

```cmd
services:
  web:
    build:
      context: .
    ports:
      - 5173:5173
    volumes:
      - .:/app
      - /app/node_modules 
```

