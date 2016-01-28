### 02 DOCKER BASICS
#### 0201 Running the Containerized Commands

##### Running a container

- docker run  
  ```
  docker run --help
  >> Usage: docker run [OPTIONS] IMAGE [COMMAND] [ARG...]
  ```
  - Foreground commands (Run an attached container)  
    ```
    docker run --rm ubuntu ping google.com
    ```
  - Interactive commands  
    ```
    docker run --rm -i -t ubuntu bash
    ```
  - Background commands (Run a detached container)  
    ```
    docker run -d ubuntu ping google.com
    ```

- docker logs  
  ```
  docker logs --help
  >> Usage: docker logs [OPTIONS] CONTAINER
  ```
  - Logs of the latest container  
    ```
    docker logs --tail=5 `docker ps -lq`
    ```
  - Follow the logs of the _running_ latest container  
    ```
    docker logs -f `docker ps -lq`
    ```

===

##### Cleaning up

- docker kill  
  ```
  docker kill --help
  >> Usage: docker kill [OPTIONS] CONTAINER [CONTAINER...]
  ```
  - Kill the latest _running_ background process  
    ```
    docker kill `docker ps -lq`
    ```

- docker rm  
  ```
  docker rm --help
  >> Usage: docker rm [OPTIONS] CONTAINER [CONTAINER...]
  ```
  - Remove the latest container  
    ```
    docker rm `docker ps -lq`
    ```
  - Remove all containers  
    ```
    docker ps -aq | xargs rm -f
    or
    docker rm $(docker ps -a -q)
    ```
