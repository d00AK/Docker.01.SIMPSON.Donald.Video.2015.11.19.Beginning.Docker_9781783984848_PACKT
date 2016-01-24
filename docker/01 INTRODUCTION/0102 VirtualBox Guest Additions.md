In case of Guest Additions mismatch:

```bash
vagrant up

>...
>default: The guest additions on this VM do not match the installed version of
>default: VirtualBox!
>...
```

install the a Vagrant plugin which automatically installs the host's VirtualBox Guest Additions on the guest system

```bash
vagrant halt
vagrant plugin install vagrant-vbguest
```

Finally, verify that Guest additions match

```bash
vagrant up

>...
>GuestAdditions 5.0.10 running --- OK.
>...
```
done.
