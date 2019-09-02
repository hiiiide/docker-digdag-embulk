# docker-digdag-embulk
An Alpine Linux based ETL workflow container.

[![dockeri.co](https://dockeri.co/image/exelexe/digdag-embulk)](https://hub.docker.com/r/exelexe/digdag-embulk)

## Docker Tags
- [`0.3.0-ruby2.6-alpine3.10`, `latest`](https://github.com/exelexe/docker-digdag-embulk/blob/master/0.3.0/ruby2.6-alpine3.10/Dockerfile)
- [`0.3.0-alpine3.10`](https://github.com/exelexe/docker-digdag-embulk/blob/master/0.3.0/alpine3.10/Dockerfile)
- [`0.2.0-ruby2.6-alpine3.9`](https://github.com/exelexe/docker-digdag-embulk/blob/master/0.2.0/ruby2.6-alpine3.9/Dockerfile)
- [`0.2.0-alpine3.9`](https://github.com/exelexe/docker-digdag-embulk/blob/master/0.2.0/alpine3.9/Dockerfile)
- [`0.1.0-ruby2.6-alpine3.9`](https://github.com/exelexe/docker-digdag-embulk/blob/master/0.1.0/ruby2.6-alpine3.9/Dockerfile)
- [`0.1.0-alpine3.9`](https://github.com/exelexe/docker-digdag-embulk/blob/master/0.1.0/alpine3.9/Dockerfile)
- [`0.0.0-alpine3.8`](https://github.com/exelexe/docker-digdag-embulk/blob/master/0.0.0/alpine3.8/Dockerfile)


## How to use

For example

```Dockerfile
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
