# bench-notes-docker-build
Bench notes for using docker build / docker hub.

```
$ sudo docker build -t technomada/basic-slides .
$ sudo docker images
$ sudo docker image rm technomada/basic-slides
$ sudo docker run -d --restart=always --name=slides --env MASTER_KEY="mk.21iqp" -p 3010:3000 technomada/basic-slides
$ sudo docker push technomada/basic-slides
```

> create a git repo

> use that git repo on docker hub.
