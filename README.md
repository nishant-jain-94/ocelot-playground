# Ocelot Playground with Consul

Using Ocelot with Consul

## Instructions:

- Run Consul
  ```
  $ docker run -d -p 8500 --name=dev-consul -e CONSUL_BIND_INTERFACE=eth0 consul
  ```

- Run Registrator
  ```
  $ docker run -d \
    --name=registrator \
    --net=host \
    --volume=/var/run/docker.sock:/tmp/docker.sock \
    gliderlabs/registrator:latest \
      consul://localhost:8500
  ```

- Run the docker-compose.yml
  ```
  docker-compose up --build -d --remove-orphans
  ```
