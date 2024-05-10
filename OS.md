# OPERATING SYSTEM
---
> From ***exam point*** of view. 
## Important Topics:
    - Basics.
        - types.
        - processes.
        - diagram.
        - system call.

    - Process Scheduling.
        - Scheduling Algorithm's.
            - FIFO.
            - SJF.
            - Round Robbin.
            - Premptive.
            - ... and more.

    - Process Synchronization.
        - Semaphore.
        - Peterson's algorithm

    - Dead lock and threads.
        - Bankers algorithm.

    - Memory Management.
        - Paging
        - segmentaion
        - fragmentation (internal, external).
        - virtual Memory.
        - page replacement algorithms.

    - Disk Scheduling.
        - scan algorithm
        - c-scan algorithm
        - ... (more)

    - Unix Commands.
        - ls, mkdir, cd, chmod (simple commands)
        - open system calls

    - File Management and Security. 
        - algorithms to fetch data from file.
            - sequential access.
            - random access.
            - linked access.

---

# Operating System and Functions

Operaing System is a software which acts as an intermediate between the user's
and the Hardware(Cpu- the brain, I/O devies - keyboard mouse scanner,
RAM - main menory, HardDrive - secondarey manory.
> The user dosn't access the hardwares directly, The Operating system helps in 
accessing.

- The primary goal of the operating system is to provide convenicnce to the
user.
- Throughput: number of tasks excuted per unit time. The more task are being 
excuted the mroe the through put.

`Functions of OS`
- resource Managemet: which user should provide how much hardware and for what 
time. mostly used in parallel processing (multiple users accessing
the same device), to maintain the load.
- cpu scheduling: how the process is excuted on the CPU, in the most efficient
way
- storage managemet: It constans the secondary device (HardDrive). Done using 
fiel system (common interface and network interface file system). like how the 
data comming is to be stored in the hardrive perminantly.
- memory Mangaement: It's the RAM (ram is limited) first the processed goes to
the ram. then those processes are sent to the cup. How much ram should be 
allocated and then with time it should be rellocated via swap.
- Security and Privacy: It authenticate the user. It wont allow one process to 
interfare with the other process.

> **Operating System** work's on System call's

`Types of Operating System`

- Batch

> They used to use Punch cards (paperTape/magnetic tape).
Those punch cards were converted into batches (similar processed)
then those batches were provided to the cpu.
**Major disadvantage**: the cpu remains idle when the process wants some 
dependencies (may be I/O operation). The next job won't be excted unless 
the previous process has been excuted. At the time Monitors (Fortram by ibm 
and ibsys709x) were used


- Multi-Programmed

> The idea was to put more and more processes inside the main memory (RAM).
In multiple program the excution of these processes is non-premptive. 
multi program focuses on *Idle time*
i.e the processes in the RAM were given to cpu 2 cases arise.

>> 1. The process dosn't have outside dependencies, in this case the *CPU* will 
excute the whole process.
>> 2. The process has dependencies e.g *input output*, in this case the *CPU* 
will go to the **next process**.


- Multi-Tasking
> Also know as ***Time Shearing***, this is just Multi-program but with 
premption. The cpu will excute a process for a time and then will excute anoter
process. Multi tasking focuses on *responce Time*.
There are multiple algorithms to pull this off
- 
