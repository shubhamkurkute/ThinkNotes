In python memory allocation and deallocation is handled automatically by the garbage collector.

#### Garbage Collection 
Garbage collection is the process in which the interpreter frees up the memory when not in use to make it available for the other objects. So the case in which no reference is pointing toward the object on the memory than the virtual machine has the garbage collector which deletes the object from the heap memory.

#### Reference Counting
- Reference counting works by counting the number of times the object is referenced by other objects int the system. 
- When the references to an object is removed, the reference count for an object is decremented.
- When the reference count becomes zero, the object is deallocated.


#### Memory Allocation in Python
There are two parts of memory:
1. Stack Memory
2. Heap Memory

The methods/method calls and the references are stored in stack memory and the values and the objects are stored in the private heap memory.
