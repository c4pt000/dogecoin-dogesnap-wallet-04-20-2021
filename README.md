# dogecoin-dogesnap-wallet-04-20-2021

requires docker
must have ports open for 22555,22556 on the docker host

mountable from guest-to-host

mkdir /opt/dogesnap-wallet

docker run -it -d --privileged -v /opt/dogesnap-wallet:/opt/ -v /sys/fs/cgroup:/sys/fs/cgroup:ro -e "DISPLAY=${DISPLAY:-:0.0}" -v /tmp/.X11-unix:/tmp/.X11-unix 
