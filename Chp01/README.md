# Chapter 1 – Introduction to Parallel and Distributed Computing

## Objective
This program demonstrates the basic difference between **Threading** and **Multiprocessing** in Python.  
It shows how tasks can be executed in parallel using both approaches and compares their execution times.

---

## Code Explanation
1. **Threading Section**
   - Multiple threads share the same memory space.
   - The code uses a shared variable `total` and a thread lock to safely update values.
   - Each thread adds two numbers and prints the result.

2. **Multiprocessing Section**
   - Each process has its own memory space.
   - The code uses `multiprocessing.Value` and a `Lock` to synchronize processes.
   - Each process performs the same addition task as the threading version.

---

## Output
Below is the output of the program showing that both Threading and Multiprocessing achieve the same results, but may differ slightly in execution time.

**Program Output:**
Running with Threads:
Step 1: 1 + 2 = 3
The sum of 3 and 3 is 6
The sum of 6 and 4 is 10
Total sum is: 10
Total Execution time is: 1.00 seconds

Now, Running with Multiprocessing:
The sum of 3 and 3 is 6
The sum of 6 and 4 is 10
Total sum is: 10
Total Execution time is: 1.19 seconds

![Output Screenshot](./screenshots/output.PNG)

---

## Conclusion
- **Threading** and **Multiprocessing** both allow parallel execution, but use different approaches for sharing data.
- **Threading** is better for lightweight tasks where threads share memory.
- **Multiprocessing** is better for CPU-intensive tasks since it uses separate memory spaces.
- This experiment helps understand how Python handles concurrency and process synchronization.


