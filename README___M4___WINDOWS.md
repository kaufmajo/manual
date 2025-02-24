# Windows

## Set up a NAT network

https://learn.microsoft.com/en-us/virtualization/hyper-v-on-windows/user-guide/setup-nat-network

```ps
$ New-VMSwitch -SwitchName "Internal Switch" -SwitchType Internal

$ New-NetIPAddress -IPAddress 10.99.99.1 -PrefixLength 24 -InterfaceIndex 24

$ New-NetNat -Name MyNATnetwork -InternalIPInterfaceAddressPrefix 10.99.99.0/24
```

## Set up Portproxy

```ps
$ netsh interface portproxy add v4tov4 listenport=3306 listenaddress=0.0.0.0 connectport=3306 connectaddress=172.22.144.1

$ netsh interface portproxy add v4tov4 listenport=3306 listenaddress=0.0.0.0 connectport=3306 connectaddress=172.23.145.10

$ netsh interface portproxy show v4tov4

$ netsh interface portproxy delete v4tov4 listenport=3306 listenaddress=0.0.0.0
```

## Set up firewall rules

```ps
$ iex "New-NetFireWallRule -DisplayName 'WSL 2 Firewall Unlock' -Direction Outbound -LocalPort 3306 -Action Allow -Protocol TCP";

$ iex "New-NetFireWallRule -DisplayName 'WSL 2 Firewall Unlock' -Direction Inbound -LocalPort 3306 -Action Allow -Protocol TCP";
```

# Misc

WSL <-> HyperV enable network forwarding

https://techcommunity.microsoft.com/blog/itopstalkblog/windows-subsystem-for-linux-2---addressing-traffic-routing-issues/1764074

https://learn.microsoft.com/en-us/windows/wsl/networking#default-networking-mode-nat

https://superuser.com/questions/1635668/hyper-v-and-wsl2-networks-do-not-communicate

https://github.com/microsoft/WSL/issues/4150
