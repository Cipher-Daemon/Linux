# How To

If you come from Windows you know when you want to launch a command it'll execute a process and once it finishes launching you can still use the same CMD window, in Linux you can still do that with some workarounds

Run the `setsid` command followed by a program (say `firefox`) and redirect the output to the null device.

Example

```shell
setsid firefox &>/dev/null
```

Once done you can use the same terminal window freely while your program is running, you can even close the terminal window and it will not close the program that you called to launch.
