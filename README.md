# Ocelot Playground with Consul

Using Ocelot with Consul

## Instructions:

- Run Consul
  ```
  $ docker run -d --name=dev-consul -e CONSUL_BIND_INTERFACE=eth0 consul
  ```
- Run the docker-compose.yml
  ```
  docker-compose up --build -d --remove-orphans
  ```
