# How to trigger bug

Running Containerlab:
```
sudo containerlab deploy --reconfigure -t frr-bug.yaml
```

From "fabric" side:
```
docker exec -ti clab-frr-bug-fabric vtysh
fabric# clear bgp peer-group leaf1-to-server 
fabric# clear bgp peer-group leaf2-to-server 
fabric# clear bgp peer-group leaf1-to-server 
fabric# clear bgp peer-group leaf2-to-server
```

Check on "server" side:
```
docker exec -ti clab-frr-bug-server vtysh
server# show evpn rmac vni all
```