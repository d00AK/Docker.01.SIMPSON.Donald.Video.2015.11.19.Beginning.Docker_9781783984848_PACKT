In case of an access error

```bash
vagrant -v

-bash: /usr/bin/vagrant: No such file or directory
```

Make a symbolic link

```bash
sudo ln -s /usr/local/bin/vagrant /usr/bin/vagrant
```

to get

```bash
vagrant -v

Vagrant 1.8.1
```
