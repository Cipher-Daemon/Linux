# UFW (Uncomplicated FireWall)

## Rule Format

```bash
sudo ufw [allow|deny|reject] from <IP_ADDRESS> to <IP_ADDRESS> port [1-65535] proto [tcp|udp|icmp] comment <ANY_COMMENT_IN_QUOTES>
```

## Example Rule Creation
By default rules are added at the bottom

To allow SSH on the server (Assuming IP is 192.168.0.1) from 172.16.0.1

```
ufw allow from 172.16.0.1 to 192.168.0.1 port 22 proto tcp comment "This is an example"
```

To create Rules at the very top run:

```
sudo ufw prepend RULE
```

To insert at a specific spot as a number:

```
sudo ufw insert NUM RULE
```


## List Rules numbered

```bash
sudo ufw status numbered
```

Output will be:

```
Status: active

     To                         Action      From
     --                         ------      ----
[ 1] 192.168.0.1 22/tcp      ALLOW IN    192.168.0.0/24           
[ 2] 192.168.0.2 514/tcp     ALLOW IN    192.168.0.1
[ 3] 192.168.0.3 514/udp     ALLOW IN    192.168.0.1 
```

# Delete Rules

Rule list

```
     To                         Action      From
     --                         ------      ----
[ 1] 192.168.0.1 22/tcp      ALLOW IN    192.168.0.0/24           
[ 2] 192.168.0.2 514/tcp     ALLOW IN    192.168.0.1
[ 3] 192.168.0.3 514/udp     ALLOW IN    192.168.0.1 
```

Say we want to delete Rule 3 we would type:

```
sudo ufw delete 2
```

## Restart The Firewall Service

Simply run these 2 commands:

```
sudo ufw disable
sudo ufw enable
```
