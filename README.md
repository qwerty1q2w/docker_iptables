# docker-compose_iptables
If you want manage your iptables rules in docker-compose yourself. Docker might be exposing ports to the world.
1) add this to /etc/docker/daemon.json
```
{
  "iptables" : false
}
```
2) systemctl restart docker
3) apt-get update && apt-get install iptables-persistent
4) Put rules.v4 to /etc/iptables/rules.v4  **Check your IP!!!**
5) iptables-restore < /etc/iptables/rules.v4
