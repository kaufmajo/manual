# Debian

## Static network

```sh
$ vi /etc/network/interfaces
```

```sh
auto eth0
    iface eth0 inet static
    address 10.99.99.20/24
    gateway 10.99.99.1
```