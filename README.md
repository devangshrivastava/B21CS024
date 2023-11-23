# XV Quiz (CSL 3030)

Welcome to the XV Quiz for CSL 3030 - Operating Systems!



## Instructions
- Answer the multiple-choice questions by selecting the correct option.
- For theoretical questions, provide concise and accurate explanations.
- Feel free to use this quiz for self-assessment or educational purposes.

## Multiple-Choice Questions

#### Question 1: Basics
1. What is XV6?
   - a. A programming language
   - b. A Unix-like operating system
   - c. A file system
   - d. An assembly language

#### Question 2: Architecture
2. XV6 is based on which earlier operating system?
   - a. Windows
   - b. Linux
   - c. BSD
   - d. DOS

#### Question 3: File System
3. Which file system is used in XV6?
   - a. FAT32
   - b. NTFS
   - c. ext4
   - d. simple

#### Question 4: System Calls
4. How are system calls implemented in XV6?
   - a. As functions in the C standard library
   - b. As interrupts
   - c. Through the command line
   - d. As external programs

#### Question 5: Processes
5. In XV6, what is the maximum number of processes that can run simultaneously?
   - a. 128
   - b. 256
   - c. 512
   - d. 1024

#### Question 6: Shell
6. What is the name of the shell used in XV6?
   - a. Bash
   - b. Zsh
   - c. Sh
   - d. Fish

#### Question 7: Scheduling
7. How does XV6 handle process scheduling?
   - a. Round-robin scheduling
   - b. Priority-based scheduling
   - c. First-Come-First-Serve (FCFS)
   - d. Random scheduling

#### Question 8: Memory Management
8. Which memory management technique is used in XV6?
   - a. Paging
   - b. Segmentation
   - c. Virtual Memory
   - d. None of the above

#### Question 9: Interrupts
9. How are interrupts handled in XV6?
   - a. Through polling
   - b. Using hardware interrupts
   - c. Using software interrupts
   - d. Both b and c

#### Question 10: Multithreading
10. Does XV6 support multithreading?
    - a. Yes
    - b. No

#### Bonus Question:
11. Who developed XV6?
    - a. Microsoft
    - b. Google
    - c. MIT
    - d. IBM

## Theoretical Questions

#### Question 12: Process States
12. Briefly explain the different states a process can be in within the XV6 operating system.

#### Question 13: File System Structure
13. Describe the structure of the file system in XV6. Include the key components and their roles.

#### Question 14: System Calls vs. Library Functions
14. Explain the difference between system calls and library functions in the context of XV6. Provide examples of each.

#### Question 15: Memory Paging
15. How does memory paging work in XV6? Discuss the benefits of using paging in memory management.

#### Question 16: Shell Commands
16. Name and briefly explain three essential shell commands in the XV6 operating system.

#### Question 17: Process Synchronization
17. Discuss the concept of process synchronization in XV6. Why is it essential, and what mechanisms are used to achieve it?

#### Question 18: Interrupt Handling
18. Explain the role of interrupts in the XV6 operating system. How are interrupts handled, and what is their significance in system operation?

#### Question 19: Virtual Memory
19. What is virtual memory, and how is it implemented in XV6? Discuss the advantages of using virtual memory.

#### Question 20: Boot Process
20. Outline the steps involved in the boot process of XV6. What happens from the moment the computer is powered on to when the XV6 kernel is loaded into memory?

## Answers
Please write your answers here
1. b
2. c
3. d
4. b
5. a
6. c
7. a
8. a
9. d
10. b
11. c

12. 
--> Unused: process is not in use or has been terminated, might be waiting to be assigned to a new program.
--> Embryo: process is in the process of being created but is not yet ready to run, it is still undergoing initialization.
--> Sleeping: process is waiting for an event to occur. This could be waiting for user input, for a file to become available etc.
--> Runnable: process is ready to run and is waiting to be scheduled by the operating system's scheduler. It is in the main memory and can be scheduled to run on the CPU.
--> Running: process is currently being executed on the CPU.
--> Zombie: process has completed execution, but its exit status is still needed by its parent process. The process remains in the system until the parent retrieves its exit status.( similar to that of linux zimbie process)
    
13. XV6 consists of 7 layers
Disk: it reads and writes blocks on an Virtio hard drive.
Buffer cache: It caches the disk blocks and synchronizes them such that only one kernel prcoess modify data at a time.
Logging: it allows the higher layers to wrap updates to several blocks in a transaction, also ensuring that the blocks are updated atomically.
Inode: It provides individual file each called an inode with a unique i-number.
Directory : It implement each directory as a specail type of inode.
Pathname: provide hierarchal file name
File decripter: It abstracts many unix layer (e.g., pipes, devices, files, etc.) using the file
system interface.

15. XV6 uses a two-level page table structure. The top-level page table is pointed to by a register, and each entry in this table points to a page directory.

16. Three shell commands are:
--> ls: displays a list of files and directories in the current directory.
--> cd: Changes the current working directory to the specified directory.
--> cp: Copies files or directories from a source location to a destination.

17. In XV6, process synchronization is vital to prevent race conditions and ensure data consistency in a multi-process environment. Locks provide mutual exclusion for critical sections, semaphores control access to shared resources, and conditional variables allow processes to wait for specific conditions. These mechanisms safeguard against deadlocks, coordinate process execution, and maintain the integrity of shared data, contributing to the overall stability and reliability of the operating system.

18. Interrupts play a crucial role in XV6 by allowing the operating system to respond to events asynchronously. When a hardware event or exceptional condition occurs, an interrupt is triggered, causing the CPU to suspend its current task and execute an interrupt service routine. XV6 handles interrupts by using an interrupt descriptor table. Significantly, interrupts enable efficient event-driven processing, supporting timely responses to external events and improving overall system responsiveness and functionality.

19. Virtual memory in XV6 is a memory management technique that provides processes with an illusion of a larger address space than physically available. It is implemented using paging, where virtual addresses are mapped to physical addresses through page tables. This allows efficient use of physical memory and enables processes to execute in a contiguous address space. Advantages include improved process isolation, simplified memory allocation, and the ability to run larger programs than the available physical memory allows.

20. In the XV6 boot process, the computer is powered on, and the firmware (e.g., BIOS) loads the bootloader (e.g., GRUB). The bootloader then loads the XV6 kernel from the storage device into memory. The kernel initializes essential data structures, sets up page tables, configures devices, and starts the first user-level process. Finally, control is transferred to the user process, marking the completion of the boot process and the initiation of the operating system's functionality.
