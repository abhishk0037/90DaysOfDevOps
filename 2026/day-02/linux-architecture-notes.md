# Linux Architecture Notes

## Kernel

- The kernel is the core component of the operating system.
- It acts as the interface between hardware and user-space processes.
- The Linux kernel is the first program loaded during boot and the last one to stop.
- It is written in C and maintained by the Linux community, originally started by Linus Torvalds.

### Kernel responsibilities

1. Memory management
2. Process management
3. Device driver management
4. System calls and security

### Check kernel version

- `uname -r`
- `uname -a`

## User Space

- User space is a restricted area of memory where user applications run.
- Examples: C programs, Java applications, Docker containers, web servers.
- User programs cannot directly access hardware or kernel memory.
- They use system calls to request services from the kernel.

## Example: `ls -l`

1. `ls` runs in user space.
2. It requests a directory listing through a system call.
3. The kernel checks permissions and reads file information from disk.
4. The kernel copies the data back to user space.
5. `ls` displays the output.

> The user program never accesses disk hardware directly.

## systemd

- `systemd` is the first user-space process started by the kernel.
- It has PID 1.
- It is responsible for starting and managing system services.

## Process States

- **Running (R)**: Process is actively using the CPU.
- **Sleeping (S)**: Process is waiting for an event or resource.
- **Stopped (T)**: Process execution is paused.
- **Zombie (Z)**: Process has finished execution but still remains in the process table.

## Common daily commands

- `ls -lh`
- `cd`
- `pwd`
- `vi`
- `mkdir -p`
