

In case of an access error after Vagrant installation

```bash
vagrant -v

>-bash: /usr/bin/vagrant: No such file or directory
```

find the Vagrant location on your system

```bash
which vagrant

>/usr/local/bin/vagrant
```

and make a symbolic link to it

```bash
sudo ln -s /usr/local/bin/vagrant /usr/bin/vagrant
```

Finally, verify the access to Vagrant

```bash
vagrant -v

>Vagrant 1.8.1
```
done.
