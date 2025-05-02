# UFW (Uncomplicated FireWall)

Rule Format:

```bash
sudo ufw [allow|deny] from <IP_ADDRESS> to <IP_ADDRESS> port [1-65535] proto [tcp|udp|icmp] comment <ANY_COMMENT_IN_QUOTES>
```

To allow SSH on the server (Assuming IP is 192.168.0.1) from 172.16.0.1

```
ufw allow from 172.16.0.1 to 192.168.0.1 port 22 proto tcp comment "This is an example"
```
