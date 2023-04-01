[![Publish Docker Image](https://github.com/wiiu-env/libromfs_wiiu/actions/workflows/push_image.yml/badge.svg)](https://github.com/wiiu-env/libromfs_wiiu/actions/workflows/push_image.yml)

# libromfs
Ported from [libnx](https://github.com/switchbrew/libnx/blob/e5ae43f4c2cca5320559d9c27ce256b2901aed40/nx/source/runtime/devices/romfs_dev.c)

## Building
Make you to have [wut](https://github.com/devkitPro/wut/) installed and use the following command for build:
```
make install
```

## Use this lib in Dockerfiles.
A prebuilt version of this lib can found on dockerhub. To use it for your projects, add this to your Dockerfile.
```
[...]
COPY --from=ghcr.io/wiiu-env/libromfs_wiiu:[tag] /artifacts $DEVKITPRO
[...]
```
Replace [tag] with a tag you want to use, a list of tags can be found [here](https://github.com/orgs/wiiu-env/packages/container/libromfs_wiiu/versions).
It's highly recommended to pin the version to the **latest date** instead of using `latest`.

## Format the code via docker

`docker run --rm -v ${PWD}:/src ghcr.io/wiiu-env/clang-format:13.0.0-2 -r ./source ./include -i`