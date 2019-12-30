---
layout: post
title:  "Mongo with Docker and seed"
date:   2019-12-29 10:50:20
comments: true
categories: mongo
image: https://upload.wikimedia.org/wikipedia/commons/9/93/MongoDB_Logo.svg
---

Create a Json file with your document

```json
[
  {
    "name": "Kevin Martins",
    "birthday": "29 April , 1995",
    "nick": "Red King",
    "age": 24
  },
  {
    "name": "Kauan Martins",
    "birthday": "02 July , 2008",
    "nick": "Red as Floid",
    "age": 10
  }
]
```

Create a Dockerfile and copy your Json file

```
FROM mongo

COPY init.json /init.json
CMD mongoimport --host mongo --db reach-engine --collection users --type json --file /init.json --jsonArray
```

Create a docker-compose.yml and build your Dockerfile

```yml
version: '3'
services:
  mongo:
    image: mongo:latest
    ports:
      - "27017:27017"
    volumes:
      - ./data/db:/data/db
  mongo-seed:
    build: ./mongo-seed
    links:
      - mongo
```