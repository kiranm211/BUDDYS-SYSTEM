BUDDY SYSTEM IS A MEMORY ALLOCATION METHOD

There are many allocation algorithms.

First Fit

Best fit

Worst fit

Next fit
========================================================================================================================================================================================================================================================================================================================================

First Fit
In the first fit approach is to allocate the first free partition or hole large enough which can accommodate the process. It finishes after finding the first suitable free partition.

Advantage
Fastest algorithm because it searches as little as possible.

Disadvantage
The remaining unused memory areas left after allocation become waste if it is too smaller. Thus request for larger memory requirement cannot be accomplished.
========================================================================================================================================================================================================================================================================================================================================

Best Fit
The best fit deals with allocating the smallest free partition which meets the requirement of the requesting process. This algorithm first searches the entire list of free partitions and considers the smallest hole that is adequate. It then tries to find a hole which is close to actual process size needed.

Advantage
Memory utilization is much better than first fit as it searches the smallest free partition first available.

Disadvantage
It is slower and may even tend to fill up memory with tiny useless holes.
========================================================================================================================================================================================================================================================================================================================================

Worst fit
In worst fit approach is to locate largest available free portion so that the portion left will be big enough to be useful. It is the reverse of best fit.

Advantage
Reduces the rate of production of small gaps.

Disadvantage
If a process requiring larger memory arrives at a later stage then it cannot be accommodated as the largest hole is already split and occupied.
========================================================================================================================================================================================================================================================================================================================================

Next fit
Next fit is a modified version of first fit. It begins as first fit to find a free partition. When called next time it starts searching from where it left off, not from the beginning.
========================================================================================================================================================================================================================================================================================================================================
****WHAT WE IMPLEMENTED****
Buddy's System
In buddy system, sizes of free blocks are in form of integral power of 2. E.g. 2, 4, 8, 16 etc. Up to the size of memory. When a free block of size 2k is requested, a free block from the list of free blocks of size 2k is allocated. If no free block of size 2k is available, the block of next larger size, 2k+1 is split in two halves called buddies to satisfy the request.

Example
Let total memory size be 512KB and let a process P1, requires 70KB to be swapped in. As the hole lists are only for powers of 2, 128KB will be big enough. Initially no 128KB is there, nor are blocks 256KB. Thus 512KB block is split into two buddies of 256KB each, one is further split into two 128KB blocks and one of them is allocated to the process. Next P2 requires 35KB. Rounding 35KB up to a power of 2, a 64KB block is required.

So when 128KB block is split into two 64KB buddies. Again a process P3(130KB) will be adjusted in the whole 256KB. After satisfying the request in this way when such block is free, the two blocks/buddies can be recombined to form the twice larger original block when it is second half buddy is also free.

Advantage
Buddy system is faster. When a block of size 2k is freed, a hole of 2k memory size is searched to check if a merge is possible, whereas in other algorithms all the hole list must be searched.