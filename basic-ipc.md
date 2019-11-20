## Race Conditions
The first process that reaches the critical reigion is allowed to go through the code the other isn't.

## Disabling Interrupts
### i.)
Because when you are disabling interrupts  you only do it for one processor so the other process will just run on an other processor.

### ii.)
If the process fails on a single core machine the computer isn't able to start another process

## Peterson's Solution

### i.)
#### Scenario 1
*process 1 is within the CR
*process 1 calls leave_region()

#### Scenario 2
*one of the processes will be slower and is saved as the loser
(lets say 1 is the loser)
*process 0 and 1 and will check the condition of the while loop
*proces 0 is within the CR and process 1 is remaining in the loop
*process 0 calls leave_region()
*process 1 is  within the CR
*process 1 calls leave_region()

### ii.)
process=pr
*pr0 goes over the while-loop because turn is 0
*pr1 is within the while-loop because turn is 0
*pr0 is within the CR
*turn is now 1
*pr0 leaves the CR
*pr0 is within the while-loop because turn is 1
*pr1  is within the CR
*turn is now 0
*pr1 leaves the CR
*pr0 will now make the same thing again but then it will remain in the while-loop because  pr0 has to wait that for pr1. But pr1 is called 1 time a minute and pr0 is called 8 times a minute

### iii.)
i have explained the meaning in i.),
the conditions of the for loop says that the loser has to wait if the other process is interested.

### iv.)
