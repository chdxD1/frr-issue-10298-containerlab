# How to trigger bug

Running Containerlab:
```
sudo containerlab deploy --reconfigure -t frr-bug.yaml
```

From "server01" or "server02" side:
```
docker exec -ti clab-frr-bug-server01 vtysh
server01# show evpn rmac vni all
server01# show bgp vrf testvrf ipv4 unicast 10.150.0.2/32
server01# clear bgp 192.168.100.1
server01# show bgp vrf testvrf ipv4 unicast 10.150.0.2/32
server01# show evpn rmac vni all
server01# clear bgp 192.168.100.1
server01# show evpn rmac vni all
server01# clear bgp 192.168.100.2
server01# show evpn rmac vni all
```
