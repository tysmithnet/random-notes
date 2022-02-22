# Virtual Memory
20220221193436

#memory #virtualmemory #os #cpu

Memory management technique that presents alternate memory addresses to executing processes that map to addresses in physical memory

## Summary
- cpu must support virtual memory by having a memory management unit (mmu)
    - operating system can configure the mmu to map some page of virtual memory to some page of physical memory
- allows process to use more memory than physically available
- allows sum of all processes to use more memory than available
- makes sharing of memory trivial for shared libraries
- virtual addresses are unique per process
- physical addresses are unique per machine
- mmu is needed because it would be too slow to translate every virtual address to physical address through the os
    - specifically the translation lookaside buffer (tlb) is the cache that has the mapping

##  Example
- cpu instruction that requires memory address is executed
- tlb is searched first for the virtual memory address
    - if found, it is returned
- if not there, the mmu or os will look in the page table to see if a mapping exists (page walk)
    - if found, written back to the tlb and address is returned
- if not there, **page fault** is triggered