### build an NGINX container

To build the unikernel variant for aarch64 use:

```
sed s/__ARCH__/aarch64/ -i data/www/index.html
sed s/__MODE__/rumprun unikernel/ -i data/www/index.html
docker build -t nginx-unikernel:aarch64 -f Dockerfile.unikernel . --build-arg ARCH=aarch64
```

To build the generic container variant for aarch64 use:

```
sed s/__ARCH__/aarch64/ -i data/www/index.html
sed s/__MODE__/generic container/ -i data/www/index.html
docker build -t nginx-container:aarch64 -f Dockerfile.generic . --build-arg ARCH=aarch64
```

For the `x86_64` use: `--build-arg ARCH=x86_64`
