# Linux Processes and Signals

## Overview

This directory contains Bash exercises for inspecting Linux processes, finding process IDs, sending signals, handling termination, and managing a simple background service. It introduces practical operating-system concepts commonly used in system administration and troubleshooting.

## Exercises

| File | Purpose |
| --- | --- |
| `0-what-is-my-pid` | Prints the current script's process ID. |
| `1-list_your_processes` | Lists running processes with `ps`. |
| `2-show_your_bash_pid` | Finds Bash-related process entries. |
| `3-show_your_bash_pid_made_easy` | Uses `pgrep` to display matching process IDs and names. |
| `4-to_infinity_and_beyond` | Runs a repeating process with a two-second interval. |
| `5-dont_stop_me_now` | Stops the repeating process by matching its command line. |
| `6-stop_me_if_you_can` | Locates and terminates the repeating process using its PID. |
| `7-highlander` | Installs a `SIGTERM` handler and keeps running. |
| `8-beheaded_process` | Forcefully stops the Highlander process. |
| `10-process_and_pid_file` | Writes a PID file and handles `SIGINT`, `SIGTERM`, and `SIGQUIT`. |
| `manage_my_process` | Appends a periodic heartbeat to `/tmp/my_process`. |
| `11-manage_my_process` | Starts, stops, and restarts `manage_my_process` using a PID file. |

An additional exercise variant, `67-stop_me_if_you_can`, is also included in the directory.

## Key Concepts

- **PID:** A numeric identifier assigned to a running process.
- **Signals:** Notifications used to interrupt, stop, or otherwise communicate with processes.
- **`ps` and `pgrep`:** Commands for inspecting and locating processes.
- **`kill` and `pkill`:** Commands for sending signals to processes.
- **`trap`:** A Bash mechanism for executing custom handlers in response to signals.
- **PID files:** A basic technique for tracking a background process.

## Example Usage

From inside this directory:

```bash
chmod u+x 0-what-is-my-pid 1-list_your_processes
./0-what-is-my-pid
./1-list_your_processes
```

To inspect the background-service exercise, review `manage_my_process` and `11-manage_my_process` before running them. The management script uses `/var/run/my_process.pid`, which may require elevated privileges to write.

## Skills Demonstrated

- Investigating running Linux processes.
- Identifying and terminating processes using PIDs and signals.
- Implementing signal handlers in Bash.
- Creating a basic start/stop/restart service-management script.

## Safety Note

Some exercises deliberately terminate processes using `kill`, `pkill`, or `SIGKILL`. Run them only in a disposable practice environment, and verify the processes being targeted. The PID-file service manager is a learning exercise rather than a production-grade init system.

