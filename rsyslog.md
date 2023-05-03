# rsyslog

rsyslog (or syslog) is a useful service running on a server to gather logs from devices that are able to dump logs to a server of its choice.

## Prerequisites

Make sure that your server rsyslog service is set to enabled on system boot, you can run the follwoing to enable this:

```bash
systemctl start syslog
systemctl enable rsyslog
```

Verify that its running by running this:

```bash
service --status-all
```

You should see the "+" sign beside rsyslog that looks like this:

```
[ + ]  rsyslog
```
If you are running a firewall on the server make sure to allow port 514 (default) for TCP and/or UDP to allow incoming traffic.

## Configuring Basic Syslog Server

Open the terminal as root and edit the following file to get syslog to work:

```BASH
nano /etc/rsyslog.conf
```

### Configuring Listening Port And Protocol
For now we are only going to uncomment which protocol we are going to enable, for this instance we are going to enable UDP which is the most common. If for some reason it needs to run under TCP uncomment for that as well.

Before:

```
#module(load="imudp")
#input(type="imudp" port="514")
```

After:

```
module(load="imudp")
input(type="imudp" port="514")
```

### Configuring Dump Files

For this example assuming that you want to dump files to the /var/log/remotelogs directory and each host/IP gets its own folder with the respected application name you'll configure the following (Note: Completely optional, you can add the ###CUSTOM### field so you know the changes/customizations that you added for easy reading)

At the bottom of the configuration file add this:

```
$template RemInputLogs, "/var/log/remotelogs/%FROMHOST-IP%/%PROGRAMNAME%.log"
*.* ?RemInputLogs
```

After Chages have been made restart the syslog service for chnages to kick in:

```bash
systemctl restart rsyslog
```
