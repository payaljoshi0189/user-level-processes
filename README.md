This project implements creation of user-level processes and implementation of 2 system calls namely SystemShutdown() and Exec().

At a high level the logic for the implemented system calls is as follows:

1. ``` Sys_Exec ()``` :  Read a new executable program from disk and copy it into the address space of the process which invoked the Exec. Begin execution of the new program and  overwrite the address space of the parent process.

2. ```Sys_Shutdown()```: This function causes an immediate shutdown of the kernel. It will not return.

Creating User-Level processes:

To initiate a user-level process following methods are implemented:

1. ```InitFirstProcess()```: This function calls ThreadManager's GetANewThread () method to request for a resource thread, initializes the Thread returned by ThreadManager and calls a Fork on it to execute 'StartUserProcess' function.

2. ```StartUserProcess()```: Newly acquired 'UserProgram' thread executes this function.