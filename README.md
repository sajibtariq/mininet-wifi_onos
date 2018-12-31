


### Configure the ONOS
Open a terminal and access the onos container using ssh:
```
$ ssh -p 8101 karaf@172.28.0.13
password: karaf
onos> app activate org.onosproject.openflow-base
onos> app activate org.onosproject.openflow
onos> app activate org.onosproject.fwd
```

### Start the topology in mininet
In another terminal execute:
```
$ sudo docker exec -it mininet-wifi bash
# echo -e "karaf\nkaraf" | passwd root
# /etc/init.d/ssh start
# exit
$ ssh -YA root@172.28.0.10
# mn --custom topology.py --topo mytopo --controller remote,ip=172.28.0.13 --arp --link tc



http://localhost:8181/onos/ui/index.html

