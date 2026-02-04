**Day 02 – Linux Architecture, Processes, and systemd**

**Task Done**

**- The core components of Linux (kernel, user space, init/systemd)**
- **Kernel:** The Linux kernel is the central component, acting as the bridge between the hardware and the software. It manages the system's resources, including memory, CPU access, and peripheral devices, and facilitates communication between hardware and processes.
**User Space:** This is the environment where all applications, system libraries, and user programs run. The kernel enforces isolation between different processes in user space to maintain system stability and security. Key elements include the GNU C Library (glibc), which provides essential system call interfaces, and various system utilities and desktop environments like GNOME.
**Init System:** Ubuntu, like most modern Linux distributions, uses systemd as its init (initialization) system and service manager [1].
Init (Initialization): This is the first process the kernel starts after booting. It is responsible for bringing the system into a functional state, including mounting file systems and starting other essential services.
**systemd:** It manages system processes after boot, handling service startup and shutdown, logging, and daemon management. It is designed for parallel processing of services during startup, which helps achieve faster boot times.

**- How processes are created and managed.**
**- In Linux**, processes are created using the fork() system call (creating a child process identical to the parent) and the exec() system call (loading a new binary into the process's memory space). The kernel manages these instances using unique Process IDs (PIDs), scheduling them based on states like running.

**-What systemd does and why it matters**
**-Systemd** is the default system and service manager for most modern Linux distributions, acting as the first process (PID 1) to boot the user space, manage services, and control system state. It improves efficiency by enabling parallel service startup, managing dependencies, handling logging via journald, and using systemctl for centralized control. 

