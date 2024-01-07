# Docker Best Practices

Using Multi-Stage build to optimize Docker Image Size

Docker command:

- build image
  docker build -t multistate-no-optimize -f Dockerefile1 .
  docker build -t multistate-optimize -f Dockerefile2 .

- get list image
  docker image ls
