# Message Of The Day

Everytime you log into a ubuntu server via console or SSH you see a message like this:

```
Welcome to Ubuntu 20.04.6 LTS (GNU/Linux 5.4.0-200-generic x86_64)

 * Documentation:  https://help.ubuntu.com
 * Management:     https://landscape.canonical.com
 * Support:        https://ubuntu.com/pro

 System information as of Sat 01 Jan 2000 08:00:00 PM EST

  System load:              0.08
  Usage of /:               75.7% of 228.11GB
  Memory usage:             8%
  Swap usage:               0%
  Processes:                140
  Users logged in:          0
  IPv4 address for enp0s25: 192.168.X.X
  IPv6 address for enp0s25: ::1
  IPv6 address for enp0s25: ::1

 * Strictly confined Kubernetes makes edge and IoT secure. Learn how MicroK8s
   just raised the bar for easy, resilient and secure K8s cluster deployment.

   https://ubuntu.com/engage/secure-kubernetes-at-the-edge

Expanded Security Maintenance for Applications is not enabled.

0 updates can be applied immediately.

Enable ESM Apps to receive additional future security updates.
See https://ubuntu.com/esm or run: sudo pro status
```

You can add, change or replace the message by editing or adding files to the `/etc/update-motd.d` directory.

Each file is process by its respected number to it can process in the correct order.
