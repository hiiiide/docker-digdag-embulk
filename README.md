# docker-digdag-embulk
An Alpine Linux based ETL workflow container.

![dockeri.co](http://dockeri.co/image/exelexe/docker-digdag-embulk)

## Docker Tags

- [`0.1.0-ruby2.6-alpine3.9`, `latest`](https://github.com/exelexe/docker-digdag-embulk/blob/master/0.1.0/ruby2.6-alpine3.9/Dockerfile)
- [`0.1.0-alpine3.9`](https://github.com/exelexe/docker-digdag-embulk/blob/master/0.1.0/alpine3.9/Dockerfile)
- [`0.0.0-alpine3.8`](https://github.com/exelexe/docker-digdag-embulk/blob/master/0.0.0/alpine3.8/Dockerfile)


## How to use.

```
FROM exelexe/digdag-embulk:latest

RUN embulk gem install \
        embulk-input-mysql \
        embulk-output-bigquery

WORKDIR /usr/src/
CMD ["digdag", "init", "my_workflow"]

WORKDIR /usr/src/my_workflow
COPY . .
CMD ["digdag","run","sample.dig"]
```
