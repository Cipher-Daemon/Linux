# Hex to File

```bash
echo "[HEX Code]" | xxd -r -p
```

Valid examples:

```bash
echo "41 61"|xxd -r -p
```

```bash
echo "4161"|xxd -r -p
```

If done correctly it'll ooutput the following:
```
Aa
```

Also note hex characters are not case sensitive when running the command syntax above so "4A" and "4a" will still output the capital letter "J" in the terminal.
