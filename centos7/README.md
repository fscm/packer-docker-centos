**[DEPRECATED] This repository is no longer maintained**
> While this project is fully functional, the content is no longer maintained and therefore is no longer up to date. You are still welcome to explore, learn, and use the code provided here.
>
> This project was replaced by the [docker-centos](https://github.com/fscm/docker-centos) project.

# CentOS 7 Docker

![No longer maintained](https://img.shields.io/badge/maintenance-OFF-red.svg?&style=flat-square)

Packer templates to build a Docker CentOS 7 base image.

## Synopsis

This script will create a Docker base image with a minimum installation of
CentOS 7.

This script creates what is called a *Base Image* for Docker from scratch
using technology other than Docker for that.

## Getting Started

There are a couple of things needed for the templates to work.

### Prerequisites

Packer tools need to be installed on your local computer.

#### Packer

Packer installation instructions can be found [here](https://www.packer.io/docs/installation.html).

#### Virtualbox

Virtualbox installation instructions can be found [here](https://www.virtualbox.org/wiki/Downloads).

### Installation

Nothing special to be done. Just download the template that you wish to use.

### Usage

In order to create the base image using this packer script you may have to
provide a few options.

```
Usage:
  packer build [-var 'option=value'] centos7.json
```

#### Script Options
- `checksum_type` - The type of the ISO checksum specified in `checksum_value` (default value: "none"). If set to something other than "*none*" then the `checksum_value` must also be set. Possible values are "*none*", "*md5*", "*sha1*", "*sha256*", or "*sha512*".
- `checksum_value` - The checksum for the ISO file (default value: ""). Make sure that the type of the checksum is specified with the `checksum_type` variable.
- `docker_name` - The Docker image name (default value: "centos7").
- `headless` - Hide the console of the machine being built (default value: "true").
- `os_codename` - Codename of the Operating System (default value: "centos").
- `os_version` - Version of the Operating System (default value: "7").
- `os_version_build` - Version of the Operating System (default value: "1804").


### Add the image to Docker

Adding the resulting image to Docker can be done with the following command:

```
docker import path/to/the/image.tar <user>/<image>:<tag>
```

Additional tags can be added to the image using the following command:

```
docker tag <image_id> <user>/<image>:<extra_tag>
```

#### Push the image to Docker Hub

After adding an image to Docker, that image can be pushed to a Docker registry... Like Docker Hub.

Make sure that you are logged in to the service.

```
docker login
```

When logged in, an image can be pushed using the following command:

```
docker push <user>/<image>:<tag>
```

Extra tags can also be pushed.

```
docker push <user>/<image>:<extra_tag>
```

## Contributing

Contributing to this project is no longer possible since the project is no
longer maintained.

## Versioning

This project uses [SemVer](http://semver.org/) for versioning. For the versions
available, see the [tags on this repository](https://github.com/fscm/packer-docker-centos/tags).

## Authors

* **Frederico Martins** - [fscm](https://github.com/fscm)

See also the list of [contributors](https://github.com/fscm/packer-docker-centos/contributors)
who participated in this project.

## License

This project is licensed under the MIT License - see the [LICENSE](../LICENSE)
file for details
