
### 02 DOCKER BASICS
#### 0202 Managing Your Containers

##### See containers

- docker ps
  ```bash
  docker ps --help
  >> Usage: docker ps [OPTIONS]
  ```

  - See _running_ containers
    ```bash
    docker ps
    ```

  - See all containers
    ```bash
    docker ps -a
    ```

  - See the latest container
    ```bash
    docker ps -l
    ```

  - See the __latest container's ID__
    ```bash
    docker ps -lq
    ```

  - List the __IDs of all containers__
    ```bash
    docker ps -aq
    ```

===

##### Inspect containers

- docker inspect
  ```bash
  docker inspect --help
  >> Usage: docker inspect [OPTIONS] CONTAINER|IMAGE [CONTAINER|IMAGE...]
  ```

  - Inspect the latest container
    ```bash
    docker inspect `docker ps -lq`
    ```

===

##### Stop containers

- docker stop
  ```bash
  docker stop --help
  >> Usage: docker stop [OPTIONS] CONTAINER [CONTAINER...]
  ```

  - Stop and kill (after __timeout__) the latest _running_ process
    ```bash
    docker stop `docker ps -lq`
    ```

  - Stop and kill (immediately) the latest _running_ process
    ```bash
    docker kill `docker ps -lq`
    ```

