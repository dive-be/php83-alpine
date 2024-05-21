# php83-alpine

## What is this?

This is a custom build based on PHP 8.3's Alpine docker image, with changes to make Laravel back-end testing easily possible.

## Quick start

In order to build and then test the container:

    docker buildx build . -t diveinteractive/php83-alpine \
    && docker run -it diveinteractive/php83-alpine sh

To make an Intel-compatible build on Apple silicon, provide the `--platform` flag, but beware that this is very slow. Releasing via GitHub Actions is **always** preferred.

    docker buildx build . --platform linux/amd64 -t diveinteractive/php83-alpine \
    && docker run -it diveinteractive/php83-alpine sh

## Tagging & pushing

    docker image tag diveinteractive/php83-alpine:latest diveinteractive/php83-alpine:{tagname}
    docker push diveinteractive/php83-alpine:{tagname}

## Automatic builds

The automatically build the container and have it pushed, you must:

- Tag the commit you wish to build
- Create a new release with said tag

The Docker action will automatically build the release and push it under that tag to Docker Hub.

## Where can I find it?

You can find the image on Docker Hub here: https://hub.docker.com/r/diveinteractive/php83-alpine.
