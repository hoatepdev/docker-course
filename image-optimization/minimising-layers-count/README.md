# Docker Best Practices

Minimizing number of Layers to optimize Docker Image Size

Docker command:

- build image
  docker build -t minilayer-no-optimize -f Dockerefile1 .
  docker build -t minilayer-optimize -f Dockerefile2 .

- get list image show image size
  docker image ls
