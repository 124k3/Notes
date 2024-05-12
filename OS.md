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
RAM - main menory, HardDrive - secondarey manory).
> The user dosn't access the hardwares directly, The Operating system helps in accessing.

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

> They used to use Punch cards (paperTape/magnetic tape). Those punch cards were converted into batches (similar processed) then those batches were provided to the cpu.

*Major disadvantage*: the cpu remains idle when the process wants some dependencies (may be I/O operation). The next job won't be excted unless the previous process has been excuted. At the time Monitors (Fortram by ibm and ibsys709x) were used

- **Multi-Programmed** : The idea was to put more and more processes inside the main memory (RAM).In multiple program the excution of these processes is non-premptive. multi program focuses on *Idle time* i.e the processes in the RAM were given to cpu 2 cases arise.

> 1. The process dosn't have outside dependencies, in this case the *CPU* will 
excute the whole process.
> 2. The process has dependencies e.g *input output*, in this case the *CPU* 
will go to the **next process**.

- **Multi-Tasking** : Also know as ***Time Shearing***, this is just Multi-program but with premption. The cpu will excute a process for a time and then will excute anoter process. Multi tasking focuses on *responce Time*. There are multiple algorithms to pull this off.

- **RealTime OS** :  The time constrainain is introduced, the delay shouldn't happen. The responce time is fast. It's of two forms 
> 1. Hard : There is no room for lag/delay. Delay will cause Damages to the workflow.
> 2. Soft : The delays to somewhat leavel are acceptable.

- **Distributed** :  The environment where processing is hapenning is dirstributed at multiple places and over a network tey are combined 

- **Clustered** : multiple devices/systems connected over a local network. To manage such complex structure a clustred os is used.

- **Embedded** : which works on the fixed functinality. The changes cannot be made. Once the instructions are set they are not changed.


`Process States`
These are the states/changes a **Process** goes through while being excuted. 
> **Primary State**
>> - **new** : when the process was created.when the process was created and loaded in memory (or stored in Secondary memory).
>> - **Ready Queue** : when the process in the new state was loaded in the main memory i.e RAM. Out of n number of new process only a few are put into the ready Queue and who does it. Its the **Long Term Scheduler**. And this longTermSchedular performs mutliProgramming i.e to load multiple programs in main memory.
>>> Here the process can take two path's.
>>> - **Running** : The process is *patched* i.e scheduled and given to the CPU for excution OR in oter terms 'process get's the cpu'.
 >>>> While excuting the process if another process of higher priority eners the Ready state then the current process will be taken out and Put into the **Ready State**, while the process with high priority would be put in the *RUNNING State*.
 >>> - **Waiting/Block State** : While The execution of the process, if the Process needs some I/O (has to read some data form the secondary memory or hardware with is slow.) the process is put into the **waiting state** and once the I/O operation has been finished, the process is put into the ready queue for it's execution.
>> - **Terminated** : after the process  has been excuted. Deallocation of resources takes place (the memory provided, the I/O devices etc).

> **Addtitonal States**
>> - **Suspend wait or Suspend block state** : when the block state is so much filled so that the ram starvation is going on, the processes are thrown in the **suspended wait/block** i.e they are set back to the secondary state.when the space is free in the wait state then the process can return to it. *This is handled by Medium term scheduler* : its functionality is if ram is getting filled put the processes into the secondary memory.
>> - **Suspend ready state** : if the ready state is filled and the process was already in the wait state, then in such case the process will go into the *suspend ready state*.