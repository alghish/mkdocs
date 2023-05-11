# Build the image & Run Container

## Steps

### 1- Build the image:

```bash
  docker build --tag mysite-img .
```

### 2- View local images:

```bash
 docker image ls
```

### 3- Tag images:

**Optional**

```bash
  docker image tag mysite-img:latest mysite-img:v1.0
```

### 4- Run your image as a container:

```bash
  docker run mysite-img
```

### 5- Run in detached mode with publish port, add name to container

```bash
  docker run -d -p 8080:8080 --name mysite-cotr mysite-img
```

### 6- View all containers with details

```bash
  docker ps -a
```

### 7- Stop running container

```bash
  docker stop mysite-cotr
```

## Remove image with tag or shorthand

```bash
  docker image rm docker-gs-ping:v1.0 # Remove
  docker rmi docker-gs-ping:v1.0 # shorthand
   docker rm mysite-cotr # Remove container
```

## References

- [Docker docs](https://docs.docker.com/language/golang/build-images/)
