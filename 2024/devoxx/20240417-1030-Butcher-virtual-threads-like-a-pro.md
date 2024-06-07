
# Butcher Virtual thread

## Main info
45' by Piotr Pryzbyl (Elastic)

lien de la conf: https://www.youtube.com/watch?v=8ZtYOTUU6d8

TL;DR: 
Virtual threads are one of the main features in java 21. This talks shows how NOT to use virtual threads.
It is useful for introducing the new feature and avoid common pitfalls. 
Also introduces the concept of structured concurrency to start tasks in parallel avoiding thread leaks and callback hell.

negatives:
- speaker is way too fast
- pb with demo and slides
- 

## Notes

Java threads were mapped (in a one to one relationship) with OS threads. With lot of threads, we exceed limit of computer. => To avoid this pb we have Virtual Threads
Enable to have "reactive" app without using reactive stack.

OS threads are slow, if we want to increase perf by avoiding blocked threads we had to use reactive stack (Mono, Flux...). 
But this is impossible to debug (trust me, 2 years using it with SNCF). With Java 21 we have the benefits of reactiv apps with imperativ coding (thanks to virtual threads).

Virtual threads:
- cheap to start
- carried by OS threads
- always daemon threads (threads with low priority that won't stop the JVM from exiting when program finishes)

To fully grasp the concept of virtual threads, we ccan use the analogy of taxi in a city.
The taxies are the OS threads and the virtual threads are the clients. 

You can take a taxi from A to B to do smtg and then take a taxi from B to C. But you don't need the taxi to wait for you while doing smtg at B. It can take someone else and drive him around and come back when you're ready for the second part of your journey

ATTENTION: Using Virtual Threads will not make your app faster ! It will just scale better (still good though)

We can create virtual threads the same way we used to create threads:
- Threads.ofVirtual(Runnable n).start();
- using ExecutorService (if you don't know what it is OCP 17 chap 13)

What not to do:
- reuse virtual threads / pooling
- pin (wait for a VT -> completely blocks the the thread. If you block a virtual thread, it works as a common java thread (see virtual thread as mechanical stairs, if it does not work, it is just traditionnal stairs)

To be able to detect pinning we can use JFR (Java Flight Recorder). We can use it for example to detect pinning during a call to an api/io.
We can easily do it intests but it is important to delay request/op to see the pinning (if it is too fast it is not detected) +> use tools such as toxiproxi

WARNING: do not use monitors inside virtual threads. Monitoring VT induces IO in the threads => PINNING

**Scoped Variables**
variables shared by VT ? Works as long as variables are not mutable ? 

** Structured Concurrency**
Not uncommon bug to have 2 clients connecting at the same time and one client seeing the info of another

The idea of structured concurrency is to start several process at the same time in // and wait for all results to do smtg
Using structured concurrency we can aoid thread leaks. We can use it to do // tasks and avoid future and callback hell (one thread must tell all the other that process is interrupted...)
With structured concurrency you can stop all // threads that are INTERRUPTABLE easily and avoid computing for nothing
