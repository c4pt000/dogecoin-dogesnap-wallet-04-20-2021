# dogecoin-dogesnap-wallet-04-20-2021

* requires docker (--privileged , requires libfuse for AppImage)
must have ports open for 22555,22556 on the docker host

mountable from guest-to-host


# must run docker commit or wallet.dat will be lost -> to backup wallet.dat from guest

cd Dogecoin_Wallet_dogesnap.04-20-2021-DMq9mjF2BpWA9EZhMcpMmi6voVXiBMJY9B/dogecoin-datadir/

copy wallet.dat -> /opt/host-opt in guest to backup your wallet

wallet.dat will be located in /opt/host-opt on host 


# linux docker host
```
docker run -it c4pt/dogesnap-wallet

docker run -it -d  --net=host --privileged -v /opt/host-opt:/opt/host-opt -v /sys/fs/cgroup:/sys/fs/cgroup:ro -e "DISPLAY=${DISPLAY:-:0.0}" -v /tmp/.X11-unix:/tmp/.X11-unix c4pt/dogesnap-wallet

docker exec -it <docker_vm_hash> bash

cd /opt

cd Dogecoin_Wallet_dogesnap.04-20-2021-DMq9mjF2BpWA9EZhMcpMmi6voVXiBMJY9B/

dogecoin

copy wallet.dat -> /opt/host-opt in guest to backup your wallet

wallet.dat will be located in /opt/host-opt on host 

```

# windows docker host
![s1](https://res.cloudinary.com/practicaldev/image/fetch/s--1fOShFRZ--/c_limit%2Cf_auto%2Cfl_progressive%2Cq_auto%2Cw_880/https://thepracticaldev.s3.amazonaws.com/i/3eh1lry7125modpdj6a2.png)


```
https://dev.to/darksmile92/run-gui-app-in-linux-docker-container-on-windows-host-4kde

https://chocolatey.org/

choco install vcxsrv

run Xlaunch from the start menu 


(enable "disable access control")

open -> powershell

ipconfig    (get LAN ip)
                                  
set-variable -name DISPLAY -value 192.168.xxx.xx:0.0      <- replace with your LAN ip
docker run -it c4pt/dogesnap-wallet

docker run -it -d  --net=host --privileged -v C:/opt/host-opt:/opt/host-opt -e DISPLAY=$DISPLAY c4pt/dogesnap-wallet

docker exec -it <docker_vm_hash> bash

dogecoin

cd /opt

cd Dogecoin_Wallet_dogesnap.04-20-2021-DMq9mjF2BpWA9EZhMcpMmi6voVXiBMJY9B/

dogecoin

copy wallet.dat -> /opt/host-opt in guest to backup your wallet

wallet.dat will be located in C:\opt\host-opt on host 

```
dogecoin is located in /usr/bin/dogecoin
--------------------------------

```
#!/bin/bash
cd /opt/Dogecoin_Wallet_dogesnap.04-20-2021-DMq9mjF2BpWA9EZhMcpMmi6voVXiBMJY9B
./Dogecoin_Wallet_dogesnap-x86_64.AppImage -conf=dogecoin-datadir/dogecoin.conf -datadir=dogecoin-datadir -prune=2200 &

```

if you found this useful my DOGE deposit address

![s1](https://raw.githubusercontent.com/c4pt000/dogecoin-dogesnap-wallet-04-20-2021/main/my-doge-deposit.png)

DMq9mjF2BpWA9EZhMcpMmi6voVXiBMJY9B
