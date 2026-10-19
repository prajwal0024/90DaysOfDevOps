## Linux Architecture

Linux architecture can be divided into the following layers:

- **Applications/User Space:** The layer where applications and commands run to perform tasks for users.
- **Shell/System Libraries:** The shell interprets user commands, while system libraries provide functions that applications use to interact with the kernel.
- **Kernel:** The core component that manages system resources and facilitates communication between software and hardware.
- **Hardware:** The physical components of a computer, such as the CPU, RAM, storage, and network devices.

## Process states

A process is an instance of executing a program or command. While these processes exist, they’ll be in one of the five possible states:

- Running or Runnable (R): A process that is currently executing on the CPU or is ready and waiting for CPU time.
- Uninterruptible Sleep (D): A process waiting for certain operations, commonly I/O, to complete and typically not responding to ordinary signals while in this state.
- Interruptible Sleep (S): A process waiting for an event or resource and able to be woken by signals.
- Stopped (T): A process whose execution has been paused, usually by a signal or a debugging operation.
- Zombie (Z): A process that has finished execution but remains in the process table until its parent collects its exit status.

## 5 useful commands

- ps aux: Lists currently running processes along with their users, process IDs, CPU usage, and memory usage.
- top: Displays a live, interactive view of running processes and their CPU and memory usage.
- kill PID: Sends a signal to a process identified by its PID, typically to request it to terminate.
- systemctl: Manages and inspects systemd services, including starting, stopping, restarting, and checking their status.
- journalctl: Displays and filters system logs collected by the systemd journal, helping troubleshoot services and system issues.
