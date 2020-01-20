# Reasons for concurrency and parallelism


To complete this exercise you will have to use git. Create one or several commits that adds answers to the following questions and push it to your groups repository to complete the task.

When answering the questions, remember to use all the resources at your disposal. Asking the internet isn't a form of "cheating", it's a way of learning.

 ### What is concurrency? What is parallelism? What's the difference?
- Concurrency means multiple computations are happening at the same time. 
- Parallel computing is a type of computation in which many calculations or the execution of processes are carried out simultaneously. 
- Concurrency is the composition of independently executing processes, while parallelism is the simultaneous execution of (possibly related) computations. 

 ### Why have machines become increasingly multicore in the past decade?
- In order to continue to increase CPU performance, machines have become increasingly multicore in the past decade since we have reached "the limit" in terms of increasing clock frequency, power consumption and generated heat.

 ### What kinds of problems motivates the need for concurrent execution?
 (Or phrased differently: What problems do concurrency help in solving?)
- More optimal use of the CPU resource, i.e. the problem can be solved more effectively.
 
 ### Does creating concurrent programs make the programmer's life easier? Harder? Maybe both?
 (Come back to this after you have worked on part 4 of this exercise)
 > *Your answer here*
 
 ### What are the differences between processes, threads, green threads, and coroutines?
- A process is the instance of a computer program that is being executed by one or many threads. 
- A thread of execution is the smallest sequence of programmed instructions that can be managed independently by a scheduler, which is typically a part of the operating system. 
- Green threads are threads implemented at the application level rather than in the OS. This is usually done when the OS does not provide a thread API, or it doesn't work the way you need. Thus, the advantage is that you get thread-like functionality at all. The disadvantage is that green threads can't actually use multiple cores.
- Coroutines are computer program components that generalize subroutines for non-preemptive multitasking, by allowing execution to be suspended and resumed.
 
 ### Which one of these do `pthread_create()` (C/POSIX), `threading.Thread()` (Python), `go` (Go) create?
- pthread_create(): Creates a new thread (C/POSIX)
- threading.Thread(): Creates a new thread (Python)
- go: Creates a new thread, i.e. a gowroutine (Go)
 
 ### How does pythons Global Interpreter Lock (GIL) influence the way a python Thread behaves?
- The Python Global Interpreter Lock or GIL, in simple words, is a mutex (or a lock) that allows only one thread to hold the control of the Python interpreter. This means that only one thread can be in a state of execution at any point in time.

 ### With this in mind: What is the workaround for the GIL (Hint: it's another module)?
- By using multiprocessing, we are utilizing the capability of multiple processes and hence we are utilizing multiple instances of the GIL
 
 ### What does `func GOMAXPROCS(n int) int` change? 
- The GOMAXPROCS variable limits the number of operating system threads that can execute user-level Go code simultaneously. 
- GOMAXPROCS sets the maximum number of CPUs that can be executing simultaneously and returns the previous setting. If n < 1, it does not change the current setting. The number of logical CPUs on the local machine can be queried with NumCPU. This call will go away when the scheduler improves.
