
### 02 DOCKER BASICS
#### 0202 Managing Your Containers

##### See containers

- docker ps  
  ```
  docker ps --help
  >> Usage: docker ps [OPTIONS]
  ```
  - See _running_ containers  
    ```
    docker ps
    ```
  - See all containers  
    ```
    docker ps -a
    ```
  - See the latest container  
    ```
    docker ps -l
    ```
  - See the __latest container's ID__  
    ```
    docker ps -lq
    ```
  - List the __IDs of all containers__  
    ```
    docker ps -aq
    ```

===

##### Inspect containers

- docker inspect  
  ```
  docker inspect --help
  >> Usage: docker inspect [OPTIONS] CONTAINER|IMAGE [CONTAINER|IMAGE...]
  ```
  - Inspect the latest container  
    ```
    docker inspect `docker ps -lq`
    ```

===

##### Stop containers

- docker stop  
  ```
  docker stop --help
  >> Usage: docker stop [OPTIONS] CONTAINER [CONTAINER...]
  ```
  - Stop and kill (after __timeout__) the latest _running_ process  
    ```
    docker stop `docker ps -lq`
    ```
  - Stop and kill (immediately) the latest _running_ process  
    ```
    docker kill `docker ps -lq`
    ```

