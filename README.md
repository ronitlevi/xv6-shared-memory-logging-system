# xv6-shared-memory-logging-system
This project extends the xv6 operating system with shared memory support and demonstrates inter-process communication through a multi-process logging system.

## Overview

The project adds the ability for processes to share physical memory pages, enabling efficient communication between processes without copying data.

On top of this mechanism, a concurrent logging system was implemented, where multiple child processes write messages into a shared buffer, and a parent process reads and prints them.

## Features

### Shared Memory
- Mapping physical pages between processes
- Custom system calls:
  - `map_shared_pages`
  - `unmap_shared_pages`
- Proper handling of page alignment and memory size
- Safe memory deallocation using a custom shared page flag

### Multi-Process Logging System
- Multiple processes write to a shared buffer
- Lock-free coordination using atomic operations (`compare-and-swap`)
- Custom message format with headers:
  - Process ID
  - Message length
- Parent process reads and parses messages sequentially

## Technologies

- C
- xv6 (RISC-V)
- Low-level memory management
- Atomic operations

## Key Concepts

- Virtual memory and page tables
- Inter-process communication (IPC)
- Shared memory
- Concurrency and synchronization
- Atomic operations and memory alignment

## How to Run

1. Clone the xv6 repository
2. Apply the project changes
3. Build and run xv6:
   ```bash
   make qemu
4. Run the test program:
    ```bash
   shmem_test
or:
 ```bash
   log_test

## What I Learned
How operating systems manage virtual and physical memory
How to safely share memory between processes
Challenges of concurrent programming without locks
How atomic operations prevent race conditions
Debugging low-level OS code

## Notes
This project was developed as part of an Operating Systems course and focuses on extending kernel functionality and building systems on top of it.
