#!/usr/bin/env bash
# configure HAproxy

sudo apt-get -y update
sudo apt-get -y upgrade
sudo apt-get -y install haproxy
sudo sed -i 's/ENABLED=0/ENABLED=1/' /etc/default/haproxy
sudo cp /etc/haproxy/haproxy.cfg /etc/haproxy/haproxy.cfg.original
sudo sed -i "$ a\listen webapp 0.0.0.0:80\n\tmode http\n\tbalance roundrobin\n\toption httpclose\n\toption forwardfor\n\tserver 17407-web-01 3.227.208.30:80 check\n\tserver 17407-web-02 3.234.212.251:80 check" /etc/haproxy/haproxy.cfg
sudo service haproxy start
