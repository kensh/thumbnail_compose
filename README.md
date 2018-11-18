# thumbnail_compose
thumbnail_compose


* Written in Node.js

* Automated tests
```bash
$ cd thumbnail_web
$ npm test
```

* Docker 

You can run the app either 

```bash
$ docker-compose up
```
or

```bash
$ docker swarm init
$ docker stack deploy --compose-file docker-compose.yml thumbnail
```

---

# Description

### Web Server

* install

```
$ npm install express --save
$ vi app.js
$ node app.js
```

* fileupload

```
$ npm install multer --save
$ npm install path --save
$ npm install amqplib --save
```

* datastore

```
$ npm install redis --save
```

* docker

```
$ docker build ./ -t kensh/thumbnail_web:0.1
```


### Worker

* imagemagick https://github.com/rsms/node-imagemagick

```
iinstall on host
$ brew install imagemagick

ex)
$ convert sample.jpg -resize 100x100 sample.png
```

```
install on node
$ npm install imagemagick --save
```

* subscriber

```
$ ln -s ../thumbnail_web/upload/ ./upload
$ npm init
$ npm install amqplib --save
```

* datastore

```
$ npm install redis --save
```

* docker

```
$ docker build ./ -t kensh/thumbnail_worker:0.1
```
