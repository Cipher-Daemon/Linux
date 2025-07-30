# CSV Export

To export logs from the past 30 days
```sql
sqlite3 /etc/pihole/pihole-FTL.db -header -csv "Select * from queries where timestamp > strftime('%s','now','-30 days');" > ./export.csv
```

To export specific client IPs 
```sql
sqlite3 /etc/pihole/pihole-FTL.db -header -csv "Select * from queries where timestamp > strftime('%s','now','-30 days') and (client like '192.168.2.17' or client like '192.168.2.15');"
```
