# dogecoin-dogesnap-wallet-04-20-2021

* requires docker (--privileged , requires libfuse for AppImage)
must have ports open for 22555,22556 on the docker host

mountable from guest-to-host


# must run docker commit or wallet.dat will be lost -> to backup wallet.dat from guest

cd Dogecoin_Wallet_dogesnap.04-20-2021-DMq9mjF2BpWA9EZhMcpMmi6voVXiBMJY9B/dogecoin-datadir/

copy wallet.dat -> /opt/host-opt in guest to backup your wallet

wallet.dat will be located in /opt/host-opt on host 

```
docker run -it -d  --net=host --privileged -v /opt/host-opt:/opt/host-opt -v /sys/fs/cgroup:/sys/fs/cgroup:ro -e "DISPLAY=${DISPLAY:-:0.0}" -v /tmp/.X11-unix:/tmp/.X11-unix c4pt/dogesnap-wallet

docker exec -it <docker_vm_hash> bash

cd /opt

cd Dogecoin_Wallet_dogesnap.04-20-2021-DMq9mjF2BpWA9EZhMcpMmi6voVXiBMJY9B/

dogecoin

```

dogecoin is located in /usr/bin/dogecoin
--------------------------------

```
#!/bin/bash
cd /opt/Dogecoin_Wallet_dogesnap.04-20-2021-DMq9mjF2BpWA9EZhMcpMmi6voVXiBMJY9B
./Dogecoin_Wallet_dogesnap-x86_64.AppImage -conf=dogecoin-datadir/dogecoin.conf -datadir=dogecoin-datadir -prune=2200 &

```


