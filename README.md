# Development moved to: https://github.com/membraneframework/docker-membrane

# Ubuntu 18.04 based Membrane Docker image

A docker image based on Ubuntu, with Erlang, Elixir and libraries necessary to test and run the [Membrane Framework](https://membraneframework.org).

[Available on Docker Hub](https://hub.docker.com/r/membrane/bionic-membrane).

This image is based on Ubuntu 18.04 (Bionic) and contains:
- Erlang 21.3 and 22.2
- Elixir 1.9.4
- FFmpeg 4.2.2
- SDL2
- FDK AAC 2.0
- Portaudio 19.6.0
- MAD 0.15.1
- FLAC 1.3.2

## Building the image
To rebuild the image, run the following command:

```sh
make build
```

Optionally, one can add the following variables:
* `VERSION=string`, which adds the version tag (for example, `1.1.1`). Set to `latest` by default.
* `IMAGE=name`, which will override the default image name. If not specified, this is set to `membrane/bionic-membrane`

## Sample usage

Execute the following command while being in you app's directory:

```sh
make run
```

or from anywhere:

```sh
DIR=/my/app/directory make run
```

This will start the container with the application directory mapped to `/app`. Inside the container, go to that directory:

```sh
cd /app
```

and execute your app's code (for example tests)
```sh
mix test
```

## Version selection

The image contains multiple erlang versions and the default is 22.2. You can specify which one should be selected by running: `asdf global erlang <version>` in your script.

# Copyright and License

Copyright 2019, [Software Mansion](https://swmansion.com/?utm_source=git&utm_medium=readme&utm_campaign=docker-bionic-membrane)

[![Software Mansion](https://membraneframework.github.io/static/logo/swm_logo_readme.png)](https://swmansion.com/?utm_source=git&utm_medium=readme&utm_campaign=docker-bionic-membrane)

Licensed under the [Apache License, Version 2.0](LICENSE)
