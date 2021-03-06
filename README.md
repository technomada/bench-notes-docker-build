# Bench Notes: Docker Build
Bench notes for using docker build / docker hub.



```
$ cd ~/dev/basic-slides
$ sudo docker build -t technomada/basic-slides .
$ sudo docker images
$ sudo docker image rm technomada/basic-slides
$ sudo docker run -d --restart=always --name=slides --env MASTER_KEY="mk.21iqp" -p 3010:3000 technomada/basic-slides
$ sudo docker push technomada/basic-slides
```
> create a git repo

> use that git repo on docker hub.

FROM DOCKER HUB... automate building on master git changes.
* select repo > builds > configure automated builds
* BUILD RULES +
* Save and Build

see Builds for progress (can take minutes)

Dockerfile
```
FROM node:14

WORKDIR /usr/src/app

COPY package*.json ./

RUN npm install

COPY . .

EXPOSE 3000

CMD ["node","server.js"]
```

.dockerignore
```
node_modules
npm-debug.log
```

### notes:
when you test pull you should see `Unable to find image 'technomada/basic-slides:latest' locally` otherwise you may be pulling from your local image cache.
