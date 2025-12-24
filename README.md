# Multithreading-In-Java

🧵 Java Multithreading – Complete Guide

This repository documents my complete learning of Java Multithreading from Vipul Tyagi (Engineering Digest).
Earlier, I had basic knowledge, but after this learning, I now clearly understand how threads work internally, how CPU scheduling happens, and how real-world concurrent systems are built.

📌 What is Multithreading?

Multithreading allows multiple threads to run concurrently within a single process.
It helps in:

Better CPU utilization

Faster execution

Improved application performance

A thread is the smallest unit of execution inside a process.

🧠 Process vs Thread
Process	Thread
Independent execution unit	Sub-unit of a process
Has its own memory space	Shares memory
Heavy-weight	Lightweight
Slower context switching	Faster context switching
⚙️ Program Execution Flow

A process starts when a program runs.

Inside a process, multiple threads can execute.

CPU uses time slicing to switch between threads.

Context switching occurs when CPU switches execution between threads.

⏱️ Time Slicing & Context Switching
Time Slicing

Each thread gets a small slice of CPU time.

Context Switching

The CPU saves the state of one thread and loads another thread’s state.

🧵 Creating Threads in Java
1. Using Thread Class
class MyThread extends Thread {
    public void run() {
        System.out.println("Thread is running");
    }
}

2. Using Runnable Interface (Preferred)
class MyRunnable implements Runnable {
    public void run() {
        System.out.println("Thread is running");
    }
}


✔ Preferred because Java supports single inheritance.

🔄 Thread Life Cycle

New

Runnable

Running

Waiting / Sleeping

Terminated

🛠️ Important Thread Methods
Method	Description
start()	Starts thread execution
run()	Contains thread logic
sleep()	Pauses thread
join()	Waits for another thread
setPriority()	Sets thread priority
interrupt()	Interrupts thread
yield()	Pauses current thread temporarily
setDaemon()	Makes thread a daemon thread
🔒 Synchronization

Used to avoid data inconsistency when multiple threads access shared resources.

⚠️ Race Condition

Occurs when multiple threads access shared data at the same time.

✅ Mutual Exclusion

Ensures only one thread accesses a critical section.

synchronized void method() {
    // critical section
}

🔐 Locking Mechanisms
Intrinsic Lock

Uses synchronized

Automatically managed by JVM

Explicit Lock

Provided by java.util.concurrent.locks

🔁 ReentrantLock

More flexible than synchronized.

Common Methods:
lock()
unlock()
tryLock()

Benefits:

Better control

Fair locking

Helps avoid deadlocks

☠️ Deadlock

A situation where two or more threads wait forever for each other.

Causes:

Mutual exclusion

Hold and wait

No preemption

Circular wait

Prevention:

Lock ordering

Avoid nested locks

Use tryLock()

🔄 Inter-Thread Communication

Threads communicate using:

wait()

notify()

notifyAll()

Used when one thread depends on another.

⚡ Thread Pool & Executor Framework

Creating threads manually is expensive.

Thread Pool:

Reuses threads

Improves performance

Reduces overhead

Executor Framework:

Provides better thread management.

Common Interfaces:

Executor

ExecutorService

ScheduledExecutorService

🚀 Key Learnings

Deep understanding of multithreading

How CPU scheduling works

Safe and efficient concurrency

Deadlock prevention

Real-world Java concurrency usage

🙌 Credits

Special thanks to Vipul Tyagi (Engineering Digest) for the excellent explanation and structured teaching.

📌 Conclusion

Multithreading is not just about writing concurrent code —
it’s about understanding how systems actually work internally.

This learning strengthened my Java backend and system-level programming skills.
