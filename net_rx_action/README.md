# flamegraph

These two scripts may be handy:
    wget https://raw.githubusercontent.com/brendangregg/FlameGraph/master/stackcollapse-stap.pl 
    wget https://raw.githubusercontent.com/brendangregg/FlameGraph/master/flamegraph.pl



# How to Install Debug Symbol

https://wiki.ubuntu.com/Kernel/Systemtap

sudo apt-key adv --keyserver keyserver.ubuntu.com --recv-keys C8CAB6595FDFF622 
codename=$(lsb_release -c | awk  '{print $2}')
sudo tee /etc/apt/sources.list.d/ddebs.list << EOF
deb http://ddebs.ubuntu.com/ ${codename}      main restricted universe multiverse
deb http://ddebs.ubuntu.com/ ${codename}-security main restricted universe multiverse
deb http://ddebs.ubuntu.com/ ${codename}-updates  main restricted universe multiverse
deb http://ddebs.ubuntu.com/ ${codename}-proposed main restricted universe multiverse
EOF

sudo apt-get update
sudo apt-get install linux-image-$(uname -r)-dbgsym
