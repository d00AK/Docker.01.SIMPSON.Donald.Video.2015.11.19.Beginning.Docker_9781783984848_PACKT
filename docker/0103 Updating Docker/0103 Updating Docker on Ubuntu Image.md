Add user and check the Docker version:

```bash
vagrant ssh
vagrant@vagrant-ubuntu-trusty-64:~$ sudo usermod -aG docker vagrant
vagrant@vagrant-ubuntu-trusty-64:~$ exit
vagrant ssh
vagrant@vagrant-ubuntu-trusty-64:~$ docker version

>...
>Last stable version: 1.9.1, please update docker
```

---
In case of a Docker run error:

```bash
docker run -it ubuntu /bin/bash

>Unable to find image 'ubuntu' locally
>Pulling repository ubuntu
>...
```
press Ctrl+C now to abort the output.

---
Update Docker to the latest version

```bash
curl -sSL https://get.docker.com/ | sh
vagrant@vagrant-ubuntu-trusty-64:~$ exit
```

---
Finally, verify the Docker version and its run

```bash
vagrant ssh
vagrant@vagrant-ubuntu-trusty-64:~$ docker version
docker run -it ubuntu /bin/bash

>Unable to find image 'ubuntu:latest' locally
>latest: Pulling from library/ubuntu
>...
>Status: Downloaded newer image for ubuntu:latest

root@70ad8d479504:/# exit
vagrant@vagrant-ubuntu-trusty-64:~$ exit
>logout
>Connection to 127.0.0.1 closed.
vagrant halt
>==> default: Attempting graceful shutdown of VM...
vagrant status
>default                   poweroff (virtualbox)
```

done.

