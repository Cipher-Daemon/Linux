# Disable Terminal Verbose

When you are on a linux system and the screen keeps scrolling with output verbose text that is interrupting your work flow type this in the terminal window:

```bash
sudo dmesg -n 1
```

or

```bash
sudo dmesg -D
```

To turn this back on type:

```bash
sudo dmesg -E
```

To fix this on each boot edit the following file `/etc/rc.local`.
