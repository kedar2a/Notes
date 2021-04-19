# Concepts

## Program
> Program is an executable file containing the set of instructions written to perform a specific job on your computer.
- Stored on a disk or a secondary memory on your computer.
- They are read into the primary memory and executed by the kernel.
- Sometimes referred as passive entity as it resides on a secondary memory.

## Process
> Process is an executing instance of a program.
- referred as active entity as it resides on the primary memory
- Several processes may related to same program
- Inter process communication is slow as processes have different memory address.
- Context switching between the process is more expensive.

## Thread
> Thread is the smallest executable unit of a process.
- process can have multiple threads.
- Each thread will have their own task and own path of execution in a process.
- Threads run in the same unique memory heap.
- **All threads of the same process share memory of that process**, hence communication between the threads is fast and context switching is less expensive.
