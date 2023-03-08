---
_schema: default
title: Local Development
linkTitle: Local Development
weight:
description: |
  Making local changes to DocsyCannon.
categories:
  - Examples
  - Getting Started
tags:
  - Local Development
  - Docker
---
## Prerequisites

1. Git
2. Hugo&nbsp;
3. Docker Desktop (if using docker)

## Hugo Server

Clone the repository from GitHub. Run in the root of the repository on your local using Hugo Server:

```console
npm i
npm start
```

## Docker Compose

Clone the repository from GitHub. Run in the root of the repository on your local using Hugo Server:

```console
npm i
docker-compose build
docker-compose up
```

To cleanup your system and delete the container image follow the next steps.

1. Stop Docker Compose with&nbsp;**Ctrl + C**.
2. Remove the produced images

   <div> </div>

```console
docker-compose rm
```