# ⚠️ Error Types 

_By Anwaar Al-Zadjali — 15 April 2025_

---

## 📚 Table of Contents
1. [Timeout Error ⏳](#1-timeout-error-)
2. [Linker Error 🖇️](#2-linker-error-)
3. [Runtime Errors ▶️](#3-runtime-errors-)
4. [Resource Errors 📂](#4-resource-errors-)

---

## 1. Timeout Error ⏳

A **timeout error** occurs when a program or operation takes longer than expected or permitted to complete. These errors are common in network communications, data processing, or any time-constrained tasks.

### 🔹 Occurs when:
- The task exceeds the allotted time limit (e.g., API request timeouts).
- Inefficient algorithms, resource contention, or large data inputs cause delays.
- resource contention: Resource contention happens when two or more programs, threads, or processes try to use the same resource at the same time, but the resource can't be shared easily — so they have to "fight" over it.
Fight over CPU , Memory , Disk access, network bandwidth
- A process is blocked due to synchronization issues, deadlocks, or unavailable resources.
### 📌 Example (python):
```python
import requests

try:
    # Setting a very low timeout to simulate the error
    response = requests.get("https://httpbin.org/delay/5", timeout=2)
    print(response.text)
except requests.exceptions.Timeout:
    print("Error: The request timed out!")

```
### 🔴 Error (bash):
```bash
Error: The request timed out!
```
---
## 2. Linker Error 🖇️
A **linker error** happens during the build process when the compiler cannot find the definition for a declared symbol (function, variable, etc.).

### 🔹 Occurs when:
- Symbols are declared but not defined in any linked file or library.
- Required libraries are missing or incompatible.

### 📌 Example (python):
```cpp
// main.cpp
#include <iostream>
void sayHello();  // Declared but not defined

int main() {
    sayHello();    // Causes linker error
    return 0;
}
```
### 🔴 Error (bash):
```bash
PermissionError: [Errno 13] Permission denied
```
---
## 3. Runtime Errors ▶️

**Runtime errors** occur **while the program is running**, after it has successfully compiled or been interpreted.

These errors are detected **during the execution** of the program. They happen when the program is syntactically correct but encounters an operation the computer cannot perform.

### 🔹 Common Causes:

1. **Invalid Input Handling**  
   When the program receives input it can't handle, such as parsing a non-numeric string as an integer.

2. **Memory Allocation Issues**  
   Attempting to access memory that hasn't been allocated or accessing memory that has already been freed.

3. **Division by Zero**  
   Dividing a number by zero causes an arithmetic exception and halts the program.

### 📌 Example (Python):
```python
a = 10
b = 0
print(a / b)  # Raises ZeroDivisionError
```
### 🔴 Error (bash):

```bash
ZeroDivisionError: division by zero
```
---
## 4. Resource Errors 📂

Resource errors in programming refer to issues related to the **allocation**, **utilization**, or **availability** of system resources such as memory, file handles, network connections, and CPU cycles.

### 🔹 Occurs when:

- **Memory exhaustion** – When a program uses more RAM than is available.
- **Disk space shortage** – Not enough storage to write or read files.
- **Too many open files** – Exceeding the file descriptor limit.
- **Database connection limits** – Too many users connecting simultaneously.
- **Network failures** – Poor connection, timeout, or unreachable host.
- **Permission issues** – Trying to access a file or port without proper rights.

### 📌 Example (python):
```cpp
open("/protected/system/file.txt", "r")
```
### 🔴 Error (bash):
```bash
PermissionError: [Errno 13] Permission denied
```
