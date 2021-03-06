This repository holds the recipe for `skhep/manylinuxgcc-*` images. These produce manylinux1 wheels with some caveats with a modern GCC.

GCC 10 is not compatible with RHEL 5, so this is capped at version 9.

## Example build

This is an example build on a 24 core machine:

```bash
docker build -t skhep/manylinuxgcc-x86_64 . -f Dockerfile --build-arg CORES=48
```

Here is a 32-bit build:

```bash
docker build -t skhep/manylinuxgcc-i686 . -f Dockerfile --build-arg CORES=48 --build-arg ARCH=i686
```

## Tags

Make sure you tag accordingly. Also, do not use the default "latest" tag if you are not building the latest GCC. Here are the current set of tags:

```bash
docker tag skhep/manylinuxgcc-i686:latest skhep/manylinuxgcc-i686:9
docker tag skhep/manylinuxgcc-i686:latest skhep/manylinuxgcc-i686:9.3
docker tag skhep/manylinuxgcc-x86_64:latest skhep/manylinuxgcc-x86_64:9
docker tag skhep/manylinuxgcc-x86_64:latest skhep/manylinuxgcc-x86_64:9.3
docker push skhep/manylinuxgcc-i686
docker push skhep/manylinuxgcc-x86_64
```
