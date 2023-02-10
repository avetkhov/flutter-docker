# Flutter Docker

[![build](https://github.com/avetkhov/flutter-docker/actions/workflows/build.yml/badge.svg?branch=main)](https://github.com/avetkhov/flutter-docker/actions/workflows/build.yml)
![Docker Image Version (latest semver)](https://img.shields.io/docker/v/avetkhov/flutter?sort=semver&logo=docker&logoColor=white&label=version)
![Docker Image Size (latest semver)](https://img.shields.io/docker/image-size/avetkhov/flutter?logo=docker&logoColor=white&label=size)
![Docker Pulls](https://img.shields.io/docker/pulls/avetkhov/flutter?logo=docker&logoColor=white&label=pulls)
![Docker Stars](https://img.shields.io/docker/stars/avetkhov/flutter?logo=docker&logoColor=white&label=stars)

Based on [`avetkhov/android-sdk:tools`][1].


## Supported toolchains

- `iOS`
- `Android`
- `Linux`
- `Web`


## What is Flutter?

Flutter is Google's UI toolkit for building beautiful, natively compiled applications for mobile, web, and desktop from a single codebase. Flutter works with existing code, is used by developers and organizations around the world, and is free and open source.

[flutter.dev](https://flutter.dev)

![Flutter Logo](https://storage.googleapis.com/cms-storage-bucket/c823e53b3a1a7b0d36a9.png)


## How to use this image

```
docker run -t --rm avetkhov/flutter flutter doctor
```
Alternatively, a simple `Dockerfile` can be used to generate a new image that includes the necessary package dependencies:
```
FROM avetkhov/flutter

COPY pubspec.yaml .

RUN flutter pub get \
    && rm pubspec.*
```
Place this file in the flutter project directory, run `docker build -t my-app-flutter .`, then start your container:
```
docker run --name my-app -d my-app-flutter
```

## License

Flutter is licensed under [BSD 3-Clause "New" or "Revised" license][2].

As with all Docker images, these likely also contain other software which may be under other licenses (such as Bash, etc from the base distribution, along with any direct or indirect dependencies of the primary software being contained).

As for any pre-built image usage, it is the image user's responsibility to ensure that any use of this image complies with any relevant licenses for all software contained within.

[1]: https://hub.docker.com/r/avetkhov/android-sdk
[2]: https://github.com/flutter/flutter/blob/master/LICENSE