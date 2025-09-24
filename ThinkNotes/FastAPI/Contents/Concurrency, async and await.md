
## Asynchronous Code
Asynchronous code means that the language has a way to tell the computer that at a some point in code it will have to wait for *something else* to finish somewhere else. Lets say *something else* means *slow-file*.
At this time the computer can finish and do some other work while *slow file* finishes its work.

**For Example:** *If we go to hotel and there is a long queue at that time I will go to do some other work during that time and again join the hotel queue.*

Asynchronous helps in solving IO bound tasks. This task mainly consist of :
- The data from the client sent over the network
- The data sent to the client
- The contents of file in the disk to be read by the system and given to your program
- a remote API operation
- a database operation to finish 
- to query the DB to return the results.

This is called asynchronous because the computer/program doesnt have to be synchronized with the slow task, waiting for the task to finish and then continue the work.

Asynchronous sometimes called "concurrency". It is different from "parallelism".

## Async and Await
The key here is the *await*. It tells the pyhton it has to wait for fucntion to finish doing its thing before storing the results in the variable. With that, python know it can go and do something else in the meanwhile.

For *await* to work it has to be inside a function that supports this asynchronicity. To do that, you just declare it with async def.

With the *async def*, Python knows that, inside the function, it has to be aware of the await expressions, and it can "pause" the execution of that function and go do something else before coming.

The functions with *async def* can only be called inside the *async def* functions.