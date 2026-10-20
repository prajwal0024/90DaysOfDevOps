# Day 03 – Linux Commands Cheatsheet

## Process Management

- `ps aux` — List running processes with their resource usage.
- `top` — Monitor processes and CPU/memory usage in real time.
- `kill PID` — Send a signal to a process using its PID.
- `systemctl status SERVICE` — Check the status of a systemd service.
- `journalctl -u SERVICE` — View logs for a specific systemd service.

## Filesystem and Navigation

- `cd /path` — Change the current working directory.
- `pwd` — Print the current working directory.
- `ls -lah` — List files, including hidden files, with details and readable sizes.
- `du -sh /path` — Display the total disk space used by a directory.
- `df -h` — Show available and used filesystem space.
- `mkdir -p path` — Create a directory, including missing parent directories.
- `cp source destination` — Copy files or directories.
- `mv source destination` — Move or rename files and directories.
- `grep "error" app.log` — Find lines containing a specific pattern in a file.

## Networking Troubleshooting

- `ip addr` — Display network interfaces and their IP addresses.
- `ping example.com` — Check network reachability and measure round-trip time.
- `dig example.com` — Query DNS records for a domain.
- `curl -I https://example.com` — Display HTTP response headers from a URL.

## System Information

- `uname -r` — Display the running Linux kernel version.
- `uptime` — Show system uptime and load averages.
- `whoami` — Display the current username.
- `history` — Display previously executed shell commands.
- `clear` — Clear the terminal screen.
