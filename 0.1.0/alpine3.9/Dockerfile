FROM alpine:3.9

ENV DIGDAG_VERSION 0.9.33
ENV EMBULK_VERSION 0.9.14
ENV JAVA_VERSION 8

RUN apk --no-cache add \
        libc6-compat \
        openjdk${JAVA_VERSION}

RUN apk add --no-cache --virtual build-dependencies \
        curl \
    # install Digdag
    && curl --create-dirs -o /usr/local/bin/digdag \
    -L "https://dl.bintray.com/digdag/maven/digdag-${DIGDAG_VERSION}.jar" \
    && chmod +x /usr/local/bin/digdag \
    # install Embulk
    && curl --create-dirs -o /usr/local/bin/embulk \
    -L "https://dl.bintray.com/embulk/maven/embulk-${EMBULK_VERSION}.jar" \
    && chmod +x /usr/local/bin/embulk \
    && apk del build-dependencies
