# **Chapter 3 – Process Based Parallelism**

## **Overview**
This chapter explores **process-based parallelism** using Python’s `multiprocessing` module.  
It demonstrates how multiple independent processes can run simultaneously, communicate, or be terminated — allowing true parallel execution across multiple CPU cores.  
The programs in this chapter focus on **process creation**, **daemon processes**, and **process control**.

---

## **Files Included**

### **1. spawn.py**
- Demonstrates the basic concept of **process spawning** using `multiprocessing.Process`.  
- Each uploader process represents a separate file being uploaded in parallel.  
- The program uses `join()` to ensure that the main process waits until all uploads are complete.

**Key Concepts:**
- Process creation using `multiprocessing.Process`
- Parallel execution
- Synchronization using `join()`

**Output Summary:**  
Four uploader processes start uploading simultaneously.  
Each finishes after a random delay, and finally the main process prints:  
`All uploads completed successfully!`

---

### **2. parallel_backups.py**
- Simulates **parallel backups** of multiple folders using separate processes.  
- Demonstrates how to assign **custom process names** and use **daemon processes** that run in the background.  
- The main process waits only for non-daemon processes, exiting once essential backups are done.

**Key Concepts:**
- Naming processes for clarity
- Using `daemon` processes
- Managing multiple independent workers

**Output Summary:**  
Three backup workers start in parallel — two as regular processes and one as a daemon.  
Each reports when it starts and finishes its task.  
After non-daemon processes complete, the main process exits, while the daemon may continue briefly in the background.

---

### **3. killingque.py**
- Demonstrates **process monitoring and termination** using methods like `is_alive()`, `terminate()`, and `exitcode`.  
- Simulates multiple file downloads and shows how a specific process (File2) can be cancelled during execution.

**Key Concepts:**
- Process state checking (`is_alive()`)
- Terminating a running process
- Handling exit codes (`exitcode`)

**Output Summary:**  
Three download processes start simultaneously.  
File2 is terminated mid-way, while File1 and File3 complete successfully.  
The final output displays their exit codes — `0` for successful completion and `-15` for the terminated process.

---

## **Conclusion**
- **Multiprocessing** enables Python programs to utilize multiple CPU cores, achieving real parallelism.  
- You can control individual processes — start, monitor, and terminate them safely.  
- **Daemon processes** allow background tasks, while **exit codes** help verify process completion status.  
- These examples form the foundation for more advanced multiprocessing systems involving **inter-process communication**, **resource sharing**, and **task synchronization**.


