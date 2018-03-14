# January (18-23)-18
## Tables
#### Memory tables
- Keep track of main and secondary (virtual) memory
- Stores allocation of main memory and secondary memory to proceses
- Has protection attributes for shared memory
        
#### I/O Tables
- Used by the OS to manage I/O devices
- Status of I/O Operations
- Location in main memory being used as the source of destination

#### File Tables
- Existence of files
- Location in secondary memory
- Status, attributes (permissions)

#### Process tables
- Where process is stored in memory
- Attributes of process image
- Stack, Program, Data
- PCB (allows cross referencing to other tables)
 
___
 
## Processes
** A Process can be charactered by:**
- **Identifier:** A unique identifier associated with this process, to distinguish it
from all other processes.
    - Also stores parent IDs (process that made this one), user identifier
- **State:** If the process is currently executing, it is in the running state.
    - User visible registers
    - Control and Status registers
- **Priority:** Priority level relative to other processes.
- **Program counter:** The address of the next instruction in the program to be
executed
- **Memory pointers:** Include pointers to the program code and data associated
with this process, plus any memory blocks shared with other processes.
- **Context data:** These are data that are present in registers in the processor
while the process is executing.
- **I/O status** information: Includes outstanding I/O requests, I/O devices (e.g.,
disk drives) assigned to this process, a list of files in use by the process, and
so on.
- **Accounting** information: May include the amount of processor time and clock
time used, time limits, account numbers, and so on

Stored in a **Process Control Block** (PCB)

#### Two State Process Model
- Every process is either running or not running
    - Need to know about the current state of each process, where they're stored in memory
    - Other processes not running are stored in a queue
    
#### Process Creation
4 Reasons of process creation:
1. **New batch job** - process is created to respond to a request
2. **Interactive log on**
3. **Created by OS to provide a service**
4. **Spawned by exiting processes**
- Only case where one process is responsible for creating another 


### 5 State Model
1) **New** - OS is aware of a new process but hasn't devoted resources into the execution of the process
2) **Ready**
3) **Running**
4) **Blocked**
5) **Exit**

Some transitions we care about:
**Ready -> Running**: Decided by process scheduler
**Running -> Ready**: process has reached max allowable time allocated for an process execution for multiprogramming


**Have a blocked queue for every event that processes are waiting on**

___
## Context Switching
#### When?
1. Interrupts
2. Memory fault
3. Traps (error or exception)
4. Supervisor call

####Steps
1. Save context of the processor (PC, other registers)
2. Update the PCB of the process in the running state (change state to appropriate state)
3. Move PCB to ready, blocked, ready/suspend
4. Select a new process to be executed, change its state
5. Update memory management structures
6. Restore old process (eventually)


