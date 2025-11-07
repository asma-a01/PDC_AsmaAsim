# Chapter 2 – Thread Based Parallelism

## Overview
This chapter demonstrates various synchronization techniques used in multithreading and multiprocessing.  
Each program focuses on a different synchronization primitive that helps manage access to shared resources, prevent race conditions, and coordinate tasks among threads.

---

## Files Included

### 1. **Barrier.py**
- Demonstrates how a **Barrier** synchronizes multiple threads, making them wait until all have reached a certain point before continuing.
- Ensures that all threads complete one phase before starting the next.

**Output Summary:**  
All workers reach the first and second barriers together and proceed in synchronized steps.  
At the end, all threads finish execution together.

---

### 2. **Condition.py**
- Uses a **Condition object** to manage communication between threads.
- The car waits for a “green light,” which the traffic signal thread activates using `notify_all()`.

**Output Summary:**  
The car thread waits until the signal thread sets the condition to green, then proceeds successfully.

---

### 3. **Event.py**
- Demonstrates how an **Event** can be used to start multiple threads simultaneously.
- The race controller sets the event (green light), allowing all car threads to start racing at once.

**Output Summary:**  
All car threads wait for the controller’s green light event, then start and finish the race in random order.

---

### 4. **Lockex.py**
- Shows the use of a **Lock** to prevent race conditions when multiple threads update a shared variable.
- Only one thread at a time can modify the balance.

**Output Summary:**  
Each thread deposits safely without conflicts. The final balance confirms successful synchronization.

---

### 5. **Queue.py**
- Demonstrates **thread-safe communication** using a `queue.Queue`.
- A waiter thread places orders, while a chef thread processes them in order.

**Output Summary:**  
Orders are placed and processed sequentially. Once all orders are done, the chef thread closes the kitchen.

---

### 6. **Rlock.py**
- Uses a **Reentrant Lock (RLock)** to allow the same thread to acquire the lock multiple times safely.
- Prevents deadlock situations where a thread tries to re-lock itself.

**Output Summary:**  
All threads increment and decrement a shared counter safely.  
Final counter value verifies correct locking and unlocking behavior.

---

### 7. **Semaphore.py**
- Demonstrates how a **Semaphore** restricts access to a limited number of resources.
- Here, only three cars can park in the parking lot at the same time.

**Output Summary:**  
Cars enter the parking lot in groups of three, and new cars wait until space is available.

---

### 8. **Threads.py**
- Introduces basic **multithreading** in Python.
- Each thread performs a simple task concurrently to show how total execution time decreases with parallel execution.

**Output Summary:**  
All threads start and finish around the same time.  
Total time shows that tasks run concurrently instead of sequentially.

---

## Conclusion
- Thread synchronization is essential to ensure data consistency and prevent race conditions in concurrent programs.  
- Python provides several synchronization primitives such as **Lock**, **RLock**, **Semaphore**, **Condition**, **Barrier**, and **Event** to manage thread coordination.  
- Each mechanism serves a specific use case — from simple locking to complex signaling and controlled access.  
- This chapter strengthens understanding of **thread safety**, **communication**, and **coordination** in concurrent programming.


