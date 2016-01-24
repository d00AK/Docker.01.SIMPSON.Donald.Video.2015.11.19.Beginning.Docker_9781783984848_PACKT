<!-- ### 02 DOCKER BASICS -->
### 0201 Running the Containerized Commands
#### Running a container

- ##### docker run
  ```bash
  docker run --help
  >> Usage: docker run [OPTIONS] IMAGE [COMMAND] [ARG...]
  ```

  - Foreground commands
    ```bash
    docker run --rm ubuntu ping google.com
    ```
  - Interactive commands
    ```bash
    docker run --rm -i -t ubuntu bash
    ```
  - Background commands
    ```bash
    docker run -d ubuntu ping google.com
    ```

- docker logs

  ```bash
  docker logs --help
  >> Usage: docker logs [OPTIONS] CONTAINER
  ```

  - Logs of the latest container  
    ```bash
    docker logs --tail=5 `docker ps -lq`
    ```

===

#### Cleaning up
##### docker kill

```bash
docker kill --help
>> Usage: docker kill [OPTIONS] CONTAINER [CONTAINER...]
```

- Kill the latest background process  
  ```bash
  docker kill `docker ps -lq`
  ```

===

##### docker rm

```bash
docker rm --help
>> Usage: docker rm [OPTIONS] CONTAINER [CONTAINER...]
```

- Remove the latest container  
  ```bash
  docker rm `docker ps -lq`
  ```



