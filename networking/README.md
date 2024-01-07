# Docker networking

Docker networking là thành phần quan trọng giúp container giao tiếp với các mạng bên ngoài (external network) và giữa các contariner với nhau

Docker có 3 chế độ làm việc : **_bride, none, host_**

## Bride network:

Là mode cho phép container giao tiếp với nhau và giao tiếp ra bên ngoài.

Docker command:

- Network create when run container:
  `docker run -d --name nginx nginx`
- Get list network:
  `docker network ls`
- Inspect bride network:
  `docker network inspect <ip>`

## None network:

Là mode network cô lập container với các network bên ngoài.

Container sẽ không được cấp card mạng ảo và sẽ không có IP.

Container chạy none network sẽ không phụ thuộc vào các tiến trình ở network bên ngoài.

Docker command:

- Run container with none network:
  `docker run nginx --network=none`

## Host network

Là mode network cho phép container sử dụng Network stack (IP) của HOST (sử dụng chung network interface)

Port của tiến trình tạo container sẽ được tạo ra trực tiếp trên HOST

Container sử dụng mode host sẽ yêu cầu về hiệu năng cao của network (network-intense)

Docker command:

- Run container with host network:
  `docker run nginx --network=host`

Note: ở mode bride network sẽ tạo ra layer bride network để cho phép truy cập vào container qua đó sẽ giảm hiệu năng của network. Đối với mode host network thì sẽ không tạo ra layer trung gian nào mà được tạo ra trực tiếp từ network namespace của Host do đó sẽ tăng hiệu năng truy cập từ network.

## Overlay network

Cho phép containers trên nhiều host vật lý có thể truy cập được với nhau
Quản lý overlay network sử dụng docker swarm hoặc kubernetes (k8s)
