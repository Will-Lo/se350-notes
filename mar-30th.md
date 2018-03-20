# March 20 2018

### Disk Scheduling Policies
#### First in, first out
- Process requests sequentially
- Fair to all processes
- Approaches random scheduling in performance if there are many processes
- **Pros**:
    - Easy to implement
- **Cons**:
    - Slow

#### Priority based scheduling
- Goal is not to optimize disk but meet other objects
- Other goals include prioritizes short batch jobs, deadlines, etc.
- Can lead to starvation

#### Last In first out
- Good for transaction processing systems
    - Device is given to most recent user, so little disk arm movement
- Possible starvation

#### Shortest Seek Time First
- Select disk I/O request that requires the least movement of the arm to its current position
- Always chose minimum seek time
- **Cons**: 


#### SCAN
- Arm moves in one direction only, satisfying all outstanding requests until it reaches the last track in the direction and reverses it
- Need to know/assume initial direction
- **Pros**:
    - Reasonable performance
    - No starvation
- **Cons**:


#### C-SCAN
- Restricts scanning to *one direction only*
- When the last track has been visited in a direction, the arm returns to the opposite end of the disk and scan begins again
- **Pros**:
    - Deterministic
    - Reduces delay for new requests
    - Good for real-time systems
- **Cons**:
    - Slower than SCAN

#### N-step-SCAN
- Optimizes SCAN
- Segments disk request queue into subqueues of length N
- Processes subqueues using SCAN


### RAID (Redundant Array of Independent Disks)
- Organize data which redundancy can be added to improve reliability
- Allows for recovery 
