FROM alpine:3.8

ENV DIGDAG_VERSION 0.9.28
ENV EMBULK_VERSION 0.9.14
ENV JAVA_VERSION 8
ENV PKG_VERSION_CURL 7.61.1-r1
ENV PKG_VERSION_LIB6COMPAT 1.1.19-r10
ENV PKG_VERSION_OPENJDK 8.191.12-r0

RUN apk --no-cache add \
        libc6-compat=${PKG_VERSION_LIB6COMPAT} \
        openjdk${JAVA_VERSION}=${PKG_VERSION_OPENJDK}

RUN apk add --no-cache --virtual build-dependencies \
        curl=${PKG_VERSION_CURL} \
    # install Digdag
    && curl --create-dirs -o /usr/local/bin/digdag \
    -L "https://dl.bintray.com/digdag/maven/digdag-${DIGDAG_VERSION}.jar" \
    && chmod +x /usr/local/bin/digdag \
    # install Embulk
    && curl --create-dirs -o /usr/local/bin/embulk \
    -L "https://dl.bintray.com/embulk/maven/embulk-${EMBULK_VERSION}.jar" \
    && chmod +x /usr/local/bin/embulk \
    && apk del build-dependencies
