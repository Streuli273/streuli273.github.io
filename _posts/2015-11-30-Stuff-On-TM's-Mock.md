---
title: Stuff On TM's Mock
layout: post
author: streuli273
source-id: 1BY9VzbdDymmkjn6Hz5s9hq-GMgovtyHOh3FKVkZinlY
published: true
---
**Stuff On TM's Mock**

**No full stops at the end of bullet points**

* **1.1.3.****_x_** Input, Output and Storage Devices

    * (n)ez(n+2)me let n=2 ez pz lmn sqz

    * Discrete or automatic

        * Discrete - non continuous input of data (mouse button 1)

        * Automatic - continuous input of data (temperature sensor, webcam, mouse)

    * RAM / ROM

        * RAM - Random access memory

        * ROM - Read only memory

            * Used for data that you do not want to be change (program on a disk)

            * Used to store bootstrap program which "gets the system going". It goes through a POSTing sequence (checks) and initialises the OS. ? POSTing refers to Power On Self Test-ing

* **1.2.1.****_a_*** *The need for, function and purpose of operating systems

    * Purposes

        * To manage and control the system's hardware  

        * To manage the running, installation and removal of programs 

        * To provide an interface between human and computer (HCI) 

        * To manage the system's memory  

        * To facilitate interrupt handling (see 1.2.1.c) 

        * To schedule jobs  

        * To provide and manage the security of the system  

        * To facilitate spooling (simultaneous peripheral operations online)   

* **1.2.1.****_b_** Memory management

    * Two different types of memory management:

        * Paging - Memory is **physically** divided into **equal sized** blocks, and programs/data are allocated one or more block

            * This can lead to a lot of wasted space because blocks are very rarely full - very inefficient

            * Blocks do not have to be next to each other (contiguous)

            * Blocks can be any size but are often not much larger than a few KB otherwise lots of space is wasted

        * Segmentation is where memory is divided logically into three segments:

            * Instructions, data and a stack for subroutines/interrupts

            * The program segment is constant in size as this will not change, but the other two can change in size if they need to, meaning a lot less space is wasted

        * Virtual memory is used when primary memory is full and no more data can be loaded into it, then virtual memory comes into play

            * This is where data in primary memory not currently in use is copied across to the secondary memory, freeing up space for new instructions/data to be put in that space

            * When the memory copied into secondary is needed, it is swapped for something not in use

            * This results in disk thrashing as the hard drive is constantly having data read and write to it, which can damage the hard drive if used constantly

            * Also, virtual memory is slow as moving data to and from the hard drive is very slow

* **1.2.1.****_c_** Interrupt handling

    * Types of interrupts

        * hardware interrupt: a hardware device needs attention. For example, a printer buffer may need filling, or a power off button has been pressed, facilitating a shutdown of the system  

        * software interrupt: a program needs attention because something has gone wrong or because access to an input/output device is required. For example, software interrupts are used to trap exceptions, handle division by zero and to request data from a storage device  

        * timer interrupt: certain processes need regular attention, and interrupt the processor on a timed basis in order to be fulfilled. For example, updating the screen, or reading from a sensor

    * The interrupt service routine

        * After each instruction has been executed the processor looks to see if any interrupts have been received  

        * If an interrupt has been received, then the OS checks to see if the interrupt has a higher priority than the current job   

        * If the received interrupt has a lower priority it is placed in a queue to be handled when the current job has finished  

        * If the received interrupt has a higher priority then the contents of the program counter and other registers are copied and placed in a stack. The program counter is then set to  the address of the interrupting job and that job is executed until it is completed, or a higher priority interrupt is received. When the interrupt is finished, the previous job is copied from the stack, placed into the program counter and registers and processing continues with that job as before  

        * It is possible for the processor to receive a series of higher priority interrupts. If this happens, each interrupted job is placed on the stack and resumed once the higher priority job is completed

* **1.2.1.****_d_** Scheduling

    * Determines the order in which processes are performed

        * Can be done in many different ways:

            * Round robin (RR)

            * First come first served (FCFS)

            * Shortest job first (SJF)

            * Shortest time remaining (STR)

            * Multi-level Feedback Queues (MFQ)

                * This is where you have lots of queues and jobs can be moved to a lower or higher priority according to their needs

    * Incorrect use of scheduling leads to processes starvation - a process is never given to the processor because it is always pushed to the back of the queue (a long job when using SJF

* **1.2.1.****_e_** Distributed, embedded, multi-tasking, multi-user and real time operating system

    * Types of OS

        * Single user - one user

        * Multi user - several users

        * Single-tasking - one application at a time

        * Multi-tasking - several concurrent applications - timesharing

        * Distributed - control and coordinate several computers simultaneously and assign them individual tasks. User sees a single system

        * Embedded - within a specific device, e.g. TV, ATM, car. Usually has one/few jobs

        * Real-time - designed to carry out actions within a guaranteed amount of time Response time is usually a fraction of a second. Often used in safety/critical systems e.g. autopilot

* **1.2.1.****_f_** BIOS

    * *Basic input/output system*

    * The computer looks into the BIOS when it is powered on, the program counter points towards the BIOS' memory

        * The BIOS checks if the system is functional, has accessible memory and that the processor is functioning 

        * This is called the power-on self test (POST) 

        * The bootloader is then loaded in order to load the OS

    * Is stored in flash memory as it occasionally needs to be updated

* **1.2.1.****_g_** Device Drivers

    * Operating systems are expected to communicate with a wide variety of devices, each with different models and manufacturers. It would be impossible for the makers of operating systems to program them to handle all existing and future devices. This is why we need device drivers

    * A device driver is a piece of software, usually supplied with a device, that tells the operating system how it can communicate with the device

* **1.2.1.****_h_** Virtual Machines

    * Can be virtual processes or virtual systems

        * Processes are a single program, system is the whole system (game emulation)

    * Java uses a virtual machine to compile the bytecode so a single program can be run on multiple different OSs)

    * Virtual machines allow you to make one machine act as many, useful in servers

