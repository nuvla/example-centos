# CentOS SSH

An example, minimal [CentOS 7](https://www.centos.org/) container that
can be accessed via [SSH](https://en.wikipedia.org/wiki/Secure_Shell)
and integrates well with [Nuvla](https://docs.nuvla.io/).

## Supported tags and respective `Dockerfile` links

Multi-architecture tags: 

 - `latest` ([Dockerfile](https://github.com/nuvla/example-centos/blob/master/Dockerfile))

Architecture-specific tags:

 - `latest-amd64` ([Dockerfile](https://github.com/nuvla/example-centos/blob/master/Dockerfile))
 - `latest-arm64` ([Dockerfile](https://github.com/nuvla/example-centos/blob/master/Dockerfile))


## How to register this image in a Nuvla installation

To register this container on your Nuvla on-premise installation, clone the sources
from the
[nuvla/example-centos](https://github.com/nuvla/example-centos)
GitHub, then run the following commands, after having exported the required environment variables:

```sh
pip install nuvla-api
python add-module.py
```

You should now see the module component in the App Store called *CentOS SSHD*.

## How to use this image locally

To run the container:

```sh
docker run -d -p 2222:22 -e AUTHORIZED_SSH_KEY='your public key' nuvla/example-centos
```

You can then access the container with the command:

```sh
ssh -p 2222 root@localhost
```

Use the standard Docker commands to stop and remove the container.

## How to build this image

To build the container on your current platform, clone the sources
from the
[nuvla/example-centos](https://github.com/nuvla/example-centos)
GitHub, then run the following Docker command:

```sh
docker build . --tag nuvla/example-centos
```

To build the container for all supported platforms, run the commands:

```sh
./.travis.before_install.sh
./.travis.script.sh
```

The `before_install.sh` script may not be necessary if "binfmt_misc"
support is already included in your Docker installation (e.g. MacOS).
