# Day 04 – Linux Practice: Processes and Services

## Environment

- OS: Ubuntu Server on AWS EC2
- Service inspected: SSH (`ssh`)

## Process Checks

### 1. `ps aux | head -n 10`

- **Purpose:** Inspect a sample of running processes.
- **Observation:** PID 1 was `/sbin/init`, and kernel threads such as `kthreadd` and `kworker` were visible.

### 2. `pgrep -a sshd`

- **Purpose:** Find SSH daemon and session processes.
- **Observation:** An SSH listener and multiple SSH session processes were present.

## Service Checks

### 3. `systemctl status ssh`

- **Purpose:** Check SSH service health.
- **Observation:** The service was `active (running)`, with main PID 1017. The output also showed that it was triggered by `ssh.socket`.

### 4. `systemctl list-units --type=service --state=running`

- **Purpose:** List running systemd services.
- **Observation:** 23 running service units were listed, including `cron`, `chrony`, `rsyslog`, and `ssh`.

## Log Checks

### 5. `sudo journalctl -u ssh -n 20 --no-pager`

- **Purpose:** Inspect recent SSH logs.
- **Observation:** Logs showed successful public-key authentication, session creation, connection resets, and a failed key lookup.

### 6. `sudo journalctl -u ssh --since "2 minutes ago" --no-pager`

- **Purpose:** Filter SSH logs by time.
- **Observation:** No matching entries were found in that window. A wider 12-minute window showed earlier events.

## Mini Troubleshooting Flow

1. Checked SSH processes using `pgrep -a sshd`.
2. Verified service status using `systemctl status ssh`.
3. Inspected recent logs using `journalctl -u ssh -n 20 --no-pager`.
4. **Finding:** SSH was running, and logs showed successful connections alongside some connection resets.
