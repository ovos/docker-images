# Shared CI docker images

This repository contains shared docker images that can be used as CircleCI executors.

* less
* gren
* sentry
* cypress12


## Usage

```yaml
executors:
  gren:
    working_directory: /home/circleci/project
    docker:
      - image: ovos/ci:gren
```
