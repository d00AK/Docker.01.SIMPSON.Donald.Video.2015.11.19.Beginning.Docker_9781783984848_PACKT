### 02 DOCKER BASICS
#### 0203 Committing Changes to a Container Image

##### Show downloaded Docker container images

- docker images  
  ```
  docker images --help  
  >> Usage: docker images [OPTIONS] [REPOSITORY[:TAG]]
  ```
  - list all Docker images  
    ```
    docker images
    ```
  - list all intermediate Docker images  
    ```
    docker images -a
    ```

===

##### Create a container based on a stock ubuntu image to run a SSH server

- docker run  
  ```
  docker diff --help  
  >> Usage: docker run [OPTIONS] IMAGE [COMMAND] [ARG...]
  ```
  - start by running a container from the base ubuntu image  
    ```
    docker run -it ubuntu bash
    ```
  - install the SSH server  
    ```
    apt-get update  
    apt-get install -y openssh-server
    ```
  - create the start directory  
    ```
    mkdir /var/run/sshd
    ```
  - set a passwort for the root user  
    ```
    echo 'root:demo' | chpasswd
    ```
  - allow root login updating the config file  
    ```
    sed -i 's/PermitRootLogin without-password/PermitRootLogin yes/g' /etc/ssh/sshd_config
    ```
  - allow authentication to work updating the config file  
    ```
    sed -ri 's/UsePAM yes/UsePAM no/g' /etc/ssh/sshd_config
    ```
  - stop the container  
    ```
    exit
    ```

===

##### Inspect the installation changes on a container's filesystem

- docker diff  
  ```
  docker diff --help  
  >> Usage: docker diff [OPTIONS] CONTAINER
  ```
  - use docker diff to see the changes we've made upon the base image container  
    ```
    docker diff `docker ps -lq`
    ```  
    or  
    ```
    docker diff `docker ps -lq` | less
    ```

===

##### Make a custom Docker container image based on a changed container

- docker commit  
  ```
  docker commit --help  
  >> Usage: docker commit [OPTIONS] CONTAINER [REPOSITORY[:TAG]]
  ```
  - persist the container changes with docker commmit into a new [USERNAME/IMAGENAME] named image  
    ```
    docker commit `docker ps -lq` myname/sshd
    ```
  - start the sshd server in a container from the new image  
    ```
    docker run -d -p 2222:22 myname/sshd /usr/sbin/sshd -D
    ```
  - connect to the opened port 2222  
    ```
    ssh root@localhost -p 2222
    ```
  - in case of a connection problem clear the known hosts entry and reconnect  
    ```
    ssh-keygen -f "/home/vagrant/.ssh/known_hosts" -R [localhost]:2222  
    ssh root@localhost -p 2222
    ```
  - exit when you're done  
    ```
    exit
    ```
