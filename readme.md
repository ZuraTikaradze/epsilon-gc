-XX:+UnlockExperimentalVMOptions -XX:+UseEpsilonGC

1. Introduction
Epsilon Garbage Collector (JEP 318): JDK 11 introduced a new garbage collector called Epsilon, which is a no-op garbage collector. 
It is designed for scenarios where memory management is handled externally or for performance testing purposes. 
Epsilon eliminates the overhead of garbage collection, resulting in faster execution for short-lived applications or applications with specific memory requirements.


3. Explanation

In computer science, "No-Op" stands for "No Operation" or "No Operation Performed."
It refers to an operation or function that does nothing or has no effect when executed.
In the context of a garbage collector, a "No-Op Garbage Collector" its refers garbage collection  mechanism
that does not perform any actual garbage collection.

Garbage collection is a crucial process in programming languages with automatic memory management.
It involves identifying and reclaiming memory that is no longer in use to make it available for future allocations.
The garbage collector is responsible for this task.

A No-Op Garbage Collector is trivial implementation of the garbage collector that simply pretends to do the job but does not actually reclaim any memory.
Instead of analyzing the memory usage, identifying unreachable objects, and releasing them, it would effectively skip the entire garbage collection process.

A No-Op Garbage Collector could be used in specific situations where you don't want memory to be reclaimed, or if you want to disable the garbage collector for testing or debugging purposes.
However, in real-world scenarios, a No-Op Garbage Collector would defeat the purpose of automatic memory management and could lead to memory leaks and inefficient memory usage over time.
No-Op Garbage Collector is not typically used in production environments.


2. Demo

This code package (ge.computerscince.Main) creates one-megabyte-arrays in a loop.  it means we allocate 10 gigabytes of memory, which is probably higher than the available maximum heap size.

When we run the  application with the standard VM options, it completes fine,
however if We enable  Epsilon GC  Using Following VM Options  " -XX:+UnlockExperimentalVMOptions -XX:+UseEpsilonGC " 
and when we run the application, we get the following error:

Starting pollution
Terminating due to java.lang.OutOfMemoryError: Java heap space




